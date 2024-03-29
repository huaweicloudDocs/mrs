# ALM-18011 Yarn任务挂起内存超过阈值<a name="alm_18011"></a>

## 告警解释<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section43920869"></a>

系统每30秒周期性检查YARN服务处于挂起状态（Pending）的任务所占内存量，并把挂起状态任务的内存量和阈值进行比较。当检测到挂起状态任务的内存量超过阈值时产生该告警。

用户可通过“系统设置\> 阈值配置 \> 服务 \> Yarn \> 队列root挂起的内存量 \> 队列root挂起的内存量”修改阈值。

当挂起状态任务的内存量小于或等于阈值时，告警清除。

## 告警属性<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section59743502"></a>

<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_table64843092"></a>
<table><thead align="left"><tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row10409628"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p37873528"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p37873528"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p37873528"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p47856888"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p47856888"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p47856888"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p51202692"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p51202692"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p51202692"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row53777413"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0227101910_p431016914314"><a name="zh-cn_topic_0227101910_p431016914314"></a><a name="zh-cn_topic_0227101910_p431016914314"></a>18011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0227101910_p73091983110"><a name="zh-cn_topic_0227101910_p73091983110"></a><a name="zh-cn_topic_0227101910_p73091983110"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0227101910_p2308169103111"><a name="zh-cn_topic_0227101910_p2308169103111"></a><a name="zh-cn_topic_0227101910_p2308169103111"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section820607"></a>

<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_table66543927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row61284534"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p65100236"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p65100236"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p65100236"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p38627770"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p38627770"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p38627770"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row41841705"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0227101910_p9439174316"><a name="zh-cn_topic_0227101910_p9439174316"></a><a name="zh-cn_topic_0227101910_p9439174316"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p48178601"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p48178601"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p48178601"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row30954226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p24264406"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p24264406"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p24264406"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0227101910_p8405174319"><a name="zh-cn_topic_0227101910_p8405174319"></a><a name="zh-cn_topic_0227101910_p8405174319"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_row39121107"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p14693133"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p14693133"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p14693133"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p49293152"><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p49293152"></a><a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_p49293152"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0227101910_row1987111012143"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0227101910_p189541711101411"><a name="zh-cn_topic_0227101910_p189541711101411"></a><a name="zh-cn_topic_0227101910_p189541711101411"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0227101910_p995431113148"><a name="zh-cn_topic_0227101910_p995431113148"></a><a name="zh-cn_topic_0227101910_p995431113148"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section7385465"></a>

可能导致任务堆积，无法及时处理。

## 可能原因<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section66469189"></a>

集群运算能力低于任务提交速率，导致任务提交后无法及时运行处理。

## 处理步骤<a name="zh-cn_topic_0227101910_section14111549283"></a>

1.  检查Yarn页面的内存和vcore使用情况。

    查看Yarn原生页面的Memory Used|Memory Total和VCores Used|VCores Total，看是否已经到达或者接近最大值。

    -   是，执行[2](#zh-cn_topic_0227101910_li181801656143013)。
    -   否，执行[5](#zh-cn_topic_0227101910_li572522141314)。

2.  <a name="zh-cn_topic_0227101910_li181801656143013"></a>判断当前任务提交数量。

    查看当前运行中的任务是否为正常的提交频率。

    -   是，执行[3](#zh-cn_topic_0227101910_li10509161210322)。
    -   否，执行[5](#zh-cn_topic_0227101910_li572522141314)。

3.  <a name="zh-cn_topic_0227101910_li10509161210322"></a>对集群进行扩容。

    根据实际使用情况对集群进行扩容，扩容操作请参考  [扩容集群](扩容集群.md)。

4.  扩容完成后查看告警是否消失。
    -   是，处理完毕。
    -   否，执行[5](#zh-cn_topic_0227101910_li572522141314)。

5.  <a name="zh-cn_topic_0227101910_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0227101910_zh-cn_topic_0087039425_section15295265"></a>

无。

