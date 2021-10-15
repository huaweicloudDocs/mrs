# ALM-45275 Ranger服务不可用<a name="ALM-45275"></a>

## 告警解释<a name="section62655484"></a>

告警模块按180秒周期检测Ranger服务状态，当检测到Ranger服务异常时，系统产生此告警。

当系统检测到Ranger服务恢复正常，且告警处理完成时，告警恢复。

## 告警属性<a name="section27028451"></a>

<a name="table8158160"></a>
<table><thead align="left"><tr id="row12642219"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p17386810"><a name="p17386810"></a><a name="p17386810"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p66154394"><a name="p66154394"></a><a name="p66154394"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p56905715"><a name="p56905715"></a><a name="p56905715"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row45960172"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31786413"><a name="p31786413"></a><a name="p31786413"></a>45275</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p24562655"><a name="p24562655"></a><a name="p24562655"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p43418025"><a name="p43418025"></a><a name="p43418025"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section41929471"></a>

<a name="table27199156"></a>
<table><thead align="left"><tr id="row33667339"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p42699947"><a name="p42699947"></a><a name="p42699947"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p36143663"><a name="p36143663"></a><a name="p36143663"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1613632821611"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row41955584"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57135782"><a name="p57135782"></a><a name="p57135782"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row44459997"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46923229"><a name="p46923229"></a><a name="p46923229"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row19655878"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46093362"><a name="p46093362"></a><a name="p46093362"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section41820921"></a>

当Ranger服务不可用时，Ranger无法正常工作，Ranger原生UI无法访问。

## 可能原因<a name="section40843970"></a>

-   Ranger服务所依赖内部服务DBService故障。
-   RangerAdmin角色实例异常。

## 处理步骤<a name="section734118525279"></a>

**检查DBService进程状态。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”页面，查看系统是否上报“ALM-27001 DBService服务不可用”告警。
    -   是，执行[2](#li24833719161349)。
    -   否，执行[3](#li43869374161349)。

2.  <a name="li24833719161349"></a>参考“ALM-27001 DBService服务不可用”告警帮助指导对DBService服务状态异常进行处理，待DBService告警消除后，查看“Ranger服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[3](#li43869374161349)。


**检查所有RangerAdmin实例。**

1.  <a name="li43869374161349"></a>以**omm**用户登录RangerAdmin实例所在节点，执行**ps -ef|grep "proc\_rangeradmin"**命令查看当前节点是否存在RangerAdmin进程。
    -   是，执行[5](#li16749195915615)。
    -   否，重启RangerAdmin故障实例或Ranger服务，执行[4](#li60791811161349)。

2.  <a name="li60791811161349"></a>在告警列表中查看“Ranger服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[5](#li16749195915615)。


**收集故障信息。**

1.  <a name="li16749195915615"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Ranger”。
3.  单击右上角的![](figures/zh-cn_image_0293180907.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20027245"></a>

无。

