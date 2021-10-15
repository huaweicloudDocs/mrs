# ALM-18009 JobHistoryServer堆内存使用率超过阈值<a name="ALM-18009"></a>

## 告警解释<a name="section46467513"></a>

系统每30秒周期性检测Mapreduce JobHistoryServer堆内存使用率，并把实际的Mapreduce JobHistoryServer堆内存使用率和阈值相比较。当Mapreduce JobHistoryServer堆内存使用率超出阈值（默认为最大堆内存的95%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Mapreduce”修改阈值。

平滑次数为1，MapReduce JobHistoryServer堆内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，MapReduce JobHistoryServer堆内存使用率小于或等于阈值的95%时，告警恢复。

## 告警属性<a name="section15554440"></a>

<a name="table29676093"></a>
<table><thead align="left"><tr id="row40212317"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p35972254"><a name="p35972254"></a><a name="p35972254"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p28071463"><a name="p28071463"></a><a name="p28071463"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p59196065"><a name="p59196065"></a><a name="p59196065"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row30151988"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p26391943"><a name="p26391943"></a><a name="p26391943"></a>18009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57372610"><a name="p57372610"></a><a name="p57372610"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p16669838"><a name="p16669838"></a><a name="p16669838"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section5772232"></a>

<a name="table8079634"></a>
<table><thead align="left"><tr id="row17444750"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p3738651"><a name="p3738651"></a><a name="p3738651"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p34395333"><a name="p34395333"></a><a name="p34395333"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row19330144162016"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row34558579"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45097725"><a name="p45097725"></a><a name="p45097725"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row3226344"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28751554"><a name="p28751554"></a><a name="p28751554"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row57437397"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p30495700"><a name="p30495700"></a><a name="p30495700"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row6025849"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p18331773"><a name="p18331773"></a><a name="p18331773"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8478608"><a name="p8478608"></a><a name="p8478608"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section51950091"></a>

Mapreduce JobHistoryServer堆内存使用率过高，会影响Mapreduce 服务日志归档的性能，甚至造成内存溢出导致Mapreduce服务不可用。

## 可能原因<a name="section64897643"></a>

该节点Mapreduce JobHistoryServer实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section47207880"></a>

**检查内存使用量。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> MapReduce JobHistoryServer堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Mapreduce \> 实例 \> JobHistoryServer（对应上报告警实例主机名）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“JobHistoryServer堆内存使用百分比统计”。查看堆内存使用情况。
3.  查看JobHistoryServer使用的堆内存是否已达到JobHistoryServer设定的最大堆内存的95%。
    -   是，执行[4](#li4372053183245)。
    -   否，执行[6](#li4136199883245)。

4.  <a name="li4372053183245"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Mapreduce \> 配置 \> 全部配置 \> JobHistoryServer \> 系统”。将“GC\_OPTS”参数根据实际情况调大，并单击“保存”，单击“确定”并进重启。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >历史任务数10000和JobHistoryServer内存的对应关系如下：
    >-Xms30G -Xmx30G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  观察界面告警是否清除？
    -   是，处理完毕。
    -   否，执行[6](#li4136199883245)。


**收集故障信息。**

1.  <a name="li4136199883245"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   Mapreduce

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section22217739"></a>

无。

