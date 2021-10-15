# ALM-38004 Kafka直接内存使用率超过阈值<a name="ALM-38004"></a>

## 告警解释<a name="section56594331"></a>

系统每30秒周期性检测Kafka服务直接内存使用状态，当连续10次检测到Kafka实例直接内存使用率超出阈值（最大内存的80%）时，产生该告警。

平滑次数为1，直接内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，直接内存使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section39586939"></a>

<a name="table63482411"></a>
<table><thead align="left"><tr id="row54064365"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p17137444"><a name="p17137444"></a><a name="p17137444"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p45955715"><a name="p45955715"></a><a name="p45955715"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p31425459"><a name="p31425459"></a><a name="p31425459"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row62434268"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p24010917"><a name="p24010917"></a><a name="p24010917"></a>38004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65836086"><a name="p65836086"></a><a name="p65836086"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p31122744"><a name="p31122744"></a><a name="p31122744"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section20738133"></a>

<a name="table37914322"></a>
<table><thead align="left"><tr id="row51140217"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p48716908"><a name="p48716908"></a><a name="p48716908"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p53755484"><a name="p53755484"></a><a name="p53755484"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row13529200683"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row59226928"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p27554726"><a name="p27554726"></a><a name="p27554726"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row46665943"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24620926"><a name="p24620926"></a><a name="p24620926"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row20261744"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61756187"><a name="p61756187"></a><a name="p61756187"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row18934775"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p57321808"><a name="p57321808"></a><a name="p57321808"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p12554906"><a name="p12554906"></a><a name="p12554906"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section52425476"></a>

Kafka可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section2067240"></a>

该节点Kafka实例直接内存使用率过大，或配置的直接内存大小不合理，导致使用率超过阈值。

## 处理步骤<a name="section18605162"></a>

**检查Kafka实例直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Kafka直接内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  <a name="li11440902155229"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，选择上报告警实例主机名对应的角色。单击图表区域右上角的下拉菜单，选择“定制 \> 进程 \> Kafka直接内存使用率”，单击“确定”。

    **图 1**  Kafka直接内存使用率<a name="fig870614162815"></a>  
    ![](figures/Kafka直接内存使用率.png "Kafka直接内存使用率")

3.  查看Kafka使用的直接内存是否已达到Kafka设定的最大直接内存的80%。
    -   是，执行[4](#li184411445123817)。
    -   否，执行[7](#li15805504155229)。


**检查Kafka配置的直接内存大小。**

1.  <a name="li184411445123817"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置 \> 全部配置 \> Broker（角色）\> 环境变量”。将“KAFKA\_HEAP\_OPTS”参数中配置的“-Xmx”值参考如下说明调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   建议“KAFKA\_HEAP\_OPTS”参数中“-Xmx”和“-Xms”值保持一致。
    >-   建议根据[2](#li11440902155229)查看“Kafka直接内存使用率”，调整“KAFKA\_HEAP\_OPTS”的值为“Kafka使用的直接内存大小”的两倍（可根据实际业务场景进行修改）。

2.  保存配置，并重启Kafka服务。
3.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li15805504155229)。


**收集故障信息**

1.  <a name="li15805504155229"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section33228731"></a>

无。

