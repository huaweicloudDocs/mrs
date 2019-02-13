# ALM-18003 NodeManager不健康<a name="ZH-CN_TOPIC_0093195064"></a>

## 告警解释<a name="zh-cn_topic_0035998738_section53704644"></a>

系统每30秒周期性检测异常NodeManager节点数，并把异常节点数和阈值相比较。“非健康的节点数”指标默认提供一个阈值范围。当检测到“非健康的节点数”的值超出阈值范围时产生该告警。

当“非健康的节点数”的值小于或等于阈值范围时，告警自动清除。

## 告警属性<a name="zh-cn_topic_0035998738_section13579756"></a>

<a name="zh-cn_topic_0035998738_table8146160"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998738_row10966323"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998738_p15856984"><a name="zh-cn_topic_0035998738_p15856984"></a><a name="zh-cn_topic_0035998738_p15856984"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998738_p9347313"><a name="zh-cn_topic_0035998738_p9347313"></a><a name="zh-cn_topic_0035998738_p9347313"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998738_p18934887"><a name="zh-cn_topic_0035998738_p18934887"></a><a name="zh-cn_topic_0035998738_p18934887"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998738_row57330849"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998738_p13287175"><a name="zh-cn_topic_0035998738_p13287175"></a><a name="zh-cn_topic_0035998738_p13287175"></a>18003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998738_p2519427"><a name="zh-cn_topic_0035998738_p2519427"></a><a name="zh-cn_topic_0035998738_p2519427"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998738_p2747002"><a name="zh-cn_topic_0035998738_p2747002"></a><a name="zh-cn_topic_0035998738_p2747002"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998738_section55108945"></a>

<a name="zh-cn_topic_0035998738_table21180630"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998738_row54284994"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998738_p35008393"><a name="zh-cn_topic_0035998738_p35008393"></a><a name="zh-cn_topic_0035998738_p35008393"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998738_p17107576"><a name="zh-cn_topic_0035998738_p17107576"></a><a name="zh-cn_topic_0035998738_p17107576"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998738_row43536440"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998738_p36790769"><a name="zh-cn_topic_0035998738_p36790769"></a><a name="zh-cn_topic_0035998738_p36790769"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998738_p27262282"><a name="zh-cn_topic_0035998738_p27262282"></a><a name="zh-cn_topic_0035998738_p27262282"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998738_row44033946"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998738_p9979846"><a name="zh-cn_topic_0035998738_p9979846"></a><a name="zh-cn_topic_0035998738_p9979846"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998738_p3061223"><a name="zh-cn_topic_0035998738_p3061223"></a><a name="zh-cn_topic_0035998738_p3061223"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998738_row27551015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998738_p17039762"><a name="zh-cn_topic_0035998738_p17039762"></a><a name="zh-cn_topic_0035998738_p17039762"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998738_p38043494"><a name="zh-cn_topic_0035998738_p38043494"></a><a name="zh-cn_topic_0035998738_p38043494"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998738_row6847126"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998738_p17746329"><a name="zh-cn_topic_0035998738_p17746329"></a><a name="zh-cn_topic_0035998738_p17746329"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998738_p28166553"><a name="zh-cn_topic_0035998738_p28166553"></a><a name="zh-cn_topic_0035998738_p28166553"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998738_section26218460"></a>

-   故障的NodeManager节点无法提供Yarn服务。
-   容器减少，集群性能下降。

## 可能原因<a name="zh-cn_topic_0035998738_section34639550"></a>

-   NodeManager节点所在主机的硬盘空间不足。
-   NodeManager节点本地目录**omm**用户无访问权限。

## 处理步骤<a name="zh-cn_topic_0035998738_section43320496"></a>

请联系运维人员，并发送已收集的故障日志信息。

## 参考信息<a name="zh-cn_topic_0035998738_section54340147"></a>

无。

