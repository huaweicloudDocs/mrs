# Kakfa消费者读取单条记录过长问题<a name="ZH-CN_TOPIC_0226521603"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274552_s20deae74a71143aeabad239c7a22f024"></a>

和“Kafka生产者写入单条记录过长问题”相对应的，在写入数据后，用户开发一个应用，以消费者调用新接口（org.apache.kafka.clients.consumer.\*）到Kafka上读取数据，但读取失败，报异常大致如下：

```
..........
1687 [KafkaConsumerExample] INFO  org.apache.kafka.clients.consumer.internals.AbstractCoordinator  - Successfully joined group DemoConsumer with generation 1
1688 [KafkaConsumerExample] INFO  org.apache.kafka.clients.consumer.internals.ConsumerCoordinator  - Setting newly assigned partitions [default-0, default-1, default-2] for group DemoConsumer
2053 [KafkaConsumerExample] ERROR com.huawei.bigdata.kafka.example.NewConsumer  - [KafkaConsumerExample], Error due to 
org.apache.kafka.common.errors.RecordTooLargeException: There are some messages at [Partition=Offset]: {default-0=177} whose size is larger than the fetch size 1048576 and hence cannot be ever returned. Increase the fetch size on the client (using max.partition.fetch.bytes), or decrease the maximum message size the broker will allow (using message.max.bytes).
2059 [KafkaConsumerExample] INFO  com.huawei.bigdata.kafka.example.NewConsumer  - [KafkaConsumerExample], Stopped 
.......
```

## 原因分析<a name="zh-cn_topic_0167274552_s7dfa4353c00142a991338a71eaf7d6ad"></a>

经分析因为在读取数据时Kafka客户端会比较待读取数据大小和配置项“max.partition.fetch.bytes”值，若超过此配置项值，则抛出上述异常。

## 解决办法<a name="zh-cn_topic_0167274552_section54311375103045"></a>

1.  在初始化建立Kafka消费者实例时，设置此配置项“max.partition.fetch.bytes”的值。

    例如，参考本例，可以将此配置项设置为“5252880”：

    ```
    ......
    // 安全协议类型
    props.put(securityProtocol, kafkaProc.getValues(securityProtocol, "SASL_PLAINTEXT"));
    // 服务名
    props.put(saslKerberosServiceName, "kafka");
            
    props.put("max.partition.fetch.bytes","5252880");
    ......
    ```


