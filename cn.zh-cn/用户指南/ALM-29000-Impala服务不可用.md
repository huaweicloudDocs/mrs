# ALM-29000 Impala服务不可用<a name="ALM-29000"></a>

## 告警解释<a name="section8280367"></a>

以30s为周期检测Impala服务状态，当检测到Impala服务异常时，系统产生此告警。

当系统检测到Impala服务恢复正常，或告警处理完成时，告警解除。

## 告警属性<a name="section7414445"></a>

<a name="table45079949"></a>
<table><thead align="left"><tr id="row5683496"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p57710042"><a name="p57710042"></a><a name="p57710042"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p44001849"><a name="p44001849"></a><a name="p44001849"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7380012"><a name="p7380012"></a><a name="p7380012"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row60910108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p16488194717492"><a name="p16488194717492"></a><a name="p16488194717492"></a>29000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p588994817496"><a name="p588994817496"></a><a name="p588994817496"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p34071398"><a name="p34071398"></a><a name="p34071398"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66730009"></a>

<a name="table8319831"></a>
<table><thead align="left"><tr id="row40868022"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p21975462"><a name="p21975462"></a><a name="p21975462"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p35182007"><a name="p35182007"></a><a name="p35182007"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row594512751512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p8838358184914"><a name="p8838358184914"></a><a name="p8838358184914"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p837170125015"><a name="p837170125015"></a><a name="p837170125015"></a>产生告警的集群名称</p>
</td>
</tr>
<tr id="row1558195005814"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2558115015581"><a name="p2558115015581"></a><a name="p2558115015581"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1558185055810"><a name="p1558185055810"></a><a name="p1558185055810"></a>产生告警的服务名称</p>
</td>
</tr>
<tr id="row75507459583"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p18550114518585"><a name="p18550114518585"></a><a name="p18550114518585"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13550134575817"><a name="p13550134575817"></a><a name="p13550134575817"></a>产生告警的角色名称</p>
</td>
</tr>
<tr id="row262316413588"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p562384175813"><a name="p562384175813"></a><a name="p562384175813"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1262318410582"><a name="p1262318410582"></a><a name="p1262318410582"></a>产生告警的主机名</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63699172"></a>

Impala服务异常，无法通过FusionInsight Manager对Impala进行集群操作，无法使用Impala服务功能。

## 可能原因<a name="section36421639"></a>

-   Hive服务异常
-   KrbServer服务异常
-   Impala进程故障

## 处理步骤<a name="section2425015133012"></a>

**检查Impala依赖的服务是否正常**

1.  在FusionInsight Manager首页，选择“集群 \> 服务”，查看Hive、KrbServer是否已停止。
    -   是，启动已停止的服务，执行[2](#li4280171311238)。
    -   否，执行[3](#li4780161772310)。

2.  <a name="li4280171311238"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中，查看“Impala服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[3](#li4780161772310)。

3.  <a name="li4780161772310"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中，查看是否存在告警“ALM-16004 Hive服务不可用”，“ALM-25500 KrbServer服务不可用”。
    -   是，执行[4](#li54181588154249)。
    -   否，执行[5](#li5408163052918)。

4.  <a name="li54181588154249"></a>参考“ALM-16004 Hive服务不可用”，“ALM-25500 KrbServer服务不可用”告警帮助文档进行处理后，检查本告警是否清除。
    -   是，处理完毕。
    -   否，执行[5](#li5408163052918)。


**检查Impala进程是否正常**。

1.  <a name="li5408163052918"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中查看是否存在“ALM-12007 进程故障”告警。
    -   是，执行[6](#li14910220522)。
    -   否，执行[7](#li17918612154249)。

2.  <a name="li14910220522"></a>参考“ALM-12007进程故障”告警帮助文档进行处理后，检出本告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li17918612154249)。


**收集故障信息。**

1.  <a name="li17918612154249"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Impala”。
3.  单击右上角的![](figures/zh-cn_image_0295310731.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无

