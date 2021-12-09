# ALM-14016 DataNode直接内存使用率超过阈值<a name="ALM-14016"></a>

## 告警解释<a name="section7978296"></a>

系统每30秒周期性检测HDFS服务直接内存使用状态，当检测到DataNode实例直接内存使用率超出阈值（最大内存的90%）时，产生该告警。

直接内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section4695804"></a>

<a name="table45595801"></a>
<table><thead align="left"><tr id="row11217243"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p36181452"><a name="p36181452"></a><a name="p36181452"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p45016494"><a name="p45016494"></a><a name="p45016494"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p22457384"><a name="p22457384"></a><a name="p22457384"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row7108835"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p38944775"><a name="p38944775"></a><a name="p38944775"></a>14016</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p410170"><a name="p410170"></a><a name="p410170"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p33223847"><a name="p33223847"></a><a name="p33223847"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section42262236"></a>

<a name="table6777076"></a>
<table><thead align="left"><tr id="row9420492"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p24862365"><a name="p24862365"></a><a name="p24862365"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p585716"><a name="p585716"></a><a name="p585716"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row684592262710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row47442998"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22603169"><a name="p22603169"></a><a name="p22603169"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row2101933"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33468688"><a name="p33468688"></a><a name="p33468688"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row32782743"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p3670791"><a name="p3670791"></a><a name="p3670791"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row33037121"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p58761149"><a name="p58761149"></a><a name="p58761149"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62032625"><a name="p62032625"></a><a name="p62032625"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section44815811"></a>

DataNode可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section689121"></a>

该节点DataNode实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section6202095"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ALM-14016 DataNode直接内存使用率超过阈值”所在行的下拉菜单，在“定位信息”中查看告警上报的角色名并确定实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例 \> DataNode（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“DataNode内存使用详情”。查看直接内存使用情况。
3.  查看DataNode使用的直接内存是否已达到DataNode设定的最大直接内存的90%\(默认阈值\)。
    -   是，执行[4](#li3399087993722)。
    -   否，执行[8](#li5838381193722)。

4.  <a name="li3399087993722"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置 \> DataNode \> 系统”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，执行[5](#li062164310159)。
    -   否，执行[6](#li111010376180)。

5.  <a name="li062164310159"></a>在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。保存配置，并重启DataNode实例。
6.  <a name="li111010376180"></a>查看告警信息，是否存在告警“ALM-14008 DataNode堆内存使用率超过阈值”。
    -   是，参考“ALM-14008 DataNode堆内存使用率超过阈值”进行处理。
    -   否，执行[7](#li5868287393722)。

7.  <a name="li5868287393722"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li5838381193722)。


**收集故障信息。**

1.  <a name="li5838381193722"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“DataNode”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section55818863"></a>

无。

