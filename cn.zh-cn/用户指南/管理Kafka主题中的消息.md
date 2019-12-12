# 管理Kafka主题中的消息<a name="ZH-CN_TOPIC_0173177964"></a>

## 操作场景<a name="s97aa33d045f046bb9c1d9907172b3db2"></a>

用户可以根据业务需要，使用MRS集群客户端，在Kafka主题中产生消息，或消费消息。启用Kerberos认证的集群，需要用户拥有在Kafka主题中执行相应操作的权限。

## 前提条件<a name="sa5c652338d284a47ad73fc0e957155c5"></a>

已刷新客户端。

## 操作步骤<a name="s87eef4ea94af42b7944cf554191823a4"></a>

1.  登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0207903633.png)进行IAM用户同步）。  
    >-   针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“Kafka  \>  实例“，查看Kafka角色实例的IP地址。

    记录Kafka角色实例其中任意一个的IP地址即可。

3.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[使用MRS客户端](使用MRS客户端.md)。

4.  执行以下命令切换用户。

    **sudo su - omm**

5.  执行以下命令，切换到客户端目录，例如“/opt/client/Kafka/kafka/bin“。

    **cd /opt/client/Kafka/kafka/bin**

6.  执行以下命令，配置环境变量。

    **source /opt/client/bigdata\_env**

7.  启用Kerberos认证的集群，执行以下命令认证用户身份。未启用Kerberos认证集群无需执行。

    **kinit** _**Kafka用户**_

    例如，**kinit admin**

8.  根据业务需要，管理Kafka主题中的消息。

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


