# 访问KafkaManager的WebUI<a name="ZH-CN_TOPIC_0173178872"></a>

用户可以通过KafkaManager的WebUI，在图形化界面监控管理Kafka集群。

## 前提条件<a name="section3181241161011"></a>

-   已安装KafkaManager服务的集群。
-   获取用户“admin”帐号密码。“admin”密码在创建MRS集群时由用户指定。

## 访问KafkaManager的WebUI<a name="section16790101115"></a>

1.  登录集群详情页面，选择“组件管理 \> KafkaManager”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“点击同步”进行IAM用户同步）。  
    >-   针对MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  在KafkaManager概述的“KafkaManager WebUI“中单击任意一个UI链接，打开KafkaManager的WebUI页面。

    KafkaManager的WebUI支持查看以下信息：

    -   Kafka集群列表
    -   Kafka集群Broker节点列表和Metric监控
    -   Kafka集群副本监控
    -   Kafka集群Consumer监控

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >在KafkaManager的任何子页面单击左上角KafkaManager的Logo都可以回到KafkaManager的WebUI主界面，显示集群列表信息。  


