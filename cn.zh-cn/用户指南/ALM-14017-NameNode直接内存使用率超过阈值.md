# ALM-14017 NameNode直接内存使用率超过阈值<a name="ALM-14017"></a>

## 告警解释<a name="section20652455"></a>

系统每30秒周期性检测HDFS服务直接内存使用状态，当检测到NameNode实例直接内存使用率超出阈值（最大内存的90%）时，产生该告警。

直接内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section51654367"></a>

<a name="table49321766"></a>
<table><thead align="left"><tr id="row27442333"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p8236513"><a name="p8236513"></a><a name="p8236513"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p63177780"><a name="p63177780"></a><a name="p63177780"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p17126593"><a name="p17126593"></a><a name="p17126593"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row45076782"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p27340707"><a name="p27340707"></a><a name="p27340707"></a>14017</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p4809"><a name="p4809"></a><a name="p4809"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p389575"><a name="p389575"></a><a name="p389575"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section62236125"></a>

<a name="table31555654"></a>
<table><thead align="left"><tr id="row52256791"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p4941707"><a name="p4941707"></a><a name="p4941707"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p64733987"><a name="p64733987"></a><a name="p64733987"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1661491782715"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row8961608"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p9747287"><a name="p9747287"></a><a name="p9747287"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row20616720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41939895"><a name="p41939895"></a><a name="p41939895"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row41914739"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57587398"><a name="p57587398"></a><a name="p57587398"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row48524542"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p38173804"><a name="p38173804"></a><a name="p38173804"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5070386"><a name="p5070386"></a><a name="p5070386"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section23254217"></a>

NameNode可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section7961364"></a>

该节点NameNode实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section4543415"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ALM-14017 NameNode直接内存使用率超过阈值”所在行的下拉菜单，在“定位信息”中查看告警上报的角色名并确定实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例 \> NameNode（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“NameNode内存使用详情”。查看直接内存使用情况。
3.  查看NameNode使用的直接内存是否已达到NameNode设定的最大直接内存的90%\(默认阈值\)。
    -   是，执行[4](#li4815782094036)。
    -   否，执行[8](#li2261375794036)。

4.  <a name="li4815782094036"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> NameNode \> 全部配置”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，执行[5](#li158819371110)。
    -   否，执行[6](#li1572704262813)。

5.  <a name="li158819371110"></a>在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。保存配置，并重启NameNode实例。
6.  <a name="li1572704262813"></a>查看告警信息，是否存在告警“ALM-14007 NameNode堆内存使用率超过阈值”。
    -   是，查看“ALM-14007 NameNode堆内存使用率超过阈值”进行处理。
    -   否，执行[7](#li996918094036)。

7.  <a name="li996918094036"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li2261375794036)。


**收集故障信息。**

1.  <a name="li2261375794036"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“NameNode”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40890739"></a>

无。

