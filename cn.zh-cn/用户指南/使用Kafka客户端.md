# 使用Kafka客户端<a name="mrs_01_24191"></a>

## 操作场景<a name="zh-cn_topic_0264266588_section43461647164218"></a>

用户可以在集群客户端完成Topic的创建、查询、删除等基本操作。

## 前提条件<a name="zh-cn_topic_0264266588_section1022821213273"></a>

已安装客户端，例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

## 使用Kafka客户端（MRS 3.x之前版本）<a name="zh-cn_topic_0264266588_section179001923123114"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
2.  进入ZooKeeper实例页面：

    单击集群名称，登录集群详情页面，选择“组件管理 \> ZooKeeper \> 实例”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“同步”进行IAM用户同步）。

3.  查看ZooKeeper角色实例的IP地址。

    记录ZooKeeper角色实例其中任意一个的IP地址即可。

4.  登录安装客户端的节点。
5.  执行以下命令，切换到客户端目录，例如“/opt/hadoopclient/Kafka/kafka/bin”。

    **cd /opt/hadoopclient/Kafka/kafka/bin**

6.  执行以下命令，配置环境变量。

    **source /opt/hadoopclient/bigdata\_env**

7.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** _Kafka用户_

8.  <a name="zh-cn_topic_0264266588_li1147589014556"></a>创建一个Topic：

    **sh kafka-topics.sh --create --topic **_主题名称_** --partitions** _主题占用的分区数_ **--replication-factor** _主题的备份个数_ **--zookeeper** _ZooKeeper角色实例所在节点IP地址**:**clientPort_**/kafka**

9.  执行以下命令，查询集群中的Topic信息：

    **sh kafka-topics.sh --list --zookeeper **_ZooKeeper角色实例所在节点IP地址:clientPort_**/kafka**

10. 删除[8](#zh-cn_topic_0264266588_li1147589014556)中创建的Topic：

    **sh kafka-topics.sh --delete --topic** _主题名称_ **--zookeeper** _ZooKeeper角色实例所在节点IP地址_:_clientPort_**/kafka**

    输入 "y"，回车。


## 使用Kafka客户端（MRS 3.x及之后版本）<a name="zh-cn_topic_0264266588_section2695144004617"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。
2.  进入ZooKeeper实例页面：

    登录FusionInsight Manager，具体请参见[访问FusionInsight Manager（MRS 3.x及之后版本）](访问FusionInsight-Manager（MRS-3-x及之后版本）.md)。然后选择“集群 \>  _待操作的集群名_称 \> 服务 \> ZooKeeper \> 实例”。

3.  查看ZooKeeper角色实例的IP地址。

    记录ZooKeeper角色实例其中任意一个的IP地址即可。

4.  登录安装客户端的节点。
5.  执行以下命令，切换到客户端目录，例如“/opt/hadoopclient/Kafka/kafka/bin”。

    **cd /opt/hadoopclient/Kafka/kafka/bin**

6.  执行以下命令，配置环境变量。

    **source /opt/hadoopclient/bigdata\_env**

7.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** _Kafka用户_

8.  <a name="zh-cn_topic_0264266588_li4808125415465"></a>创建一个Topic：

    **sh kafka-topics.sh --create --topic **_主题名称_** --partitions** _主题占用的分区数_ **--replication-factor** _主题的备份个数_ **--zookeeper** _ZooKeeper角色实例所在节点IP地址**:**clientPort_**/kafka**

9.  执行以下命令，查询集群中的Topic信息：

    **sh kafka-topics.sh --list --zookeeper **_ZooKeeper角色实例所在节点IP地址:clientPort_**/kafka**

10. 删除[8](#zh-cn_topic_0264266588_li4808125415465)中创建的Topic：

    **sh kafka-topics.sh --delete --topic** _主题名称_ **--zookeeper** _ZooKeeper角色实例所在节点IP地址_:_clientPort_**/kafka**

    输入 "y"，回车。


