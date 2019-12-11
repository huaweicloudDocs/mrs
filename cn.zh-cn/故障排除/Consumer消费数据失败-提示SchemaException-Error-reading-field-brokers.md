# Consumer消费数据失败，提示SchemaException: Error reading field 'brokers'<a name="ZH-CN_TOPIC_0183415855"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276398_s8c5a413588744f3ea1320d012fdb73cb"></a>

Consumer来消费Kafka中指定Topic的消息时，发现无法从Kafka中获取到数据。提示如下错误： org.apache.kafka.common.protocol.types.SchemaException: Error reading field 'brokers': Error reading field 'host': Error reading string of length 28271, only 593 bytes available。

```
Exception in thread "Thread-0" org.apache.kafka.common.protocol.types.SchemaException: Error reading field 'brokers': Error reading field 'host': Error reading string of length 28271, only 593 bytes available
at org.apache.kafka.common.protocol.types.Schema.read(Schema.java:73)
at org.apache.kafka.clients.NetworkClient.parseResponse(NetworkClient.java:380)
at org.apache.kafka.clients.NetworkClient.handleCompletedReceives(NetworkClient.java:449)
at org.apache.kafka.clients.NetworkClient.poll(NetworkClient.java:269)
at org.apache.kafka.clients.consumer.internals.ConsumerNetworkClient.clientPoll(ConsumerNetworkClient.java:360)
at org.apache.kafka.clients.consumer.internals.ConsumerNetworkClient.poll(ConsumerNetworkClient.java:224)
at org.apache.kafka.clients.consumer.internals.ConsumerNetworkClient.poll(ConsumerNetworkClient.java:192)
at org.apache.kafka.clients.consumer.internals.ConsumerNetworkClient.poll(ConsumerNetworkClient.java:163)
atorg.apache.kafka.clients.consumer.internals.AbstractCoordinator.ensureCoordinatorReady(AbstractCoordinator.java:179)
at org.apache.kafka.clients.consumer.KafkaConsumer.pollOnce(KafkaConsumer.java:973)
at org.apache.kafka.clients.consumer.KafkaConsumer.poll(KafkaConsumer.java:937)
at KafkaNew.Consumer$ConsumerThread.run(Consumer.java:40)

```

## 可能原因<a name="zh-cn_topic_0167276398_s32d34cd2ed084d9dbf63d1ca6576eea0"></a>

客户端和服务端Jar版本不一致。

## 解决办法<a name="zh-cn_topic_0167276398_section54081112311"></a>

修改Consumer应用程序中kafka jar，确保和服务端保持一致。

