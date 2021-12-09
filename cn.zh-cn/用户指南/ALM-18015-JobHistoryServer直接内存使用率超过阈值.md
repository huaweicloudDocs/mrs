# ALM-18015 JobHistoryServer直接内存使用率超过阈值<a name="ALM-18015"></a>

## 告警解释<a name="section60352731"></a>

系统每30秒周期性检测MapReduce服务直接内存使用状态，当检测到JobHistoryServer实例直接内存使用率超出阈值（最大内存的90%，默认阈值）时，产生该告警。

直接内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section6303673"></a>

<a name="table35427225"></a>
<table><thead align="left"><tr id="row21003110"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p23530331"><a name="p23530331"></a><a name="p23530331"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p26908673"><a name="p26908673"></a><a name="p26908673"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p32118911"><a name="p32118911"></a><a name="p32118911"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row51495038"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p10348582"><a name="p10348582"></a><a name="p10348582"></a>18015</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p32928798"><a name="p32928798"></a><a name="p32928798"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p49986958"><a name="p49986958"></a><a name="p49986958"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section56733060"></a>

<a name="table22411807"></a>
<table><thead align="left"><tr id="row8024025"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p45966287"><a name="p45966287"></a><a name="p45966287"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p32281737"><a name="p32281737"></a><a name="p32281737"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row7271192191913"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row64683887"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61641698"><a name="p61641698"></a><a name="p61641698"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row17904376"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p30103972"><a name="p30103972"></a><a name="p30103972"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row2500292"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p29857724"><a name="p29857724"></a><a name="p29857724"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row284064"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23009248"><a name="p23009248"></a><a name="p23009248"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p51809817"><a name="p51809817"></a><a name="p51809817"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section40835493"></a>

MapReduce可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section31975117"></a>

该节点JobHistoryServer实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section19340597"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18015 JobHistory直接内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> MapReduce \> 实例 \> JobHistoryServer（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“JobHistoryServer内存使用详情”。查看直接内存使用情况。
3.  查看MapReduce使用的直接内存是否已达到MapReduce设定的最大直接内存的90%。
    -   是，执行[4](#li2045812484818)。
    -   否，执行[9](#li5018885984818)。

4.  <a name="li2045812484818"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> MapReduce \> 配置 \> 全部配置 \> JobHistoryServer \> 系统”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，执行[5](#li109341843132619)。
    -   否，执行[7](#li1474810218279)。

5.  <a name="li109341843132619"></a>在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。
6.  保存配置，并重启JobHistoryServer实例。
7.  <a name="li1474810218279"></a>查看告警信息，是否存在告警“ALM-18009 JobHistoryServer堆内存使用率超过阈值”。
    -   是，查看“ALM-18009 JobHistoryServer堆内存使用率超过阈值”进行处理。
    -   否，执行[8](#li1303308084818)。

8.  <a name="li1303308084818"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li5018885984818)。


**收集故障信息。**

1.  <a name="li5018885984818"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“JobHistoryServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section39847646"></a>

无。

