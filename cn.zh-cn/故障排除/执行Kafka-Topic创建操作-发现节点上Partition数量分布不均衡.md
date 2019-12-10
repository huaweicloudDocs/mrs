# 执行Kafka Topic创建操作，发现节点上Partition数量分布不均衡<a name="ZH-CN_TOPIC_0187791612"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276449_s5d135719deec4560b99adb07a0aa6416"></a>

在使用Kafka客户端命令创建Topic时，发现创建Topic Partition分布不均衡。

## 可能原因<a name="zh-cn_topic_0167276449_s8efdc02bbb1a42cba8fa3e43e2e68817"></a>

Kafka节点设置机架，且不同机架上节点数量不一致。

## 原因分析<a name="zh-cn_topic_0167276449_section10342981143649"></a>

1.  通过MRS Manager查看Kafka服务Broker实例节点信息，发现不同机架节点数不同。
2.  发现机架节点数上的Broker实例分配的Partition多。

## 解决办法<a name="zh-cn_topic_0167276449_section3518145211446"></a>

1.  确保不同机架上Broker实例数量一致。
2.  创建Topic时，禁用机架感知分配，增加参数**--disable-rack-aware**。

    例如：

    189-120-205-85:/opt/client \#  **kafka-topics.sh --create --topic test --partitions 18 --replication-factor 2 --zookeeper 192.168.205.85:2181/kafka --disable-rack-aware**


