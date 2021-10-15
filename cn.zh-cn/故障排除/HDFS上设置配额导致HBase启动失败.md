# HDFS上设置配额导致HBase启动失败<a name="mrs_03_0113"></a>

## 问题现象<a name="zh-cn_topic_0167275487_s0fe2972fbdce490daac4377fe3fe6135"></a>

HBase启动失败。

## 原因分析<a name="zh-cn_topic_0167275487_s92314ad8bf314ffd9d5e24dcf9e57e97"></a>

查看HMaster日志信息（“/var/log/Bigdata/hbase/hm/hbase-omm-xxx.log“），出现如下异常，The DiskSpace quota of /hbase is exceeded。

![](figures/c9c62061-2203-41a5-b5f6-b1392d3e9c3a.png)

## 解决办法<a name="zh-cn_topic_0167275487_s01bb0fcfd11a428e9bc2a94265bd7067"></a>

1.  通过后台使用**df -h**命令查看数据盘目录空间已满，因此需要删除无用的数据来进行应急恢复。
2.  后续需要扩容节点来解决数据目录空间不足问题。

