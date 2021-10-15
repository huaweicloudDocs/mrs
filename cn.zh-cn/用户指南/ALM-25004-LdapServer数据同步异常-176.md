# ALM-25004 LdapServer数据同步异常<a name="ALM-25004"></a>

## 告警解释<a name="section50606270"></a>

系统按30秒周期性检测LdapServer数据，如果连续12次检测，Manager的主备LdapServer的数据内容都不一致，产生该告警，当两者的数据一致时，对应告警恢复。

系统按30秒周期性检测LdapServer数据，如果连续12次检测，集群中的LdapServer的数据与Manager的LdapServer数据都不一致，产生该告警，当两者的数据一致时，对应告警恢复。

## 告警属性<a name="section52803249"></a>

<a name="table28152143"></a>
<table><thead align="left"><tr id="row20512638"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p50910977"><a name="p50910977"></a><a name="p50910977"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p30148481"><a name="p30148481"></a><a name="p30148481"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p26107877"><a name="p26107877"></a><a name="p26107877"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row34363286"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31962747"><a name="p31962747"></a><a name="p31962747"></a>25004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p38845692"><a name="p38845692"></a><a name="p38845692"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p59493379"><a name="p59493379"></a><a name="p59493379"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section5467196"></a>

<a name="table54234357"></a>
<table><thead align="left"><tr id="row49597124"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p57944109"><a name="p57944109"></a><a name="p57944109"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p62961287"><a name="p62961287"></a><a name="p62961287"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row872212081518"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row66699514"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p65719624"><a name="p65719624"></a><a name="p65719624"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row54605708"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p40940319"><a name="p40940319"></a><a name="p40940319"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row32918557"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22333161"><a name="p22333161"></a><a name="p22333161"></a>产生告警的主机节点信息。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section49204768"></a>

LdapServer数据不一致时，有可能是Manager上的LdapServer数据损坏，也有可能是集群上的LdapServer数据损坏，此时数据损坏的LdapServer进程将无法对外提供服务，影响Manager和集群的认证功能。

## 可能原因<a name="section40189735"></a>

-   LdapServer进程所在的节点网络故障。
-   LdapServer进程异常。
-   OS重启导致的LdapServer数据损坏。

## 处理步骤<a name="section26163296"></a>

**检查LdapServer所在的节点网络是否故障。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”。记录该告警定位信息中的“主机名”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1、IP2、IP3等）。
2.  联系运维人员，登录IP1节点，在这个节点上使用**ping**命令检查该节点与主OMS节点的管理平面IP是否可达。
    -   是，执行[4](#li3735544785829)。
    -   否，执行[3](#li1657677685829)。

3.  <a name="li1657677685829"></a>联系网络管理员恢复网络，然后查看“LdapServer数据同步异常“告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li3735544785829)。


**检查LdapServer进程是否正常。**

1.  <a name="li3735544785829"></a>在FusionInsight Manager的“告警”页面，查看是否有LdapServer的“OLdap资源异常“告警产生。
    -   是，执行[5](#li589235385829)。
    -   否，执行[7](#li56729885829)。

2.  <a name="li589235385829"></a>按照“ALM-12004 OLdap资源异常”提供的步骤处理该告警。
3.  在告警列表中查看“LdapServer数据同步异常“告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li56729885829)。

4.  <a name="li56729885829"></a>在FusionInsight Manager的“告警”页面，查看是否有LdapServer的“进程故障“告警产生。
    -   是，执行[8](#li4595119285829)。
    -   否，执行[10](#li5651967185829)。

5.  <a name="li4595119285829"></a>按照“ALM-12007 进程故障”提供的步骤处理该告警。
6.  在告警列表中查看“LdapServer数据同步异常“告警是否清除。
    -   是，处理完毕。
    -   否，执行[10](#li5651967185829)。


**检查是否存在因为OS重启导致LdapServer数据损坏。**

1.  <a name="li5651967185829"></a>在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”。记录该告警定位信息中的“主机名”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1，IP2，IP3等）。选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer \> 配置”，记录LdapServer的端口号PORT（若告警定位信息中的IP地址为备管理节点IP地址，选择“系统 \> OMS \> oldap \> 修改配置”，记录LdapServer服务侦听端口号）。
2.  以**omm**用户登录IP1节点。
3.  执行以下命令，观察查询出来的内容是否提示有error错误信息。

    **ldapsearch -H ldaps://**_I__P1_:_PORT_** -LLL -x -D cn=root,dc=hadoop,dc=com -W -b ou=Peoples,dc=hadoop,dc=com**

    执行命令后需输入**LDAP**管理员密码，请联系系统管理员获取。

    -   是，执行[13](#li4043724785829)。
    -   否，执行[15](#li467004985829)。

4.  <a name="li4043724785829"></a>使用告警出现日期之前的备份文件进行LdapServer恢复和OMS恢复。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >必须使用同一时间点的OMS和LdapServer备份数据进行恢复，否则可能造成业务和操作失败。当业务正常时需要恢复数据，建议手动备份最新管理数据后，再执行恢复数据操作，否则会丢失从备份时刻到恢复时刻之间的Manager数据。

5.  在告警列表中查看“LdapServer数据同步异常“告警是否清除。
    -   是，处理完毕。
    -   否，执行[15](#li467004985829)。


**收集故障信息。**

1.  <a name="li467004985829"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“LdapServer”和“OmsLdapServer”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section34143078"></a>

无。

