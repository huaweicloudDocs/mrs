# ALM-14000 HDFS服务不可用<a name="ALM-14000"></a>

## 告警解释<a name="section18794533"></a>

系统每60秒周期性检测NameService的服务状态，当检测到所有的NameService服务都异常时，就会认为HDFS服务不可用，此时产生该告警。

至少一个NameService服务正常后，系统认为HDFS服务恢复，告警清除。

## 告警属性<a name="section34933073"></a>

<a name="table52262125"></a>
<table><thead align="left"><tr id="row24697033"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p54302662"><a name="p54302662"></a><a name="p54302662"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p36439520"><a name="p36439520"></a><a name="p36439520"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65919998"><a name="p65919998"></a><a name="p65919998"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row37919625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p51590760"><a name="p51590760"></a><a name="p51590760"></a>14000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p18102020"><a name="p18102020"></a><a name="p18102020"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56977476"><a name="p56977476"></a><a name="p56977476"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section45962205"></a>

<a name="table51772816"></a>
<table><thead align="left"><tr id="row55869420"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p29129184"><a name="p29129184"></a><a name="p29129184"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10653667"><a name="p10653667"></a><a name="p10653667"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row136842296329"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row57640736"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22422626"><a name="p22422626"></a><a name="p22422626"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row477048"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p42904606"><a name="p42904606"></a><a name="p42904606"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row50597141"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p47406613"><a name="p47406613"></a><a name="p47406613"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section11006666"></a>

无法为基于HDFS服务的HBase和MapReduce等上层部件提供服务。用户无法读写文件。

## 可能原因<a name="section31951138"></a>

-   ZooKeeper服务异常。
-   所有NameService服务异常。

## 处理步骤<a name="section19124788"></a>

**检查ZooKeeper服务状态。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”页面，查看系统是否上报“ALM-13000 ZooKeeper服务不可用”告警。
    -   是，执行[2](#li43268947161840)。
    -   否，执行[4](#li32841804161840)。

2.  <a name="li43268947161840"></a>参考“ALM-13000 ZooKeeper服务不可用”对ZooKeeper服务状态异常进行处理，然后查看ZooKeeper服务的运行状态是否恢复为“良好”。
    -   是，执行[3](#li40737202161840)。
    -   否，执行[7](#li57092876161840)。

3.  <a name="li40737202161840"></a>在“运维 \> 告警”页面，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li32841804161840)。


**处理NameService服务异常告警。**

1.  <a name="li32841804161840"></a>在FusionInsight Manager首页，选择“运维 \> 告警”页面，查看是否有“ALM-14010 NameService服务异常”告警。
    -   是，执行[5](#li19543101161840)。
    -   否，执行[7](#li57092876161840)。

2.  <a name="li19543101161840"></a>按照“ALM-14010 NameService服务异常”的处理方法，依次对这些服务异常的NameService进行处理，然后查看是否消除各个NameService服务异常告警。
    -   是，执行[6](#li36169814161840)。
    -   否，执行[7](#li57092876161840)。

3.  <a name="li36169814161840"></a>在“运维 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li57092876161840)。


**收集故障信息。**

1.  <a name="li57092876161840"></a>在FusionInsight Manager首页，单击“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   ZooKeeper
    -   HDFS

3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section37905371"></a>

无。

