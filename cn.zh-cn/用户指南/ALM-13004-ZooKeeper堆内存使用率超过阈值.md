# ALM-13004 ZooKeeper堆内存使用率超过阈值<a name="ALM-13004"></a>

## 告警解释<a name="section35674807"></a>

系统每60秒周期性检测ZooKeeper服务堆内存使用状态，当检测到ZooKeeper实例堆内存使用率超出阈值（最大内存的95%）时产生该告警。

堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section52637814"></a>

<a name="table47538321"></a>
<table><thead align="left"><tr id="row10159271"><th class="cellrowborder" valign="top" width="33.3033303330333%" id="mcps1.1.4.1.1"><p id="p17594659"><a name="p17594659"></a><a name="p17594659"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.36333633363336%" id="mcps1.1.4.1.2"><p id="p15881242"><a name="p15881242"></a><a name="p15881242"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p11312246"><a name="p11312246"></a><a name="p11312246"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row43876767"><td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.1.4.1.1 "><p id="p64357244"><a name="p64357244"></a><a name="p64357244"></a>13004</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.1.4.1.2 "><p id="p45554294"><a name="p45554294"></a><a name="p45554294"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66019188"><a name="p66019188"></a><a name="p66019188"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section3978286"></a>

<a name="table45954015"></a>
<table><thead align="left"><tr id="row58835946"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p982283"><a name="p982283"></a><a name="p982283"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p12456093"><a name="p12456093"></a><a name="p12456093"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row0466615183315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p153831612118"><a name="p153831612118"></a><a name="p153831612118"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row2310599"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p60350470"><a name="p60350470"></a><a name="p60350470"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row6283318"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20009785"><a name="p20009785"></a><a name="p20009785"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row45870339"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39149758"><a name="p39149758"></a><a name="p39149758"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row16803507"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p18906804"><a name="p18906804"></a><a name="p18906804"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55056187"><a name="p55056187"></a><a name="p55056187"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section35804574"></a>

ZooKeeper可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="section53805712"></a>

该节点ZooKeeper实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section14489366"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ZooKeeper堆内存使用率超过阈值”所在行的下拉菜单，在定位信息中确认告警上报的主机名所在的节点IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 实例”，单击对应IP地址的“角色”列的“quorumpeer”。单击图表区域右上角的下拉菜单，选择“定制 \> CPU 和内存”，勾选“ZooKeeper堆内存与直接内存使用率”，单击“确定”，查看堆内存使用情况。
3.  查看ZooKeeper使用的堆内存是否已达到ZooKeeper设定的最大堆内存的95%。
    -   是，执行[4](#li11182638195516)。
    -   否，执行[7](#li5001370016167)。

4.  <a name="li11182638195516"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 配置 \> 全部配置 \> quorumpeer \> 系统”。将GC\_OPTS参数中-Xmx的值根据实际情况调大，具体调整方案如下：
    1.  单击“实例”，选择对应IP地址的“角色”列的“quorumpeer”，单击图表区域右上角的下拉菜单，选择“定制 \> CPU 和内存”，勾选“ZooKeeper堆内存与直接内存资源状况”，单击“确定”，查看ZooKeeper实际使用的堆内存大小。
    2.  根据堆内存实际使用量，修改GC\_OPTS参数中的-Xmx值，该值一般为Zookeeper数据容量的2倍。例如当前ZooKeeper堆内存使用达到2G，则GC\_OPTS建议配置为“-Xms4G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=512M -XX:MetaspaceSize=64M -XX:MaxMetaspaceSize=64M -XX:CMSFullGCsBeforeCompaction=1”。

5.  保存配置，并重启ZooKeeper服务。
6.  观察界面告警是否清除？
    -   是，处理完毕。
    -   否，执行[7](#li5001370016167)。


**收集故障信息。**

1.  <a name="li5001370016167"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section63295431"></a>

无。

