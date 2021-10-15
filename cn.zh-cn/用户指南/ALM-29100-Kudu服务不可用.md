# ALM-29100  Kudu服务不可用<a name="ALM-29100"></a>

## 告警解释<a name="section60313499"></a>

系统每60秒周期性检测Kudu的服务状态，当检测到所有的Kudu实例都异常时，就会认为Kudu服务不可用，此时产生该告警。

至少一个Kudu实例正常后，系统认为Kudu实例服务恢复，告警清除。

## 告警属性<a name="section5950580"></a>

<a name="table15548096"></a>
<table><thead align="left"><tr id="row49989141"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p22588643"><a name="p22588643"></a><a name="p22588643"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p17740769"><a name="p17740769"></a><a name="p17740769"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p27716151"><a name="p27716151"></a><a name="p27716151"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row30415758"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p47757325"><a name="p47757325"></a><a name="p47757325"></a>29100</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p43138141"><a name="p43138141"></a><a name="p43138141"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p4528550"><a name="p4528550"></a><a name="p4528550"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section53555227"></a>

<a name="table9390101503313"></a>
<table><thead align="left"><tr id="row14412171593313"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p2412151583313"><a name="p2412151583313"></a><a name="p2412151583313"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p1141231511335"><a name="p1141231511335"></a><a name="p1141231511335"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row3413181517336"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1441316156335"><a name="p1441316156335"></a><a name="p1441316156335"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p16413141593313"><a name="p16413141593313"></a><a name="p16413141593313"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row54131815103314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p194131715133310"><a name="p194131715133310"></a><a name="p194131715133310"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p14413171593311"><a name="p14413171593311"></a><a name="p14413171593311"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row144131315133312"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p34130155333"><a name="p34130155333"></a><a name="p34130155333"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p0413115183317"><a name="p0413115183317"></a><a name="p0413115183317"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row114131215163315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p7413111513336"><a name="p7413111513336"></a><a name="p7413111513336"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1141321510333"><a name="p1141321510333"></a><a name="p1141321510333"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section12235000"></a>

用户无法使用Kudu服务。

## 可能原因<a name="section43006140"></a>

Kudu有实例存在异常。

## 处理步骤<a name="section262620715412"></a>

**处理Kudu实例异常**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”页面，找到“ALM-29100 Kudu服务异常”告警。
2.  <a name="li53993521460"></a>查看告警的“定位信息”一栏，记录主机名与角色名。
3.  选择“集群 \> 服务 \> Kudu \> 实例”，单击[2](#li53993521460)中对应主机名的角色名称，通过查看本实例的日志，修复这个实例，然后查看是否消除各个Kudu实例异常告警。
    -   是，执行[4](#li081419456453)。
    -   否，执行[5](#li54033805411)。

4.  <a name="li081419456453"></a>在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li54033805411)。


**收集故障信息**

1.  <a name="li54033805411"></a>在FusionInsight Manager首页，单击“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   Kudu

3.  单击右上角的![](figures/zh-cn_image_0295974381.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除

## 参考信息<a name="section53362350"></a>

无

