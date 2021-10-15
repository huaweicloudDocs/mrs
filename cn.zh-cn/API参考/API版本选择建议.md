# API版本选择建议<a name="mrs_02_0006"></a>

当前MRS服务对外API提供云服务自定义规范的API V1.1和V2两类接口，V2版本目前仅部分接口支持，主要用于提交作业和提交SQL语句。在接口功能相同的情况下，推荐您优先使用V2接口。

在某些功能上V2接口以V1.1接口为基础，在功能上做了如下功能增强：

-   支持安全集群提交作业。
-   支持HiveSql、Spark python和Flink作业。
-   支持SparkSql和SparkScript结果查询。

整体API及对应功能列表详见[API概览](API概览.md)。

