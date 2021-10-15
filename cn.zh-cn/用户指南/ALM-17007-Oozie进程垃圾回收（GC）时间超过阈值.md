# ALM-17007 Oozie进程垃圾回收（GC）时间超过阈值<a name="ALM-17007"></a>

## 告警解释<a name="section15936016"></a>

系统每60秒周期性检测Oozie进程的垃圾回收（GC）占用时间，当检测到Oozie进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section9206421"></a>

<a name="table63221355"></a>
<table><thead align="left"><tr id="row31817672"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p27094678"><a name="p27094678"></a><a name="p27094678"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p47185320"><a name="p47185320"></a><a name="p47185320"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p63914599"><a name="p63914599"></a><a name="p63914599"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row9700026"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p47504650"><a name="p47504650"></a><a name="p47504650"></a>17007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p22671422"><a name="p22671422"></a><a name="p22671422"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p24445887"><a name="p24445887"></a><a name="p24445887"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section15748925"></a>

<a name="table33959796"></a>
<table><thead align="left"><tr id="row12041852"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35865940"><a name="p35865940"></a><a name="p35865940"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p19460004"><a name="p19460004"></a><a name="p19460004"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row6761927132120"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row32756501"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32823928"><a name="p32823928"></a><a name="p32823928"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row26979903"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49072303"><a name="p49072303"></a><a name="p49072303"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row38997545"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43906777"><a name="p43906777"></a><a name="p43906777"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row59616680"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p64221796"><a name="p64221796"></a><a name="p64221796"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p34583021"><a name="p34583021"></a><a name="p34583021"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section7522603"></a>

导致Oozie提交任务响应变慢。

## 可能原因<a name="section594567"></a>

该节点Oozie实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section5351106"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Oozie进程垃圾回收（GC）时间超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Oozie \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> GC”中的“Oozie垃圾回收（GC）总时间”，单击“确定”。

    **图 1**  定制Oozie垃圾回收（GC）总时间<a name="fig10901454184117"></a>  
    ![](figures/定制Oozie垃圾回收（GC）总时间.png "定制Oozie垃圾回收（GC）总时间")

3.  查看Oozie每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#l68c669991267443fafa667b5b1990b73)。
    -   否，执行[6](#d0e32169)。

4.  <a name="l68c669991267443fafa667b5b1990b73"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Oozie \> 配置”，选择“全部配置”，在搜索栏里搜索“GC\_OPTS”参数。将“-Xmx”的值根据实际情况调大，并单击“保存”，单击“确定”进行保存。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >Oozie的GC参数配置建议：
    >建议“-Xms”和“-Xmx”设置成相同的值，这样可以避免JVM动态调整堆内存大小时影响性能。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e32169)。


**收集故障信息。**

1.  <a name="d0e32169"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Oozie”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895663.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40120107"></a>

无。

