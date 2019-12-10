# 执行Kafka Topic创建操作，发现无法创建提示NoNode for /brokers/ids<a name="ZH-CN_TOPIC_0185002838"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275137_s5d135719deec4560b99adb07a0aa6416"></a>

在使用Kafka客户端命令创建Topic时，发现Topic无法被创建。

```
kafka-topics.sh --create  --replication-factor 1 --partitions 2 --topic test --zookeeper 192.168.234.231:2181
```

提示错误NoNodeException: KeeperErrorCode = NoNode for /brokers/ids。

具体如下：

```
Error while executing topic command : org.apache.zookeeper.KeeperException$NoNodeException: KeeperErrorCode = NoNode for /brokers/ids
[2017-09-17 16:35:28,520] ERROR org.I0Itec.zkclient.exception.ZkNoNodeException: org.apache.zookeeper.KeeperException$NoNodeException: KeeperErrorCode = NoNode for /brokers/ids
	at org.I0Itec.zkclient.exception.ZkException.create(ZkException.java:47)
	at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:995)
	at org.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:675)
	at org.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:671)
	at kafka.utils.ZkUtils.getChildren(ZkUtils.scala:541)
	at kafka.utils.ZkUtils.getSortedBrokerList(ZkUtils.scala:176)
	at kafka.admin.AdminUtils$.createTopic(AdminUtils.scala:235)
	at kafka.admin.TopicCommand$.createTopic(TopicCommand.scala:105)
	at kafka.admin.TopicCommand$.main(TopicCommand.scala:60)
	at kafka.admin.TopicCommand.main(TopicCommand.scala)
Caused by: org.apache.zookeeper.KeeperException$NoNodeException: KeeperErrorCode = NoNode for /brokers/ids
	at org.apache.zookeeper.KeeperException.create(KeeperException.java:115)
	at org.apache.zookeeper.KeeperException.create(KeeperException.java:51)
	at org.apache.zookeeper.ZooKeeper.getChildren(ZooKeeper.java:2256)
	at org.apache.zookeeper.ZooKeeper.getChildren(ZooKeeper.java:2284)
	at org.I0Itec.zkclient.ZkConnection.getChildren(ZkConnection.java:114)
	at org.I0Itec.zkclient.ZkClient$4.call(ZkClient.java:678)
	at org.I0Itec.zkclient.ZkClient$4.call(ZkClient.java:675)
	at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:985)
	... 8 more
 (kafka.admin.TopicCommand$)
```

## 可能原因<a name="zh-cn_topic_0167275137_s8efdc02bbb1a42cba8fa3e43e2e68817"></a>

-   Kafka服务处于停止状态
-   客户端命令中zookeeper地址参数配置错误。

## 原因分析<a name="zh-cn_topic_0167275137_section10342981143649"></a>

1.  使用客户端命令，打印NoNodeException异常。

    ```
    Error while executing topic command : org.apache.zookeeper.KeeperException$NoNodeException: KeeperErrorCode = NoNode for /brokers/ids
    [2017-09-17 16:35:28,520] ERROR org.I0Itec.zkclient.exception.ZkNoNodeException: org.apache.zookeeper.KeeperException$NoNodeException: KeeperErrorCode = NoNode for /brokers/ids
    	at org.I0Itec.zkclient.exception.ZkException.create(ZkException.java:47)
    	at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:995)
    	at org.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:675)
    	at org.I0Itec.zkclient.ZkClient.getChildren(ZkClient.java:671)
    	at kafka.utils.ZkUtils.getChildren(ZkUtils.scala:541)
    	at kafka.utils.ZkUtils.getSortedBrokerList(ZkUtils.scala:176)
    	at kafka.admin.AdminUtils$.createTopic(AdminUtils.scala:235)
    	at kafka.admin.TopicCommand$.createTopic(TopicCommand.scala:105)
    	at kafka.admin.TopicCommand$.main(TopicCommand.scala:60)
    	at kafka.admin.TopicCommand.main(TopicCommand.scala)
    ```

2.  通过MRS Manager查看Kafka服务是否处于正常状态。

    **图 1**  Kafka状态<a name="zh-cn_topic_0167275137_fig18285327113316"></a>  
    ![](figures/Kafka状态.png "Kafka状态")

3.  检查客户端命令中ZooKeeper地址是否正确，访问ZooKeeper上所存放的Kafka信息，其路径（Znode）应该加上/kafka，发现配置中缺少/kafka：

    ```
    [root@10-10-144-2 client]# 
    kafka-topics.sh --create  --replication-factor 1 --partitions 2 --topic test --zookeeper 192.168.234.231:2181
    ```


## 解决办法<a name="zh-cn_topic_0167275137_section3518145211446"></a>

1.  保证Kafka服务处于正常状态。
2.  创建命令中ZooKeeper地址信息需要添加/kafka。

    ```
    [root@10-10-144-2 client]# 
    kafka-topics.sh --create  --replication-factor 1 --partitions 2 --topic test --zookeeper 192.168.234.231:24002/kafka
    ```


