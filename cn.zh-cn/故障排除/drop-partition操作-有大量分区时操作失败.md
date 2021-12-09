# drop partition操作，有大量分区时操作失败<a name="mrs_03_0182"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275042_s7bff89706cab436ba99310b49244d1ed"></a>

执行drop  partitions 操作，执行异常：

```
MetaStoreClient lost connection. Attempting to reconnect. | org.apache.hadoop.hive.metastore.RetryingMetaStoreClient.invoke(RetryingMetaStoreClient.java:187)
org.apache.thrift.transport.TTransportException
at org.apache.thrift.transport.TIOStreamTransport.read(TIOStreamTransport.java:132)
at org.apache.thrift.transport.TTransport.readAll(TTransport.java:86)
at org.apache.thrift.transport.TSaslTransport.readLength(TSaslTransport.java:376)
at org.apache.thrift.transport.TSaslTransport.readFrame(TSaslTransport.java:453)
at org.apache.thrift.transport.TSaslTransport.read(TSaslTransport.java:435)
...
```

查看对应metaStore日志，有StackOverFlow异常

```
2017-04-22 01:00:58,834 | ERROR | pool-6-thread-208 | java.lang.StackOverflowError
at org.datanucleus.store.rdbms.sql.SQLText.toSQL(SQLText.java:330)
at org.datanucleus.store.rdbms.sql.SQLText.toSQL(SQLText.java:339)
at org.datanucleus.store.rdbms.sql.SQLText.toSQL(SQLText.java:339)
at org.datanucleus.store.rdbms.sql.SQLText.toSQL(SQLText.java:339)
at org.datanucleus.store.rdbms.sql.SQLText.toSQL(SQLText.java:339)
```

## 原因分析<a name="zh-cn_topic_0167275042_s0bbd8e714847401bb381b6a096b6574d"></a>

drop partition的处理逻辑是将找到所有满足条件的分区，将其拼接起来，最后统一删除。由于分区数过多，拼删元数据堆栈较深，出现StackOverFlow异常。

## 解决办法<a name="zh-cn_topic_0167275042_section5881851220334"></a>

分批次删除分区。

