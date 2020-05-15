# ALM-38001 Kafka磁盘容量不足<a name="ZH-CN_TOPIC_0191883124"></a>

## 告警解释<a name="zh-cn_topic_0191813921_section44214237175627"></a>

系统按60秒周期检测Kafka磁盘空间使用率，并把实际磁盘使用率和阈值相比较。磁盘使用率默认提供一个阈值范围。当检测到磁盘使用率高于阈值时产生该告警。

用户可通过“系统设置 \> 阈值配置“修改阈值。

当Kafka磁盘使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813921_section45103477175627"></a>

<a name="zh-cn_topic_0191813921_table29503024175627"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813921_row3019899175627"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813921_p43285239175627"><a name="zh-cn_topic_0191813921_p43285239175627"></a><a name="zh-cn_topic_0191813921_p43285239175627"></a><strong id="zh-cn_topic_0191813921_b54022838175627"><a name="zh-cn_topic_0191813921_b54022838175627"></a><a name="zh-cn_topic_0191813921_b54022838175627"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813921_p13773744175627"><a name="zh-cn_topic_0191813921_p13773744175627"></a><a name="zh-cn_topic_0191813921_p13773744175627"></a><strong id="zh-cn_topic_0191813921_b56854838175627"><a name="zh-cn_topic_0191813921_b56854838175627"></a><a name="zh-cn_topic_0191813921_b56854838175627"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813921_p41839176175627"><a name="zh-cn_topic_0191813921_p41839176175627"></a><a name="zh-cn_topic_0191813921_p41839176175627"></a><strong id="zh-cn_topic_0191813921_b41008271175627"><a name="zh-cn_topic_0191813921_b41008271175627"></a><a name="zh-cn_topic_0191813921_b41008271175627"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813921_row33335618175627"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813921_p27679988181341"><a name="zh-cn_topic_0191813921_p27679988181341"></a><a name="zh-cn_topic_0191813921_p27679988181341"></a>38001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813921_p27486570181341"><a name="zh-cn_topic_0191813921_p27486570181341"></a><a name="zh-cn_topic_0191813921_p27486570181341"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813921_p11819704181341"><a name="zh-cn_topic_0191813921_p11819704181341"></a><a name="zh-cn_topic_0191813921_p11819704181341"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813921_section20277855175627"></a>

<a name="zh-cn_topic_0191813921_table31893524175627"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813921_row4661276175627"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813921_p42019060175627"><a name="zh-cn_topic_0191813921_p42019060175627"></a><a name="zh-cn_topic_0191813921_p42019060175627"></a><strong id="zh-cn_topic_0191813921_b42627221175627"><a name="zh-cn_topic_0191813921_b42627221175627"></a><a name="zh-cn_topic_0191813921_b42627221175627"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813921_p30252905175627"><a name="zh-cn_topic_0191813921_p30252905175627"></a><a name="zh-cn_topic_0191813921_p30252905175627"></a><strong id="zh-cn_topic_0191813921_b3840693175627"><a name="zh-cn_topic_0191813921_b3840693175627"></a><a name="zh-cn_topic_0191813921_b3840693175627"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813921_row42660718175627"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813921_p45748722181358"><a name="zh-cn_topic_0191813921_p45748722181358"></a><a name="zh-cn_topic_0191813921_p45748722181358"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813921_p14658969181358"><a name="zh-cn_topic_0191813921_p14658969181358"></a><a name="zh-cn_topic_0191813921_p14658969181358"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813921_row7363765175627"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813921_p16079573181358"><a name="zh-cn_topic_0191813921_p16079573181358"></a><a name="zh-cn_topic_0191813921_p16079573181358"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813921_p27377011181358"><a name="zh-cn_topic_0191813921_p27377011181358"></a><a name="zh-cn_topic_0191813921_p27377011181358"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813921_row24637125175627"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813921_p26508469181358"><a name="zh-cn_topic_0191813921_p26508469181358"></a><a name="zh-cn_topic_0191813921_p26508469181358"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813921_p66811235181358"><a name="zh-cn_topic_0191813921_p66811235181358"></a><a name="zh-cn_topic_0191813921_p66811235181358"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813921_row62397464181347"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813921_p51464303181358"><a name="zh-cn_topic_0191813921_p51464303181358"></a><a name="zh-cn_topic_0191813921_p51464303181358"></a>PartitionName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813921_p7859032181358"><a name="zh-cn_topic_0191813921_p7859032181358"></a><a name="zh-cn_topic_0191813921_p7859032181358"></a>产生告警的磁盘分区。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813921_row49070508181351"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813921_p24980969181358"><a name="zh-cn_topic_0191813921_p24980969181358"></a><a name="zh-cn_topic_0191813921_p24980969181358"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813921_p10192581181358"><a name="zh-cn_topic_0191813921_p10192581181358"></a><a name="zh-cn_topic_0191813921_p10192581181358"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813921_section11667204175627"></a>

磁盘容量不足会导致Kafka写入数据失败。

## 可能原因<a name="zh-cn_topic_0191813921_section49675514175627"></a>

-   用于存储Kafka数据的磁盘配置（如磁盘数目、磁盘大小等），无法满足当前业务数据流量，导致磁盘使用率达到上限。
-   数据保存时间配置过长，数据累积达到磁盘使用率上限。
-   业务规划不合理，导致数据分配不均，使部分磁盘达到使用率上限。

## 处理步骤<a name="zh-cn_topic_0191813921_section46014572175627"></a>

1.  登录MRS集群详情页面，选择“告警管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“告警管理”。  

2.  <a name="zh-cn_topic_0191813921_li13769123214531"></a>在告警列表中单击该告警，从“告警详情“的“定位信息“中获得HostName（主机名称）和PartitionName（磁盘分区名称）。
3.  在“主机管理“页面，单击[2](#zh-cn_topic_0191813921_li13769123214531)中获取的主机名称。
4.  检查“磁盘“区域中是否包含该告警中的磁盘分区名称。
    -   是，执行[5](#zh-cn_topic_0191813921_li15769133210538)。
    -   否，手动清除该告警，操作结束。

5.  <a name="zh-cn_topic_0191813921_li15769133210538"></a>检查“磁盘“区域中包含该告警中的磁盘分区使用率是否达到百分之百。
    -   是，执行[6](#zh-cn_topic_0191813921_li16769832165314)。
    -   否，执行[8](#zh-cn_topic_0191813921_li1476912324536)。

6.  <a name="zh-cn_topic_0191813921_li16769832165314"></a>在“实例“区域中，单击“Broker \> 实例配置“，进入当前节点“实例配置“页面，将“基础配置”切换为“全部配置“，查看数据目录配置参数“log.dirs“。
7.  单击“组件管理 \> Kafka \> 实例“，进入“Kafka实例“页面，停止[2](#zh-cn_topic_0191813921_li13769123214531)中对应的Broker实例，并登录该节点，手动删除[6](#zh-cn_topic_0191813921_li16769832165314)中配置的数据目录，然后继续执行后续步骤，待后续步骤执行完成后，再启动当前Broker实例。
8.  <a name="zh-cn_topic_0191813921_li1476912324536"></a>单击“组件管理 \> Kafka \> 服务配置“，进入“Kafka服务配置“页面。
9.  查看参数“disk.adapter.enable“是否配置为“true“。
    -   是，执行[11](#zh-cn_topic_0191813921_li19769532105319)。
    -   否，配置为“true“，开启该功能，执行[10](#zh-cn_topic_0191813921_li37691432185316)。

10. <a name="zh-cn_topic_0191813921_li37691432185316"></a>查看参数“adapter.topic.min.retention.hours“所配置的数据最短保存周期是否合理。

    -   是，执行[12](#zh-cn_topic_0191813921_li076953295311)。
    -   否，根据业务需求合理调整数据保存周期，执行[12](#zh-cn_topic_0191813921_li076953295311)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果有个别Topic不能做保存周期调整，那么可配置在“disk.adapter.topic.blacklist”中。  

11. <a name="zh-cn_topic_0191813921_li19769532105319"></a>等待10分钟，查看故障磁盘使用率是否有减少。
    -   是，继续等待直到告警消除。
    -   否，执行[12](#zh-cn_topic_0191813921_li076953295311)。

12. <a name="zh-cn_topic_0191813921_li076953295311"></a>进入“Kafka Topic监控“页面，查看Kafka配置的数据保存时间配置，根据业务需求和业务量权衡，考虑是否需要调小数据保存时间。
    -   是，执行[13](#zh-cn_topic_0191813921_li10769173213539)。
    -   否，执行[14](#zh-cn_topic_0191813921_li1176913210535)。

13. <a name="zh-cn_topic_0191813921_li10769173213539"></a>根据[2](#zh-cn_topic_0191813921_li13769123214531)中上报告警的磁盘分区，找到数据量较大的Topic，手动调小保存周期，使用Kafka的linux客户端，执行如下操作命令：

    **kafka-topics.sh --zookeeper** _ZooKeeper地址:24002/kafka_ **--alter --topic** _Topic名称_ **--config retention.ms=**_保存时间_

14. <a name="zh-cn_topic_0191813921_li1176913210535"></a>查看是否由于某些Topic的Partition配置不合理导致部分磁盘使用率达到上限（例如：数据量非常大的Topic的Partition数目小于配置的磁盘个数，导致各磁盘上数据分配无法均匀，进而部分磁盘达到使用率上限）。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果不清楚哪些Topic业务数据量较大，可以根据[2](#zh-cn_topic_0191813921_li13769123214531)中获取到的主机节点信息，登录到实例节点上，进入对应的数据目录（即[6](#zh-cn_topic_0191813921_li16769832165314)中“log.dirs“修改之前的配置路径），查看该目录下哪些Topic的Patition目录占用的磁盘空间比较大。  

    -   是，执行[15](#zh-cn_topic_0191813921_li137701132145312)。
    -   否，执行[16](#zh-cn_topic_0191813921_li9770103214530)。

15. <a name="zh-cn_topic_0191813921_li137701132145312"></a>通过Kafka客户端对Topic的Partion进行扩展，命令行操作命令如下：

    **kafka-topics.sh --zookeeper** _ZooKeeper地址:24002/kafka_ **--alter --topic** _Topic名称_ **--partitions=**_新Partition数目_

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >新Partition数目建议配置为Kafka数据磁盘数量的倍数。  
    >当前步骤修改可能不会很快解决当前告警，需要结合数据保存时间逐渐均衡数据。  

16. <a name="zh-cn_topic_0191813921_li9770103214530"></a>考虑是否需要扩容。
    -   是，请为集群添加节点，然后执行[17](#zh-cn_topic_0191813921_li4770432185318)。
    -   否，执行[17](#zh-cn_topic_0191813921_li4770432185318)。

17. <a name="zh-cn_topic_0191813921_li4770432185318"></a>等待一段时间，检查告警是否清除。
    -   是，操作结束。
    -   否，执行[18](#zh-cn_topic_0191813921_li572522141314)。

18. <a name="zh-cn_topic_0191813921_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813921_section57848114175627"></a>

无。

