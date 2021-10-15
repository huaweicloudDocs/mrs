# ALM-23007 Loader进程垃圾回收（GC）时间超过阈值<a name="ALM-23007"></a>

## 告警解释<a name="section29279455"></a>

系统每60秒周期性检测Loader进程的垃圾回收（GC）占用时间，当连续5次检测到Loader进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section62188507"></a>

<a name="table25636271"></a>
<table><thead align="left"><tr id="row59713398"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p4947044"><a name="p4947044"></a><a name="p4947044"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p65166250"><a name="p65166250"></a><a name="p65166250"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p43974897"><a name="p43974897"></a><a name="p43974897"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row5196896"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p18295456"><a name="p18295456"></a><a name="p18295456"></a>23007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p5536985"><a name="p5536985"></a><a name="p5536985"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p45842610"><a name="p45842610"></a><a name="p45842610"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section22825656"></a>

<a name="table22263891"></a>
<table><thead align="left"><tr id="row64987789"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p29519567"><a name="p29519567"></a><a name="p29519567"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p42274750"><a name="p42274750"></a><a name="p42274750"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1832323391619"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row1702721"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p31484965"><a name="p31484965"></a><a name="p31484965"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row14929232"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p38862996"><a name="p38862996"></a><a name="p38862996"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row14222652"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33504565"><a name="p33504565"></a><a name="p33504565"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row33105635"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p64310755"><a name="p64310755"></a><a name="p64310755"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41788676"><a name="p41788676"></a><a name="p41788676"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section4104320"></a>

导致Loader服务响应缓慢。

## 可能原因<a name="section36938882"></a>

该节点Loader实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section64014489"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Loader进程垃圾回收（GC）时间超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader \> 实例”，单击上报告警实例主机名对应的角色名，单击图表区域右上角的下拉菜单，选择“定制”，勾选“GC”中的“Loader的总GC时间”，单击“确定”。

    **图 1**  Loader的总GC时间<a name="fig127721111611"></a>  
    ![](figures/Loader的总GC时间.png "Loader的总GC时间")

3.  查看Loader每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li5761013917357)。
    -   否，执行[6](#d0e41866)。

4.  <a name="li5761013917357"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader \> 配置”，选择“全部配置”，在搜索栏里搜索“LOADER\_GC\_OPTS”参数。将“-Xmx”的值根据实际情况调大，并单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前Loader实例设置的堆内存无法满足当前数据传输所需的堆内存，建议参考[ALM-23004 Loader堆内存使用率超过阈值](ALM-23004-Loader堆内存使用率超过阈值.md)的处理措施[4](ALM-23004-Loader堆内存使用率超过阈值.md#d0e41176)进行处理。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e41866)。


**收集故障信息。**

1.  <a name="d0e41866"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Loader”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

