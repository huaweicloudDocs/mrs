# ALM-45278 RangerAdmin直接内存使用率超过阈值<a name="ALM-45278"></a>

## 告警解释<a name="section35136898"></a>

系统每60秒周期性检测RangerAdmin服务直接内存使用状态，当连续5次检测到RangerAdmin实例直接内存使用率超出阈值（最大内存的80%）时，产生该告警。当RangerAdmin直接内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section47796626"></a>

<a name="table58337011"></a>
<table><thead align="left"><tr id="row62299817"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p13120377"><a name="p13120377"></a><a name="p13120377"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p56117589"><a name="p56117589"></a><a name="p56117589"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p49230886"><a name="p49230886"></a><a name="p49230886"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row28278868"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p8886982"><a name="p8886982"></a><a name="p8886982"></a>45278</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p48756965"><a name="p48756965"></a><a name="p48756965"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p57000088"><a name="p57000088"></a><a name="p57000088"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section27516457"></a>

<a name="table53604424"></a>
<table><thead align="left"><tr id="row30968229"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p25398627"><a name="p25398627"></a><a name="p25398627"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p44022946"><a name="p44022946"></a><a name="p44022946"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1083384091512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row9088906"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39642994"><a name="p39642994"></a><a name="p39642994"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row21242631"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p54903620"><a name="p54903620"></a><a name="p54903620"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row24370534"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41764972"><a name="p41764972"></a><a name="p41764972"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row19533456154912"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15179191519371"><a name="p15179191519371"></a><a name="p15179191519371"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1517911153376"><a name="p1517911153376"></a><a name="p1517911153376"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section46321527"></a>

直接内存溢出可能导致服务崩溃。

## 可能原因<a name="section14240565"></a>

节点RangerAdmin实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section168730599458"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-45278 RangerAdmin直接内存使用率超过阈值”，检查该告警的“定位信息”，查看告警上报的实例主机名。
2.  <a name="li7677390"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存 \> RangerAdmin直接内存使用率”，单击“确定”。

    **图 1**  RangerAdmin直接内存使用率<a name="fig145427393219"></a>  
    ![](figures/RangerAdmin直接内存使用率.png "RangerAdmin直接内存使用率")

3.  查看RangerAdmin使用的直接内存是否已达到RangerAdmin设定的阈值（默认值为最大直接内存的80%）。
    -   是，执行[4](#li10450762161055)。
    -   否，执行[6](#d0e43963)。

4.  <a name="li10450762161055"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例 \> RangerAdmin \> 实例配置”，单击“全部配置”，选择“RangerAdmin \> 系统”。将“GC\_OPTS”参数中“-XX:MaxDirectMemorySize”的值根据实际情况调大，并保存配置。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前RangerAdmin设置的直接内存无法满足当前RangerAdmin进程所需的直接内存，建议根据[2](#li7677390)查看“RangerAdmin直接内存使用率”，调整“GC\_OPTS”参数中“-XX:MaxDirectMemorySize”的值为“RangerAdmin使用的直接内存大小”的两倍（可根据实际业务场景进行修改）。

5.  重新启动受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e43963)。


**收集故障信息。**

1.  <a name="d0e43963"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Ranger”。
3.  单击右上角的![](figures/zh-cn_image_0293242788.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无。

