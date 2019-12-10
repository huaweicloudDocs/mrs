# 如何针对Topic进行配置增加和删除<a name="ZH-CN_TOPIC_0205107986"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275091_section4387018310447"></a>

使用Kafka过程中常常需要对特定Topic进行配置或者修改。

Topic级别可以修改参数列表：

```
cleanup.policy
compression.type
delete.retention.ms
file.delete.delay.ms
flush.messages
flush.ms
index.interval.bytes
max.message.bytes
min.cleanable.dirty.ratio
min.insync.replicas
preallocate
retention.bytes
retention.ms
segment.bytes
segment.index.bytes
segment.jitter.ms
segment.ms
unclean.leader.election.enable
```

## 处理步骤<a name="zh-cn_topic_0167275091_section1380098220429"></a>

-   前提条件

    已安装Kafka客户端。

-   操作步骤
    1.  使用PuTTY工具，以客户端安装用户，登录安装Kafka客户端的节点。
    2.  切换到Kafka客户端安装目录，例如“/opt/client”。

        **cd /opt/client**

    3.  执行以下命令，配置环境变量。

        **source bigdata\_env**

    4.  执行以下命令，进行用户认证。（普通模式跳过此步骤）

        **kinit** _组件业务用户_

    5.  执行以下命令，切换到Kafka客户端安装目录。

        **cd Kafka/kafka/bin**

    6.  执行以下命令，针对Topic修改配置和删除配置。

        **kafka-topics.sh --alter --topic <topic\_name\> --zookeeper <zookeeper\_host:port\>/kafka --config <name=value\>**

        **kafka-topics.sh --alter --topic <topic\_name\> --zookeeper <zookeeper\_host:port\>/kafka --delete-config <name\>**

        例如：

        **kafka-topics.sh --alter --topic test1 --zookeeper 192.168.100.100:24002/kafka  --config retention.ms=86400000**

        **kafka-topics.sh --alter --topic test1 --zookeeper 192.168.100.100:24002/kafka --delete-config retention.ms**

    7.  执行以下命令，查询topic信息。

        **kafka-topics.sh --describe -topic <topic\_name\> --zookeeper <zookeeper\_host:port\>/kafka**



