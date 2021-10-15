# ALM-38006 Kafka未完全同步的Partition百分比超过阈值<a name="ALM-38006"></a>

## 告警解释<a name="section48693389"></a>

系统每60秒周期性检测Kafka服务未完全同步的Partition数占Partition总数的百分比，当连续3次检测到该比率超出阈值（默认50%）时产生该告警。

平滑次数为1，未完全同步的Partition百分比小于或等于阈值时，告警恢复；平滑次数大于1，未完全同步的Partition百分比小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section35587318"></a>

<a name="table3700505"></a>
<table><thead align="left"><tr id="row41936390"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41404449"><a name="p41404449"></a><a name="p41404449"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p65426085"><a name="p65426085"></a><a name="p65426085"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65021496"><a name="p65021496"></a><a name="p65021496"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row32249861"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p62101938"><a name="p62101938"></a><a name="p62101938"></a>38006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p64201063"><a name="p64201063"></a><a name="p64201063"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p32903629"><a name="p32903629"></a><a name="p32903629"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section51850411"></a>

<a name="table47948299"></a>
<table><thead align="left"><tr id="row43302596"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p17849403"><a name="p17849403"></a><a name="p17849403"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p36515567"><a name="p36515567"></a><a name="p36515567"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row637619451472"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row4970951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66614789"><a name="p66614789"></a><a name="p66614789"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row62662193"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17748959"><a name="p17748959"></a><a name="p17748959"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row25522907"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p54089623"><a name="p54089623"></a><a name="p54089623"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19183310"><a name="p19183310"></a><a name="p19183310"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64000515"></a>

Kafka服务未完全同步的Partition数过多，会影响服务的可靠性，一旦发生leader切换，可能会导致丢数据。

## 可能原因<a name="section39133729"></a>

部分Broker实例所在节点故障或者实例停止运行，导致Kafka中某些Partition的副本下线。

## 处理步骤<a name="section16659245"></a>

**检查Broker实例。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，进入Kafka实例页面。
2.  <a name="li33827117154518"></a>查看所有Broker实例中是否有故障的节点。
    -   是，记录当前节点主机名，并执行[3](#li55641967154518)。
    -   否，执行[5](#li50823531154518)。

3.  <a name="li55641967154518"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”。查看所有告警信息中是否有[2](#li33827117154518)中节点主机对应的故障告警，根据对应的告警指导进行处理。
4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，进入Kafka实例页面。
5.  <a name="li50823531154518"></a>查看所有Broker实例中是否有已停止的实例。
    -   是，执行[6](#li54758597154518)。
    -   否，执行[7](#li10197980154518)。

6.  <a name="li54758597154518"></a>勾选所有已停止的Broker实例，单击“启动实例”。
7.  <a name="li10197980154518"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li24672963154518)。


**收集故障信息。**

1.  <a name="li24672963154518"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section15715480"></a>

无。

