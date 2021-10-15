# ALM-18019 JobHistoryServer非堆内存使用率超过阈值<a name="ALM-18019"></a>

## 告警解释<a name="section23885605"></a>

系统每30秒周期性检测MapReduce JobHistoryServer非堆内存使用率，并把实际的MapReduce JobHistoryServer非堆内存使用率和阈值相比较。当MapReduce JobHistoryServer非堆内存使用率超出阈值（默认为最大非堆内存的90%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> MapReduce”修改阈值。

当MapReduce JobHistoryServer非堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section13643857"></a>

<a name="table35012496"></a>
<table><thead align="left"><tr id="row2534604"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p3976396"><a name="p3976396"></a><a name="p3976396"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p53652677"><a name="p53652677"></a><a name="p53652677"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50899550"><a name="p50899550"></a><a name="p50899550"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row29222847"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p18240401"><a name="p18240401"></a><a name="p18240401"></a>18019</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1077499"><a name="p1077499"></a><a name="p1077499"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p20168614"><a name="p20168614"></a><a name="p20168614"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section55685851"></a>

<a name="table23045050"></a>
<table><thead align="left"><tr id="row20725005"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p1003825"><a name="p1003825"></a><a name="p1003825"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p14200994"><a name="p14200994"></a><a name="p14200994"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1495317532188"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row9429831"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61858895"><a name="p61858895"></a><a name="p61858895"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row19859143"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p37534159"><a name="p37534159"></a><a name="p37534159"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row2263116"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17248425"><a name="p17248425"></a><a name="p17248425"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row21018099"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p24744486"><a name="p24744486"></a><a name="p24744486"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58146329"><a name="p58146329"></a><a name="p58146329"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section31410612"></a>

MapReduce JobHistoryServer非堆内存使用率过高，会影响MapReduce任务提交和运行的性能，甚至造成内存溢出导致MapReduce服务不可用。

## 可能原因<a name="section14260053"></a>

该节点MapReduce JobHistoryServer实例非堆内存使用量过大，或分配的非堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section61231615"></a>

**检查非堆内存使用量。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警 \> ALM-18019 MapReduce JobHistoryServer非堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> MapReduce \> 实例 \> JobHistoryServer（对应上报告警实例主机名）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“JobHistoryServer非堆内存使用百分比统计”。查看非堆内存使用情况。
3.  查看JobHistoryServer使用的非堆内存是否已达到JobHistoryServer设定的最大非堆内存的90%。
    -   是，执行[4](#li77876868573)。
    -   否，执行[6](#li233093928573)。

4.  <a name="li77876868573"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> MapReduce \> 配置 \> 全部配置 \> JobHistoryServer \> 系统”。对NodeManager 的内存参数“GC\_OPTS”进行调整，并单击“保存”，单击“确定”进行重启。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >历史任务数10000和JobHistoryServer内存的对应关系如下：
    >-Xms30G -Xmx30G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li233093928573)。


**收集故障信息。**

1.  <a name="li233093928573"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   MapReduce

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section14213627"></a>

无。

