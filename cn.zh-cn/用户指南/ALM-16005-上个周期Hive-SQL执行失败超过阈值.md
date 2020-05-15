# ALM-16005 上个周期Hive SQL执行失败超过阈值<a name="ZH-CN_TOPIC_0226470318"></a>

## 告警解释<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section43920869"></a>

上个10min的周期内，Hive SQL执行失败数超过阈值。该告警每10min钟检测一次，如果上个10min周期内，发生Hive SQL执行失败数大于设定的阈值时候，会发生该告警。在下个10min周期，如果运行失败的Hive SQL执行失败数低于阈值时该告警会自动消除。

## 告警属性<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section59743502"></a>

<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_table64843092"></a>
<table><thead align="left"><tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row10409628"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p37873528"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p37873528"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p37873528"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p47856888"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p47856888"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p47856888"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p51202692"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p51202692"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p51202692"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row53777413"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0225531116_p431016914314"><a name="zh-cn_topic_0225531116_p431016914314"></a><a name="zh-cn_topic_0225531116_p431016914314"></a>16005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0225531116_p73091983110"><a name="zh-cn_topic_0225531116_p73091983110"></a><a name="zh-cn_topic_0225531116_p73091983110"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0225531116_p2308169103111"><a name="zh-cn_topic_0225531116_p2308169103111"></a><a name="zh-cn_topic_0225531116_p2308169103111"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section820607"></a>

<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_table66543927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row61284534"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p65100236"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p65100236"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p65100236"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p38627770"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p38627770"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p38627770"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row41841705"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225531116_p108042015539"><a name="zh-cn_topic_0225531116_p108042015539"></a><a name="zh-cn_topic_0225531116_p108042015539"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225531116_p1042201717316"><a name="zh-cn_topic_0225531116_p1042201717316"></a><a name="zh-cn_topic_0225531116_p1042201717316"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row30954226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p24264406"><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p24264406"></a><a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_p24264406"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225531116_p8405174319"><a name="zh-cn_topic_0225531116_p8405174319"></a><a name="zh-cn_topic_0225531116_p8405174319"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0225531116_zh-cn_topic_0087039425_row39121107"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225531116_p439111716311"><a name="zh-cn_topic_0225531116_p439111716311"></a><a name="zh-cn_topic_0225531116_p439111716311"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225531116_p4388177317"><a name="zh-cn_topic_0225531116_p4388177317"></a><a name="zh-cn_topic_0225531116_p4388177317"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section7385465"></a>

无。

## 可能原因<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section66469189"></a>

Hive SQL语法有问题，导致Hive SQL执行失败。

## 处理步骤<a name="zh-cn_topic_0225531116_section14111549283"></a>

查看运行失败的Hive SQL，修改为正确语法后再执行。

## 参考信息<a name="zh-cn_topic_0225531116_zh-cn_topic_0087039425_section15295265"></a>

无。

