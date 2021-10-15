# Storm组件的Storm UI页面中events超链接地址无效<a name="mrs_03_0034"></a>

## 用户问题<a name="section18305143583116"></a>

Storm组件的Storm UI页面中events超链接地址无效。

## 问题现象<a name="section117424454313"></a>

用户提交拓扑后无法查看拓扑数据处理日志，按钮events地址无效。

## 原因分析<a name="section1237061220324"></a>

MRS集群提交拓扑时默认不开启拓扑数据处理日志查看功能。

## 处理步骤<a name="section1910962617165"></a>

1.  进入服务页面：
    -   MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)，然后选择“服务管理 ”。
    -   MRS 1.8.10之后及2._x_版本，单击集群名称，登录集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

    -   MRS 3.x及后续版本，登录FusionInsight Manager，然后选择“集群 \>  _待操作的集群名_称 \> 服务 ”。

2.  登录Storm WebUI：
    -   MRS 2.x及之前版本：选择“Storm“，在“Storm 概述“的“Storm WebUI“，单击任意一个UI链接，打开Storm的WebUI。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >第一次访问Storm WebUI，需要在浏览器中添加站点信任以继续打开页面。

    -   MRS 3.x及后续版本：选择“Storm  \>   概览“，在“基本信息“的“Storm WebUI“，单击任意一个UI链接，打开Storm的WebUI。

3.  单击“Topology Summary“区域的指定拓扑名称，打开拓扑的详细信息。
4.  在“Topology actions“区域单击“Kill“删除已经提交的Storm拓扑。
5.  重新提交Storm拓扑，并开启查看拓扑数据处理日志功能，在提交Storm拓扑时增加参数“topology.eventlogger.executors”，该参数设置为一个不为0的正整数。例如：

    **storm jar  _拓扑包路径 拓扑Main方法的类名称 拓扑名称_  -c topology.eventlogger.executors=X**

6.  在Storm UI界面，单击“Topology Summary“区域的指定拓扑名称，打开拓扑的详细信息。
7.  在“Topology actions“区域单击“Debug“，输入采样数据的百分比数值，并单击“OK“开始采样。
8.  单击拓扑的“Spouts“或“Bolts“任务名称，在“Component summary“单击“events“即可打开处理数据日志。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如需开启特定“Spouts“或“Bolts“任务的拓扑数据处理日志查看功能，请单击拓扑的“Spouts“或“Bolts“任务名称后，“Topology actions“区域单击“Debug“按钮，输入采样数据的百分比数值。


