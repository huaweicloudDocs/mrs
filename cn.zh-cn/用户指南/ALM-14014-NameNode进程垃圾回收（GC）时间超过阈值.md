# ALM-14014 NameNode进程垃圾回收（GC）时间超过阈值<a name="ALM-14014"></a>

## 告警解释<a name="section40857075"></a>

系统每60秒周期性检测NameNode进程的垃圾回收（GC）占用时间，当检测到NameNode进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。

垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section32169356"></a>

<a name="table62371224"></a>
<table><thead align="left"><tr id="row14511981"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p34619835"><a name="p34619835"></a><a name="p34619835"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p52743225"><a name="p52743225"></a><a name="p52743225"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p44342799"><a name="p44342799"></a><a name="p44342799"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row34996966"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p16181989"><a name="p16181989"></a><a name="p16181989"></a>14014</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p35672757"><a name="p35672757"></a><a name="p35672757"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p3812222"><a name="p3812222"></a><a name="p3812222"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section21088755"></a>

<a name="table40354535"></a>
<table><thead align="left"><tr id="row60504204"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p1893530"><a name="p1893530"></a><a name="p1893530"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p19158252"><a name="p19158252"></a><a name="p19158252"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row17391233192720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row8314603"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p59715598"><a name="p59715598"></a><a name="p59715598"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row569472"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45320027"><a name="p45320027"></a><a name="p45320027"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row5227064"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2138848"><a name="p2138848"></a><a name="p2138848"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row19249632"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15716344"><a name="p15716344"></a><a name="p15716344"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p65064328"><a name="p65064328"></a><a name="p65064328"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55581072"></a>

NameNode进程的垃圾回收时间过长，可能影响该NameNode进程正常提供服务。

## 可能原因<a name="section30467604"></a>

该节点NameNode实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section5772984"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ALM-14014 NameNode进程垃圾回收（GC）时间超过阈值”所在行的下拉菜单，在“定位信息”中查看告警上报的角色名并确定实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例 \> NameNode（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 垃圾回收”，勾选“NameNode垃圾回收（GC）时间”。查看NameNode每分钟的垃圾回收时间统计情况。

    **图 1**  NameNode垃圾回收（GC）时间<a name="fig1526714111407"></a>  
    ![](figures/NameNode垃圾回收（GC）时间.png "NameNode垃圾回收（GC）时间")

3.  查看NameNode每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li3527760692939)。
    -   否，执行[7](#li6594738492939)。

4.  <a name="li3527760692939"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置 \> NameNode \> 系统”。将“GC\_OPTS”参数值根据实际情况调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >HDFS的文件对象数量（filesystem objects=files+blocks）和NameNode配置的JVM参数的对应关系建议如下：
    >-   文件对象数量达到10,000,000，则JVM参数建议配置为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M
    >-   文件对象数量达到20,000,000，则JVM参数建议配置为：-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G
    >-   文件对象数量达到50,000,000，则JVM参数建议配置为：-Xms32G -Xmx32G -XX:NewSize=3G -XX:MaxNewSize=3G
    >-   文件对象数量达到100,000,000，则JVM参数建议配置为：-Xms64G -Xmx64G -XX:NewSize=6G -XX:MaxNewSize=6G
    >-   文件对象数量达到200,000,000，则JVM参数建议配置为：-Xms96G -Xmx96G -XX:NewSize=9G -XX:MaxNewSize=9G
    >-   文件对象数量达到300,000,000，则JVM参数建议配置为：-Xms164G -Xmx164G -XX:NewSize=12G -XX:MaxNewSize=12G

5.  保存配置，并重启该NameNode实例。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li6594738492939)。


**收集故障信息。**

1.  <a name="li6594738492939"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“NameNode”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section51956861"></a>

无。

