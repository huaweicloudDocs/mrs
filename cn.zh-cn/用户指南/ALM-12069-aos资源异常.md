# ALM-12069 aos资源异常<a name="ALM-12069"></a>

## 告警解释<a name="section10369415133116"></a>

HA每81秒周期性检测Manager的aos资源。当HA连续2次检测到aos资源异常时，产生该告警。

当HA检测到aos资源正常后，告警恢复。

aos资源为单主资源，一般资源异常会导致主备倒换，看到告警时，基本已经主备倒换，并在新主环境上启动新的acs资源，告警恢复。该告警用于提示用户，Manager主备倒换的原因。

## 告警属性<a name="section8323192410322"></a>

<a name="table1479793583212"></a>
<table><thead align="left"><tr id="row107991735133210"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p18799183583212"><a name="p18799183583212"></a><a name="p18799183583212"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p1680123511326"><a name="p1680123511326"></a><a name="p1680123511326"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p1980173523217"><a name="p1980173523217"></a><a name="p1980173523217"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row880183517329"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p108014356328"><a name="p108014356328"></a><a name="p108014356328"></a>12069</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p19802163593213"><a name="p19802163593213"></a><a name="p19802163593213"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p880215356323"><a name="p880215356323"></a><a name="p880215356323"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section652875914327"></a>

<a name="table1090459143316"></a>
<table><thead align="left"><tr id="row190429173313"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p129062911339"><a name="p129062911339"></a><a name="p129062911339"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10906093332"><a name="p10906093332"></a><a name="p10906093332"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row17451710103612"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row18907109203311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p99095916333"><a name="p99095916333"></a><a name="p99095916333"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4909159173310"><a name="p4909159173310"></a><a name="p4909159173310"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row4910691332"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39101953320"><a name="p39101953320"></a><a name="p39101953320"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5911189173310"><a name="p5911189173310"></a><a name="p5911189173310"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row59118923315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p0912169123319"><a name="p0912169123319"></a><a name="p0912169123319"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p169131916332"><a name="p169131916332"></a><a name="p169131916332"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2990133614335"></a>

-   Manager主备倒换。
-   aos进程持续重启，可能引起无法登录FusionInsight Manager。

## 可能原因<a name="section950130153414"></a>

aos进程异常。

## 处理步骤<a name="section1541443812244"></a>

**检查aos进程是否异常。**

1.  打开FusionInsight Manager页面，在告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895369.png)，查看该告警的主机名称。
2.  以**root**用户登录该告警的主机地址，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行命令**su - omm**，执行**sh $\{BIGDATA\_HOME\}/om-server/OMS/workspace0/ha/module/hacom/script/status\_ha.sh**，查询当前HA管理的aos资源状态是否正常（单机模式下面，aos资源为normal状态；双机模式下，aos资源在主节点为normal状态，在备节点为stopped状态。）
    -   是，执行[6](#li6152360163635)。
    -   否，执行[4](#li139657016249)。

4.  <a name="li139657016249"></a>执行命令**vi $BIGDATA\_LOG\_HOME/omm/oms/ha/scriptlog/aos.log**，查看ha的aos资源日志，是否有关键字“ERROR”，分析日志查看资源异常原因并修复。
5.  等待五分钟，查看告警是否恢复。
    -   是，操作结束。
    -   否，执行[6](#li6152360163635)。


**收集故障信息。**

1.  <a name="li6152360163635"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“Controller”和“OmmServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895883.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section129720811223"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section3193699"></a>

无。

