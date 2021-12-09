# ALM-13002 ZooKeeper直接内存使用率超过阈值<a name="ALM-13002"></a>

## 告警解释<a name="section32667790"></a>

系统每30秒周期性检测ZooKeeper服务直接内存使用状态，当检测到ZooKeeper实例直接内存使用率超出阈值（最大内存的80%）时产生该告警。

平滑次数为1，ZooKeeper直接内存使用率小于阈值时，告警恢复；平滑次数大于1，ZooKeeper直接内存使用率小于阈值的80%时，告警恢复。

## 告警属性<a name="section25574658"></a>

<a name="table30976514"></a>
<table><thead align="left"><tr id="row50150899"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p35690985"><a name="p35690985"></a><a name="p35690985"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p5288672"><a name="p5288672"></a><a name="p5288672"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p25729279"><a name="p25729279"></a><a name="p25729279"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row3696879"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31011800"><a name="p31011800"></a><a name="p31011800"></a>13002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p28927841"><a name="p28927841"></a><a name="p28927841"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p61453746"><a name="p61453746"></a><a name="p61453746"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section28845335"></a>

<a name="table11697524"></a>
<table><thead align="left"><tr id="row42685878"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35004117"><a name="p35004117"></a><a name="p35004117"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p16761224"><a name="p16761224"></a><a name="p16761224"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row19384264337"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p88603521119"><a name="p88603521119"></a><a name="p88603521119"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row15481912"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41115053"><a name="p41115053"></a><a name="p41115053"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row34491157"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5395474"><a name="p5395474"></a><a name="p5395474"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row48559274"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p31619523"><a name="p31619523"></a><a name="p31619523"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row16140258"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p32292531"><a name="p32292531"></a><a name="p32292531"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p65558220"><a name="p65558220"></a><a name="p65558220"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section58281431"></a>

ZooKeeper可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section54770833"></a>

该节点ZooKeeper实例直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section23175456"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ZooKeeper直接内存使用率超过阈值”所在行的下拉菜单。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>_ 待操作集群的名称_  \> 服务 \> ZooKeeper \> 实例 \> quorumpeer（对应上报告警实例ip）”。单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“ZooKeeper堆内存与直接内存使用率”，单击“确定”，查看直接内存使用情况。
3.  查看ZooKeeper使用的直接内存是否已达到ZooKeeper设定的最大直接内存的80%？
    -   是，执行[4](#li4865794016944)。
    -   否，执行[8](#li5810672316944)。

4.  <a name="li4865794016944"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 配置 \> 全部配置 \> quorumpeer \> 系统”。查看“GC\_OPTS”参数中是否存在“-XX:MaxDirectMemorySize”。
    -   是，在“GC\_OPTS”中把参数“-XX:MaxDirectMemorySize”删除。执行[5](#li3526828416944)。
    -   否，执行[6](#li2423728152018)。

5.  <a name="li3526828416944"></a>保存配置，并重启ZooKeeper服务。
6.  <a name="li2423728152018"></a>查看告警信息，是否存在“ALM-13004 ZooKeeper堆内存使用率超过阈值”告警。
    -   是，按照“ALM-13004 ZooKeeper堆内存使用率超过阈值”告警进行处理。
    -   否，执行[7](#li4373900416944)。

7.  <a name="li4373900416944"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li5810672316944)。


**收集故障信息。**

1.  <a name="li5810672316944"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section7252516"></a>

无。

