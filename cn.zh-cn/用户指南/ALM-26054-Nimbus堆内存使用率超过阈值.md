# ALM-26054 Nimbus堆内存使用率超过阈值<a name="ALM-26054"></a>

## 告警解释<a name="section4965009"></a>

系统每30秒周期性检测Storm Nimbus堆内存使用率，并把实际的Storm Nimbus堆内存使用率和阈值相比较。当连续5次检测到Storm Nimbus堆内存使用率超出阈值（默认值为80%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Storm \> Nimbus”修改阈值。

当Storm Nimbus堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section44685082"></a>

<a name="table63435007"></a>
<table><thead align="left"><tr id="row27251607"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p59896547"><a name="p59896547"></a><a name="p59896547"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p19782099"><a name="p19782099"></a><a name="p19782099"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p58846159"><a name="p58846159"></a><a name="p58846159"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row1809600"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p12359950"><a name="p12359950"></a><a name="p12359950"></a>26054</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p61631904"><a name="p61631904"></a><a name="p61631904"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p26128351"><a name="p26128351"></a><a name="p26128351"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66621420"></a>

<a name="table36021682"></a>
<table><thead align="left"><tr id="row28891113"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p58478831"><a name="p58478831"></a><a name="p58478831"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p39164877"><a name="p39164877"></a><a name="p39164877"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1317925217120"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row18238508"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7752332"><a name="p7752332"></a><a name="p7752332"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row2662125"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17903033"><a name="p17903033"></a><a name="p17903033"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row26909574"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57408755"><a name="p57408755"></a><a name="p57408755"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row46916749"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42160295"><a name="p42160295"></a><a name="p42160295"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p59540717"><a name="p59540717"></a><a name="p59540717"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section62721872"></a>

Storm Nimbus堆内存使用率过高时可能造成频繁GC，甚至造成内存溢出，进而影响Storm任务提交。

## 可能原因<a name="section27625944"></a>

该节点Storm Nimbus实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section47306908"></a>

**检查堆内存使用量。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \>Storm Nimbus堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> Nimbus \> Nimbus堆内存使用率”。单击“确定”。
3.  查看Nimbus使用的堆内存是否已达到Nimbus设定的阈值（默认值为最大堆内存的80%）。
    -   是，执行[4](#li1692032320113)。
    -   否，执行[6](#li4997677220113)。

4.  <a name="li1692032320113"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Storm \> 配置 \> 全部配置 \> Nimbus \> 系统”。将“NIMBUS\_GC\_OPTS”参数中“-Xmx”的值根据实际情况进行调整，然后单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   建议“-Xms”和“-Xmx”设置成相同的值，避免JVM动态调整堆内存大小时影响性能。
    >-   当Storm集群规模越大，Worker数量越多时，可以适当调大Nimbus的GC\_OPTS参数，配置建议如下：Worker数量为20个时，“-Xmx”设置为不小于1G；Worker超过100个时，“-Xmx”设置为不小于5G，以此类推。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li4997677220113)。


**收集故障信息。**

1.  <a name="li4997677220113"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   Storm

3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section23108988"></a>

无。

