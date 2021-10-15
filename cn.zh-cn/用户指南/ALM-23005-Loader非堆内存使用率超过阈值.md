# ALM-23005 Loader非堆内存使用率超过阈值<a name="ALM-23005"></a>

## 告警解释<a name="section45844938"></a>

系统每30秒周期性检测Loader服务非堆内存使用状态，当连续5次检测到Loader实例非堆内存使用率超出阈值（最大内存的80%）时产生该告警。非堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section9951266"></a>

<a name="table28831118"></a>
<table><thead align="left"><tr id="row11229151"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p37146043"><a name="p37146043"></a><a name="p37146043"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p56039503"><a name="p56039503"></a><a name="p56039503"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p42905924"><a name="p42905924"></a><a name="p42905924"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row52827842"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p51196784"><a name="p51196784"></a><a name="p51196784"></a>23005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p53298806"><a name="p53298806"></a><a name="p53298806"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p22236029"><a name="p22236029"></a><a name="p22236029"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section22452530"></a>

<a name="table56287916"></a>
<table><thead align="left"><tr id="row44491726"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p47060014"><a name="p47060014"></a><a name="p47060014"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p53764762"><a name="p53764762"></a><a name="p53764762"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row202818478160"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row59978491"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p59616187"><a name="p59616187"></a><a name="p59616187"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row66783642"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13702426"><a name="p13702426"></a><a name="p13702426"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row56212973"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p50109826"><a name="p50109826"></a><a name="p50109826"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row48335250"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p22841184"><a name="p22841184"></a><a name="p22841184"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p38196655"><a name="p38196655"></a><a name="p38196655"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section746180"></a>

非堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section6715626"></a>

该节点Loader实例非堆内存使用率过大，或配置的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section60440635"></a>

**检查非堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Loader非堆内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制”，勾选“内存”中的“Loader非堆内存使用率”，单击“确定”。

    **图 1**  Loader非堆内存使用率<a name="fig142857267518"></a>  
    ![](figures/Loader非堆内存使用率.png "Loader非堆内存使用率")

3.  查看Loader使用的非堆内存是否已达到Loader设定的阈值（默认值为最大非堆内存的80%）。
    -   是，执行[4](#li59563582172012)。
    -   否，执行[6](#d0e41420)。

4.  <a name="li59563582172012"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Loader \> 配置”，选择“全部配置”，在搜索栏里搜索“LOADER\_GC\_OPTS”参数。如果之前没有显示指定“-XX: MaxPermSize”参数，初次添加可将初始值设置为“-XX: MaxPermSize=256M”（第一次调整完如果告警未消失，可参考说明部分进行二次调整）。单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >出现此告警时，说明当前Loader实例设置非堆内存大小无法满足当前业务使用场景，建议打开“Loader非堆内存资源状况”监控图表，观察该监控图表中“Loader使用的非堆内存大小”的变化趋势，根据当前非堆内存使用的大小，调整“-XX:MaxPermSize”的值为当前非堆内存使用量的两倍（或根据实际情况进行调整）。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e41420)。


**收集故障信息。**

1.  <a name="d0e41420"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Loader”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

