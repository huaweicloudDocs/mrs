# Storm组件的Storm UI页面中events超链接地址无效<a name="ZH-CN_TOPIC_0181149862"></a>

## 用户问题<a name="section18305143583116"></a>

Storm组件的Storm UI页面中events超链接地址无效

## 问题现象<a name="section117424454313"></a>

用户提交拓扑后无法查看拓扑数据处理日志，按钮events地址无效

## 原因分析<a name="section1237061220324"></a>

MRS集群提交拓扑时默认不开启拓扑数据处理日志查看功能。

## 处理步骤<a name="section1910962617165"></a>

1.  访问MRS Manager。
2.  在Manager选择“服务管理  \>  Storm“，在“Storm 概述“的“Storm WebUI“，单击任意一个UI链接，打开Storm的WebUI。
3.  单击“Topology Summary“区域的指定拓扑名称，打开拓扑的详细信息。
4.  在“Topology actions“区域单击“Kill“删除已经提交的Storm拓扑。
5.  重新提交Storm拓扑，并开启查看拓扑数据处理日志功能，在提交Storm拓扑时增加参数“topology.eventlogger.executors”，该参数设置为一个不为0的正整数。例如：

    **storm jar  _拓扑包路径 拓扑Main方法的类名称 拓扑名称_  -c topology.eventlogger.executors=X**

6.  在Storm UI界面，单击“Topology Summary“区域的指定拓扑名称，打开拓扑的详细信息。
7.  在“Topology actions“区域单击“Debug“，输入采样数据的百分比数值，并单击“OK“开始采样。
8.  单击拓扑的“Spouts“或“Bolts“任务名称，在“Component summary“单击“events“即可打开处理数据日志。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如需开启特定“Spouts“或“Bolts“任务的拓扑数据处理日志查看功能，请单击拓扑的“Spouts“或“Bolts“任务名称后，“Topology actions“区域单击“Debug“按钮，输入采样数据的百分比数值。  


