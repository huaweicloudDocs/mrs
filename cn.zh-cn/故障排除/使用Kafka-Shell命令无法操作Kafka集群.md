# 使用Kafka Shell命令无法操作Kafka集群<a name="mrs_03_0199"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275431_s20deae74a71143aeabad239c7a22f024"></a>

用户执行Kafka命令查看当前topic信息，但发现业务执行失败。

具体信息如下：

```
root@Slave2bin]#./kafka-topics.sh --describe --topic example-metric1 --zookeeper 192.119.147.231:2181,192.119.147.228:2181,192.119.147.227:2181
Error while executing topic command:org.apache.zookeeper.KeeperException$AuthFailedException:KeeperErrorCode=AuthFailedfor/brokers/topics
[2016-09-2616:58:59,873]ERRORorg.I0Itec.zkclient.exception.ZkException:org.apache.zookeeper.KeeperException$AuthFailedException:KeeperErrorCode=AuthFailedfor/brokers/topics
atorg.I0Itec.zkclient.exception.ZkException.create(ZkException.java:68)
atorg.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:995)
atorg.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:675)
atorg.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:671)
atkafka.utils.ZkUtils.getChildrenParentMayNotExist(ZkUtils.scala:548)
atkafka.utils.ZkUtils.getAllTopics(ZkUtils.scala:798)
atkafka.admin.TopicCommand$.getTopics(TopicCommand.scala:82)
atkafka.admin.TopicCommand$.describeTopic(TopicCommand.scala:183)
atkafka.admin.TopicCommand$.main(TopicCommand.scala:66)
atkafka.admin.TopicCommand.main(TopicCommand.scala)
Causedby:org.apache.zookeeper.KeeperException$AuthFailedException:KeeperErrorCode=AuthFailedfor/brokers/topics
atorg.apache.zookeeper.KeeperException.create(KeeperException.java:127)
atorg.apache.zookeeper.KeeperException.create(KeeperException.java:51)
atorg.apache.zookeeper.ZooKeeper.getChildren(ZooKeeper.java:2256)
atorg.apache.zookeeper.ZooKeeper.getChildren(ZooKeeper.java:2284)
atorg.I0Itec.zkclient.ZkConnection.getChildren(ZkConnection.java:114)
atorg.I0Itec.zkclient.ZkClient$4.call(ZkClient.java:678)
atorg.I0Itec.zkclient.ZkClient$4.call(ZkClient.java:675)
atorg.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:985)
...8more
(kafka.admin.TopicCommand$)

```

## 原因分析<a name="zh-cn_topic_0167275431_s7dfa4353c00142a991338a71eaf7d6ad"></a>

用户反馈已经排查了执行此命令的账号权限，此账号具有操作Kafka组件的最高权限，不应该仍然会有权限不足的问题。

经确认执行命令有问题，访问ZooKeeper上所存放的Kafka信息，其路径（Znode）应该加上/kafka，完整的查询命令应该是：

```
root@Slave2bin]#./kafka-topics.sh --describe --topic example-metric1 --zookeeper 192.168.147.231:2181,192.168.147.228:2181,192.168.147.227:2181/kafka
```

## 解决办法<a name="zh-cn_topic_0167275431_section54311375103045"></a>

属于命令操作有误，具体细节请参考[Kafka Shell命令](https://support.huaweicloud.com/devg-mrs/mrs_06_0319.html)章节。

