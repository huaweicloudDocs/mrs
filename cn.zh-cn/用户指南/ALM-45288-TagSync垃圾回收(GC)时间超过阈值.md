# ALM-45288 TagSync垃圾回收\(GC\)时间超过阈值<a name="ALM-45288"></a>

## 告警解释<a name="section8280367"></a>

系统每60秒周期性检测TagSync进程的垃圾回收（GC）占用时间，当连续5次检测到TagSync进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section7414445"></a>

<a name="table45079949"></a>
<table><thead align="left"><tr id="row5683496"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p57710042"><a name="p57710042"></a><a name="p57710042"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p44001849"><a name="p44001849"></a><a name="p44001849"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7380012"><a name="p7380012"></a><a name="p7380012"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row60910108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p34771696"><a name="p34771696"></a><a name="p34771696"></a>45288</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65043985"><a name="p65043985"></a><a name="p65043985"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p34071398"><a name="p34071398"></a><a name="p34071398"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66730009"></a>

<a name="table8319831"></a>
<table><thead align="left"><tr id="row40868022"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p21975462"><a name="p21975462"></a><a name="p21975462"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p35182007"><a name="p35182007"></a><a name="p35182007"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row594512751512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row31170320"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p27766973"><a name="p27766973"></a><a name="p27766973"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row48576167"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8237383"><a name="p8237383"></a><a name="p8237383"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row7027591"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4237968"><a name="p4237968"></a><a name="p4237968"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row781512358516"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15179191519371"><a name="p15179191519371"></a><a name="p15179191519371"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1517911153376"><a name="p1517911153376"></a><a name="p1517911153376"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63699172"></a>

导致TagSync响应缓慢。

## 可能原因<a name="section36421639"></a>

该节点TagSync实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section2425015133012"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-45288 TagSync垃圾回收（GC）时间超过阈值”，检查该告警的“定位信息”，查看告警上报的实例主机名。
2.  <a name="li43047473"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> GC \> TagSync垃圾回收（GC）时间”，单击“确定”。

    **图 1**  TagSync垃圾回收（GC）时间<a name="fig8996183518272"></a>  
    ![](figures/TagSync垃圾回收（GC）时间.png "TagSync垃圾回收（GC）时间")

3.  查看TagSync每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#d0e44388)。
    -   否，执行[6](#d0e44409)。

4.  <a name="d0e44388"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例 \> TagSync \> 实例配置”，单击“全部配置”，选择“TagSync \> 系统”。将“GC\_OPTS”参数中“-Xmx”的值根据实际情况调大，并保存配置。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前TagSync设置的堆内存无法满足当前TagSync进程所需的堆内存，建议根据[2](#li43047473)查看“TagSync堆内存使用率”，调整“GC\_OPTS”参数中“-Xmx”的值为“TagSync使用的堆内存大小”的两倍（可根据实际业务场景进行修改）。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e44409)。


**收集故障信息。**

1.  <a name="d0e44409"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Ranger”。
3.  单击右上角的![](figures/zh-cn_image_0293269551.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无。

