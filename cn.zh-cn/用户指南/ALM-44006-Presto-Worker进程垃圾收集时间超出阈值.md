# ALM-44006 Presto Worker进程垃圾收集时间超出阈值<a name="alm_44006"></a>

## 告警解释<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section43920869"></a>

系统每30s周期性采集Presto Worker进程的垃圾收集（GC）时间，当检测到GC时间超出阈值（连续3次检测超过5s）时产生该告警。用户可在MRS Manager中通过“系统设置 \> 阈值配置 \> 服务 \> Presto \> Worker \> Presto进程GC时间 \> Worker进程GC时间”修改阈值。当 Worker进程GC时间小于或等于告警阈值时，告警清除。

## 告警属性<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section59743502"></a>

<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_table64843092"></a>
<table><thead align="left"><tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row10409628"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p37873528"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p37873528"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p37873528"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p47856888"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p47856888"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p47856888"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p51202692"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p51202692"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p51202692"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row53777413"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p61003235"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p61003235"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p61003235"></a>44006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p42315013"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p42315013"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p42315013"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p4964052"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p4964052"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p4964052"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section820607"></a>

<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_table66543927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row61284534"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p65100236"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p65100236"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p65100236"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p38627770"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p38627770"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p38627770"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row41841705"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p33734977"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p33734977"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p33734977"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p48178601"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p48178601"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p48178601"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row30954226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p24264406"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p24264406"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p24264406"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p19259870"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p19259870"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p19259870"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_row39121107"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p14693133"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p14693133"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p14693133"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p49293152"><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p49293152"></a><a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_p49293152"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section7385465"></a>

Worker进程GC时间过长，会影响Worker进程运行的性能，甚至造成Worker进程不可用。

## 可能原因<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section66469189"></a>

该节点Worker进程堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="zh-cn_topic_0225312713_section14111549283"></a>

1.  检查GC时间。
    1.  登录MRS集群详情页面，选择“告警管理”。
    2.  选中“告警ID”为“44006”的告警，查看“定位信息”中的实例的IP地址及角色名。
    3.  单击“组件管理 \> Presto \> 实例 \> Worker（对应上报告警实例IP地址） \> 定制 \> Presto进程GC时间“。单击“确定”，查看GC时间。
    4.  查看Worker进程的GC时间是否大于5秒。
        -   是，执行[1.e](#zh-cn_topic_0225312713_li3841416113916)。
        -   否，执行[2](#zh-cn_topic_0225312713_li572522141314)。

    5.  <a name="zh-cn_topic_0225312713_li3841416113916"></a>单击“组件管理 \> Presto \> 服务配置 \> 全部配置 \> Presto \> Worker“。将“JAVA\_OPTS”参数中的最大堆内存-Xmx值根据实际情况调大。
    6.  观察界面告警是否清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0225312713_li572522141314)。

2.  <a name="zh-cn_topic_0225312713_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0225312713_zh-cn_topic_0087039425_section15295265"></a>

无。

