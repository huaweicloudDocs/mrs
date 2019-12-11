# 读文件失败No common protection layer<a name="ZH-CN_TOPIC_0181713168"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274845_sec075651f94f47e2bbbc953c2db7da77"></a>

shell客户端或者其他客户端操作HDFS失败，报“**No common protection layer between client and server**”。

在集群外的机器，执行任意hadoop命令，如**hadoop fs -ls /**均失败，最底层的报错为"**No common protection layer between client and server**"。

```
2017-05-13 19:14:19,060 | ERROR | [pool-1-thread-1] |  Server startup failure  | org.apache.sqoop.core.SqoopServer.initializeServer(SqoopServer.java:69)
org.apache.sqoop.common.SqoopException: MAPRED_EXEC_0028:Failed to operate HDFS - Failed to get the file /user/loader/etl_dirty_data_dir status
        at org.apache.sqoop.job.mr.HDFSClient.fileExist(HDFSClient.java:85)
...
        at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.IOException: Failed on local exception: java.io.IOException: Couldn't setup connection for loader/hadoop@HADOOP.COM to loader37/10.162.0.37:25000; Host Details : local host is: "loader37/10.162.0.37"; destination host is: "loader37":25000;
        at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:776)
...
        ... 10 more
Caused by: java.io.IOException: Couldn't setup connection for loader/hadoop@HADOOP.COM to loader37/10.162.0.37:25000
        at org.apache.hadoop.ipc.Client$Connection$1.run(Client.java:674
        ... 28 more
Caused by: javax.security.sasl.SaslException: No common protection layer between client and server
        at com.sun.security.sasl.gsskerb.GssKrb5Client.doFinalHandshake(GssKrb5Client.java:251)
...
        at org.apache.hadoop.ipc.Client$Connection.setupIOstreams(Client.java:720)


```

## 原因分析<a name="zh-cn_topic_0167274845_s26acf5fdeead4e479b626d2036a86220"></a>

1.  HDFS的客户端和服务端数据传输走的rpc协议，该协议有多种加密方式，由hadoop.rpc.protection参数控制。
2.  如果客户端和服务端的hadoop.rpc.protection参数的配置值不一样，即会报**No common protection layer between client and server**错误。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >hadoop.rpc.protection参数表示数据可通过以下任一方式在节点间进行传输。  
    >-   privacy：默认值，指数据在鉴权及加密后再传输。这种方式会降低性能。  
    >-   auhtentication：指数据在鉴权后直接传输，不加密。这种方式能保证性能但存在安全风险。  
    >-   integrity：指数据直接传输，即不加密也不鉴权。 为保证数据安全，请谨慎使用这种方式。  


## 解决办法<a name="zh-cn_topic_0167274845_s199a3d59e10c4afdb760a75305019fcc"></a>

1.  重新下载客户端，如果是应用程序，更新应用程序中的配置文件。

