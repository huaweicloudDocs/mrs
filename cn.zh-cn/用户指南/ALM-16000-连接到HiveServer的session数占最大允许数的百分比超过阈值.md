# ALM-16000 连接到HiveServer的session数占最大允许数的百分比超过阈值<a name="ZH-CN_TOPIC_0191883102"></a>

## 告警解释<a name="zh-cn_topic_0191813892_section12470207"></a>

系统每30秒周期性检测连接到HiveServer的Session数占HiveServer允许的最大session数的百分比，该指标可在Hive服务监控界面查看。连接到HiveServer的session数占最大允许数的百分比指标默认提供一个阈值范围（90%），当检测到百分比指标超过阈值范围产生该告警。

当百分比指标小于或等于阈值时，可自动清除告警。

## 告警属性<a name="zh-cn_topic_0191813892_section45123001"></a>

<a name="zh-cn_topic_0191813892_table33142240"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813892_row21192109"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813892_p38839231"><a name="zh-cn_topic_0191813892_p38839231"></a><a name="zh-cn_topic_0191813892_p38839231"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813892_p58970022"><a name="zh-cn_topic_0191813892_p58970022"></a><a name="zh-cn_topic_0191813892_p58970022"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813892_p11842506"><a name="zh-cn_topic_0191813892_p11842506"></a><a name="zh-cn_topic_0191813892_p11842506"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813892_row19718930"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813892_p53729511"><a name="zh-cn_topic_0191813892_p53729511"></a><a name="zh-cn_topic_0191813892_p53729511"></a>16000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813892_p57123120"><a name="zh-cn_topic_0191813892_p57123120"></a><a name="zh-cn_topic_0191813892_p57123120"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813892_p63570006"><a name="zh-cn_topic_0191813892_p63570006"></a><a name="zh-cn_topic_0191813892_p63570006"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813892_section3453833"></a>

<a name="zh-cn_topic_0191813892_table48896832"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813892_row17284754"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813892_p57887863"><a name="zh-cn_topic_0191813892_p57887863"></a><a name="zh-cn_topic_0191813892_p57887863"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813892_p58405349"><a name="zh-cn_topic_0191813892_p58405349"></a><a name="zh-cn_topic_0191813892_p58405349"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813892_row33212803"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813892_p5882489"><a name="zh-cn_topic_0191813892_p5882489"></a><a name="zh-cn_topic_0191813892_p5882489"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813892_p6719600"><a name="zh-cn_topic_0191813892_p6719600"></a><a name="zh-cn_topic_0191813892_p6719600"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813892_row60476403"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813892_p66750478"><a name="zh-cn_topic_0191813892_p66750478"></a><a name="zh-cn_topic_0191813892_p66750478"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813892_p38079613"><a name="zh-cn_topic_0191813892_p38079613"></a><a name="zh-cn_topic_0191813892_p38079613"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813892_row7172200"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813892_p44077297"><a name="zh-cn_topic_0191813892_p44077297"></a><a name="zh-cn_topic_0191813892_p44077297"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813892_p13491266"><a name="zh-cn_topic_0191813892_p13491266"></a><a name="zh-cn_topic_0191813892_p13491266"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813892_row54312533"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813892_p37239078"><a name="zh-cn_topic_0191813892_p37239078"></a><a name="zh-cn_topic_0191813892_p37239078"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813892_p63575380"><a name="zh-cn_topic_0191813892_p63575380"></a><a name="zh-cn_topic_0191813892_p63575380"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813892_section31084503"></a>

发生连接数告警时，表示连接到HiveServer的session数过多，将会导致无法建立新的连接。

## 可能原因<a name="zh-cn_topic_0191813892_section11325076"></a>

连接HiveServer的客户端过多。

## 处理步骤<a name="zh-cn_topic_0191813892_section34816825"></a>

1.  增加Hive最大连接数配置。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  选择“Hive \> 服务配置”，将“基础配置”切换为“全部配置”。
    3.  然后查找“hive.server.session.control.maxconnections”，调大该配置项的数值。设该配置项的值为A，阈值为B，连接到HiveServer的session数为C，调整策略为A x B \> C ，连接到HiveServer的session数可在Hive的监控界面查看。
    4.  查看本告警是否恢复。
        -   是，操作结束。
        -   否，执行[2](#zh-cn_topic_0191813892_li572522141314)。

2.  <a name="zh-cn_topic_0191813892_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813892_section44915976"></a>

无。

