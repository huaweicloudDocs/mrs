# Kafka生产者写入单条记录过长问题<a name="ZH-CN_TOPIC_0226521602"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275360_s20deae74a71143aeabad239c7a22f024"></a>

用户在开发一个Kafka应用，作为一个生产者调用新接口（org.apache.kafka.clients.producer.\*）往Kafka写数据，单条记录大小为1100055，超过了kafka配置文件server.properties中message.max.bytes=1000012。用户修改了Kafka服务配置中message.max.bytes大小为5242880，同时也将replica.fetch.max.bytes大小修改为5242880后，仍然无法成功。报异常大致如下：

```
..........
14749 [Thread-0] INFO  com.huawei.bigdata.kafka.example.NewProducer  - The ExecutionException occured : {}.
java.util.concurrent.ExecutionException: org.apache.kafka.common.errors.RecordTooLargeException: The message is 1100093 bytes when serialized which is larger than the maximum request size you have configured with the max.request.size configuration.
at org.apache.kafka.clients.producer.KafkaProducer$FutureFailure.<init>(KafkaProducer.java:739)
at org.apache.kafka.clients.producer.KafkaProducer.doSend(KafkaProducer.java:483)
at org.apache.kafka.clients.producer.KafkaProducer.send(KafkaProducer.java:430)
at org.apache.kafka.clients.producer.KafkaProducer.send(KafkaProducer.java:353)
at com.huawei.bigdata.kafka.example.NewProducer.run(NewProducer.java:150)
Caused by: org.apache.kafka.common.errors.RecordTooLargeException: The message is **** bytes when serialized which is larger than the maximum request size you have configured with the max.request.size configuration.
.......
```

## 原因分析<a name="zh-cn_topic_0167275360_s7dfa4353c00142a991338a71eaf7d6ad"></a>

经分析因为在写数据到Kafka时，Kafka客户端会先比较配置项“max.request.size ”值和本次写入数据大小，若写入数据大小超过此配置项“max.request.size ”的缺省值，则抛出上述异常。

## 解决办法<a name="zh-cn_topic_0167275360_section54311375103045"></a>

1.  在初始化Kafka生产者实例时，设置此配置项“max.request.size ”的值。

    例如，参考本例，可以将此配置项设置为“5252880”：

    ```
            // 协议类型:当前支持配置为SASL_PLAINTEXT或者PLAINTEXT
            props.put(securityProtocol, kafkaProc.getValues(securityProtocol, "SASL_PLAINTEXT"));
            // 服务名
            props.put(saslKerberosServiceName, "kafka");
            props.put("max.request.size", "5252880");
            .......
    ```


