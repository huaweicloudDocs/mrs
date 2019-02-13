# ALM-18002 NodeManager心跳丢失<a name="ZH-CN_TOPIC_0093195063"></a>

## 告警解释<a name="zh-cn_topic_0035998737_section65004788"></a>

系统每30秒周期性检测丢失的NodeManager节点数，并把丢失的节点数和阈值相比较。“丢失的节点数”指标默认提供一个阈值范围。当检测到“丢失的节点数”的值超出阈值范围时产生该告警。

当“丢失的节点数”的值小于或等于阈值范围时，告警自动清除。

## 告警属性<a name="zh-cn_topic_0035998737_section48172185"></a>

<a name="zh-cn_topic_0035998737_table65488131"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998737_row18827362"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998737_p48621330"><a name="zh-cn_topic_0035998737_p48621330"></a><a name="zh-cn_topic_0035998737_p48621330"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998737_p46013667"><a name="zh-cn_topic_0035998737_p46013667"></a><a name="zh-cn_topic_0035998737_p46013667"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998737_p36119548"><a name="zh-cn_topic_0035998737_p36119548"></a><a name="zh-cn_topic_0035998737_p36119548"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998737_row40002310"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998737_p18961705"><a name="zh-cn_topic_0035998737_p18961705"></a><a name="zh-cn_topic_0035998737_p18961705"></a>18002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998737_p59503116"><a name="zh-cn_topic_0035998737_p59503116"></a><a name="zh-cn_topic_0035998737_p59503116"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998737_p55023063"><a name="zh-cn_topic_0035998737_p55023063"></a><a name="zh-cn_topic_0035998737_p55023063"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998737_section30896486"></a>

<a name="zh-cn_topic_0035998737_table27683123"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998737_row23047586"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998737_p54915211"><a name="zh-cn_topic_0035998737_p54915211"></a><a name="zh-cn_topic_0035998737_p54915211"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998737_p18947112"><a name="zh-cn_topic_0035998737_p18947112"></a><a name="zh-cn_topic_0035998737_p18947112"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998737_row58321122"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998737_p26390432"><a name="zh-cn_topic_0035998737_p26390432"></a><a name="zh-cn_topic_0035998737_p26390432"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998737_p57250251"><a name="zh-cn_topic_0035998737_p57250251"></a><a name="zh-cn_topic_0035998737_p57250251"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998737_row45490212"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998737_p60828573"><a name="zh-cn_topic_0035998737_p60828573"></a><a name="zh-cn_topic_0035998737_p60828573"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998737_p28167350"><a name="zh-cn_topic_0035998737_p28167350"></a><a name="zh-cn_topic_0035998737_p28167350"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998737_row52179558"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998737_p65794642"><a name="zh-cn_topic_0035998737_p65794642"></a><a name="zh-cn_topic_0035998737_p65794642"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998737_p27765811"><a name="zh-cn_topic_0035998737_p27765811"></a><a name="zh-cn_topic_0035998737_p27765811"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998737_row48565715"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998737_p41508862"><a name="zh-cn_topic_0035998737_p41508862"></a><a name="zh-cn_topic_0035998737_p41508862"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998737_p6774674"><a name="zh-cn_topic_0035998737_p6774674"></a><a name="zh-cn_topic_0035998737_p6774674"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998737_section9632925"></a>

-   丢失的NodeManager节点无法提供Yarn服务。
-   容器减少，集群性能下降。

## 可能原因<a name="zh-cn_topic_0035998737_section19587461"></a>

-   NodeManager没有经过退服操作，强制被删除。
-   NodeManager所有实例被停止或者进程故障。
-   NodeManager节点所在主机故障。
-   NodeManager和ResourceManager之间的网络断连或者繁忙。

## 处理步骤<a name="zh-cn_topic_0035998737_section42069424"></a>

请联系运维人员，并发送已收集的故障日志信息。

## 参考信息<a name="zh-cn_topic_0035998737_section43080504"></a>

无。

