# 管理Kafka主题中的消息<a name="ZH-CN_TOPIC_0057181200"></a>

## 操作场景<a name="zh-cn_topic_0054328610_section63666741154720"></a>

用户可以根据业务需要，使用MRS集群客户端，在Kafka主题中产生消息，或消费消息。启用Kerberos认证的集群，需要用户拥有在Kafka主题中执行相应操作的权限。

## 前提条件<a name="zh-cn_topic_0054328610_section951436815483"></a>

已刷新客户端。

## 操作步骤<a name="zh-cn_topic_0054328610_section2210939420957"></a>

1.  在MRS Manager，选择“服务管理  \>  Kafka  \>  实例“，查看Kafka角色实例的IP地址。

    记录Kafka角色实例其中任意一个的IP地址即可。

2.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[客户端管理](客户端管理.md)。

3.  执行以下命令切换用户。

    **sudo su - omm**

4.  执行以下命令，切换到客户端目录，例如“/opt/client/Kafka/kafka/bin“。

    **cd /opt/client/Kafka/kafka/bin**

5.  执行以下命令，配置环境变量。

    **source /opt/client/bigdata\_env**

6.  启用Kerberos认证的集群，执行以下命令认证用户身份。未启用Kerberos认证集群无需执行。

    **kinit** _**Kafka用户**_

    例如，**kinit admin**

7.  根据业务需要，管理Kafka主题中的消息。

    -   在主题中产生消息

        **sh kafka-console-producer.sh --broker-list** _**Kafka角色实例所在节点的IP地址**_**:9092 --topic** _**主题名称**_ **--producer.config /opt/client/Kafka/kafka/config/producer.properties**

        用户可以输入指定的内容作为生产者产生的消息，输入完成后按回车发送消息。如果需要结束产生消息，使用“Ctrl + C“退出任务。

    -   消费主题中的消息

        **sh kafka-console-consumer.sh --topic** _**主题名称**_ **--bootstrap-server** _**Kafka角色实例所在节点的IP地址**_**:9092 --new-consumer --consumer.config /opt/client/Kafka/kafka/config/consumer.properties**

        配置文件中“group.id“指定的消费者组默认为“example-group1“。用户可根据业务需要，自定义其他消费者组。每次消费时生效。

        执行命令时默认会读取当前消费者组中未被处理的消息。如果在配置文件指定了新的消费者组且命令中增加参数“--from-beginning“，则会读取所有Kafka中未被自动删除的消息。


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   Kafka角色实例所在节点IP地址，填写Broker角色实例其中任意一个的IP地址即可。  
    >-   如果集群启用Kerberos认证，则端口需要修改为“21007“。  
    >-   MRS 1.6.2及之前的版本，未启用Kerberos认证集群端口默认为21005，详见[开源组件端口列表](开源组件端口列表.md)  


