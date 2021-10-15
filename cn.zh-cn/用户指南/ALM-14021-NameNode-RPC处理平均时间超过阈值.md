# ALM-14021 NameNode RPC处理平均时间超过阈值<a name="ALM-14021"></a>

## 告警解释<a name="section6703922"></a>

系统每30秒周期性检测NameNode的RPC处理平均时间，并把实际的NameNode的RPC处理平均时间和阈值（默认为100ms）相比较。当检测到NameNode的RPC处理平均时间连续多次（默认为10次）超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

如果平滑次数为1，NameNode的RPC处理平均时间小于或等于阈值时，告警恢复；如果平滑次数大于1，NameNode的RPC处理平均时间小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section60335301"></a>

<a name="table13583837"></a>
<table><thead align="left"><tr id="row40817340"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p17870258"><a name="p17870258"></a><a name="p17870258"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p38204800"><a name="p38204800"></a><a name="p38204800"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7581135"><a name="p7581135"></a><a name="p7581135"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row10092231"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p12164367"><a name="p12164367"></a><a name="p12164367"></a>14021</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p45789647"><a name="p45789647"></a><a name="p45789647"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p17973936"><a name="p17973936"></a><a name="p17973936"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section6146798"></a>

<a name="table46602713"></a>
<table><thead align="left"><tr id="row44686168"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p62809826"><a name="p62809826"></a><a name="p62809826"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p54431128"><a name="p54431128"></a><a name="p54431128"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row135167459266"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row46845284"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p60420695"><a name="p60420695"></a><a name="p60420695"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row6915351"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p6026987"><a name="p6026987"></a><a name="p6026987"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row54242887"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p9278288"><a name="p9278288"></a><a name="p9278288"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row16395729"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p52985690"><a name="p52985690"></a><a name="p52985690"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p63982467"><a name="p63982467"></a><a name="p63982467"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row38971291"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2557975"><a name="p2557975"></a><a name="p2557975"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5869448"><a name="p5869448"></a><a name="p5869448"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55321182"></a>

NameNode无法及时处理来自HDFS客户端、依赖于HDFS的上层服务、DataNode等的RPC请求，表现为访问HDFS服务的业务运行缓慢，严重时会导致HDFS服务不可用。

## 可能原因<a name="section28128590"></a>

-   NameNode节点的CPU性能不足，导致NameNode无法及时处理消息。
-   NameNode所设置的内存太小，频繁Full GC造成JVM卡顿。
-   NameNode配置参数不合理，导致NameNode无法充分利用机器性能。

## 处理步骤<a name="section51830719"></a>

**获取该告警的信息。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警“，在告警列表中找到该告警。
2.  单击该告警，查看下面的告警详情。从“定位信息“中的“主机名”信息可知发出该告警的NameNode节点主机名；从“定位信息“中的NameServiceName信息可知发出该告警的NameService名称。

**查看阈值是否设置过低。**

1.  查看依赖于HDFS的业务的运行状态是否正常运行。查看是否存在运行慢、执行任务超时的情况。
    -   是，执行[8](#li2190062915649)
    -   否，执行[4](#li12794575145018)

2.  <a name="li12794575145018"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”，单击图表区域右上角的下拉菜单，选择“定制 \> RPC”，在弹出的对话框中选择“主NameNode RPC处理平均时间“，单击“确定“。

    **图 1**  主NameNode RPC处理平均时间<a name="fig2052810155115"></a>  
    ![](figures/主NameNode-RPC处理平均时间.png "主NameNode-RPC处理平均时间")

3.  查看“主NameNode RPC处理平均时间“监控中，获取发出告警的NameService的当前的监控值。
4.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”，找到“主NameNode RPC处理平均时间“，单击default规则中“操作“栏中的“修改”，修改“阈值“为告警出现前后1天内监控值的峰值的150%。单击“确定“，保存新阈值。

    **图 2**  修改阈值<a name="fig1163332574013"></a>  
    ![](figures/修改阈值.png "修改阈值")

5.  等待5分钟，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[8](#li2190062915649)


**查看NameNode节点的CPU性能是否不足。**

1.  <a name="li2190062915649"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否有该NameNode节点的ID为“12016““ALM-12016 CPU使用率超过阈值“告警。
    -   是，执行[9](#li4691210415930)
    -   否，[11](#li1696839151443)

2.  <a name="li4691210415930"></a>按照“ALM-12016 CPU使用率超过阈值“告警处理文档，处理该告警。
3.  处理完12016告警后，等待10分钟，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[11](#li1696839151443)


**查看NameNode节点的内存是否设置过小。**

1.  <a name="li1696839151443"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否有该NameNode节点的ID为“14007““ALM-14007 HDFS NameNode堆内存使用率超过阈值“告警。
    -   是，执行[12](#li51365499151443)
    -   否，执行[14](#li2489812715139)

2.  <a name="li51365499151443"></a>按照“ALM-14007 HDFS NameNode堆内存使用率超过阈值“告警处理文档，处理该告警。
3.  处理完14007告警后，等待10分钟，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[14](#li2489812715139)


**查看该NameNode配置参数是否合理。**

1.  <a name="li2489812715139"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置”，搜索配置项“dfs.namenode.handler.count“，查看其值。如果值小于或等于128，则设置为128；如果大于128但小于192，则设置为192。
2.  搜索配置项“ipc.server.read.threadpool.size“，查看其值。如果值小于5，则设置为5。
3.  单击“保存“，单击“确定“。
4.  在HDFS的“实例“页面，先勾选发出该告警的NameService的备NameNode，在“更多“中单击“重启实例“，输入密码后单击“确定“，等待备NameNode启动完毕。
5.  在HDFS的“实例“页面，先勾选发出该告警的NameService的主NameNode，在“更多“中单击“重启实例“，输入密码后单击“确定“，等待主NameNode启动完毕。
6.  等待1小时，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[20](#li162921216241)


**收集故障信息。**

1.  <a name="li162921216241"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   HDFS

3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section63823290"></a>

无。

