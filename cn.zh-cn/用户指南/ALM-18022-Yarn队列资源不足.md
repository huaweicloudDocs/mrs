# ALM-18022 Yarn队列资源不足<a name="ALM-18022"></a>

## 告警解释<a name="section31658481"></a>

告警模块按60秒周期检测Yarn队列资源，当队列可用资源或队列AM（ApplicationMaster）可用资源不足时，产生该告警。

当可用资源充足时，该告警自动消除。

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
<tbody><tr id="row11834698184"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p138359915188"><a name="p138359915188"></a><a name="p138359915188"></a>18022</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p108361599186"><a name="p108361599186"></a><a name="p108361599186"></a>次要</p>
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
<tr id="row14833183410545"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p26086497"><a name="p26086497"></a><a name="p26086497"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32631511"><a name="p32631511"></a><a name="p32631511"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section60692571"></a>

-   应用任务结束时间变长。
-   新应用提交后长时间无法运行。

## 可能原因<a name="section9362234"></a>

-   NodeManager节点资源过小。
-   队列最大资源容量设置过小。
-   AM最大资源百分比设置过小。

## 处理步骤<a name="section349312151712"></a>

**检查告警详情。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”，弹出告警页面。
2.  查看“Yarn队列资源不足”告警详情中的“定位信息”，查看“定位信息”是否为“队列名=root;队列指标名=Memory”或“队列名=root;队列指标名=vCores”。
    -   是，执行[3](#li46851012470)。
    -   否，执行[4](#li176859110474)。

3.  <a name="li46851012470"></a>出现该定位信息表示Yarn集群内存或CPU不足，登录NodeManager节点，分别使用命令**free -g**和**cat /proc/cpuinfo**，查询节点可用内存和可用CPU，据此在FusionInsight Manager界面增大Yarn NodeManager的资源参数“yarn.nodemanager.resource.memory-mb“和“yarn.nodemanager.resource.cpu-vcores“的值，然后重启NodeManager实例。查看该告警是否消除。
    -   是，处理完毕。
    -   否，执行[4](#li176859110474)。

4.  <a name="li176859110474"></a>查看“定位信息”为“队列名=<租户队列名\>;队列指标名=Memory”或“队列名=<租户队列名\>;队列指标名=vCores”，然后查看“附加信息”是否包含“available Memory =”或“available vCores =”。
    -   是，执行[5](#li86857113478)。
    -   否，执行[7](#li1068514117474)。

5.  <a name="li86857113478"></a>出现该附加信息表示该租户队列内存或者CPU不足，选择“租户资源 \> 动态资源计划 \> 资源分布策略”，调大“最大资源容量”的值，查看该告警是否消除。
    -   是，处理完毕。
    -   否，执行[6](#li109354114148)。

6.  <a name="li109354114148"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置”，输入搜索关键字“threshold”，单击“ResourceManager”，调整如下参数阈值：

    如果“附加信息”中包含“available Memory =”，调整“yarn.queue.memory.alarm.threshold”的阈值使其小于“附加信息”中的“available Memory =”的值。

    如果“附加信息”中包含“available vCores =”，调整“yarn.queue.vcore.alarm.threshold”的阈值使其小于“附加信息”中的“available vCores =”的值。

    等待5分钟，查看该告警是否消除。

    -   是，处理完毕。
    -   否，执行[9](#li76841314475)。

7.  <a name="li1068514117474"></a>查看“附加信息”包含“available AmMemory =”或“available AmvCores =”，表示该租户队列的ApplicationMaster内存和CPU不足，选择“租户资源 \> 动态资源计划 \> 队列配置”，增大“AM最大资源百分比”，查看该告警是否消除。
    -   是，处理完毕。
    -   否，执行[8](#li1382974791617)。

8.  <a name="li1382974791617"></a>选择“集群 \>  _待操作集群的名称_  \>服务 \> Yarn \> 配置 \> 全部配置”，输入搜索关键字“threshold”，单击“ResourceManager”：调整如下参数阈值：

    如果“附加信息”包含“available AmMemory =”，调整“yarn.am.memory.alarm.threshold”的阈值使其小于“附加信息”中的“available AmMemory =”的值。

    如果“附加信息”包含“available AmvCores =”，调整“yarn.am.vcore.alarm.threshold”的阈值使其小于“附加信息”中的“available AmvCores =”的值。

    等待5分钟，查看该告警是否消除。

    -   是，处理完毕。
    -   否，执行[9](#li76841314475)。


**收集故障信息。**

1.  <a name="li76841314475"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20143465"></a>

无。

