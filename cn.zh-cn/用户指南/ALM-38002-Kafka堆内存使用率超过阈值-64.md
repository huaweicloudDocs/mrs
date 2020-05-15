# ALM-38002 Kafka堆内存使用率超过阈值<a name="ZH-CN_TOPIC_0174499382"></a>

## 告警解释<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section52353819175629"></a>

系统每30秒周期性检测Kafka服务堆内存使用状态，当检测到Kafka实例堆内存使用率超出阈值（最大内存的80%）时产生该告警。

堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section30241955175629"></a>

<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_table33679253175629"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row65360264175629"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p59690045175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p59690045175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p59690045175629"></a><strong id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b339495175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b339495175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b339495175629"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p27499162175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p27499162175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p27499162175629"></a><strong id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b46165868175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b46165868175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b46165868175629"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p48447798175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p48447798175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p48447798175629"></a><strong id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b33377000175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b33377000175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b33377000175629"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row19182484175629"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4847978518153"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4847978518153"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4847978518153"></a>38002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p3454851718153"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p3454851718153"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p3454851718153"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4696648918153"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4696648918153"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p4696648918153"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section2896740175629"></a>

<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_table33309393175629"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row59803701175629"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p12261637175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p12261637175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p12261637175629"></a><strong id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b43245875175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b43245875175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b43245875175629"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p13254975175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p13254975175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p13254975175629"></a><strong id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b52185911175629"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b52185911175629"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_b52185911175629"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row66309224175629"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p10028037181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p10028037181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p10028037181514"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p6964689181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p6964689181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p6964689181514"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row26722922175629"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p44094143181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p44094143181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p44094143181514"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p14855797181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p14855797181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p14855797181514"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row31138966175629"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p25349263181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p25349263181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p25349263181514"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p40024426181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p40024426181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p40024426181514"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_row945715918157"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p52559716181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p52559716181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p52559716181514"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p29478573181514"><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p29478573181514"></a><a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_p29478573181514"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section9094994175629"></a>

Kafka可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section53582251175629"></a>

该节点Kafka实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section32561289175629"></a>

1.  检查堆内存使用率。
    1.  在MRS Manager首页，单击“告警管理 \> ALM-38002 Kafka堆内存使用率超过阈值 \> 定位信息“。查看告警上报的实例的IP地址。
    2.  在MRS Manager首页，单击“服务管理 \> Kafka \> 实例 \> Broker（对应上报告警实例IP地址） \> 定制 \> Kafka堆内存资源状况“。查看堆内存使用情况。
    3.  查看Kafka使用的堆内存是否已达到Kafka设定的最大堆内存的80%。
        -   是，执行[1.d](#zh-cn_topic_0093195081_zh-cn_topic_0053790971_li1011493181634)。
        -   否，执行[2](#zh-cn_topic_0093195081_zh-cn_topic_0053790971_li40881691175629)。

    4.  <a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_li1011493181634"></a>在MRS Manager首页，单击“服务管理 \> Kafka \> 服务配置 \> 全部配置 \> Broker \> 环境变量“。将“KAFKA\_HEAP\_OPTS“参数的值根据实际情况调大。
    5.  观察界面告警是否清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0093195081_zh-cn_topic_0053790971_li40881691175629)。

2.  <a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_li40881691175629"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出“。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195081_zh-cn_topic_0053790971_section51615207175629"></a>

无。

