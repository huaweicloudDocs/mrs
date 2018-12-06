# 查看Storm拓扑日志<a name="ZH-CN_TOPIC_0057181205"></a>

## 操作场景<a name="zh-cn_topic_0053981410_section63666741154720"></a>

用户需要查看Storm拓扑在worker进程中的执行情况时，需要查看worker中关于拓扑的日志。如果需要查询拓扑在运行时数据处理的日志，提交拓扑并启用“Debug“功能后可以查看日志。仅启用Kerberos认证的流集群支持该场景，且用户需要是拓扑的提交者，或者加入“stormadmin“。

## 前提条件<a name="zh-cn_topic_0053981410_section652713881741"></a>

-   在工作环境完成网络配置，请参见[相关任务](访问支持Kerberos认证的Manager.md#section5824002417933)。
-   需要查看处理数据的拓扑，提交时已启用采样功能。

## 查看worker进程日志<a name="zh-cn_topic_0053981410_section951436815483"></a>

1.  访问Storm的WebUI。
2.  在“Topology Summary“区域单击指定的拓扑名称，打开拓扑的详细信息。
3.  单击要查看日志的“Spouts“或“Bolts“任务，在“Executors \(All time\)“区域单击“Port“列的端口值，查看详细日志内容。

## 查看拓扑处理数据日志<a name="zh-cn_topic_0053981410_section3146436417554"></a>

1.  访问Storm的WebUI。
2.  在“Topology Summary“区域单击指定的拓扑名称，打开拓扑的详细信息。
3.  单击“Debug“，输入采样数据的百分比数值，并单击“OK“开始采样。
4.  单击拓扑的“Spouts“或“Bolts“任务，在“Component summary“单击“events“打开处理数据日志。

