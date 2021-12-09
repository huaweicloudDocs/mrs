# ALM-18021 Mapreduce服务不可用<a name="ALM-18021"></a>

## 告警解释<a name="section31658481"></a>

告警模块按60秒周期检测Mapreduce服务状态。当检测到Mapreduce服务不可用时产生该告警。

Mapreduce服务恢复时，告警恢复。

## 告警属性<a name="section16490876"></a>

<a name="table57735442"></a>
<table><thead align="left"><tr id="row3620625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p24835204"><a name="p24835204"></a><a name="p24835204"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p65494516"><a name="p65494516"></a><a name="p65494516"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p3455560"><a name="p3455560"></a><a name="p3455560"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row11464937"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56244670"><a name="p56244670"></a><a name="p56244670"></a>18021</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p59524399"><a name="p59524399"></a><a name="p59524399"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56747046"><a name="p56747046"></a><a name="p56747046"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section14200159"></a>

<a name="table33107976"></a>
<table><thead align="left"><tr id="row44598351"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p55696680"><a name="p55696680"></a><a name="p55696680"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p15137266"><a name="p15137266"></a><a name="p15137266"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row9934113891815"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row18159061"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p23367171"><a name="p23367171"></a><a name="p23367171"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row8977951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49868946"><a name="p49868946"></a><a name="p49868946"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row46167336"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41593300"><a name="p41593300"></a><a name="p41593300"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section60692571"></a>

集群无法提供Mapreduce服务，如无法通过Mapreduce查看任务日志，无法提供Mapreduce服务的日志归档功能等。

## 可能原因<a name="section9362234"></a>

-   JobHistoryServer实例异常。
-   KrbServer服务异常。
-   ZooKeeper服务异常。
-   HDFS服务异常。
-   Yarn服务异常。

## 处理步骤<a name="section17151243"></a>

**检查Mapreduce服务JobHistoryServer实例状态。**

1.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Mapreduce \> 实例”。
2.  查看**JobHistoryServer**的“运行状态”，检查**JobHistoryServer**是否处于良好状态。
    -   是，执行[11](#li5243240019306)。
    -   否，执行[3](#li3741775112334)。


**检查KrbServer服务状态。**

1.  <a name="li3741775112334"></a>在FusionInsight Manager的告警列表中，查看是否有“ALM-25500 KrbServer服务不可用”告警产生。
    -   是，执行[4](#li55051145112334)。
    -   否，执行[5](#li3940579417196)。

2.  <a name="li55051145112334"></a>参考“ALM-25500 KrbServer服务不可用”的处理步骤处理故障后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li3940579417196)。


**检查Zookeeper服务状态。**

1.  <a name="li3940579417196"></a>在FusionInsight Manager的告警列表中，查看是否有“ALM-13000 ZooKeeper服务不可用”告警产生。
    -   是，执行[6](#li6414570217196)。
    -   否，执行[7](#li59686491171917)。

2.  <a name="li6414570217196"></a>参考“ALM-13000 ZooKeeper服务不可用”的处理步骤处理故障后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li59686491171917)。


**检查HDFS服务状态。**

1.  <a name="li59686491171917"></a>在FusionInsight Manager的告警列表中，查看是否有“ALM-14000 HDFS服务不可用”告警产生。
    -   是，执行[8](#li38829410171917)。
    -   否，执行[9](#li1247500119306)。

2.  <a name="li38829410171917"></a>参考“ALM-14000 HDFS服务不可用”的处理步骤处理故障后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[9](#li1247500119306)。


**检查Yarn服务状态。**

1.  <a name="li1247500119306"></a>在FusionInsight Manager的告警列表中，查看是否有“ALM-18000 Yarn服务不可用”告警产生。
    -   是，执行[10](#li4814237019306)。
    -   否，执行[11](#li5243240019306)。

2.  <a name="li4814237019306"></a>参考“ALM-18000 Yarn服务不可用”的处理步骤处理故障后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li5243240019306)。


**收集故障信息。**

1.  <a name="li5243240019306"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Mapreduce”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20143465"></a>

无。

