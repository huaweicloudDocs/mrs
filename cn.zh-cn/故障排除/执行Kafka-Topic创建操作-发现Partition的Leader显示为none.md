# 执行Kafka Topic创建操作，发现Partition的Leader显示为none<a name="mrs_03_0139"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274710_s5d135719deec4560b99adb07a0aa6416"></a>

在使用Kafka客户端命令创建Topic时，发现创建Topic Partition的Leader显示为none。

```
[root@10-10-144-2 client]# 
kafka-topics.sh --create  --replication-factor 1 --partitions 2 --topic test --zookeeper 10.6.92.36:2181/kafka

Created topic "test".
```

```
[root@10-10-144-2 client]# 
kafka-topics.sh --describe --zookeeper 10.6.92.36:2181/kafka

Topic:test      PartitionCount:2        ReplicationFactor:2     Configs:
        Topic: test     Partition: 0    Leader: none       Replicas: 2,3   Isr:
        Topic: test     Partition: 1    Leader: none       Replicas: 3,1   Isr:
```

## 可能原因<a name="zh-cn_topic_0167274710_s8efdc02bbb1a42cba8fa3e43e2e68817"></a>

-   Kafka服务处于停止状态。
-   找不到用户组信息。

## 原因分析<a name="zh-cn_topic_0167274710_section10342981143649"></a>

1.  查看kafka服务状态及监控指标。
    -   MRS Manager界面操作：登录MRS Manager，依次选择 "服务管理 \> Kafka ，查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。
    -   FusionInsight Manager界面操作：登录FusionInsight Manager，选择“集群 \> 待操作集群的名称 \> 服务 \> Kafka，查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。

2.  在Kafka概览页面获取Controller节点信息。
3.  登录Controller所在节点，通过**cd /var/log/Bigdata/kafka/broker**命令进入节点日志目录，在state-change.log发现存在ZooKeeper权限异常，提示NoAuthException。

    ```
    2018-05-31 09:20:42,436 | ERROR | [ZkClient-EventThread-34-10.6.92.36:24002,10.6.92.37:24002,10.6.92.38:24002/kafka] | Controller 4 epoch 6 initiated state change for partition [test,1] from NewPartition to OnlinePartition failed | state.change.logger (Logging.scala:103) 
    
     org.I0Itec.zkclient.exception.ZkException: org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /brokers/topics/test/partitions
     at org.I0Itec.zkclient.exception.ZkException.create(ZkException.java:68)
     at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:1000)
     at org.I0Itec.zkclient.ZkClient.create(ZkClient.java:527)
     at org.I0Itec.zkclient.ZkClient.createPersistent(ZkClient.java:293)
    ```

4.  查看对应时间段ZooKeeper审计日志，权限异常。

    ```
    2018-05-31 09:20:42,421 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions/0/state	result=failure 
    2018-05-31 09:20:42,423 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions/0	result=failure 
    2018-05-31 09:20:42,435 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions	result=failure 
    2018-05-31 09:20:42,439 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions/1/state	result=failure 
    2018-05-31 09:20:42,441 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions/1	result=failure 
    2018-05-31 09:20:42,453 | ERROR | CommitProcWorkThread-1 | session=0xc3000007015d5a18	user=10.6.92.39,kafka/hadoop.hadoop.com@HADOOP.COM,kafka/hadoop.hadoop.com@HADOOP.COM	ip=10.6.92.39	operation=create znode	target=ZooKeeperServer	znode=/kafka/brokers/topics/test/partitions	result=failure 
    ```

5.  在ZooKeeper各个实例节点上执行**id -Gn kafka**命令，发现有一个节点无法查询用户组信息。

    ```
    [root @bdpsit3ap03 ~]# id -Gn kafka
    id:  kafka: No such user
    [root @bdpsit3ap03 ~]#
    ```

6.  MRS集群中的用户管理由LDAP服务管理提供，又依赖于操作系统的sssd（redhat），nscd（suse）服务，用户的建立到同步到sssd服务需要一定时间，如果此时用户没有生效，或者sssd版本存在bug的情况下，某些情况下在ZooKeeper节点会出现用户无效的情况，导致创建Topic异常。

## 解决办法<a name="zh-cn_topic_0167274710_section65290195402"></a>

1.  重启sssd/nscd服务。
    -   RedHat

        ```
        service sssd restart
        ```

    -   SUSE

        ```
        sevice nscd restart
        ```

2.  重启相关服务后，在节点通过**id username**命令查看相应用户信息是否已有效。

