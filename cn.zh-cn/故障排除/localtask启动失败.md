# localtask启动失败<a name="mrs_03_0183"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275537_section842971116813"></a>

1.  执行join等操作，数据量较小时，会启动localtask执行，执行过程会报错：

    ```
    jdbc:hive2://10.*.*.*:21066/> select a.name ,b.sex from student a join student1 b on (a.name = b.name);
    ERROR : Execution failed with exit status: 1
    ERROR : Obtaining error information
    ERROR : 
    Task failed!
    Task ID:
      Stage-4
    ...
    Error: Error while processing statement: FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.mr.MapredLocalTask (state=08S01,code=1)
    ...
    ```

2.  查看对应hiveserver日志，发现是启动localtask失败

    ```
    2018-04-25 16:37:19,296 | ERROR | HiveServer2-Background-Pool: Thread-79 | Execution failed with exit status: 1 | org.apache.hadoop.hive.ql.session.SessionState$LogHelper.printError(SessionState.java:1016)
    2018-04-25 16:37:19,296 | ERROR | HiveServer2-Background-Pool: Thread-79 | Obtaining error information | org.apache.hadoop.hive.ql.session.SessionState$LogHelper.printError(SessionState.java:1016)
    2018-04-25 16:37:19,297 | ERROR | HiveServer2-Background-Pool: Thread-79 |
    Task failed!
    Task ID:
      Stage-4
    Logs:
     | org.apache.hadoop.hive.ql.session.SessionState$LogHelper.printError(SessionState.java:1016)
    2018-04-25 16:37:19,297 | ERROR | HiveServer2-Background-Pool: Thread-79 | /var/log/Bigdata/hive/hiveserver/hive.log | org.apache.hadoop.hive.ql.session.SessionState$LogHelper.printError(SessionState.java:1016)
    2018-04-25 16:37:19,297 | ERROR | HiveServer2-Background-Pool: Thread-79 | Execution failed with exit status: 1 | org.apache.hadoop.hive.ql.exec.mr.MapredLocalTask.executeInChildVM(MapredLocalTask.java:342)
    2018-04-25 16:37:19,309 | ERROR | HiveServer2-Background-Pool: Thread-79 | FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.mr.MapredLocalTask | org.apache.hadoop.hive.ql.session.SessionState$LogHelper.printError(SessionState.java:1016)
    ...
    2018-04-25 16:37:36,438 | ERROR | HiveServer2-Background-Pool: Thread-88 | Error running hive query:  | org.apache.hive.service.cli.operation.SQLOperation$1$1.run(SQLOperation.java:248)
    org.apache.hive.service.cli.HiveSQLException: Error while processing statement: FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.mr.MapredLocalTask
            at org.apache.hive.service.cli.operation.Operation.toSQLException(Operation.java:339)
            at org.apache.hive.service.cli.operation.SQLOperation.runQuery(SQLOperation.java:169)
            at org.apache.hive.service.cli.operation.SQLOperation.access$200(SQLOperation.java:75)
            at org.apache.hive.service.cli.operation.SQLOperation$1$1.run(SQLOperation.java:245)
            at java.security.AccessController.doPrivileged(Native Method)
            at javax.security.auth.Subject.doAs(Subject.java:422)
            at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1710)
            at org.apache.hive.service.cli.operation.SQLOperation$1.run(SQLOperation.java:258)
            at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
            at java.util.concurrent.FutureTask.run(FutureTask.java:266)
            at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
            at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
            at java.lang.Thread.run(Thread.java:745)
    ```

3.  查看对应hiveserver日志目录\(/var/log/Bigdata/hive/hiveserver\)下，hs\_err\_pid\_\*\*\*\*\*.log，发现有内存不够的错误

    ```
    # There is insufficient memory for the Java Runtime Environment to continue.
    # Native memory allocation (mmap) failed to map 20776943616 bytes for committing reserved memory.
      ...
    ```


## 原因分析<a name="zh-cn_topic_0167275537_section724010302087"></a>

Hive在执行join操作，数据量小时会生成MapJoin，执行MapJoin时会生成localtask任务，localtask启动的jvm内存继承了父进程的内存。

当有多个join执行的时候，启动多个localtask，如果机器内存不够，就会导致启动localtask失败。

## 解决办法<a name="zh-cn_topic_0167275537_section4534334783"></a>

1.  进入Hive服务配置页面：
    -   MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)，然后选择“服务管理 \> Hive \> 服务配置”，单击“基础配置”下拉菜单，选择“全部配置”。
    -   MRS 1.8.10之后及2._x_版本，单击集群名称，登录集群详情页面，选择“组件管理 \> Hive \> 服务配置”，单击“基础配置”下拉菜单，选择“全部配置”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“同步”进行IAM用户同步）。

    -   MRS 3.x及后续版本，登录FusionInsight Manager，然后选择“集群 \>  _待操作的集群名_称 \> 服务 \> Hive \> 配置 \> 全部配置”。

2.  搜索“hive.auto.convert.join”参数并修改hive的配置hive.auto.convert.join 为false，保存配置并重启服务。

    该参数修改后会对业务性能有一定影响。继续执行后续步骤可不影响业务性能。

3.  搜索“HIVE\_GC\_OPTS”参数并修改 hive的HIVE\_GC\_OPTS，把Xms调小，具体要根据业务评估，最小设置为Xmx的一半，修改完后保存配置并重启服务。

