# ALM-16005 Hive服务进程堆内存使用超出阈值<a name="ALM-16005"></a>

## 告警解释<a name="section34657480"></a>

系统每30秒周期性检测Hive堆内存使用率，并把实际的Hive堆内存使用率和阈值相比较。当Hive堆内存使用率超出阈值（默认为最大堆内存的95%）时产生该告警。

用户可通过“运维 \>告警 \> 阈值设置 \>  _待操作集群的名称_  \> Hive”修改阈值。

当Hive堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section43481872"></a>

<a name="table2570993"></a>
<table><thead align="left"><tr id="row62153267"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p1249828"><a name="p1249828"></a><a name="p1249828"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p34127238"><a name="p34127238"></a><a name="p34127238"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p12842880"><a name="p12842880"></a><a name="p12842880"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row33640379"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p40516191"><a name="p40516191"></a><a name="p40516191"></a>16005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p60586002"><a name="p60586002"></a><a name="p60586002"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p8519167"><a name="p8519167"></a><a name="p8519167"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section55792532"></a>

<a name="table18963916"></a>
<table><thead align="left"><tr id="row21786980"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p19914933"><a name="p19914933"></a><a name="p19914933"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p2496908"><a name="p2496908"></a><a name="p2496908"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1641869182520"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row922958"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p15734201"><a name="p15734201"></a><a name="p15734201"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row7390085"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33751272"><a name="p33751272"></a><a name="p33751272"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row35325999"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46975135"><a name="p46975135"></a><a name="p46975135"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row20123033"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p19352981"><a name="p19352981"></a><a name="p19352981"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24087625"><a name="p24087625"></a><a name="p24087625"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section32370740"></a>

Hive堆内存使用率过高，会影响Hive任务运行的性能，甚至造成内存溢出导致Hive服务不可用。

## 可能原因<a name="section22901211"></a>

该节点Hive实例堆内存使用量过大，或分配的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section4784313"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“16005”的告警，查看“定位信息”中的角色名并确定实例的IP地址。
    -   告警上报的角色是HiveServer，执行[2](#li30678316162827)。
    -   告警上报的角色是MetaStore，执行[3](#li19469054162827)。

2.  <a name="li30678316162827"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的HiveServer，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“HiveServer内存使用率统计”，单击“确定”，查看HiveServer进程使用的堆内存是否已达到HiveServer进程设定的最大堆内存的阈值（默认95%）。

    -   是，执行[4](#li41003766162827)。
    -   否，执行[7](#li62159379162827)。

    **图 1**  勾选HiveServer内存使用率统计<a name="fig159981629181710"></a>  
    ![](figures/勾选HiveServer内存使用率统计.png "勾选HiveServer内存使用率统计")

3.  <a name="li19469054162827"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的MetaStore，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“MetaStore内存使用率统计”，单击“确定”，查看MetaStore进程使用的堆内存是否已达到MetaStore进程设定的最大堆内存的阈值（默认95%）。

    -   是，执行[4](#li41003766162827)。
    -   否，执行[7](#li62159379162827)。

    **图 2**  勾选MetaStore内存使用率统计<a name="fig11061536182011"></a>  
    ![](figures/勾选MetaStore内存使用率统计.png "勾选MetaStore内存使用率统计")

4.  <a name="li41003766162827"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 配置”，选择“全部配置”，选择“HiveServer/MetaStore \> JVM”，将“HIVE\_GC\_OPTS/METASTORE\_GC\_OPTS”参数中“-Xmx”的值根据如下建议进行调整，并单击“保存”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >1.  HiveServer的GC参数配置建议
    >    -   当HiveServer进程使用的堆内存已达到HiveServer进程设定的堆内存的阈值时，将“-Xmx”值调整为默认值的2倍，比如：“-Xmx”默认设置为2G时，调整“-Xmx”的值为4G。在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Hive \> CPU和内存 \> HiveServer堆内存使用率统计 \(HiveServer\)”，可查看“阈值”。
    >    -   建议同时调节“-Xms”的值，使“-Xms”和“-Xmx”比值为1:2，这样可以避免JVM动态调整堆内存大小时影响性能。
    >2.  MetaServer的GC参数配置建议
    >    -   当MetaStore进程使用的堆内存已达到MetaStore进程设定的堆内存的阈值时，将“-Xmx”值调整为默认值的2倍，比如：“-Xmx”默认设置为2G时，调整“-Xmx”的值为4G。在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Hive \> CPU和内存 \> MetaStore堆内存使用率统计 \(MetaStore\)”，可查看“阈值”。
    >    -   建议同时调节“-Xms”的值，使“-Xms”和“-Xmx”比值为1:2，这样可以避免JVM动态调整堆内存大小时影响性能。

5.  选择“更多 \> 重启服务”重启服务。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li62159379162827)。


**收集故障信息。**

1.  <a name="li62159379162827"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section43058823"></a>

无。

