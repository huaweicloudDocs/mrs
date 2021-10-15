# ALM-18008 Yarn ResourceManager堆内存使用率超过阈值<a name="alm_18008"></a>

## 告警解释<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section1335609"></a>

系统每30秒周期性检测Yarn ResourceManager堆内存使用率，并把实际的Yarn ResourceManager堆内存使用率和阈值相比较。当Yarn ResourceManager堆内存使用率超出阈值（默认为最大堆内存的80%）时产生该告警。

用户可通过“系统设置 \> 阈值配置 \> 服务 \> Yarn”修改阈值。当Yarn ResourceManager堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section12020482"></a>

<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_table9634977"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row15805238"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5155867"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5155867"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5155867"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14972060"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14972060"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14972060"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4777379"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4777379"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4777379"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row51423381"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4544348"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4544348"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4544348"></a>18008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p32547936"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p32547936"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p32547936"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p19137160"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p19137160"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p19137160"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section41075474"></a>

<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_table6606141"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row49320909"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p35570664"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p35570664"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p35570664"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p62651540"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p62651540"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p62651540"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row41609976"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14964925"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14964925"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p14964925"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4199435"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4199435"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p4199435"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row37794916"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p41489361"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p41489361"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p41489361"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5195099"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5195099"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p5195099"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row46755894"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p29131061"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p29131061"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p29131061"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p10805765"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p10805765"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p10805765"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_row30143027"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p25666111"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p25666111"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p25666111"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p65689071"><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p65689071"></a><a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_p65689071"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section34134946"></a>

Yarn ResourceManager堆内存使用率过高，会影响Yarn任务提交和运行的性能，甚至造成内存溢出导致Yarn服务不可用。

## 可能原因<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section38779059"></a>

该节点Yarn ResourceManager实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section13467214"></a>

1.  检查堆内存使用率。
    1.  登录MRS集群详情页面，选择“告警管理”。
    2.  选中“告警ID”为“18008”的告警，查看“定位信息”中的实例的IP地址及角色名。
    3.  单击“组件管理 \> Yarn \> 实例 \> ResourceManager（对应上报告警实例IP地址） \> 定制 \> ResourceManager堆内存使用百分比统计“。查看堆内存使用情况。
    4.  查看ResourceManager使用的堆内存是否已达到ResourceManager进程设定的最大堆内存的80%。
        -   是，执行[1.e](#zh-cn_topic_0191813919_li1011493181634)。
        -   否，执行[2](#zh-cn_topic_0191813919_li572522141314)。

    5.  <a name="zh-cn_topic_0191813919_li1011493181634"></a>单击“组件管理 \> Yarn \> 服务配置 \> 全部配置 \> ResourceManager \> 系统“。将GC\_OPTS参数中-Xmx和-Xms的值根据实际情况调整，保证最小堆内存-Xms的值小于最大堆内存-Xmx的值，并单击“保存配置”，勾选“重新启动角色实例。”，单击“确定”进行重启。
    6.  观察界面告警是否清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813919_li572522141314)。

2.  <a name="zh-cn_topic_0191813919_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813919_zh-cn_topic_0087039423_section54096069"></a>

无。

