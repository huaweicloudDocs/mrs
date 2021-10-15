# ALM-18013 ResourceManager直接内存使用率超过阈值<a name="ALM-18013"></a>

## 告警解释<a name="section57814134"></a>

系统每30秒周期性检测ResourceManager服务直接内存使用状态，当检测到ResourceManager实例直接内存使用率超出阈值（最大内存的90%）时，产生该告警。

直接内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section50565162"></a>

<a name="table13158775"></a>
<table><thead align="left"><tr id="row33796185"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p53136426"><a name="p53136426"></a><a name="p53136426"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p9083244"><a name="p9083244"></a><a name="p9083244"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p64654150"><a name="p64654150"></a><a name="p64654150"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row2494817"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p753637"><a name="p753637"></a><a name="p753637"></a>18013</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p61044600"><a name="p61044600"></a><a name="p61044600"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p45665605"><a name="p45665605"></a><a name="p45665605"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section52433274"></a>

<a name="table7926514"></a>
<table><thead align="left"><tr id="row35523450"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p58827179"><a name="p58827179"></a><a name="p58827179"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p272226"><a name="p272226"></a><a name="p272226"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row13219124010196"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row22050308"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52473391"><a name="p52473391"></a><a name="p52473391"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row2498475"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17935054"><a name="p17935054"></a><a name="p17935054"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row27197765"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2069877"><a name="p2069877"></a><a name="p2069877"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row18628895"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p32545531"><a name="p32545531"></a><a name="p32545531"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18942351"><a name="p18942351"></a><a name="p18942351"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2137425"></a>

ResourceManager可用直接内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section19236831"></a>

该节点ResourceManager实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section38913757"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18013 ResourceManager直接内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> ResourceManager（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“ResourceManager内存使用详情”。查看直接内存使用情况。

    **图 1**  定制ResourceManager内存使用详情<a name="fig1174345115417"></a>  
    ![](figures/定制ResourceManager内存使用详情.png "定制ResourceManager内存使用详情")

3.  查看ResourceManager使用的直接内存是否已达到ResourceManager设定的最大直接内存的90%\(默认阈值\)。
    -   是，执行[4](#li3112690684330)。
    -   否，执行[9](#li4344814084330)。

4.  <a name="li3112690684330"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> ResourceManager \> 系统”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，执行[5](#li48911622152)。
    -   否，执行[7](#li881319113122)。

5.  <a name="li48911622152"></a>在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。
6.  保存配置，并重启ResourceManager实例。
7.  <a name="li881319113122"></a>查看告警信息，是否存在告警“ALM-18008 ResourceManager堆内存使用率超过阈值”。
    -   是，查看“ALM-18008 ResourceManager堆内存使用率超过阈值”进行处理。
    -   否，执行[8](#li2719719284330)。

8.  <a name="li2719719284330"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li4344814084330)。


**收集故障信息。**

1.  <a name="li4344814084330"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ResourceManager”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section14679501"></a>

无。

