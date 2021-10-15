# 如何获取Topic的分布信息<a name="mrs_03_0197"></a>

## 用户问题<a name="zh-cn_topic_0167276323_sd1dc17fee2214ed9867d242a14f38d7d"></a>

如何获取Topic在Broker实例的分布信息？

## 前置操作<a name="zh-cn_topic_0167276323_section3994733292450"></a>

-   前提条件

    已安装Kafka、ZooKeeper客户端。

-   操作步骤
    1.  以客户端安装用户，登录安装Kafka客户端的节点。
    2.  切换到Kafka客户端安装目录，例如“/opt/client”。

        **cd /opt/client**

    3.  执行以下命令，配置环境变量。

        **source bigdata\_env**

    4.  执行以下命令，进行用户认证。（普通集群跳过此步骤）

        **kinit  _组件业务用户_**

    5.  执行以下命令，切换到Kafka客户端安装目录。

        **cd Kafka/kafka/bin**

    6.  执行Kafka相关命令，获取Topic分布信息和副本同步信息，观察返回结果。

        **kafka-topics.sh** **--describe** **--zookeeper <zk\_host:port/chroot\>**

        例如：

        ```
        [root@mgtdat-sh-3-01-3 client]#kafka-topics.sh --describe --zookeeper 10.149.0.90:2181/kafka
        Topic:topic1   PartitionCount:2  ReplicationFactor:2     Configs:
        Topic: topic1  Partition: 0 Leader: 26 Replicas: 23,25 Isr: 26
        Topic: topic1  Partition: 1 Leader: 24 Replicas: 24,23 Isr: 24,23
        ```

        其中，Replicas对应副本分布信息，Isr对应副本同步信息。



## 处理方法1<a name="zh-cn_topic_0167276323_section5087984593329"></a>

1.  在ZooKeeper中查询Broker ID的对应关系。

    **sh zkCli.sh -server <zk\_host:port\>**

2.  在ZooKeeper客户端执行如下命令。

    **ls /kafka/brokers/ids**

    **get /kafka/brokers/ids/<查询出的Broker id\>**

    例如：

    ```
    [root@node-master1gAMQ kafka]# zkCli.sh -server node-master1gAMQ:2181
    Connecting to node-master1gAMQ:2181
    Welcome to ZooKeeper!
    JLine support is enabled
    
    WATCHER::
    
    WatchedEvent state:SyncConnected type:None path:null
    [zk: node-master1gAMQ:2181(CONNECTED) 0] ls /kafka/brokers/
    ids      seqid    topics
    [zk: node-master1gAMQ:2181(CONNECTED) 0] ls /kafka/brokers/ids
    [1]
    [zk: node-master1gAMQ:2181(CONNECTED) 1] get /kafka/brokers/ids/1
    {"listener_security_protocol_map":{"PLAINTEXT":"PLAINTEXT","SSL":"SSL"},"endpoints":["PLAINTEXT://192.168.2.242:9092","SSL://192.168.2.242:9093"],"rack":"/default/rack0","jmx_port":21006,"host":"192.168.2.242","timestamp":"1580886124398","port":9092,"version":4}
    [zk: node-master1gAMQ:2181(CONNECTED) 2]
    
    ```


## 处理方法2<a name="zh-cn_topic_0167276323_section4533772891919"></a>

获取节点和broker ID的对应关系

**kafka-broker-info.sh** **--zookeeper <zk\_host:port/chroot\>**

例如：

```
[root@node-master1gAMQ kafka]# bin/kafka-broker-info.sh --zookeeper 192.168.2.70:2181/kafka
Broker_ID     IP_Address
--------------------------
  1           192.168.2.242

```

