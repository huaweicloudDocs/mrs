# ALM-12004 OLdap资源异常<a name="ALM-12004"></a>

## 告警解释<a name="section6391158614659"></a>

系统按60秒周期检测Ldap资源，当连续6次监控到Manager中的Ldap资源异常时，系统产生此告警。

当Manager中的Ldap资源恢复，且告警处理完成时，告警恢复。

## 告警属性<a name="section16822331476"></a>

<a name="table2868344914724"></a>
<table><thead align="left"><tr id="row5089024414724"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p2846909114724"><a name="p2846909114724"></a><a name="p2846909114724"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p2429505914724"><a name="p2429505914724"></a><a name="p2429505914724"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p2174278014724"><a name="p2174278014724"></a><a name="p2174278014724"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row1633472514724"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p4804431014724"><a name="p4804431014724"></a><a name="p4804431014724"></a>12004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p6638389614724"><a name="p6638389614724"></a><a name="p6638389614724"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p838648214724"><a name="p838648214724"></a><a name="p838648214724"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section3623622214739"></a>

<a name="table2919978114746"></a>
<table><thead align="left"><tr id="row5697878314746"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p5187867714746"><a name="p5187867714746"></a><a name="p5187867714746"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p4142330814746"><a name="p4142330814746"></a><a name="p4142330814746"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1075817421424"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row6695364314746"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p5453602714746"><a name="p5453602714746"></a><a name="p5453602714746"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5534208414746"><a name="p5534208414746"></a><a name="p5534208414746"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row2831670914746"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1195205314746"><a name="p1195205314746"></a><a name="p1195205314746"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2859220914746"><a name="p2859220914746"></a><a name="p2859220914746"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row5600329614746"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p3997311414746"><a name="p3997311414746"></a><a name="p3997311414746"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1659682114746"><a name="p1659682114746"></a><a name="p1659682114746"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2114602614816"></a>

Ldap资源异常，Manager和组件WebUI认证服务不可用，无法对Web上层服务提供安全认证和用户管理功能，可能引起无法登录Manager和组件的WebUI。

## 可能原因<a name="section6192636114824"></a>

Manager中LdapServer进程故障。

## 处理步骤<a name="section4591490714833"></a>

**检查Manager中LdapServer进程是否正常。**

1.  以**omm**用户登录集群中的Manager所在节点主机。

    可以通过登录FusionInsight Manager浮动IP节点，执行**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**命令来查看当前Manager的双机信息。

2.  执行**ps -ef | grep slapd**，查询配置文件位于“$\{BIGDATA\_HOME\}/om-server/om/”路径下面的LdapServer资源进程是否正常。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >判断资源正常有两个标识：
    >1.  执行完**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**命令后查看到oldap的“ResHAStatus”为“Normal”。
    >2.  执行**ps -ef | grep slapd**，可以查看到有端口为21750的slapd进程。
    >    -   是，执行[3](#li3228273916249)。
    >    -   否，执行[4](#li21656734162417)。

3.  <a name="li3228273916249"></a>执行**kill -2** _ldap__进程pid_，等待20s以后，HA会自动启动OLdap进程。观察当前OLdap资源状态是否正常。
    -   是，操作结束。
    -   否，执行[4](#li21656734162417)。


**收集故障信息。**

1.  <a name="li21656734162417"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OmsLdapServer”和“OmmServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895607.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section1691434914125"></a>

无。

