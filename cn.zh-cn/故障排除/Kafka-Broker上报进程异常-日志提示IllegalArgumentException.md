# Kafka Broker上报进程异常，日志提示IllegalArgumentException<a name="mrs_03_0107"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275654_sb1249c03173b4d298f5200c3ac4b01fa"></a>

使用Manager提示进程故障告警，查看告警进程为Kafka Broker。

## 可能原因<a name="zh-cn_topic_0167275654_section64268539194528"></a>

Broker配置异常。

## 原因分析<a name="zh-cn_topic_0167275654_section34191265194843"></a>

1.  在Manager页面，在告警页面得到主机信息。
2.  通过SSH登录Kafka Broker，执行**cd /var/log/Bigdata/kafka/broker**命令进入日志目录。

    查看server.log发现如下日志抛出IllegalArgumentException异常，提示java.lang.IllegalArgumentException: requirement failed: replica.fetch.max.bytes should be equal or greater than message.max.bytes。

    ```
    2017-01-25 09:09:14,930 | FATAL | [main] |  | kafka.Kafka$ (Logging.scala:113)
    java.lang.IllegalArgumentException: requirement failed: replica.fetch.max.bytes should be equal or greater than message.max.bytes
            at scala.Predef$.require(Predef.scala:233)
            at kafka.server.KafkaConfig.validateValues(KafkaConfig.scala:959)
            at kafka.server.KafkaConfig.<init>(KafkaConfig.scala:944)
            at kafka.server.KafkaConfig$.fromProps(KafkaConfig.scala:701)
            at kafka.server.KafkaConfig$.fromProps(KafkaConfig.scala:698)
            at kafka.server.KafkaServerStartable$.fromProps(KafkaServerStartable.scala:28)
            at kafka.Kafka$.main(Kafka.scala:60)
            at kafka.Kafka.main(Kafka.scala)
    ```

    Kafka要求replica.fetch.max.bytes 需要大于等于message.max.bytes。

3.  进入Kafka配置页面，选择“全部配置“， 显示所有Kafka相关配置，分别搜索message.max.bytes、

    replica.fetch.max.bytes进行检索，发现replica.fetch.max.bytes小于message.max.bytes。


## 解决办法<a name="zh-cn_topic_0167275654_section2435112619579"></a>

1.  登录Manager界面，进入Kafka配置页面。
    -   MRS 1.8.10之后版本：登录MRS控制台，在左侧导航栏选择“集群列表 \> 现有集群”，单击集群名称。选择“组件管理 \> Kafka \> 服务配置 \> 全部配置”。
    -   MRS 3.x之前的版本：登录MRS Manager，选择“服务管理 \> Kafka \> 配置 \> 全部配置”。
    -   MRS 3.x及后续版本，登录FusionInsight Manager，选择“集群 \> 服务 \> Kafka \> 配置 \> 全部配置”。

2.  搜索并修改replica.fetch.max.bytes参数，使得replica.fetch.max.bytes的值大于等于 message.max.bytes，使得不同Broker上的Partition的Replica可以同步到全部消息。
3.  保存配置，查看集群是否存在配置过期的服务，如果存在，需重启对应服务或角色实例使配置生效。
4.  修改消费者业务应用中fetch.message.max.bytes，使得fetch.message.max.bytes的值大于等于message.max.bytes，确保消费者可以消费到全部消息。

