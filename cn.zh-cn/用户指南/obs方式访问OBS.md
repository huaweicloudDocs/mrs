# obs方式访问OBS<a name="ZH-CN_TOPIC_0173178881"></a>

MRS2.0.0之后的版本，支持使用obs的方式对接OBS服务，当前主要支持的服务为Hadoop、Hive、Spark、HBase、Presto、Flink。

## Hadoop访问OBS<a name="section2114171071418"></a>

-   在MRS客户端的HDFS目录\($client\_home/ HDFS/hadoop/etc/hadoop\)中修改core-site.xml文件，增加如下内容。

    ```
    <property>
        <name> fs.obs.access.key</name>
        <value>ak</value>
    </property>
    <property>
        <name> fs.obs.secret.key</name>
        <value>sk</value>
    </property>
    <property>
        <name> fs.obs.endpoint</name>
        <value>obs endpoint</value>
    </property>
    ```

    >![](public_sys-resources/icon-notice.gif) **须知：**   
    >在文件中设置AK/SK会明文暴露在配置文件中，请谨慎使用。  

    添加配置后无需手动添加AK/SK、endpoint就可以直接访问OBS上的数据。例如执行如下命令查看桶obs-test下面的文件夹test\_obs\_orc的文件列表。

    **hadoop fs –ls "obs://obs-test/test\_obs\_orc"**

-   每次在命令行中手动添加AK/SK、endpoint访问OBS上的数据。

    **hadoop fs -Dfs.obs.endpoint=xxx -Dfs.obs.access.key=xx -Dfs.obs.secret.key=xx -ls "obs://obs-test/ test\_obs\_orc"**


## Hive访问OBS<a name="section1164714235144"></a>

1.  登录集群详情页面，选择“组件管理 \> Hive \> 服务配置”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> Hive \> 服务配置”。  

2.  参数类别设置为“全部配置”。
3.  搜索“fs.obs.access.key”和“fs.obs.secret.key”参数，并分别配置为OBS的AK和SK。

    **图 1**  配置OBS的AK/SK<a name="fig79611510113312"></a>  
    ![](figures/配置OBS的AK-SK.png "配置OBS的AK-SK")

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。
5.  在beeline中直接使用obs的目录进行访问。例如，执行如下命令创建Hive表并指定数据存储在test-bucket桶的test\_obs目录中。

    **create table test\_obs\(a int, b string\) row format delimited fields terminated by "," stored as textfile location "obs://test-bucket/test\_obs";**


## Spark访问OBS<a name="section19812102810147"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>由于SparkSQL依赖Hive，所以在Spark上配置OBS时，需要同时修改[Hive访问OBS](#section1164714235144)的OBS配置。  

-   spark-beeline和spark-sql

    可以通过在shell中增加如下OBS的属性实现访问OBS。

    ```
    set fs.obs.endpoint=xxx
    set fs.obs.access.key=xxx
    set fs.obs.secret.key=xxx
    ```

-   spark-beeline

    spark-beeline也可以通过在MRS Manager中配置服务参数实现访问OBS。操作如下：

    1.  登录集群详情页面，选择“组件管理 \> Spark \> 服务配置”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> Spark \> 服务配置”。  

    2.  “参数类别”配置为“全部配置”。
    3.  选择“JDBCServer \> OBS”配置fs.obs.access.key、fs.obs.secret.key参数。
    4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启HBase服务。
    5.  在spark-beeline中访问OBS，例如访问obs://obs-demo-input/table/目录：

        **create table test\(id int\) location 'obs://obs-demo-input/table/';**


-   spark-sql和spark-submit

    spark-sql也可以通过修改core-site.xml配置文件实现访问OBS。

    使用spark-sql和使用spark-submit提交任务访问OBS时，配置文件修改方法一致。

    修改MRS客户端中Spark配置文件夹（$client\_home/Spark/spark/conf）中的core-site.xml，增加如下内容：

    ```
    <property>
        <name> fs.obs.access.key</name>
        <value>ak</value>
    </property>
    <property>
        <name> fs.obs.secret.key</name>
        <value>sk</value>
    </property>
    <property>
        <name> fs.obs.endpoint</name>
        <value>obs endpoint</value>
    </property>
    ```


## HBase访问OBS<a name="section4462193319149"></a>

1.  登录集群详情页面，选择页面右上角“管理操作 \> 停止所有组件”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> HBase”，单击“停止服务”。  

2.  登录任意一个Master节点，具体请参见[登录集群节点](登录集群节点.md)。
3.  执行如下命令初始化环境变量。

    **source /opt/client/bigdata\_env**

4.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** **_MRS__集群用户_**

    例如,  **kinit hbaseuser**

5.  执行如下命令清理原HBase上HDFS/ZK数据。

    **hbase clean --cleanAll**

6.  登录集群详情页面，选择“组件管理 \> HBase \> 服务配置”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> HBase \> 服务配置”。  

7.  “参数类别”配置为“全部配置”。
8.  配置如下访问OBS的相关参数。
    -   fs.obs.access.key
    -   fs.obs.secret.key
    -   hbase.wal.provider配置为filesystem
    -   hbase.rootdir配置为数据存储目录，例如，obs://bucket \_name/hbase

9.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启HBase服务。
10. 使用HBase，HBase上的hfile数据将默认放入OBS上，WAL文件依旧放在HDFS上。

## Presto访问OBS<a name="section1974614263315"></a>

该功能在MRS 2.0.5及之后版本支持。

1.  登录集群详情页面，选择“组件管理 \> Presto \> 服务配置”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> Hive \> 服务配置”。  

2.  参数类别设置为“全部配置”。
3.  搜索并配置如下参数。
    -   fs.obs.access.key配置为用户ak
    -   fs.obs.secret.key配置为用户sk

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Presto服务。
5.  选择“组件管理 \> Hive \> 服务配置”。
6.  参数类别设置为“全部配置”。
7.  搜索并配置如下参数。
    -   fs.obs.access.key配置为用户ak
    -   fs.obs.secret.key配置为用户sk

8.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。
9.  在Presto客户端中执行语句创建schema，指定location为OBS路径，例如：

    **CREATE SCHEMA hive.demo WITH \(location = 'obs://obs-demo/presto-demo/'\);**

10. 在该schema中建表，该表的数据即存储在OBS桶内，例如：

    **CREATE TABLE hive.demo.demo\_table WITH \(format = 'ORC'\) AS SELECT \* FROM tpch.sf1.customer;**


## Flink访问OBS<a name="section269994210283"></a>

在MRS客户端的Flink配置文件“客户端安装路径/Flink/flink/conf/flink-conf.yaml”中，增加如下内容。

```
fs.obs.access.key：ak  
fs.obs.secret.key: sk  
fs.obs.endpoint: obs endpoint
```

>![](public_sys-resources/icon-notice.gif) **须知：**   
>在文件中设置AK/SK会明文暴露在配置文件中，请谨慎使用。  

添加配置后无需手动添加AK/SK、endpoint就可以直接访问OBS上的数据。

