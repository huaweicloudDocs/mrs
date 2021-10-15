# ALM-18014 NodeManager直接内存使用率超过阈值<a name="ALM-18014"></a>

## 告警解释<a name="section28035685"></a>

系统每30秒周期性检测Yarn服务直接内存使用状态，当检测到NodeManager实例直接内存使用率超出阈值（最大内存的90%）时，产生该告警。

直接内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section50994573"></a>

<a name="table42673540"></a>
<table><thead align="left"><tr id="row35040539"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19711423"><a name="p19711423"></a><a name="p19711423"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p53121394"><a name="p53121394"></a><a name="p53121394"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7865695"><a name="p7865695"></a><a name="p7865695"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row33141548"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p110849"><a name="p110849"></a><a name="p110849"></a>18014</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p8978823"><a name="p8978823"></a><a name="p8978823"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56196069"><a name="p56196069"></a><a name="p56196069"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section56297979"></a>

<a name="table55587780"></a>
<table><thead align="left"><tr id="row41226821"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p51038233"><a name="p51038233"></a><a name="p51038233"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p40456209"><a name="p40456209"></a><a name="p40456209"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row3684163318199"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row55727510"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19104101"><a name="p19104101"></a><a name="p19104101"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row37719182"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45172469"><a name="p45172469"></a><a name="p45172469"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row3899041"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13131444"><a name="p13131444"></a><a name="p13131444"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row51074140"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p43364650"><a name="p43364650"></a><a name="p43364650"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22875728"><a name="p22875728"></a><a name="p22875728"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section36919767"></a>

NodeManager可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section63842450"></a>

该节点NodeManager实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section37711141"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18014 NodeManager直接内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> NodeManager（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“NodeManager内存使用率”。查看直接内存使用情况。

    **图 1**  定制NodeManager内存使用率<a name="fig267352845611"></a>  
    ![](figures/定制NodeManager内存使用率.png "定制NodeManager内存使用率")

3.  查看NodeManager使用的直接内存是否已达到NodeManager设定的最大直接内存的90%\(默认阈值\)。
    -   是，执行[4](#li6312705484614)。
    -   否，执行[9](#li3036778384614)。

4.  <a name="li6312705484614"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> NodeManager \> 系统”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，执行[5](#li1776954511226)。
    -   否，执行[7](#li55455590227)。

5.  <a name="li1776954511226"></a>在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。
6.  保存配置，并重启NodeManager实例。
7.  <a name="li55455590227"></a>查看告警信息，是否存在告警“ALM-18018 NodeManager堆内存使用率超过阈值”。
    -   是，查看“ALM-18018 NodeManager堆内存使用率超过阈值”进行处理。
    -   否，执行[8](#li1828727984614)。

8.  <a name="li1828727984614"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li3036778384614)。


**收集故障信息。**

1.  <a name="li3036778384614"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“NodeManager”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section3855953"></a>

无。

