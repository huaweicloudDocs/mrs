# ALM-19008 HBase服务进程堆内存使用率超出阈值<a name="ALM-19008"></a>

## 告警解释<a name="section49289361"></a>

系统每30秒周期性检测HBase服务堆内存使用状态，当检测到HBase服务堆内存使用率超出阈值（最大内存的90%）时产生该告警。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如HBase1服务不可用，则“定位信息”中显示服务名=HBase1，处理步骤中的操作对象也应由HBase调整为HBase1。

## 告警属性<a name="section40951072"></a>

<a name="table23329828"></a>
<table><thead align="left"><tr id="row64939285"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p25590737"><a name="p25590737"></a><a name="p25590737"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p59583813"><a name="p59583813"></a><a name="p59583813"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p61559578"><a name="p61559578"></a><a name="p61559578"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row20269944"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31252742"><a name="p31252742"></a><a name="p31252742"></a>19008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p48444140"><a name="p48444140"></a><a name="p48444140"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p31661267"><a name="p31661267"></a><a name="p31661267"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section33015336"></a>

<a name="table14425826"></a>
<table><thead align="left"><tr id="row17835892"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35421108"><a name="p35421108"></a><a name="p35421108"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p50537472"><a name="p50537472"></a><a name="p50537472"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row449435012173"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row67003457"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46628545"><a name="p46628545"></a><a name="p46628545"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row17003728"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26527760"><a name="p26527760"></a><a name="p26527760"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row37423251"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49726952"><a name="p49726952"></a><a name="p49726952"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section28702568"></a>

HBase可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section56996522"></a>

该节点HBase服务堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section43206656"></a>

**检查堆内存使用率**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“19008”的告警，查看“定位信息”中的角色名并确定实例的IP地址。
    -   告警上报的角色是HMaster，执行[2](#li4357781993318)。
    -   告警上报的角色是RegionServer，执行[3](#li3920218493318)。

2.  <a name="li4357781993318"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase \> 实例”，单击告警上报的HMaster，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存 \> HMaster堆内存使用率与直接内存使用率统计”，单击“确定”，查看HBase服务进程使用的堆内存是否已达到HBase服务进程设定的最大堆内存的90%。

    -   是，执行[4](#li1727533893318)。
    -   否，执行[6](#li2192412893318)。

    **图 1**  HMaster堆内存使用率与直接内存使用率统计<a name="fig525654414235"></a>  
    ![](figures/HMaster堆内存使用率与直接内存使用率统计.png "HMaster堆内存使用率与直接内存使用率统计")

3.  <a name="li3920218493318"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase \> 实例”，单击告警上报的RegionServer，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存 \> RegionServer堆内存使用率与直接内存使用率统计”，单击“确定”，查看HBase服务进程使用的堆内存是否已达到HBase服务进程设定的最大堆内存的90%。

    -   是，执行[4](#li1727533893318)。
    -   否，执行[6](#li2192412893318)。

    **图 2**  RegionServer堆内存使用率与直接内存使用率统计<a name="fig04211109245"></a>  
    ![](figures/RegionServer堆内存使用率与直接内存使用率统计.png "RegionServer堆内存使用率与直接内存使用率统计")

4.  <a name="li1727533893318"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase \> 配置”，单击“全部配置”， 选择“HMaster/RegionServer \> 系统”，将“GC\_OPTS”参数中“-Xmx”的值参考以下说明进行调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >1.  HMaster的GC参数配置建议
    >    -   建议“-Xms”和“-Xmx”设置成相同的值，这样可以避免JVM动态调整堆内存大小时影响性能。
    >    -   调整“-XX:NewSize”大小的时候，建议把其设置成和“-XX:MaxNewSize”相同，均为“-Xmx”大小的1/8。
    >    -   当HBase集群规模越大、Region数量越多时，可以适当调大HMaster的GC\_OPTS参数，配置建议如下：Region总数小于10万个，“-Xmx”设置为4G；超过10万个，“-Xmx”设置为不小于6G；超过10万时，每增加35000个Region，增加2G的“-Xmx”，整体的“-Xmx”的大小不超过32G。
    >2.  RegionServer的GC参数配置建议
    >    -   建议“-Xms”和“-Xmx”设置成相同的值，这样可以避免JVM动态调整堆内存大小时影响性能。
    >    -   调整“-XX:NewSize”大小的时候，建议把其设置为“-Xmx”大小的1/8。
    >    -   RegionServer需要的内存一般比HMaster要大。在内存充足的情况下，堆内存可以相对设置大一些。
    >    -   根据机器的内存大小设置“-Xmx”大小：机器内存\>200G，“-Xmx”设置为32G；128G<机器内存<200G，“-Xmx”设置为16G；机器内存<128G，“-Xmx”设置为8G。“-Xmx”配置为32G，可支持单RegionServer节点2000个Region，200个热点Region。

5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li2192412893318)。


**收集故障信息**

1.  <a name="li2192412893318"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”勾选待操作集群的“HBase”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53315585"></a>

无。

