# 执行Kakfa Topic创建操作，发现无法创建提示replication factor  larger than available brokers<a name="mrs_03_0124"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275718_s5d135719deec4560b99adb07a0aa6416"></a>

在使用Kafka客户端命令创建Topic时，发现Topic无法被创建。

```
kafka-topics.sh --create  --replication-factor 2 --partitions 2 --topic test --zookeeper 192.168.234.231:2181
```

提示错误replication factor larger than available brokers。

具体如下：

```
Error while executing topic command : replication factor: 2 larger than available brokers: 0
[2017-09-17 16:44:12,396] ERROR kafka.admin.AdminOperationException: replication factor: 2 larger than available brokers: 0
	at kafka.admin.AdminUtils$.assignReplicasToBrokers(AdminUtils.scala:117)
	at kafka.admin.AdminUtils$.createTopic(AdminUtils.scala:403)
	at kafka.admin.TopicCommand$.createTopic(TopicCommand.scala:110)
	at kafka.admin.TopicCommand$.main(TopicCommand.scala:61)
	at kafka.admin.TopicCommand.main(TopicCommand.scala)
 (kafka.admin.TopicCommand$)
```

## 可能原因<a name="zh-cn_topic_0167275718_s8efdc02bbb1a42cba8fa3e43e2e68817"></a>

-   Kafka服务处于停止状态。
-   Kafka服务当前可用Broker小于设置的replication-factor。
-   客户端命令中Zookeeper地址参数配置错误。

## 原因分析<a name="zh-cn_topic_0167275718_section10342981143649"></a>

1.  使用客户端命令，打印replication factor larger than available brokers异常。

    ```
    Error while executing topic command : replication factor: 2 larger than available brokers: 0
    [2017-09-17 16:44:12,396] ERROR kafka.admin.AdminOperationException: replication factor: 2 larger than available brokers: 0
    	at kafka.admin.AdminUtils$.assignReplicasToBrokers(AdminUtils.scala:117)
    	at kafka.admin.AdminUtils$.createTopic(AdminUtils.scala:403)
    	at kafka.admin.TopicCommand$.createTopic(TopicCommand.scala:110)
    	at kafka.admin.TopicCommand$.main(TopicCommand.scala:61)
    	at kafka.admin.TopicCommand.main(TopicCommand.scala)
     (kafka.admin.TopicCommand$)
    ```

2.  通过Manager参看Kafka服务是否处于正常状态，当前可用Broker是否小于设置的replication-factor。
3.  检查客户端命令中ZooKeeper地址是否正确，访问ZooKeeper上所存放的Kafka信息，其路径（Znode）应该加上/kafka，发现配置中缺少/kafka。

    ```
    [root@10-10-144-2 client]# 
    kafka-topics.sh --create  --replication-factor 2 --partitions 2 --topic test --zookeeper 192.168.234.231:2181
    ```


## 解决办法<a name="zh-cn_topic_0167275718_section3518145211446"></a>

1.  保证Kafka服务处于正常状态，且可用Broker不小于设置的replication-factor。
2.  创建命令中ZooKeeper地址信息需要添加/kafka。

    ```
    [root@10-10-144-2 client]# 
    kafka-topics.sh --create  --replication-factor 1 --partitions 2 --topic test --zookeeper 192.168.234.231:2181/kafka
    ```


