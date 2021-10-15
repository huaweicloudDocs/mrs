# DBService超过最大连接数，导致metastore异常<a name="mrs_03_0186"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275692_section842971116813"></a>

DBService默认最大连接数是300，如果当业务量比较大，导致连接DBService的最大连接数超过300时，metastore会出现异常，并报slots are reserved for non-replication superuser connections的错误：

```
2018-04-26 14:58:55,657 | ERROR | BoneCP-pool-watch-thread | Failed to acquire connection to jdbc:postgresql://10.*.*.*:20051/hivemeta?socketTimeout=60. Sleeping for 1000 ms. Attempts left: 9 | com.jolbox.bonecp.BoneCP.obtainInternalConnection(BoneCP.java:292)
org.postgresql.util.PSQLException: FATAL: remaining connection slots are reserved for non-replication superuser connections
	at org.postgresql.core.v3.ConnectionFactoryImpl.readStartupMessages(ConnectionFactoryImpl.java:643)
	at org.postgresql.core.v3.ConnectionFactoryImpl.openConnectionImpl(ConnectionFactoryImpl.java:184)
	at org.postgresql.core.ConnectionFactory.openConnection(ConnectionFactory.java:64)
	at org.postgresql.jdbc2.AbstractJdbc2Connection.<init>(AbstractJdbc2Connection.java:124)
	at org.postgresql.jdbc3.AbstractJdbc3Connection.<init>(AbstractJdbc3Connection.java:28)
	at org.postgresql.jdbc3g.AbstractJdbc3gConnection.<init>(AbstractJdbc3gConnection.java:20)
	at org.postgresql.jdbc4.AbstractJdbc4Connection.<init>(AbstractJdbc4Connection.java:30)
	at org.postgresql.jdbc4.Jdbc4Connection.<init>(Jdbc4Connection.java:22)
	at org.postgresql.Driver.makeConnection(Driver.java:392)
	at org.postgresql.Driver.connect(Driver.java:266)
	at java.sql.DriverManager.getConnection(DriverManager.java:664)
	at java.sql.DriverManager.getConnection(DriverManager.java:208)
	at com.jolbox.bonecp.BoneCP.obtainRawInternalConnection(BoneCP.java:361)
	at com.jolbox.bonecp.BoneCP.obtainInternalConnection(BoneCP.java:269)
	at com.jolbox.bonecp.ConnectionHandle.<init>(ConnectionHandle.java:242)
	at com.jolbox.bonecp.PoolWatchThread.fillConnections(PoolWatchThread.java:115)
	at com.jolbox.bonecp.PoolWatchThread.run(PoolWatchThread.java:82)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	at java.lang.Thread.run(Thread.java:745)
```

## 原因分析<a name="zh-cn_topic_0167275692_section724010302087"></a>

业务量大导致连接DBService的最大连接数超过了300，需要修改DBService的最大连接数。

## 解决办法<a name="zh-cn_topic_0167275692_section17326135612212"></a>

1.  进入DBService服务配置页面：
    -   MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)，然后选择“服务管理 \> DBService \> 服务配置”，单击“基础配置”下拉菜单，选择“全部配置”。
    -   MRS 1.8.10之后及2._x_版本，单击集群名称，登录集群详情页面，选择“组件管理 \> DBService \> 服务配置”，单击“基础配置”下拉菜单，选择“全部配置”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

    -   MRS 3.x及后续版本，登录FusionInsight Manager，然后选择“集群 \>  _待操作的集群名_称 \> 服务 \> DBService \> 配置 \> 全部配置”。

2.  搜索dbservice.database.max.connections配置项，并修改dbservice.database.max.connections配置的值到合适值，不能超过1000。
3.  保存配置，并重启受影响的服务或者实例。
4.  如果调整完还报超过最大连接数，需要排查业务代码，是否有连接泄露。

