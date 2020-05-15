# ALM-44004 Presto Coordinator资源组排队任务超过阈值<a name="ZH-CN_TOPIC_0226470315"></a>

## 告警解释<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section43920869"></a>

系统通过jmx接口查询资源组的排队任务数即QueuedQueries指标，当检测到资源组排队数大于阈值时产生该告警。用户可通过"组件管理 \> Presto \> 服务配置（将“基础配置”切换为“全部配置”） \>Presto \> resource-groups " 配置资源组。用户可通过"组件管理 \> Presto \> 服务配置（将“基础配置”切换为“全部配置”） \> Coordinator \> 自定义 \> resourceGroupAlarm " 配置每个资源组的阈值。

## 告警属性<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section59743502"></a>

<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_table64843092"></a>
<table><thead align="left"><tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row10409628"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p37873528"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p37873528"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p37873528"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p47856888"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p47856888"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p47856888"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p51202692"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p51202692"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p51202692"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row53777413"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p61003235"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p61003235"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p61003235"></a>44004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p42315013"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p42315013"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p42315013"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p4964052"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p4964052"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p4964052"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section820607"></a>

<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_table66543927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row61284534"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p65100236"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p65100236"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p65100236"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p38627770"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p38627770"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p38627770"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row41841705"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p33734977"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p33734977"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p33734977"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p48178601"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p48178601"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p48178601"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row30954226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p24264406"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p24264406"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p24264406"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p19259870"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p19259870"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p19259870"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_row39121107"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p14693133"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p14693133"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p14693133"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p49293152"><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p49293152"></a><a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_p49293152"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section7385465"></a>

资源组排队超过阈值可能导致大量任务处于排队状态，presto任务时间超过预期，当资源组排队数超过该组最大排队数（maxQueued）时，会导致新的任务无法执行。

## 可能原因<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section66469189"></a>

资源组配置不合理或该资源组下提交的任务过多。

## 处理步骤<a name="zh-cn_topic_0226447372_section14111549283"></a>

1.  用户可通过“组件管理 \> Presto \> 服务配置（将“基础配置”切换为“全部配置”） \>Presto \> resource-groups”调整资源组的配置。
2.  用户可通过“组件管理 \> Presto \> 服务配置（将“基础配置”切换为“全部配置”） \> Coordinator \> 自定义 \> resourceGroupAlarm”修改每个资源组的阈值。
3.  收集故障信息。
    1.  根据故障信息中的HostName登录到集群节点，在presto客户端根据附加信息中的Reource Group查询排队数。
    2.  根据故障信息中的HostName登录到集群节点，查看/var/log/Bigdata/nodeagent/monitorlog/monitor.log日志，搜索Resource group info可看到资源组监控采集信息。
    3.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0226447372_zh-cn_topic_0087039425_section15295265"></a>

无。

