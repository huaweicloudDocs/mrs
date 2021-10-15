# ALM-24000 Flume服务不可用<a name="ALM-24000"></a>

## 告警解释<a name="section62655484"></a>

告警模块按180秒周期检测Flume服务状态，当检测到Flume服务异常时，系统产生此告警。

当系统检测到Flume服务恢复正常，且告警处理完成时，告警恢复。

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
<tbody><tr id="row45960172"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31786413"><a name="p31786413"></a><a name="p31786413"></a>24000</p>
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

当Flume服务不可用时，Flume不能正常工作，数据传输业务中断。

## 可能原因<a name="section40843970"></a>

Flume实例全部故障。

## 处理步骤<a name="section32051411"></a>

1.  以**omm**用户登录Flume实例所在节点，执行**ps -ef|grep "flume.role=server"**命令查看当前节点是否存在flume进程。
    -   是，执行[3](#li22384958105055)。
    -   否，重启Flume故障实例或Flume服务，执行[2](#li62139541105055)。

2.  <a name="li62139541105055"></a>在告警列表中查看“Flume服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[3](#li22384958105055)。


**收集故障信息。**

1.  <a name="li22384958105055"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Flume”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20027245"></a>

无。

