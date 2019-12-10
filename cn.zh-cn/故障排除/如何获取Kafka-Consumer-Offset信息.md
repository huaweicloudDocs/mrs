# 如何获取Kafka Consumer Offset信息<a name="ZH-CN_TOPIC_0205107985"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276386_section4387018310447"></a>

使用Kafka Consumer消费数据时，如何获取Kafka Consumer Offset相关信息？

## Kafka API简单说明<a name="zh-cn_topic_0167276386_section2077588020116"></a>

-   新Producer API

    指org.apache.kafka.clients.producer.KafkaProducer中定义的接口，在使用“kafka-console-producer.sh”时，默认使用此API。

-   旧Producer API

    指kafka.producer.Producer中定义的接口，在使用“kafka-console-producer.sh”时，加“--old-producer”参数会调用此API。

-   新Consumer API

    指org.apache.kafka.clients.consumer.KafkaConsumer中定义的接口，在使用“kafka-console-consumer.sh”时，加“--new-consumer”参数会调用此API。

-   旧Consumer API

    指kafka.consumer.ConsumerConnector中定义的接口，在使用“kafka-console-consumer.sh”时，默认使用此API。


>![](public_sys-resources/icon-note.gif) **说明：**   
>新Producer API和新Consumer API，在下文中统称为新API。  

## 处理步骤<a name="zh-cn_topic_0167276386_section40467730202055"></a>

**旧Consumer API**

-   前提条件
    1.  系统管理员已明确业务需求，并准备一个Kafka管理员用户（属于kafkaadmin组）。
    2.  已安装Kafka客户端。

-   操作步骤
    1.  使用PuTTY工具，以客户端安装用户，登录安装Kafka客户端的节点。
    2.  切换到Kafka客户端安装目录，例如“/opt/kafkaclient”。

        **cd /opt/kafkaclient**

    3.  执行以下命令，配置环境变量。

        **source bigdata\_env**

    4.  执行以下命令，进行用户认证。（普通模式跳过此步骤）

        **kinit** _组件业务用户_

    5.  执行以下命令，切换到Kafka客户端安装目录。

        **cd Kafka/kafka/bin**

    6.  执行以下命令，获取consumer offset metric信息。

        ```
         bin/kafka-consumer-groups.sh --zookeeper <zookeeper_host:port>/kafka --list 
        ```

        ```
        bin/kafka-consumer-groups.sh --zookeeper <zookeeper_host:port>/kafka --describe --group test-consumer-group
        ```

        例如：

        ```
        kafka-consumer-groups.sh --zookeeper 192.168.100.100:2181/kafka --list 
        kafka-consumer-groups.sh --zookeeper 192.168.100.100:2181/kafka --describe --group test-consumer-group
        ```



**新Consumer API**

-   前提条件
    1.  系统管理员已明确业务需求，并准备一个Kafka管理员用户（属于kafkaadmin组）。
    2.  已安装Kafka客户端。

-   操作步骤
    1.  使用PuTTY工具，以客户端安装用户，登录安装Kafka客户端的节点。
    2.  切换到Kafka客户端安装目录，例如“/opt/client”。

        **cd /opt/client**

    3.  执行以下命令，配置环境变量。

        **source bigdata\_env**

    4.  执行以下命令，进行用户认证。（普通模式跳过此步骤）

        **kinit** _组件业务用户_

    5.  执行以下命令，切换到Kafka客户端安装目录。

        **cd Kafka/kafka/bin**

    6.  执行以下命令，获取consumer offset metric信息。

        **kafka-consumer-groups.sh --bootstrap-server <broker\_host:port\> --describe --group my-group**

        例如：

        **kafka-consumer-groups.sh --bootstrap-server 192.168.100.100:9092 --describe --group my-group**



