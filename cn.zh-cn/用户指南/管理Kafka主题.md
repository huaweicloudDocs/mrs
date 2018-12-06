# 管理Kafka主题<a name="ZH-CN_TOPIC_0057181197"></a>

## 操作场景<a name="zh-cn_topic_0053946969_section63666741154720"></a>

用户可以根据业务需要，使用MRS集群客户端管理Kafka的主题。启用Kerberos认证的集群，需要拥有管理Kafka主题的权限。

## 前提条件<a name="zh-cn_topic_0053946969_section951436815483"></a>

已刷新客户端。

## 操作步骤<a name="zh-cn_topic_0053946969_section5829420154816"></a>

1.  在MRS Manager，选择“服务管理  \>  ZooKeeper  \>  实例“，查看ZooKeeper角色实例的IP地址。

    记录ZooKeeper角色实例其中任意一个的IP地址即可。

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

7.  分别执行以下命令，管理Kafka主题。

    -   创建主题

        **sh kafka-topics.sh --create --topic  _主题名称_  --partitions** _**主题占用的分区数**_ **--replication-factor** _**主题的备份个数**_ **--zookeeper** _**ZooKeeper角色实例所在节点IP地址:clientPort**_**/kafka**

    -   删除主题

        **sh kafka-topics.sh --delete --topic** _**主题名称**_ **--zookeeper** _**ZooKeeper角色实例所在节点IP地址**_**:**_**clientPort**_**/kafka**


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   主题分区数和主题备份个数不能大于Kafka角色实例数量。  
    >-   默认情况下，ZooKeeper的“clientPort“为“2181“。  
    >    MRS 1.6.2及之前的版本，ZooKeeper clientPort默认为24002，详见[开源组件端口列表](开源组件端口列表.md)  
    >-   ZooKeeper角色实例所在节点IP地址，填写三个角色实例其中任意一个的IP地址即可。  
    >-   使用Kafka主题管理消息，请参见[管理Kafka主题中的消息](管理Kafka主题中的消息.md)。  


