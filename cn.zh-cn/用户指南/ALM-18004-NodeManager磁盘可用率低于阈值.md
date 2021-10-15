# ALM-18004 NodeManager磁盘可用率低于阈值<a name="alm_18004"></a>

## 告警解释<a name="zh-cn_topic_0191813913_section53704644"></a>

系统每30秒周期性检测NodeManager各个节点的可用磁盘空间，并把磁盘可用率和阈值相比较。“NodeManager磁盘可用率”指标默认提供一个阈值范围。当检测到实际“NodeManager磁盘可用率”的值低于阈值范围时产生该告警。

当实际“NodeManager磁盘可用率”的值大于阈值范围时，告警自动清除。

## 告警属性<a name="zh-cn_topic_0191813913_section13579756"></a>

<a name="zh-cn_topic_0191813913_table8146160"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813913_row10966323"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813913_p15856984"><a name="zh-cn_topic_0191813913_p15856984"></a><a name="zh-cn_topic_0191813913_p15856984"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813913_p9347313"><a name="zh-cn_topic_0191813913_p9347313"></a><a name="zh-cn_topic_0191813913_p9347313"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813913_p18934887"><a name="zh-cn_topic_0191813913_p18934887"></a><a name="zh-cn_topic_0191813913_p18934887"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813913_row57330849"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813913_p13287175"><a name="zh-cn_topic_0191813913_p13287175"></a><a name="zh-cn_topic_0191813913_p13287175"></a>18004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813913_p2519427"><a name="zh-cn_topic_0191813913_p2519427"></a><a name="zh-cn_topic_0191813913_p2519427"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813913_p2747002"><a name="zh-cn_topic_0191813913_p2747002"></a><a name="zh-cn_topic_0191813913_p2747002"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813913_section55108945"></a>

<a name="zh-cn_topic_0191813913_table21180630"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813913_row54284994"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813913_p35008393"><a name="zh-cn_topic_0191813913_p35008393"></a><a name="zh-cn_topic_0191813913_p35008393"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813913_p17107576"><a name="zh-cn_topic_0191813913_p17107576"></a><a name="zh-cn_topic_0191813913_p17107576"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813913_row43536440"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813913_p36790769"><a name="zh-cn_topic_0191813913_p36790769"></a><a name="zh-cn_topic_0191813913_p36790769"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813913_p27262282"><a name="zh-cn_topic_0191813913_p27262282"></a><a name="zh-cn_topic_0191813913_p27262282"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813913_row44033946"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813913_p9979846"><a name="zh-cn_topic_0191813913_p9979846"></a><a name="zh-cn_topic_0191813913_p9979846"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813913_p3061223"><a name="zh-cn_topic_0191813913_p3061223"></a><a name="zh-cn_topic_0191813913_p3061223"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813913_row27551015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813913_p17039762"><a name="zh-cn_topic_0191813913_p17039762"></a><a name="zh-cn_topic_0191813913_p17039762"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813913_p38043494"><a name="zh-cn_topic_0191813913_p38043494"></a><a name="zh-cn_topic_0191813913_p38043494"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813913_row6847126"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813913_p17746329"><a name="zh-cn_topic_0191813913_p17746329"></a><a name="zh-cn_topic_0191813913_p17746329"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813913_p28166553"><a name="zh-cn_topic_0191813913_p28166553"></a><a name="zh-cn_topic_0191813913_p28166553"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813913_section26218460"></a>

-   磁盘可用率低于阈值的NodeManager节点可能无法提供Yarn服务。
-   容器减少，集群性能可能下降。

## 可能原因<a name="zh-cn_topic_0191813913_section34639550"></a>

-   NodeManager节点所在主机的硬盘空间不足。
-   NodeManager节点本地目录**omm**用户无访问权限。

## 处理步骤<a name="zh-cn_topic_0191813913_section43320496"></a>

1.  收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813913_section54340147"></a>

无。

