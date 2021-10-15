# ALM-16001 Hive数据仓库空间使用率超过阈值<a name="ALM-16001"></a>

## 告警解释<a name="section1124074214165"></a>

系统每30秒周期性检测Hive数据仓库空间使用率，该指标可在Hive服务监控界面查看，指标名称为“Hive已经使用的HDFS空间占可使用空间的百分比”。Hive数据仓库空间使用率指标默认提供一个阈值范围（85%），当检测到Hive数据仓库空间使用率超过阈值范围时产生该告警。

用户可通过“运维 \>告警 \>阈值设置 \>  _待操作集群的名称_  \> Hive \> Hive已经使用的HDFS空间占可使用空间的百分比”修改阈值。

平滑次数为1，Hive数据仓库空间使用率小于或等于阈值时，告警恢复；平滑次数大于1，Hive数据仓库空间使用率小于或等于阈值的90%时，告警恢复。

>![](public_sys-resources/icon-note.gif) **说明：** 
>管理员可通过增加仓库容量或释放部分已使用空间的方式降低仓库空间使用率。

## 告警属性<a name="section33170460141612"></a>

<a name="table65540716141619"></a>
<table><thead align="left"><tr id="row47315100141619"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p7317901141619"><a name="p7317901141619"></a><a name="p7317901141619"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p55879110141619"><a name="p55879110141619"></a><a name="p55879110141619"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p29914096141619"><a name="p29914096141619"></a><a name="p29914096141619"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row7122739141619"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p40070966141619"><a name="p40070966141619"></a><a name="p40070966141619"></a>16001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p24522785141619"><a name="p24522785141619"></a><a name="p24522785141619"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p40188573141619"><a name="p40188573141619"></a><a name="p40188573141619"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section24869609141624"></a>

<a name="table22314716141633"></a>
<table><thead align="left"><tr id="row46233113141633"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p53894705141633"><a name="p53894705141633"></a><a name="p53894705141633"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p3394969141633"><a name="p3394969141633"></a><a name="p3394969141633"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5964103122514"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row6557049141633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4020675141633"><a name="p4020675141633"></a><a name="p4020675141633"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row36186083141633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52840658141633"><a name="p52840658141633"></a><a name="p52840658141633"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row5803875141633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28498922141633"><a name="p28498922141633"></a><a name="p28498922141633"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row55163710141633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39075493141633"><a name="p39075493141633"></a><a name="p39075493141633"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10998385141633"><a name="p10998385141633"></a><a name="p10998385141633"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section39715981141639"></a>

系统可能无法正常写入数据，导致部分数据丢失。

## 可能原因<a name="section44359748141651"></a>

-   Hive使用HDFS容量上限过小。
-   HDFS空间不足。
-   部分数据节点瘫痪。

## 处理步骤<a name="section6321282614174"></a>

**扩展系统配置。**

1.  分析集群HDFS使用情况，增加HDFS分配给Hive使用的容量上限。

    登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 配置”，选择“全部配置”，然后查找“hive.metastore.warehouse.size.percent”，调大该配置项。设配置项的值为A，HDFS总存储空间为B，阈值为C，Hive已经使用HDFS的空间大小为D。调整策略为A x B x C \> D ，HDFS总存储空间可在HDFS NameNode页面查看，Hive已经使用HDFS的空间大小可在Hive的监控界面查看监控指标“Hive已经使用的HDFS空间大小”。

2.  检查该告警是否恢复。
    -   是，操作结束。
    -   否，执行[3](#li41192157155514)。


**对系统进行扩容。**

1.  <a name="li41192157155514"></a>对系统进行扩容。
2.  检查该告警是否恢复。
    -   是，操作结束。
    -   否，执行[5](#li58335386155514)。


**检查数据节点是否正常。**

1.  <a name="li58335386155514"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”。
2.  查看是否有“ALM-12006 节点故障”、“ALM-12007 进程故障”、“ALM-14002 DataNode磁盘空间使用率超过阈值”告警。
    -   是，执行[7](#li66048350155514)。
    -   否，执行[9](#li22392749155514)。

3.  <a name="li66048350155514"></a>分别参考“ALM-12006 节点故障”、“ALM-12007 进程故障”、“ALM-14002 DataNode磁盘空间使用率超过阈值”的处理步骤处理告警。
4.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[9](#li22392749155514)。


**收集故障信息。**

1.  <a name="li22392749155514"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section26229642141726"></a>

无。

