# ALM-38002 Kafka堆内存使用率超过阈值<a name="ALM-38002"></a>

## 告警解释<a name="section52907177"></a>

系统每60秒周期性检测Kafka服务堆内存使用状态，当连续10次检测到Kafka实例堆内存使用率超出阈值（最大内存的95%）时产生该告警。

平滑次数为1，堆内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，堆内存使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section6402551"></a>

<a name="table65570314"></a>
<table><thead align="left"><tr id="row5998931"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p16151423"><a name="p16151423"></a><a name="p16151423"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p33196920"><a name="p33196920"></a><a name="p33196920"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p4596005"><a name="p4596005"></a><a name="p4596005"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row36732143"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p22513597"><a name="p22513597"></a><a name="p22513597"></a>38002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p11662072"><a name="p11662072"></a><a name="p11662072"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5103751"><a name="p5103751"></a><a name="p5103751"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section57622960"></a>

<a name="table10750675"></a>
<table><thead align="left"><tr id="row33863614"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p58598200"><a name="p58598200"></a><a name="p58598200"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p48833779"><a name="p48833779"></a><a name="p48833779"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row148976614816"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row63222039"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p67018679"><a name="p67018679"></a><a name="p67018679"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row66297202"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43396391"><a name="p43396391"></a><a name="p43396391"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row55023199"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28632988"><a name="p28632988"></a><a name="p28632988"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row56370308"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2592198"><a name="p2592198"></a><a name="p2592198"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8641501"><a name="p8641501"></a><a name="p8641501"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section48844599"></a>

Kafka可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section36948212"></a>

该节点Kafka实例堆内存使用率过大，或配置的堆内存大小不合理，导致使用率超过阈值。

## 处理步骤<a name="section64098456"></a>

**检查Kafka实例堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Kafka堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  <a name="li3524099015552"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，选择上报告警实例主机名对应的角色。单击图表区域右上角的下拉菜单，选择“定制 \> 进程 \> Kafka堆内存使用率”，单击“确定”。

    **图 1**  Kafka堆内存使用率<a name="fig1665135323320"></a>  
    ![](figures/Kafka堆内存使用率.png "Kafka堆内存使用率")

3.  查看Kafka使用的堆内存是否已达到Kafka设定的最大堆内存的95%。
    -   是，执行[4](#li18239714202814)。
    -   否，执行[6](#li5709438115552)。


**检查Kafka配置的堆内存大小。**

1.  <a name="li18239714202814"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置 \> 全部配置 \> Broker（角色） \> 环境变量”。将“KAFKA\_HEAP\_OPTS”参数的值参考如下说明调大。

    **图 2**  KAFKA\_HEAP\_OPTS参数<a name="fig1373916397361"></a>  
    ![](figures/KAFKA_HEAP_OPTS参数.png "KAFKA_HEAP_OPTS参数")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   建议“KAFKA\_HEAP\_OPTS”参数中“-Xmx”和“-Xms”值保持一致。
    >-   建议根据[2](#li3524099015552)查看“Kafka堆内存使用率”，调整“KAFKA\_HEAP\_OPTS”的值为“Kafka使用的堆内存大小”的两倍（可根据实际业务场景进行修改）。

2.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li5709438115552)。


**收集故障信息。**

1.  <a name="li5709438115552"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40015196"></a>

无。

