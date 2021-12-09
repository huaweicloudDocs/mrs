# ALM-16009 Map数超过阈值<a name="ALM-16009"></a>

## 告警解释<a name="section6164578"></a>

系统每30秒周期性检测执行的HQL的Map数是否超过阈值，超过阈值发出告警。系统默认的平滑次数为3次，默认阈值为5000。

## 告警属性<a name="section55481207"></a>

<a name="table53284255"></a>
<table><thead align="left"><tr id="row47341147"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p9427704"><a name="p9427704"></a><a name="p9427704"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p25446578"><a name="p25446578"></a><a name="p25446578"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p47906928"><a name="p47906928"></a><a name="p47906928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55255963"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46547994"><a name="p46547994"></a><a name="p46547994"></a>16009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p12291158"><a name="p12291158"></a><a name="p12291158"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56059702"><a name="p56059702"></a><a name="p56059702"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section29568819"></a>

<a name="table44541986"></a>
<table><thead align="left"><tr id="row29181518"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p14892770"><a name="p14892770"></a><a name="p14892770"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p65463685"><a name="p65463685"></a><a name="p65463685"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1281915323249"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row958306"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46323684"><a name="p46323684"></a><a name="p46323684"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row14259978"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p9959664"><a name="p9959664"></a><a name="p9959664"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row22528119"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33276087"><a name="p33276087"></a><a name="p33276087"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row10106111416473"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p57854422"><a name="p57854422"></a><a name="p57854422"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55696635"><a name="p55696635"></a><a name="p55696635"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64792783"></a>

Hive执行的HQL的Map数过高，一方面会导致HQL执行较慢，另一方面会大量占用资源。

## 可能原因<a name="section46264140"></a>

执行的HQL语句存在可以优化的可能。

## 处理步骤<a name="section91416156914"></a>

**检查HQL的Map个数。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 资源”，查看“HQL的Map数”图表，找出Map数过大的HQL语句（Map数\>=5000）。

1.  找到对应的HQL语句，优化在监控上显示map数过大的HQL语句，再尝试执行。
2.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[4](#li1284813578408)。


**收集故障信息。**

1.  <a name="li1284813578408"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895648.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

