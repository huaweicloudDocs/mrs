# KafkaManager介绍<a name="ZH-CN_TOPIC_0173178204"></a>

KafkaManager是Apache Kafka的管理工具，提供Kafka集群界面化的Metric监控和集群管理。

通过KafkaManager可以：

-   支持管理多个Kafka集群
-   支持界面检查集群状态（主题，消费者，偏移量，分区，副本，节点）
-   支持界面执行副本的leader选举
-   使用选择生成分区分配以选择要使用的分区方案
-   支持界面执行分区重新分配（基于生成的分区方案）
-   支持界面选择配置创建主题（支持多种Kafka版本集群）
-   支持界面删除主题（仅支持0.8.2+并设置了delete.topic.enable = true）
-   支持批量生成多个主题的分区分配，并可选择要使用的分区方案
-   支持批量运行重新分配多个主题的分区
-   支持为已有主题增加分区
-   支持更新现有主题的配置
-   可以为分区级别和主题级别度量标准启用JMX查询
-   可以过滤掉zookeeper中没有ids / owner /＆offsets /目录的使用者。

