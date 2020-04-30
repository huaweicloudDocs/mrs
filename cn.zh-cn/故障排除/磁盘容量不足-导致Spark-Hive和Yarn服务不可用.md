# 磁盘容量不足，导致Spark、Hive和Yarn服务不可用<a name="ZH-CN_TOPIC_0181147978"></a>

## 用户问题<a name="section18305143583116"></a>

磁盘容量不足产生致命告警，Spark、Hive和Yarn服务不可用。

## 问题现象<a name="section117424454313"></a>

用户创建的集群显示磁盘容量不足，产生致命告警，导致Spark、Hive和Yarn服务不可用。

## 原因分析<a name="section1237061220324"></a>

由于集群磁盘容量不足，会影响到HDFS的数据写入，HDFS磁盘空间使用率超过阈值，因此导致HDFS服务异常。HDFS服务异常则会导致Spark、Hive和Yarn服务不可用。

根据该集群出现磁盘容量不足产生Spark、Hive和Yarn服务不可用的报警，扩容磁盘后不再告警，可以判断是磁盘容量不足引起HDFS功能故障所导致。

## 处理步骤<a name="section520813413313"></a>

针对磁盘容量不足产生的告警处理步骤，请参考[ALM-12017 磁盘容量不足](https://support.huaweicloud.com/usermanual-mrs/alm_12017.html)。

## 建议与总结<a name="section8898183420"></a>

无

## 参考信息<a name="section18208334123312"></a>

HDFS磁盘空间使用率超过阈值处理步骤，请参考[ALM-14001 HDFS磁盘空间使用率超过阈值](https://support.huaweicloud.com/usermanual-mrs/alm_14001.html)。

为MRS集群添加新磁盘，请参考[MRS集群添加新磁盘](https://support.huaweicloud.com/trouble-mrs/mrs_03_0032.html)。

