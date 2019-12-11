# Consumer消费数据是否丢失排查<a name="ZH-CN_TOPIC_0183415856"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276280_s8c5a413588744f3ea1320d012fdb73cb"></a>

客户将消费完的数据存入数据库，发现数据与生产数据不一致，怀疑Kafka消费丢数据

## 可能原因<a name="zh-cn_topic_0167276280_s32d34cd2ed084d9dbf63d1ca6576eea0"></a>

-   客户代码原因
-   Kafka生产数据写入异常
-   Kafka消费数据异常

## 解决办法<a name="zh-cn_topic_0167276280_section54081112311"></a>

Kafka排查：

1.  通过consumer-groups.sh来观察写入和消费的offerset的变化情况（生产一定数量的消息，客户端进行消费，观察offerset的变化）。

    ![](figures/zh-cn_image_0183413122.png)

2.  新建一个消费组，用客户端进行消费，然后查看消费的消息。

    new-consumer:

    kafka-console-consumer.sh --topic <topic name\> --bootstrap-server <IP1:PORT, IP2:PORT,...\> --new-consumer --consumer.config <config file\>


客户代码排查：

1.  查看客户端里有没有提交offerset的报错。
2.  如果没有报错把消费的API里加上打印消息，打印少量数据（只打印key即可），查看丢失的数据。

