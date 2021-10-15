# 运行Kafka作业<a name="mrs_01_0494"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在Kafka主题中产生和消费消息。

暂不支持通过界面提交Kafka作业，请通过后台功能来提交作业。

## 通过后台提交作业<a name="section12299175615451"></a>

先查询ZooKeeper和Kafka的实例地址，再运行Kafka作业。

**查询实例地址（3.x版本）**

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  请参考[访问FusionInsight Manager（MRS 3.x及之后版本）](访问FusionInsight-Manager（MRS-3-x及之后版本）.md)，跳转至FusionInsight Manager页面。然后选择“服务 \> ZooKeeper \> 实例”，查看ZooKeeper角色实例的IP地址。记录ZooKeeper角色实例中任意一个的IP地址即可。
4.  选择“服务 \> Kafka \> 实例”，查看Kafka角色实例的IP地址。记录Kafka角色实例中任意一个的IP地址即可。

**查询实例地址（3.x之前版本）**

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  在MRS集群详情页面，选择“组件管理 \> ZooKeeper \> 实例”，查看ZooKeeper角色实例的IP地址。记录ZooKeeper角色实例中任意一个的IP地址即可。
4.  选择“组件管理 \> Kafka \> 实例”，查看Kafka角色实例的IP地址。记录Kafka角色实例中任意一个的IP地址即可。

**运行Kafka作业**

MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。

1.  在集群信息页面的“节点管理”页签中单击Master2节点名称，进入弹性云服务器管理控制台。
2.  单击页面右上角的“远程登录”。
3.  根据界面提示，输入Master节点的用户名和密码，用户名、密码分别为root和创建集群时设置的密码。
4.  执行如下命令初始化环境变量。

    **source /opt/Bigdata/client/bigdata\_env**

5.  如果当前集群已开启Kerberos认证，执行以下命令认证当前用户。如果当前集群未开启Kerberos认证，则无需执行该步骤。

    **kinit** **_MRS__集群用户_**

    例如,  **kinit admin**

6.  执行如下命令，创建kafka topic。

    **kafka-topics.sh --create --zookeeper <ZooKeeper角色实例IP:2181/kafka\> --partitions 2 --replication-factor 2 --topic <Topic名称\>**

7.  在topic test中产生消息。

    首先执行命令**kafka-console-producer.sh --broker-list <Kafka角色实例IP:9092\> --topic <Topic名称\> --producer.config /opt/Bigdata/client/Kafka/kafka/config/producer.properties**。

    然后输入指定的内容作为生产者产生的消息，输入完成后按回车发送消息。如果需要结束产生消息，使用“Ctrl + C”退出任务。

8.  消费topic test中的消息。

    **kafka-console-consumer.sh --topic <Topic名称\> --bootstrap-server <Kafka角色实例IP:9092\> --consumer.config /opt/Bigdata/client/Kafka/kafka/config/consumer.properties**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果集群开启Kerberos认证，则执行如上两个命令时请修改端口号9092为21007，详见[开源组件端口列表](开源组件端口列表.md)。


