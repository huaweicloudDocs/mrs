# API版本选择建议<a name="ZH-CN_TOPIC_0172602521"></a>

当前MRS服务对外API提供云服务自定义规范的API V1和V2两类接口，V2版本目前仅部分接口支持，主要用于提交作业和提交SQL语句。在接口功能相同的情况下，推荐您优先使用V2接口。

-   MRS所有版本均支持V1接口。
-   针对MRS 1.X版本的集群，MRS 1.8.7及之后版本支持V2接口。
-   针对MRS 2.X版本的集群，MRS 2.0.3及之后版本支持V2接口。

在某些功能上V2接口以V1接口为基础，在功能上做了如下功能增强：

-   支持安全集群提交作业。
-   支持HiveSql、Spark python和Flink作业。
-   支持SparkSql和SparkScript结果查询。

整体API及对应功能列表详见[API概览](API概览.md)。

