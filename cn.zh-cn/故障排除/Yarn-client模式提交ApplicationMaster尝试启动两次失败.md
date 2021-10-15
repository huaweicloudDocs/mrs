# Yarn-client模式提交ApplicationMaster尝试启动两次失败<a name="mrs_03_0112"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276500_s7f0794d3c3ab4fe789816d7e1850311c"></a>

Yarn-client模式提交任务AppMaster尝试启动两次失败。

## 原因分析<a name="zh-cn_topic_0167276500_sed50e339dfb64035a070c991a92730f8"></a>

1.  Driver端异常:

    ```
    16/05/11 18:10:56 INFO Client: 
    client token: N/A
    diagnostics: Application application_1462441251516_0024 failed 2 times due to AM Container for appattempt_1462441251516_0024_000002 exited with  exitCode: 10
    For more detailed output, check the application tracking page:https://hdnode5:26001/cluster/app/application_1462441251516_0024 Then click on links to logs of each attempt.
    Diagnostics: Exception from container-launch.
    Container id: container_1462441251516_0024_02_000001
    ```

2.  在ApplicationMaster日志中，异常如下:

    ```
    2016-05-12 10:21:23,715 | ERROR | [main] | Failed to connect to driver at 192.168.30.57:23867, retrying ... | org.apache.spark.Logging$class.logError(Logging.scala:75)
    2016-05-12 10:21:24,817 | ERROR | [main] | Failed to connect to driver at 192.168.30.57:23867, retrying ... | org.apache.spark.Logging$class.logError(Logging.scala:75)
    2016-05-12 10:21:24,918 | ERROR | [main] | Uncaught exception:  | org.apache.spark.Logging$class.logError(Logging.scala:96)
    org.apache.spark.SparkException: Failed to connect to driver!
    at org.apache.spark.deploy.yarn.ApplicationMaster.waitForSparkDriver(ApplicationMaster.scala:426)
    at org.apache.spark.deploy.yarn.ApplicationMaster.runExecutorLauncher(ApplicationMaster.scala:292)
    …
    2016-05-12 10:21:24,925 | INFO  | [Thread-1] | Unregistering ApplicationMaster with FAILED (diag message: Uncaught exception: org.apache.spark.SparkException: Failed to connect to driver!) | org.apache.spark.Logging$class.logInfo(Logging.scala:59)
    ```

    Spark-client模式任务Driver运行在客户端节点上\(通常是集群外的某个节点\)，启动时先在集群中启动AppMaster进程，进程启动后要向Driver进程注册信息，注册成功后，任务才能继续。从AppMaster日志中可以看出，无法连接至Driver，所以任务失败。


## 解决办法<a name="zh-cn_topic_0167276500_s9b29e9124eb5445297faeccce2c0517a"></a>

1.  请测试一下Driver进程所在的IP是否可以**ping**通。
2.  <a name="zh-cn_topic_0167276500_lcdf10c2839fb4dacb8a35eb3ec499c87"></a>启动一个sparkpi任务，在console端会有类似如下打印信息。

    ```
    16/05/11 18:07:20 INFO Remoting: Remoting started; listening on addresses :[akka.tcp://sparkDriver@192.168.1.100:23662]
    16/05/11 18:07:20 INFO Utils: Successfully started service 'sparkDriver' on port 23662.
    ```

3.  在该节点，也就是[2](#zh-cn_topic_0167276500_lcdf10c2839fb4dacb8a35eb3ec499c87)中示例的192.168.1.100上执行**netstat - anp | grep 23662**看下此端口是否打开，如下打印标明，相关端口是打开的。

    ```
    tcp        0      0  ip:port    :::*                    LISTEN      107274/java        
    tcp        0      0  ip:port   ip:port                  ESTABLISHED 107274/java        
    ```

4.  在AppMaster启动的节点执行**telnet 192.168.1.100 23662**看下是否可以联通该端口，请使用**root**用户和**omm**用户都执行一遍。 如果出现**Escape character is '^\]'**类似打印则说明可以联通，如果出现**connection refused**则表示失败，无法连接到相关端口。

    如果相关端口打开，但是从别的节点无法联通到该端口，则需要排查下相关网络配置。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >23662这个端口每次都是随机的，所以要根据自己启动任务打开的端口来测试。


