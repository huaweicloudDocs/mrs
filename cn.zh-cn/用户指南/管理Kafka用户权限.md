# 管理Kafka用户权限<a name="ZH-CN_TOPIC_0057181199"></a>

## 操作场景<a name="zh-cn_topic_0054328609_section2762427155642"></a>

在启用Kerberos认证的集群中，用户使用Kafka时前需要拥有对应的权限。MRS集群支持将Kafka的使用权限，授予不同用户。

Kafka默认用户组如[表1](#zh-cn_topic_0054328609_table29776035155843)所示。

**表 1**  Kafka默认用户组

<a name="zh-cn_topic_0054328609_table29776035155843"></a>
<table><thead align="left"><tr id="zh-cn_topic_0054328609_row3210325155843"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0054328609_p58625732155843"><a name="zh-cn_topic_0054328609_p58625732155843"></a><a name="zh-cn_topic_0054328609_p58625732155843"></a><strong id="zh-cn_topic_0054328609_b4707205215594"><a name="zh-cn_topic_0054328609_b4707205215594"></a><a name="zh-cn_topic_0054328609_b4707205215594"></a>用户组名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0054328609_p51063866155843"><a name="zh-cn_topic_0054328609_p51063866155843"></a><a name="zh-cn_topic_0054328609_p51063866155843"></a><strong id="zh-cn_topic_0054328609_b5473986815594"><a name="zh-cn_topic_0054328609_b5473986815594"></a><a name="zh-cn_topic_0054328609_b5473986815594"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0054328609_row56921615155843"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0054328609_p47248080155843"><a name="zh-cn_topic_0054328609_p47248080155843"></a><a name="zh-cn_topic_0054328609_p47248080155843"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0054328609_p1889303155843"><a name="zh-cn_topic_0054328609_p1889303155843"></a><a name="zh-cn_topic_0054328609_p1889303155843"></a>Kafka管理员用户组。添加入本组的用户，拥有所有主题的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0054328609_row17003727155843"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0054328609_p35124631155843"><a name="zh-cn_topic_0054328609_p35124631155843"></a><a name="zh-cn_topic_0054328609_p35124631155843"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0054328609_p26522839155843"><a name="zh-cn_topic_0054328609_p26522839155843"></a><a name="zh-cn_topic_0054328609_p26522839155843"></a>Kafka高级用户组。添加入本组的用户，拥有所有主题的读写权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0054328609_row1749078155921"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0054328609_p7457595155921"><a name="zh-cn_topic_0054328609_p7457595155921"></a><a name="zh-cn_topic_0054328609_p7457595155921"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0054328609_p85436155921"><a name="zh-cn_topic_0054328609_p85436155921"></a><a name="zh-cn_topic_0054328609_p85436155921"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定主题的读写权限，才能访问对应主题。</p>
</td>
</tr>
</tbody>
</table>

## 前提条件<a name="zh-cn_topic_0054328609_section650601541614"></a>

-   已刷新客户端。
-   用户已明确业务需求，并准备一个属于kafkaadmin组的用户，作为Kafka管理员用户。例如“admin“。

## 操作步骤<a name="zh-cn_topic_0054328609_section4157332816253"></a>

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

6.  执行以下命令，认证Kafka管理员用户。

    **kinit** _**管理员用户名**_

    例如，**kinit admin**

7.  选择业务需要对应的场景，管理Kafka用户权限：

    -   查看某个主题的权限控制列表

        **sh kafka-acls.sh --authorizer-properties zookeeper.connect=_ZooKeeper角色实例所在节点IP地址_:2181/kafka --list --topic** _**主题名称**_

    -   为某个用户添加生产者的权限

        **sh kafka-acls.sh --authorizer-properties zookeeper.connect=**_**ZooKeeper角色实例所在节点IP地址**_**:2181/kafka --add --allow-principal User:**_**用户名**_ **--producer --topic** _**主题名称**_

    -   删除某个用户的生产者权限

        **sh kafka-acls.sh --authorizer-properties zookeeper.connect=**_**ZooKeeper角色实例所在节点IP地址**_**:2181/kafka --remove --allow-principal User:**_**用户名**_ **--producer --topic** _**主题名称**_

    -   为某个用户添加消费者的权限

        **sh kafka-acls.sh --authorizer-properties zookeeper.connect=**_**ZooKeeper角色实例所在节点IP地址**_**:2181/kafka --add --allow-principal User:**_**用户名**_ **--consumer --topic** _**主题名称**_ **--group** _**消费者组名称**_

    -   删除某个用户的消息者权限

        **sh kafka-acls.sh --authorizer-properties zookeeper.connect=**_**ZooKeeper角色实例所在节点IP地址**_**:2181/kafka --remove --allow-principal User:**_**用户名**_ **--consumer --topic** _**主题名称**_ **--group** _**消费者组名称**_


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >删除权限时需要输入两次“y“确认删除权限。  
    >MRS 1.6.2及之前的版本，默认Zookeeper端口号为24002,详见[开源组件端口列表](开源组件端口列表.md)  


