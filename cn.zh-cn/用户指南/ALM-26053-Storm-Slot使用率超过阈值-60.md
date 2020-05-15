# ALM-26053 Storm Slot使用率超过阈值<a name="ZH-CN_TOPIC_0174499378"></a>

## 告警解释<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section32908243175620"></a>

系统每60秒周期性检测Slot使用率，并把实际Slot使用率和阈值相比较。当检测到Slot使用率高于阈值时产生该告警。

用户可通过“系统设置 \> 阈值配置“修改阈值。

当Slot使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section21771461175620"></a>

<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_table18657878175620"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row25584845175620"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p59106577175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p59106577175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p59106577175620"></a><strong id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b62197145175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b62197145175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b62197145175620"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4803980175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4803980175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4803980175620"></a><strong id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b43235825175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b43235825175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b43235825175620"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p12440926175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p12440926175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p12440926175620"></a><strong id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b44859472175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b44859472175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b44859472175620"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row9738609175620"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p420326841881"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p420326841881"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p420326841881"></a>26053</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p492042251881"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p492042251881"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p492042251881"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p261193031881"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p261193031881"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p261193031881"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section8062366175620"></a>

<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_table49071894175620"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row19751123175620"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p56337144175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p56337144175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p56337144175620"></a><strong id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b37272250175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b37272250175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b37272250175620"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p66262301175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p66262301175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p66262301175620"></a><strong id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b59489799175620"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b59489799175620"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_b59489799175620"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row53944385175620"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p1213631718815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p1213631718815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p1213631718815"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4351758218815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4351758218815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4351758218815"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row39776827175620"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4893377818815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4893377818815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p4893377818815"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p421312018815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p421312018815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p421312018815"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row38777247175620"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p5146605718815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p5146605718815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p5146605718815"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p800105218815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p800105218815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p800105218815"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_row5746391418810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p6140530018815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p6140530018815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p6140530018815"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p777338418815"><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p777338418815"></a><a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_p777338418815"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section3251753175620"></a>

用户无法执行新的Storm任务。

## 可能原因<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section21717983175620"></a>

-   集群中Supervisor处于异常状态。
-   集群中Supervisor的状态正常，但是处理能力不足。

## 处理步骤<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section7979165175620"></a>

1.  检查Supervisor状态。
    1.  选择“服务管理 \> Storm \> Supervisor“，进入Storm服务管理页面。
    2.  查看“角色”中是否存在状态为故障或者是恢复中的Supervisor实例。
        -   是，执行[1.c](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li6671657118374)。
        -   否，执行[2.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li25471780183642)或者[3.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li22838295183633)。

    3.  <a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_li6671657118374"></a>勾选状态为“故障“或者“恢复中“的Supervisor角色实例，选择“更多 \> 重启实例“，查看是否重启成功。
        -   是，执行[1.d](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li5198268318374)。
        -   否，执行[4.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li7366709183627)。

    4.  <a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_li5198268318374"></a>等待一段时间，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li25471780183642)或者[3.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li22838295183633)。

2.  增加Supervisor Slot数量配置。
    1.  <a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_li25471780183642"></a>登录MRS Manager管理界面，选择“服务管理 \> Storm \> Supervisor \> 服务配置 \> 参数类别 \> 全部配置“。
    2.  调整“supervisor.slots.ports“的数值，适当增加每个Supervisor上Slot的数量，并重启实例。
    3.  等待一段时间，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li7366709183627)。

3.  对Supervisor进行扩容。
    1.  <a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_li22838295183633"></a>添加节点。
    2.  等待一段时间，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0093195077_zh-cn_topic_0053790967_li7366709183627)。

4.  收集故障信息。
    1.  <a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_li7366709183627"></a>在MRS Manager界面，单击“系统设置 \> 日志导出“。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195077_zh-cn_topic_0053790967_section42067024175620"></a>

无。

