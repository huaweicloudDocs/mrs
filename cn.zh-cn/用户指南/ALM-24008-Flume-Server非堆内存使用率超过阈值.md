# ALM-24008 Flume Server非堆内存使用率超过阈值<a name="ALM-24008"></a>

## 告警解释<a name="section26053439"></a>

系统每60秒周期性检测Flume服务非堆内存使用状态，当连续5次检测到Flume实例非堆内存使用率超出阈值（最大内存的80%）时产生该告警，非堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section33154367"></a>

<a name="table53198919"></a>
<table><thead align="left"><tr id="row62016895"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p57312624"><a name="p57312624"></a><a name="p57312624"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p11811006"><a name="p11811006"></a><a name="p11811006"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p17167440"><a name="p17167440"></a><a name="p17167440"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row48385423"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p26905186"><a name="p26905186"></a><a name="p26905186"></a>24008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p31836466"><a name="p31836466"></a><a name="p31836466"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p28616934"><a name="p28616934"></a><a name="p28616934"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section29953848"></a>

<a name="table36270311"></a>
<table><thead align="left"><tr id="row13312348"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p4558436"><a name="p4558436"></a><a name="p4558436"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p33689020"><a name="p33689020"></a><a name="p33689020"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1348133541510"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row44456076"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p21195702"><a name="p21195702"></a><a name="p21195702"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row56543598"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4748349"><a name="p4748349"></a><a name="p4748349"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row42735142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4433805"><a name="p4433805"></a><a name="p4433805"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row39904249"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p11018704"><a name="p11018704"></a><a name="p11018704"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20099852"><a name="p20099852"></a><a name="p20099852"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section1149181"></a>

非堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section10342629"></a>

该节点Flume实例非堆内存使用率过大，或配置的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section25974803"></a>

**检查非堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Flume非堆内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Flume \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> Agent \> Flume非堆内存使用率”，单击“确定”。

    **图 1**  Flume非堆内存使用率<a name="fig9297199191619"></a>  
    ![](figures/Flume非堆内存使用率.png "Flume非堆内存使用率")

3.  查看Flume使用的非堆内存是否已达到Flume设定的阈值（默认值为最大非堆内存的80%）。
    -   是，执行[4](#li29985659161559)。
    -   否，执行[6](#d0e44186)。

4.  <a name="li29985659161559"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Flume \> 配置”，选择“全部配置”，选择“Flume \> 系统”。将“GC\_OPTS”参数中“-XX: MaxPermSize”的值根据实际情况调大，并单击“保存”，单击“确定”进行。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前flume server实例设置非堆内存大小无法满足当前业务使用场景，建议调整“-XX:MaxPermSize”的值为当前非堆内存使用量的两倍（或根据实际情况进行调整）。

5.  重启受影响的服务或实例观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e44186)。


**收集故障信息。**

1.  <a name="d0e44186"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Flume”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无。

