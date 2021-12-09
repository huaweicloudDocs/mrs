# ALM-16008 Hive服务进程非堆内存使用超出阈值<a name="ALM-16008"></a>

## 告警解释<a name="section6164578"></a>

系统每30秒周期性检测Hive非堆内存使用率，并把实际的Hive非堆内存使用率和阈值相比较。当Hive非堆内存使用率超出阈值（默认为最大非堆内存的95%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Hive”修改阈值。

当Hive非堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section55481207"></a>

<a name="table53284255"></a>
<table><thead align="left"><tr id="row47341147"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p9427704"><a name="p9427704"></a><a name="p9427704"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p25446578"><a name="p25446578"></a><a name="p25446578"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p47906928"><a name="p47906928"></a><a name="p47906928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55255963"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46547994"><a name="p46547994"></a><a name="p46547994"></a>16008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p12291158"><a name="p12291158"></a><a name="p12291158"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56059702"><a name="p56059702"></a><a name="p56059702"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section29568819"></a>

<a name="table44541986"></a>
<table><thead align="left"><tr id="row29181518"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p14892770"><a name="p14892770"></a><a name="p14892770"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p65463685"><a name="p65463685"></a><a name="p65463685"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row124763972413"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row958306"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46323684"><a name="p46323684"></a><a name="p46323684"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row14259978"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p9959664"><a name="p9959664"></a><a name="p9959664"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row22528119"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33276087"><a name="p33276087"></a><a name="p33276087"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row31049328"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p31967668"><a name="p31967668"></a><a name="p31967668"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39244316"><a name="p39244316"></a><a name="p39244316"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64792783"></a>

Hive非堆内存使用率过高，会影响Hive任务运行的性能，甚至造成内存溢出导致Hive服务不可用。

## 可能原因<a name="section46264140"></a>

该节点Hive实例非堆内存使用量过大，或分配的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section13724084"></a>

**检查非堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“16008”的告警，查看“定位信息”中的角色名并确定实例的IP地址。
    -   告警上报的角色是HiveServer，执行[2](#li41149921164010)。
    -   告警上报的角色是MetaStore，执行[3](#li57005192164010)。

2.  <a name="li41149921164010"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的HiveServer，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“HiveServer内存使用率统计” ，单击“确定”，查看HiveServer进程使用的非堆内存是否已达到HiveServer进程设定的最大非堆内存的阈值（默认95%）。

    -   是，执行[4](#li43284681164010)。
    -   否，执行[7](#li55270386164010)。

    **图 1**  勾选HiveServer内存使用率统计<a name="fig159981629181710"></a>  
    ![](figures/勾选HiveServer内存使用率统计-85.png "勾选HiveServer内存使用率统计-85")

3.  <a name="li57005192164010"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的MetaStore，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“MetaStore内存使用率统计” ，单击“确定”，查看MetaStore进程使用的非堆内存是否已达到MetaStore进程设定的最大非堆内存的阈值（默认95%）。

    -   是，执行[4](#li43284681164010)。
    -   否，执行[7](#li55270386164010)。

    **图 2**  勾选MetaStore内存使用率统计<a name="fig11061536182011"></a>  
    ![](figures/勾选MetaStore内存使用率统计-86.png "勾选MetaStore内存使用率统计-86")

4.  <a name="li43284681164010"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 配置”，选择“全部配置”， 选择“HiveServer/MetaStore \> JVM”，将“HIVE\_GC\_OPTS/METASTORE\_GC\_OPTS”参数中“-XX:MaxMetaspaceSize”的值根据如下建议进行调整，并单击“保存”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >1.  HiveServer的GC参数配置建议
    >    -   建议将“-XX:MaxMetaspaceSize”值设置成为“-Xmx”大小的1/8，比如：“-Xmx”设置为2G时，“-XX:MaxMetaspaceSize”设置为256M；“-Xmx”设置为4G时，“-XX:MaxMetaspaceSize”设置为512M。
    >2.  MetaServer的GC参数配置建议
    >    -   建议将“-XX:MaxMetaspaceSize”值设置成为“-Xmx”大小的1/8，比如：“-Xmx”设置为2G时，“-XX:MaxMetaspaceSize”设置为256M；“-Xmx”设置为4G时，“-XX:MaxMetaspaceSize”设置为512M。

5.  选择“更多 \> 重启服务”重启服务。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li55270386164010)。


**收集故障信息。**

1.  <a name="li55270386164010"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

