# ALM-18000 Yarn服务不可用<a name="ALM-18000"></a>

## 告警解释<a name="section31658481"></a>

告警模块按60秒周期检测Yarn服务状态。当检测到Yarn服务不可用时产生该告警。

Yarn服务恢复时，告警恢复。

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
<tbody><tr id="row11464937"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56244670"><a name="p56244670"></a><a name="p56244670"></a>18000</p>
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
<tbody><tr id="row17231203813208"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row18159061"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p23367171"><a name="p23367171"></a><a name="p23367171"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row8977951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49868946"><a name="p49868946"></a><a name="p49868946"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row46167336"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41593300"><a name="p41593300"></a><a name="p41593300"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section60692571"></a>

集群无法提供Yarn服务。用户无法执行新的application。已提交的application无法执行。

## 可能原因<a name="section9362234"></a>

-   ZooKeeper服务异常。
-   HDFS服务异常。
-   Yarn集群中没有主ResourceManager实例。
-   Yarn集群中的所有NodeManager节点异常。

## 处理步骤<a name="section17151243"></a>

**检查ZooKeeper服务状态。**

1.  在FusionInsight Manager的告警列表中，查看是否有告警“ALM-13000 ZooKeeper服务不可用”产生。
    -   是，执行[2](#li5826787919306)。
    -   否，执行[3](#li3111144119306)。

2.  <a name="li5826787919306"></a>参考“ALM-13000 ZooKeeper服务不可用”的处理步骤处理故障后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[3](#li3111144119306)。


**检查HDFS服务状态**。

1.  <a name="li3111144119306"></a>在FusionInsight Manager的告警列表中，查看是否有HDFS相关告警产生。
    -   是，执行[4](#li1629919219306)。
    -   否，执行[5](#li1247500119306)。

2.  <a name="li1629919219306"></a>选择“运维 \> 告警 \> 告警”，根据告警帮助处理HDFS相关告警后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li1247500119306)。


**检查Yarn集群中的ResourceManager状态。**

1.  <a name="li1247500119306"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \>服务 \> Yarn”。
2.  在“概览”中，检查Yarn集群中是否存在主ResourceManager实例。
    -   是，执行[7](#li3062815319306)。
    -   否，执行[10](#li5243240019306)。


**检查Yarn集群中的NodeManager节点状态。**

1.  <a name="li3062815319306"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例”。
2.  查看NodeManager的“运行状态”，检查是否有处于非健康状态的节点。
    -   是，执行[9](#li6547814519306)。
    -   否，执行[10](#li5243240019306)。

3.  <a name="li6547814519306"></a>按“ALM-18002 NodeManager心跳丢失”或“ALM-18003 NodeManager不健康”提供的步骤处理该故障，故障修复后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[10](#li5243240019306)。


**收集故障信息。**

1.  <a name="li5243240019306"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895663.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20143465"></a>

无。

