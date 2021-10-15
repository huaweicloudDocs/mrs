# ALM-14022 NameNode RPC队列平均时间超过阈值<a name="ALM-14022"></a>

## 告警解释<a name="section37271663115124"></a>

系统每30秒周期性检测NameNode的RPC队列平均时间，并把实际的NameNode的RPC队列平均时间和阈值（默认为200ms）相比较。当检测到NameNode的RPC队列平均时间连续多次（默认为10次）超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

如果平滑次数为1，NameNode的RPC队列平均时间小于或等于阈值时，告警恢复；如果平滑次数大于1，NameNode的RPC队列平均时间小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section19245716115124"></a>

<a name="table15399177115124"></a>
<table><thead align="left"><tr id="row29552962115124"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p44979704115124"><a name="p44979704115124"></a><a name="p44979704115124"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p19477444115124"><a name="p19477444115124"></a><a name="p19477444115124"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p34169099115124"><a name="p34169099115124"></a><a name="p34169099115124"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row16233655115124"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p39857712115124"><a name="p39857712115124"></a><a name="p39857712115124"></a>14022</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p7249245115124"><a name="p7249245115124"></a><a name="p7249245115124"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p50317991115124"><a name="p50317991115124"></a><a name="p50317991115124"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section50208738115124"></a>

<a name="table40375969115124"></a>
<table><thead align="left"><tr id="row51138187115124"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p48552443115124"><a name="p48552443115124"></a><a name="p48552443115124"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p40433783115124"><a name="p40433783115124"></a><a name="p40433783115124"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row15883193912268"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row53911016115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46469064115124"><a name="p46469064115124"></a><a name="p46469064115124"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row15568399115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4575151115124"><a name="p4575151115124"></a><a name="p4575151115124"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row41176362115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p44935135115124"><a name="p44935135115124"></a><a name="p44935135115124"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row1763031115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p8587829115124"><a name="p8587829115124"></a><a name="p8587829115124"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24525588115124"><a name="p24525588115124"></a><a name="p24525588115124"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row19403708115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p28196478115124"><a name="p28196478115124"></a><a name="p28196478115124"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2213397115124"><a name="p2213397115124"></a><a name="p2213397115124"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section19920580115124"></a>

NameNode无法及时处理来自HDFS客户端、依赖于HDFS的上层服务、DataNode等的RPC请求，表现为访问HDFS服务的业务运行缓慢，严重时会导致HDFS服务不可用。

## 可能原因<a name="section26588641115124"></a>

-   NameNode节点的CPU性能不足，导致NameNode无法及时处理消息。
-   NameNode所设置的内存太小，频繁Full GC造成JVM卡顿。
-   NameNode配置参数不合理，导致NameNode无法充分利用机器性能。
-   HDFS的业务访问量太大，超过了NameNode的负载能力。

## 处理步骤<a name="section9346014115124"></a>

**获取该告警的信息。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中找到该告警。
2.  单击该告警，查看下面的告警详情。从“产生时间“可知该告警的触发时间；从“定位信息“中的“主机名”信息可知发出该告警的NameNode节点主机名；从“定位信息“中的NameServiceName信息可知发出该告警的NameService名称。

**查看是否阈值设置过低。**

1.  查看依赖于HDFS的业务的运行状态是否正常运行。查看是否存在运行慢、执行任务超时的情况。
    -   是，执行[8](#li23855515115124)。
    -   否，执行[4](#li52208975115124)。

2.  <a name="li52208975115124"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”，单击图表区域右上角的下拉菜单，单击“定制”，在弹出的对话框中选择“主NameNode RPC队列平均时间“，单击“确定“。

    **图 1**  主NameNode RPC队列平均时间<a name="fig187339105812"></a>  
    ![](figures/主NameNode-RPC队列平均时间.png "主NameNode-RPC队列平均时间")

3.  查看“主NameNode RPC队列平均时间“监控中，获取发出告警的NameService的当前的监控值。
4.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”，找到“主NameNode RPC队列平均时间“，单击default规则中“操作“栏中的“修改”，修改“阈值“为当前监控值的150%。单击“确定“，保存新阈值。
5.  等待1分钟，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[8](#li23855515115124)。


**查看NameNode节点的CPU性能是否不足。**

1.  <a name="li23855515115124"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看该NameNode节点是否有“ALM-12016 CPU使用率超过阈值“告警。
    -   是，执行[9](#li42860509115124)。
    -   否，执行[11](#li49400846115124)。

2.  <a name="li42860509115124"></a>按照“ALM-12016 CPU使用率超过阈值“告警处理文档，处理该告警。
3.  处理完12016告警后，等待10分钟，查看14022告警是否自动消除。
    -   是，处理结束。
    -   否，执行[11](#li49400846115124)。


**查看NameNode节点的内存是否设置过小。**

1.  <a name="li49400846115124"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否有该NameNode节点的“ALM-14007 HDFS NameNode堆内存使用率超过阈值“告警。
    -   是，执行[12](#li44886689115124)。
    -   否，执行[14](#li5405317410056)。

2.  <a name="li44886689115124"></a>按照“ALM-14007 HDFS NameNode堆内存使用率超过阈值“告警处理文档，处理该告警。
3.  处理完14007告警后，等待10分钟，查看14022告警是否自动消除。
    -   是，处理结束。
    -   否，执行[14](#li5405317410056)。


**查看该NameNode配置参数是否合理。**

1.  <a name="li5405317410056"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置”，搜索配置项“dfs.namenode.handler.count“，查看其值。如果值小于或等于128，则设置为128；如果大于128但小于192，则设置为192。
2.  搜索配置项“ipc.server.read.threadpool.size“，查看其值。如果值小于5，则设置为5。
3.  单击“保存“，单击“确定“。
4.  在HDFS的“实例“页面，先勾选发出该告警的NameService的备NameNode，在“更多“中单击“重启实例“，输入密码后单击“确定“，等待备NameNode启动完毕。
5.  在HDFS的“实例“页面，先勾选发出该告警的NameService的主NameNode，在“更多“中单击“重启实例“，输入密码后单击“确定“，等待主NameNode启动完毕。
6.  等待1小时，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[20](#li35954467155026)。


**查看HDFS负载变化情况，适当降低HDFS负载。**

1.  <a name="li35954467155026"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”，单击图表区域右上角的下拉菜单，选择“定制”，单击“RPC”，在弹出的对话框中选择“NameNode RPC队列平均时间“，单击“确定“。

    **图 2**  主NameNode RPC队列平均时间<a name="fig15358192885914"></a>  
    ![](figures/主NameNode-RPC队列平均时间-117.png "主NameNode-RPC队列平均时间-117")

2.  单击![](figures/zh-cn_image_0263895565.png)，进入监控详细信息界面。
3.  设置监控显示的时间段，从告警产生的时间的前5天开始，到告警产生时刻结束。单击“确定“按钮。
4.  在“NameNode RPC队列平均时间“监控中，查看该监控是否有开始急剧增加的时间点。
    -   是，执行[24](#li3312625416355)。
    -   否，执行[27](#li60321407115124)。

5.  <a name="li3312625416355"></a>确认并排查在该时间点，是否有新增任务大量访问HDFS，确认该任务是否可以调优，减少对HDFS的访问。
6.  如果在该时间点有执行Balancer，则可以停止Balancer，或指定节点执行Balancer任务，来降低对HDFS的负载。
7.  等待1小时，查看该告警是否自动消除。
    -   是，处理结束。
    -   否，执行[27](#li60321407115124)。


**收集故障信息。**

1.  <a name="li60321407115124"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”勾选待操作集群的HDFS节点信息。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section54560047115124"></a>

无。

