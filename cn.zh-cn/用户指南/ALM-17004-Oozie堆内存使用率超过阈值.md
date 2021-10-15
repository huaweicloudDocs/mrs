# ALM-17004 Oozie堆内存使用率超过阈值<a name="ALM-17004"></a>

## 告警解释<a name="section5043290"></a>

系统每60秒周期性检测Oozie服务堆内存使用状态，当检测到Oozie实例堆内存使用率超出阈值（最大内存的95%）时产生该告警。堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section45389611"></a>

<a name="table37755026"></a>
<table><thead align="left"><tr id="row25369399"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41655442"><a name="p41655442"></a><a name="p41655442"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p18647617"><a name="p18647617"></a><a name="p18647617"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p34061997"><a name="p34061997"></a><a name="p34061997"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row7558333"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p8245209"><a name="p8245209"></a><a name="p8245209"></a>17004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p63882218"><a name="p63882218"></a><a name="p63882218"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p7077208"><a name="p7077208"></a><a name="p7077208"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section5853316"></a>

<a name="table36382986"></a>
<table><thead align="left"><tr id="row22923329"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p44850350"><a name="p44850350"></a><a name="p44850350"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p8999715"><a name="p8999715"></a><a name="p8999715"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row18767124319218"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row57888329"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36268998"><a name="p36268998"></a><a name="p36268998"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row57985534"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2938775"><a name="p2938775"></a><a name="p2938775"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row26448982"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55361472"><a name="p55361472"></a><a name="p55361472"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row28491208"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p26086497"><a name="p26086497"></a><a name="p26086497"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32631511"><a name="p32631511"></a><a name="p32631511"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section52679846"></a>

堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section4356570"></a>

该节点Oozie实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section39209138"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Oozie堆内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Oozie \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> 内存”中的“Oozie堆内存使用率”，单击“确定”。

    **图 1**  定制Oozie堆内存使用率<a name="fig16355181410354"></a>  
    ![](figures/定制Oozie堆内存使用率.png "定制Oozie堆内存使用率")

3.  查看Oozie使用的堆内存是否已达到Oozie设定的阈值（默认值为最大堆内存的95%）。
    -   是，执行[4](#d0e31488)。
    -   否，执行[6](#d0e31509)。

4.  <a name="d0e31488"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Oozie \> 配置”，选择“全部配置”。在搜索栏里搜索“GC\_OPTS”参数，将“-Xmx”的值根据实际情况调大，并单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >Oozie的GC参数配置建议：
    >建议“-Xms”和“-Xmx”设置成相同的值，这样可以避免JVM动态调整堆内存大小时影响性能。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e31509)。


**收集故障信息。**

1.  <a name="d0e31509"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Oozie”。
3.  单击右上角的![](figures/zh-cn_image_0263895663.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40120107"></a>

无。

