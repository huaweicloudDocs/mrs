# ALM-18023 Yarn任务挂起数超过阈值<a name="ALM-18023"></a>

## 告警解释<a name="section31658481"></a>

告警模块按60秒周期检测Yarn队列上pending的应用的数量，当root队列上处于pending状态的应用的数量超过60时，触发该告警。

## 告警属性<a name="section16490876"></a>

<a name="table7825795184"></a>
<table><thead align="left"><tr id="row10829199161819"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p7830149181817"><a name="p7830149181817"></a><a name="p7830149181817"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p4832169171818"><a name="p4832169171818"></a><a name="p4832169171818"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7834295185"><a name="p7834295185"></a><a name="p7834295185"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row11834698184"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p138359915188"><a name="p138359915188"></a><a name="p138359915188"></a>18023</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p108361599186"><a name="p108361599186"></a><a name="p108361599186"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1083810991819"><a name="p1083810991819"></a><a name="p1083810991819"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section14200159"></a>

<a name="table15448152818187"></a>
<table><thead align="left"><tr id="row2451192861813"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p445318287184"><a name="p445318287184"></a><a name="p445318287184"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p14455152871817"><a name="p14455152871817"></a><a name="p14455152871817"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row077613291817"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row8457102815185"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17459122801816"><a name="p17459122801816"></a><a name="p17459122801816"></a>队列名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8460192821819"><a name="p8460192821819"></a><a name="p8460192821819"></a>产生告警的队列名。</p>
</td>
</tr>
<tr id="row846182891817"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1546213282187"><a name="p1546213282187"></a><a name="p1546213282187"></a>队列指标名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8462142814188"><a name="p8462142814188"></a><a name="p8462142814188"></a>产生告警的队列指标名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section60692571"></a>

-   应用任务结束时间变长。
-   新应用提交后长时间无法运行。

## 可能原因<a name="section9362234"></a>

-   NodeManager节点资源过小。
-   队列最大资源容量设置过小，AM最大资源百分比设置过小。
-   监控阈值设置过小。

## 处理步骤<a name="section18537579256"></a>

**检查NodeManager节点资源**

1.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> ResourceManager\(主\)”，进入ResourceManager的WebUI页面。
2.  单击“Scheduler”，在“Application Queues”中查看root队列是否资源用满。
    -   是，执行[3](#li1894618168247)。
    -   否，执行[4](#li156321342274)。

3.  <a name="li1894618168247"></a>对Yarn服务的NodeManager实例进行扩容。扩容后，查看告警是否消除。
    -   是，处理完毕。
    -   否，执行[6](#li15314143611285)。


**检查队列最大资源容量和AM最大资源百分比**

1.  <a name="li156321342274"></a>查看pending任务对应的队列的资源是否用满。
    -   是，执行[5](#li1663218419278)。
    -   否，执行[6](#li15314143611285)。

2.  <a name="li1663218419278"></a>在FusionInsight Manager界面，选择 “租户资源 \> 动态资源计划”，根据实际需要，适当增加相应的队列资源。查看告警是否消除。
    -   是，处理完毕。
    -   否，执行[6](#li15314143611285)


**调整监控阈值**

1.  <a name="li15314143611285"></a>在FusionInsight Manager界面，选择“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Yarn \> 任务 \> 正在挂起的任务”，根据实际需要，适当增加该告警的监控阈值。
2.  等待5分钟，查看该告警是否消除。
    -   是，处理完毕。
    -   否，执行[8](#li76841314475)。


**收集故障信息。**

1.  <a name="li76841314475"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895802.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20143465"></a>

无。

