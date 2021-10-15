# ALM-12011 Manager主备节点同步数据异常<a name="ALM-12011"></a>

## 告警解释<a name="section663215"></a>

系统按60秒周期检测Manager主备节点同步数据情况，当备Manager无法与主Manager同步文件时，产生该告警。

当备Manager与主Manager正常同步文件时，告警恢复。

## 告警属性<a name="section5968939"></a>

<a name="table10143581"></a>
<table><thead align="left"><tr id="row61411666"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p8289053"><a name="p8289053"></a><a name="p8289053"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p324668"><a name="p324668"></a><a name="p324668"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p26298136"><a name="p26298136"></a><a name="p26298136"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row49774232"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p5180964"><a name="p5180964"></a><a name="p5180964"></a>12011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p17004965"><a name="p17004965"></a><a name="p17004965"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p35224963"><a name="p35224963"></a><a name="p35224963"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section53720453"></a>

<a name="table34649765"></a>
<table><thead align="left"><tr id="row18974100"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p60507121"><a name="p60507121"></a><a name="p60507121"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p2129750"><a name="p2129750"></a><a name="p2129750"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row16272251424"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row38292076"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14650458"><a name="p14650458"></a><a name="p14650458"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45836489"><a name="p45836489"></a><a name="p45836489"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row9875225"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p61695723"><a name="p61695723"></a><a name="p61695723"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p31297682"><a name="p31297682"></a><a name="p31297682"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row13243689"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66105898"><a name="p66105898"></a><a name="p66105898"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52977523"><a name="p52977523"></a><a name="p52977523"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section13722030"></a>

备Manager的配置文件没有更新。主备倒换之后，一些配置可能会丢失。Manager及部分组件可能无法正常运行。

## 可能原因<a name="section56389407"></a>

主备Manager节点间链路中断，/srv/BigData/LocalBackup目录存储空间已满。

## 处理步骤<a name="section37742617"></a>

**检查主备Manager服务器间的网络是否正常。**

1.  在FusionInsight Manager页面，选择“运维 \> 告警 \> 告警”，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，获取该告警的备Manager（即Peer Manager）IP地址。
2.  以**root**用户登录主Manager服务器，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行**ping **_备Manager IP__地址_命令检查备Manager服务器是否可达。
    -   是，执行[6](#li18750195794719)。
    -   否，执行[4](#li63406959171631)。

4.  <a name="li63406959171631"></a>联系网络管理员查看是否为网络故障。
    -   是，执行[5](#li19595462171631)。
    -   否，执行[6](#li18750195794719)。

5.  <a name="li19595462171631"></a>修复网络故障，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#li18750195794719)。


**检查/srv/BigData/LocalBackup目录存储空间是否已满**

1.  <a name="li18750195794719"></a>执行以下命令检查“/srv/BigData/LocalBackup”目录存储空间是否已满：

    **df -hl /srv/BigData/LocalBackup**

    -   是，执行[7](#li7740734122412)。
    -   否，执行[10](#li42141433171631)。

2.  <a name="li7740734122412"></a>执行以下命令清理不需要的备份文件：

    **rm -rf **_待清理的目录路径_

    例如：

    **rm -rf /srv/BigData/LocalBackup/0/default-oms\_20191211143443**

3.  在FusionInsight Manager界面，选择“运维 \> 备份恢复 \> 备份管理”。

    在待操作备份任务右侧“操作”栏下，单击“配置”，修改“最大备份数”减少备份文件集数量。

4.  等待大约1分钟，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[10](#li42141433171631)。


**收集故障信息。**

1.  <a name="li42141433171631"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选如下节点信息，单击“确定”。
    -   OmmServer
    -   Controller
    -   NodeAgent

3.  单击右上角的![](figures/zh-cn_image_0263895607.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section4139237"></a>

无。

