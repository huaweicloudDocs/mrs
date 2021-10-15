# 获取MRS集群信息<a name="mrs_02_9001"></a>

## MRS服务支持的组件<a name="section1741815651015"></a>

-   MRS 3.1.0支持的组件信息如下：
    -   分析集群包含的组件有：Hadoop,Spark2x,HBase,Hive,Hue,Loader,Flink,Oozie,ZooKeeper,Ranger,Tez,Impala,Presto,Kudu,Sqoop
    -   流式集群包含的组件有：Kafka,Flume,ZooKeeper,Ranger
    -   混合集群包含的组件有：Hadoop,Spark2x,HBase,Hive,Hue,Loader,Flink,Oozie,ZooKeeper,Ranger,Tez,Impala,Presto,Kudu,Sqoop,Kafka,Flume
    -   自定义集群包含的组件有：Hadoop,Spark2x,HBase,Hive,Hue,Loader,Kafka,Flume,Flink,Oozie,ZooKeeper,Ranger,Tez,Impala,Presto,ClickHouse,Kudu,Sqoop

-   MRS 1.9.2支持的组件信息如下：
    -   分析集群包含的组件有：Presto,Hadoop,Spark,HBase,Opentsdb,Hive,Hue,Loader,Tez,Flink,Alluxio,Ranger
    -   流式集群包含的组件有：Kafka,KafkaManager,Storm,Flume


## 获取集群ID<a name="section177891315153619"></a>

在调用作业相关接口的时候，部分URL中需要填入集群ID（cluster\_id），所以需要先在管理控制台上获取到集群ID。集群ID获取步骤如下：

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，单击待操作集群的集群名称，进入集群详情页面。
3.  选择“概览”页签，在基本信息区域获取“集群ID”。

    **图 1**  集群ID<a name="fig8194125093612"></a>  
    ![](figures/集群ID.png "集群ID")


## 获取作业ID<a name="section247234143612"></a>

在调用作业相关接口的时候，部分URL中需要填入作业ID（job\_execution\_id），所以需要先在管理控制台上获取到作业ID。作业ID获取步骤如下：

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，单击待操作集群的集群名称，进入集群详情页面。
3.  选择“作业管理”页签，在作业列表中获取待操作作业对应的“ID”。

    **图 2**  作业ID<a name="fig10965437102713"></a>  
    ![](figures/作业ID.png "作业ID")


