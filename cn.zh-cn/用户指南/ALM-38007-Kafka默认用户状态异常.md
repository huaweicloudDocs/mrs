# ALM-38007 Kafka默认用户状态异常<a name="ALM-38007"></a>

## 告警解释<a name="section48693389"></a>

系统每60秒周期性检测Kafka服务默认用户，当检测到该用户异常时发送此告警。

平滑次数为1，当用户状态恢复后，告警恢复。

## 告警属性<a name="section35587318"></a>

<a name="table3700505"></a>
<table><thead align="left"><tr id="row41936390"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41404449"><a name="p41404449"></a><a name="p41404449"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p65426085"><a name="p65426085"></a><a name="p65426085"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65021496"><a name="p65021496"></a><a name="p65021496"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row32249861"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p62101938"><a name="p62101938"></a><a name="p62101938"></a>38007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p64201063"><a name="p64201063"></a><a name="p64201063"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p32903629"><a name="p32903629"></a><a name="p32903629"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section51850411"></a>

<a name="table47948299"></a>
<table><thead align="left"><tr id="row43302596"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p17849403"><a name="p17849403"></a><a name="p17849403"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p36515567"><a name="p36515567"></a><a name="p36515567"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row97767341713"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row4970951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66614789"><a name="p66614789"></a><a name="p66614789"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row62662193"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17748959"><a name="p17748959"></a><a name="p17748959"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row188041325135012"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p4804925145020"><a name="p4804925145020"></a><a name="p4804925145020"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2804112518509"><a name="p2804112518509"></a><a name="p2804112518509"></a>产生告警的主机名称。</p>
</td>
</tr>
<tr id="row25522907"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p54089623"><a name="p54089623"></a><a name="p54089623"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19183310"><a name="p19183310"></a><a name="p19183310"></a>Kafka默认用户状态异常。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64000515"></a>

Kafka默认用户状态异常，会影响Broker之间的元数据同步，以及Kafka与ZooKeeper之间的交互，进而影响业务生产、消费和Topic的创建、删除等操作。

## 可能原因<a name="section39133729"></a>

-   Sssd服务异常导致。
-   部分Broker实例停止运行。

## 处理步骤<a name="section1197252215489"></a>

**检查是否有"Sssd服务异常"告警。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Kafka默认用户状态异常 \> 定位信息”。查看告警上报的实例的主机名。
2.  根据告警提示的主机信息，登录到该节点上。
3.  执行**id -Gn kafka**，查看返回结果是否报"No such user"。
    -   是，记录当前节点主机名，并执行[4](#li55641967154518)。
    -   否，执行[6](#li0397154618553)。

4.  <a name="li55641967154518"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”。查看所有告警信息中是否有"Sssd服务异常"告警，根据对应的告警指导进行处理。

**检查Broker实例运行状态。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，进入Kafka实例页面。
2.  <a name="li0397154618553"></a>查看所有Broker实例中是否有已停止的节点。
    -   是，执行[7](#li103971446175517)。
    -   否，执行[8](#li1339784635518)。

3.  <a name="li103971446175517"></a>勾选所有已停止的Broker实例，单击“启动实例”。
4.  <a name="li1339784635518"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li24672963154518)。


**收集故障信息。**

1.  <a name="li24672963154518"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section15715480"></a>

无。

