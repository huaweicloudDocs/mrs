# ALM-38008 Kafka数据目录状态异常<a name="ALM-38008"></a>

## 告警解释<a name="section48693389"></a>

系统每60秒周期性检测Kafka数据目录状态，当检测到某数据目录状态异常时产生该告警。

平滑次数为1，当数据目录状态恢复正常后，告警恢复。

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
<tbody><tr id="row32249861"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p62101938"><a name="p62101938"></a><a name="p62101938"></a>38008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p64201063"><a name="p64201063"></a><a name="p64201063"></a>重要</p>
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
<tbody><tr id="row49144277712"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
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
<tr id="row1888153214599"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17888173211593"><a name="p17888173211593"></a><a name="p17888173211593"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p15888632165911"><a name="p15888632165911"></a><a name="p15888632165911"></a>产生告警的主机名称。</p>
</td>
</tr>
<tr id="row168810355599"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p198811235105916"><a name="p198811235105916"></a><a name="p198811235105916"></a>目录名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1488173575915"><a name="p1488173575915"></a><a name="p1488173575915"></a>产生告警的目录名称。</p>
</td>
</tr>
<tr id="row25522907"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p54089623"><a name="p54089623"></a><a name="p54089623"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19183310"><a name="p19183310"></a><a name="p19183310"></a>Kafka数据目录状态异常。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64000515"></a>

Kafka数据目录状态异常，会导致该数据目录上所有Partition的当前副本下线，多个节点同时出现数据目录状态异常，可能会导致部分Partition不可用。

## 可能原因<a name="section39133729"></a>

-   数据目录权限被篡改。
-   数据目录所在磁盘故障。

## 处理步骤<a name="section1197252215489"></a>

**检查故障的数据目录权限。**

1.  根据告警提示的主机信息，登录到该节点上。
2.  <a name="li33827117154518"></a>查看告警详细信息中所提示的数据目录及其子目录，属组是否为omm:wheel。
    -   是，记录当前节点主机名，并执行[4](#li1741244515411)。
    -   否，执行[3](#li143537363315)。

3.  <a name="li143537363315"></a>恢复数据目录及其子目录的属组为omm:wheel。

**检查数据目录所在磁盘是否故障。**

1.  <a name="li1741244515411"></a>使用omm用户，在所提示的数据目录的上一级目录下，进行创建、删除文件测试，看能够正常读写磁盘。
    -   是，执行[6](#li1941234515411)。
    -   否，执行[5](#li9412845846)。

2.  <a name="li9412845846"></a>更换或者修复数据目录所在磁盘，保证其可以正常读写。
3.  <a name="li1941234515411"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 实例”，进入Kafka实例页面，重启[2](#li33827117154518)中主机名上的Broker实例。
4.  等待Broker启动完成之后，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li24672963154518)。


**收集故障信息。**

1.  <a name="li24672963154518"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section15715480"></a>

无。

