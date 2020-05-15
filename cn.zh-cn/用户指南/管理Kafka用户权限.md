# 管理Kafka用户权限<a name="ZH-CN_TOPIC_0173178168"></a>

## 操作场景<a name="se728d030bf0f499989fe2e36267d8a4a"></a>

在启用Kerberos认证的集群中，用户使用Kafka时前需要拥有对应的权限。MRS集群支持将Kafka的使用权限，授予不同用户。

Kafka默认用户组如[表1](#t5ed4e7771fac4113ad733d56146a3b07)所示。

**表 1**  Kafka默认用户组

<a name="t5ed4e7771fac4113ad733d56146a3b07"></a>
<table><thead align="left"><tr id="r076853725c81491db89e57a4219e1eb8"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a1c64627b000143f5816333b8e6e9f12f"><a name="a1c64627b000143f5816333b8e6e9f12f"></a><a name="a1c64627b000143f5816333b8e6e9f12f"></a><strong id="abc8c5f4cc5b346f19c8bcf06a11a4550"><a name="abc8c5f4cc5b346f19c8bcf06a11a4550"></a><a name="abc8c5f4cc5b346f19c8bcf06a11a4550"></a>用户组名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a57b26b6571eb4b89956de7fca6e77437"><a name="a57b26b6571eb4b89956de7fca6e77437"></a><a name="a57b26b6571eb4b89956de7fca6e77437"></a><strong id="a0ff4672a60834b258e5f7dc59ed138a6"><a name="a0ff4672a60834b258e5f7dc59ed138a6"></a><a name="a0ff4672a60834b258e5f7dc59ed138a6"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r414ece5231214e59807da3d66140d6ed"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2afbbea3ec4343ab8cae589a41d39de9"><a name="a2afbbea3ec4343ab8cae589a41d39de9"></a><a name="a2afbbea3ec4343ab8cae589a41d39de9"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a8837e02cee8c4e289282d8ddc9e40a9a"><a name="a8837e02cee8c4e289282d8ddc9e40a9a"></a><a name="a8837e02cee8c4e289282d8ddc9e40a9a"></a>Kafka管理员用户组。添加入本组的用户，拥有所有主题的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="r4c54cddfd5bf4f7185beebba3b0abba7"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ab2cd4dbea3184549b76509057a1f2789"><a name="ab2cd4dbea3184549b76509057a1f2789"></a><a name="ab2cd4dbea3184549b76509057a1f2789"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aab404a111ec7473594a1ce99c4aa29d4"><a name="aab404a111ec7473594a1ce99c4aa29d4"></a><a name="aab404a111ec7473594a1ce99c4aa29d4"></a>Kafka高级用户组。添加入本组的用户，拥有所有主题的读写权限。</p>
</td>
</tr>
<tr id="ra0878debfa1f4e5f9aeee2270a86f301"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="aa07efdb47cd940638fa4dc5d7d90d5be"><a name="aa07efdb47cd940638fa4dc5d7d90d5be"></a><a name="aa07efdb47cd940638fa4dc5d7d90d5be"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0054328609_p85436155921"><a name="zh-cn_topic_0054328609_p85436155921"></a><a name="zh-cn_topic_0054328609_p85436155921"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定主题的读写权限，才能访问对应主题。</p>
</td>
</tr>
</tbody>
</table>

## 前提条件<a name="sa4b650e4d82344e6adca63da0d91dc47"></a>

-   已刷新客户端。
-   用户已明确业务需求，并准备一个属于kafkaadmin组的用户，作为Kafka管理员用户。例如“admin“。

## 操作步骤<a name="sbb525980438c497999b816161b9eb948"></a>

1.  登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“点击同步”进行IAM用户同步）。  
    >-   针对MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“ZooKeeper  \>  实例“，查看ZooKeeper角色实例的IP地址。

    记录ZooKeeper角色实例其中任意一个的IP地址即可。

3.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[使用MRS客户端](使用MRS客户端.md)。

4.  执行以下命令切换用户。

    **sudo su - omm**

5.  执行以下命令，切换到客户端目录，例如“/opt/client/Kafka/kafka/bin“。

    **cd /opt/client/Kafka/kafka/bin**

6.  执行以下命令，配置环境变量。

    **source /opt/client/bigdata\_env**

7.  执行以下命令，认证Kafka管理员用户。

    **kinit** _**管理员用户名**_

    例如，**kinit admin**

8.  选择业务需要对应的场景，管理Kafka用户权限：

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


