# HDFS显示磁盘空间不足，其实还有10%磁盘空间<a name="mrs_03_0095"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274525_s158e8e298d8e463baa11b441927c46e8"></a>

1.  出现“HDFS磁盘空间使用率超过阈值”告警。
2.  查看HDFS页面，查看磁盘空间使用率非常高。

## 原因分析<a name="zh-cn_topic_0167274525_s66462fbbe386437f923a475bfab597d6"></a>

HDFS中配置了dfs.datanode.du.reserved.percentage参数：每个磁盘的保留空间所占磁盘百分比。DataNode会保留这么多可用空间，以备其他组件如Yarn的NodeManager运行计算时，或者预留升级时使用。

因为预留了10%的磁盘，当磁盘使用率达到90%的时候，HDFS的DataNode即会认为没有可用磁盘空间。

## 解决办法<a name="zh-cn_topic_0167274525_s22f5b22d4e174f86a73231a8d12d87f9"></a>

1.  扩容，在HDFS DataNode磁盘到80%，即需要及时扩容。磁盘扩容请参考[MRS集群添加新磁盘](https://support.huaweicloud.com/trouble-mrs/mrs_03_0032.html)。
2.  如不能及时扩容，需要删除HDFS中的不需要数据，释放磁盘空间。

