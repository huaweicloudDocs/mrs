# ALM-45281 UserSync堆内存使用率超过阈值<a name="ALM-45281"></a>

## 告警解释<a name="section61130422"></a>

系统每60秒周期性检测UserSync服务堆内存使用状态，当连续10次检测到UserSync实例堆内存使用率超出阈值（最大内存的95%）时产生该告警，堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section13302888"></a>

<a name="table33986641"></a>
<table><thead align="left"><tr id="row13879140"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p50468531"><a name="p50468531"></a><a name="p50468531"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p61419199"><a name="p61419199"></a><a name="p61419199"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p8899183"><a name="p8899183"></a><a name="p8899183"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row49745195"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2829020"><a name="p2829020"></a><a name="p2829020"></a>45281</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p27824106"><a name="p27824106"></a><a name="p27824106"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p39160124"><a name="p39160124"></a><a name="p39160124"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section52617132"></a>

<a name="table17853499"></a>
<table><thead align="left"><tr id="row18143824"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p60363621"><a name="p60363621"></a><a name="p60363621"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p57615147"><a name="p57615147"></a><a name="p57615147"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row13401184712152"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row36315337"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28465328"><a name="p28465328"></a><a name="p28465328"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row54861362"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p40562973"><a name="p40562973"></a><a name="p40562973"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row29522441"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20557292"><a name="p20557292"></a><a name="p20557292"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row947315290501"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15179191519371"><a name="p15179191519371"></a><a name="p15179191519371"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1517911153376"><a name="p1517911153376"></a><a name="p1517911153376"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section3792148"></a>

堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section34129336"></a>

该节点UserSync实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section722974218354"></a>

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-45281 UserSync堆内存使用率超过阈值”，检查该告警的“定位信息”，查看告警上报的实例主机名。
2.  <a name="li58624704"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存 \> UserSync堆内存使用率”，单击“确定”。

    **图 1**  UserSync堆内存使用率<a name="fig0162154142220"></a>  
    ![](figures/UserSync堆内存使用率.png "UserSync堆内存使用率")

3.  查看UserSync使用的堆内存是否已达到UserSync设定的阈值（默认值为最大堆内存的95%）。
    -   是，执行[4](#li11521246145513)。
    -   否，执行[6](#li42224042151734)。

4.  <a name="li11521246145513"></a>在FusionInsight Manager首页，选择“集群 \> 服务 \> Ranger \> 实例 \> UserSync \> 实例配置”，单击“全部配置”，选择“UserSync \> 系统”。将“GC\_OPTS”参数中“-Xmx”的值根据实际情况调大，并保存配置。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前UserSync设置的堆内存无法满足当前UserSync进程所需的堆内存，建议根据[2](#li58624704)查看“UserSync堆内存使用率”，调整“GC\_OPTS”参数中“-Xmx”的值为“UserSync使用的堆内存大小”的两倍（可根据实际业务场景进行修改）。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li42224042151734)。


**收集故障信息。**

1.  <a name="li42224042151734"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Ranger”。
3.  单击右上角的![](figures/zh-cn_image_0293246731.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无。

