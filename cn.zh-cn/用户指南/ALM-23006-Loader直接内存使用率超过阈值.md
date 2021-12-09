# ALM-23006 Loader直接内存使用率超过阈值<a name="ALM-23006"></a>

## 告警解释<a name="section47717348"></a>

系统每30秒周期性检测Loader服务直接内存使用状态，当连续5次检测到Loader实例直接内存使用率超出阈值（最大内存的80%）时，产生该告警。当Loader直接内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section26802949"></a>

<a name="table20662094"></a>
<table><thead align="left"><tr id="row63210089"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19743614"><a name="p19743614"></a><a name="p19743614"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p55728924"><a name="p55728924"></a><a name="p55728924"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p17748970"><a name="p17748970"></a><a name="p17748970"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row28380432"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p17113655"><a name="p17113655"></a><a name="p17113655"></a>23006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p44028806"><a name="p44028806"></a><a name="p44028806"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p9563558"><a name="p9563558"></a><a name="p9563558"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section39899956"></a>

<a name="table36450751"></a>
<table><thead align="left"><tr id="row64916164"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p23717957"><a name="p23717957"></a><a name="p23717957"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p42106403"><a name="p42106403"></a><a name="p42106403"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row6489154181616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row55175493"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p21202295"><a name="p21202295"></a><a name="p21202295"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row56602932"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58494710"><a name="p58494710"></a><a name="p58494710"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row56690348"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28049362"><a name="p28049362"></a><a name="p28049362"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row51117673"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p46890881"><a name="p46890881"></a><a name="p46890881"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p40065001"><a name="p40065001"></a><a name="p40065001"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section23555289"></a>

直接内存溢出可能导致服务崩溃。

## 可能原因<a name="section10671013"></a>

该节点Loader实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section28930257"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Loader直接内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制”，勾选“内存”中的“Loader直接内存使用率统计”，单击“确定”。

    **图 1**  Loader直接内存使用率统计<a name="fig057955057"></a>  
    ![](figures/Loader直接内存使用率统计.png "Loader直接内存使用率统计")

3.  查看Loader使用的直接内存是否已达到Loader设定的阈值（默认值为最大直接内存 80%）。
    -   是，执行[4](#li79703172532)。
    -   否，执行[6](#d0e41643)。

4.  <a name="li79703172532"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Loader \> 配置”，选择“全部配置”，在搜索栏里搜索“LOADER\_GC\_OPTS”参数。将“-XX:MaxDirectMemorySize”的值根据实际情况调大，并单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前Loader实例设置直接内存大小无法满足当前业务使用场景，建议打开实例监控界面，在页面上调出“Loader直接内存资源状况”监控图表，观察该监控图表中“Loader使用的直接内存大小”的变化趋势，根据当前直接内存使用的大小，调整“-XX:MaxDirectMemorySize”的值为当前直接内存使用量的两倍（或根据实际情况进行调整）。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e41643)。


**收集故障信息。**

1.  <a name="d0e41643"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Loader”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

