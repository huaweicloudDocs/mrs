# ALM-38000 Kafka服务不可用<a name="ALM-38000"></a>

## 告警解释<a name="section33366180"></a>

系统按照30秒的周期检测Kafka服务是否可用，当Kafka服务不可用，系统产生此告警。

当Kafka服务恢复正常，告警自动清除。

## 告警属性<a name="section31860167"></a>

<a name="table13368905"></a>
<table><thead align="left"><tr id="row35936934"><th class="cellrowborder" valign="top" width="33.3033303330333%" id="mcps1.1.4.1.1"><p id="p25210542"><a name="p25210542"></a><a name="p25210542"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.36333633363336%" id="mcps1.1.4.1.2"><p id="p28788035"><a name="p28788035"></a><a name="p28788035"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50129484"><a name="p50129484"></a><a name="p50129484"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row33956402"><td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.1.4.1.1 "><p id="p66114012"><a name="p66114012"></a><a name="p66114012"></a>38000</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.1.4.1.2 "><p id="p53634738"><a name="p53634738"></a><a name="p53634738"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p49446558"><a name="p49446558"></a><a name="p49446558"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section18306055"></a>

<a name="table45748229"></a>
<table><thead align="left"><tr id="row54116031"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p21322357"><a name="p21322357"></a><a name="p21322357"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p49389356"><a name="p49389356"></a><a name="p49389356"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row844572118815"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row41114891"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p44280676"><a name="p44280676"></a><a name="p44280676"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row62981765"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p34084529"><a name="p34084529"></a><a name="p34084529"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row38325312"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62569653"><a name="p62569653"></a><a name="p62569653"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section30536772"></a>

集群无法对外提供Kafka服务，用户无法执行新的Kafka任务。

## 可能原因<a name="section6395495"></a>

-   KrbServer服务故障。（非普通模式集群）
-   ZooKeeper服务故障或无响应。
-   Kafka服务中Broker实例状态异常。

## 处理步骤<a name="section57559457"></a>

**检查KrbServer服务状态。（普通模式集群跳过此步骤）**

1.  在FusionInsight Manager管理界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> KrbServer”。
2.  <a name="li293820651659"></a>查看KrbServer服务的运行状态是否为“良好”。
    -   是，执行[5](#li218505861659)。
    -   否，执行[3](#li311370961659)。

3.  <a name="li311370961659"></a>参考“ALM-25500 KrbServer服务不可用”的处理步骤进行操作。
4.  再次执行[2](#li293820651659)。

**检查ZooKeeper服务状态。**

1.  <a name="li218505861659"></a>查看ZooKeeper服务的运行状态是否为“良好”。
    -   是，执行[8](#li483742821659)。
    -   否，执行[6](#li250670761659)。

2.  <a name="li250670761659"></a>如果ZooKeeper服务已停止，则启动ZooKeeper服务，否则参考“ALM-13000 ZooKeeper服务不可用”的处理步骤进行操作。
3.  再次执行[5](#li218505861659)。

**检查Broker实例状态。**

1.  <a name="li483742821659"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，进入Kafka实例页面。
2.  查看“角色”中所有实例是否正常。
    -   是，执行[11](#li252843541659)。
    -   否，执行[10](#li416939901659)。

3.  <a name="li416939901659"></a>勾选Broker所有实例，选择“更多 \> 重启实例”，查看是否重启成功。
    -   是，执行[11](#li252843541659)。
    -   否，执行[13](#li186190921659)。

4.  <a name="li252843541659"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka”，查看运行状态是否为“良好”。
    -   是，执行[12](#li20687881659)。
    -   否，执行[13](#li186190921659)。

5.  <a name="li20687881659"></a>等待30秒，查看告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li186190921659)。


**收集故障信息。**

1.  <a name="li186190921659"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section48273067"></a>

无。

