# ALM-38005 Broker进程垃圾回收（GC）时间超过阈值<a name="ALM-38005"></a>

## 告警解释<a name="section20231696"></a>

系统每60秒周期性检测Broker进程的垃圾回收（GC）占用时间，当连续3次检测到Broker进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。

平滑次数为1，垃圾回收（GC）时间小于或等于阈值时，告警恢复；平滑次数大于1，垃圾回收（GC）时间小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section47867540"></a>

<a name="table9347550"></a>
<table><thead align="left"><tr id="row4979446"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p681951"><a name="p681951"></a><a name="p681951"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p55238032"><a name="p55238032"></a><a name="p55238032"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p45095602"><a name="p45095602"></a><a name="p45095602"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row28865132"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56374375"><a name="p56374375"></a><a name="p56374375"></a>38005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p2921675"><a name="p2921675"></a><a name="p2921675"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p35329086"><a name="p35329086"></a><a name="p35329086"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section28154684"></a>

<a name="table43083755"></a>
<table><thead align="left"><tr id="row22744955"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p30402032"><a name="p30402032"></a><a name="p30402032"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p46645505"><a name="p46645505"></a><a name="p46645505"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row167685516714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row20189592"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58124657"><a name="p58124657"></a><a name="p58124657"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row53359872"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p54289578"><a name="p54289578"></a><a name="p54289578"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row18844162"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22021457"><a name="p22021457"></a><a name="p22021457"></a>产生告警的主机名称。</p>
</td>
</tr>
<tr id="row63975386"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14623749"><a name="p14623749"></a><a name="p14623749"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43673025"><a name="p43673025"></a><a name="p43673025"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section52065568"></a>

Broker进程的垃圾回收时间过长，可能影响该Broker进程正常提供服务。

## 可能原因<a name="section65936928"></a>

该节点Kafka实例进程的垃圾回收时间过长，或配置的直接内存大小不合理，导致进程GC频繁。

## 处理步骤<a name="section56561447"></a>

**检查Broker进程的垃圾回收（GC）时间**。

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Broker进程垃圾回收（GC）时间超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，选择上报告警实例主机名对应的角色 。单击图表区域右上角的下拉菜单，选择“定制 \> 进程 \> Broker垃圾回收（GC）时间”，单击“确定”。

    **图 1**  Broker垃圾回收（GC）时间<a name="fig958910442816"></a>  
    ![](figures/Broker垃圾回收（GC）时间.png "Broker垃圾回收（GC）时间")

3.  查看Broker每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li643265354316)。
    -   否，执行[7](#li37309391154856)。


**检查Kafka配置的直接内存大小。**

1.  <a name="li643265354316"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置 \> 全部配置 \> Broker（角色） \> 环境变量”。将“KAFKA\_HEAP\_OPTS”参数中配置的“-Xmx”值参考如下说明调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   建议“KAFKA\_HEAP\_OPTS”参数中“-Xmx”和“-Xms”值保持一致。
    >-   建议根据“Kafka直接内存资源状况”调整“KAFKA\_HEAP\_OPTS”的值为“Kafka使用的直接内存大小”的两倍（可根据实际业务场景进行修改）。“Kafka直接内存资源状况”可在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，选择上报告警实例主机名对应的角色。单击图表区域右上角的下拉菜单，选择“定制 \> 进程 \> Kafka直接内存资源状况”进行查看。

2.  保存配置，并重启Kafka服务。
3.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li37309391154856)。


**收集故障信息**

1.  <a name="li37309391154856"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section39290981"></a>

无。

