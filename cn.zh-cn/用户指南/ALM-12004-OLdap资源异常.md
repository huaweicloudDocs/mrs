# ALM-12004 OLdap资源异常<a name="ZH-CN_TOPIC_0191883066"></a>

## 告警解释<a name="zh-cn_topic_0191813880_section3478476142447"></a>

当Manager中的Ldap资源异常时，系统产生此告警。

当Manager中的Ldap资源恢复，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813880_section2597747614251"></a>

<a name="zh-cn_topic_0191813880_table4792085811565"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813880_row5971015911565"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813880_p5638735211565"><a name="zh-cn_topic_0191813880_p5638735211565"></a><a name="zh-cn_topic_0191813880_p5638735211565"></a><strong id="zh-cn_topic_0191813880_b4487441411565"><a name="zh-cn_topic_0191813880_b4487441411565"></a><a name="zh-cn_topic_0191813880_b4487441411565"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813880_p1053122811565"><a name="zh-cn_topic_0191813880_p1053122811565"></a><a name="zh-cn_topic_0191813880_p1053122811565"></a><strong id="zh-cn_topic_0191813880_b6631905311565"><a name="zh-cn_topic_0191813880_b6631905311565"></a><a name="zh-cn_topic_0191813880_b6631905311565"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813880_p4621108011565"><a name="zh-cn_topic_0191813880_p4621108011565"></a><a name="zh-cn_topic_0191813880_p4621108011565"></a><strong id="zh-cn_topic_0191813880_b2150502011565"><a name="zh-cn_topic_0191813880_b2150502011565"></a><a name="zh-cn_topic_0191813880_b2150502011565"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813880_row5197070311565"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813880_p2276762511565"><a name="zh-cn_topic_0191813880_p2276762511565"></a><a name="zh-cn_topic_0191813880_p2276762511565"></a>12004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813880_p1108111911565"><a name="zh-cn_topic_0191813880_p1108111911565"></a><a name="zh-cn_topic_0191813880_p1108111911565"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813880_p3654860111565"><a name="zh-cn_topic_0191813880_p3654860111565"></a><a name="zh-cn_topic_0191813880_p3654860111565"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813880_section6147292214259"></a>

<a name="zh-cn_topic_0191813880_table3497377011565"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813880_row2906640111565"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813880_p2388048411565"><a name="zh-cn_topic_0191813880_p2388048411565"></a><a name="zh-cn_topic_0191813880_p2388048411565"></a><strong id="zh-cn_topic_0191813880_b385748311565"><a name="zh-cn_topic_0191813880_b385748311565"></a><a name="zh-cn_topic_0191813880_b385748311565"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813880_p3886656311565"><a name="zh-cn_topic_0191813880_p3886656311565"></a><a name="zh-cn_topic_0191813880_p3886656311565"></a><strong id="zh-cn_topic_0191813880_b523364411565"><a name="zh-cn_topic_0191813880_b523364411565"></a><a name="zh-cn_topic_0191813880_b523364411565"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813880_row2929125711565"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813880_p2766261511565"><a name="zh-cn_topic_0191813880_p2766261511565"></a><a name="zh-cn_topic_0191813880_p2766261511565"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813880_p636410111565"><a name="zh-cn_topic_0191813880_p636410111565"></a><a name="zh-cn_topic_0191813880_p636410111565"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813880_row3185877511565"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813880_p3772912711565"><a name="zh-cn_topic_0191813880_p3772912711565"></a><a name="zh-cn_topic_0191813880_p3772912711565"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813880_p1909660211565"><a name="zh-cn_topic_0191813880_p1909660211565"></a><a name="zh-cn_topic_0191813880_p1909660211565"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813880_row2898757911565"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813880_p1069483911565"><a name="zh-cn_topic_0191813880_p1069483911565"></a><a name="zh-cn_topic_0191813880_p1069483911565"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813880_p1815969011565"><a name="zh-cn_topic_0191813880_p1815969011565"></a><a name="zh-cn_topic_0191813880_p1815969011565"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813880_section31794279142523"></a>

OLdap资源异常，Manager认证服务不可用，无法对Web上层服务提供安全认证和用户管理功能，可能引起无法登录Manager。

## 可能原因<a name="zh-cn_topic_0191813880_section1159338714264"></a>

Manager中LdapServer进程故障。

## 处理步骤<a name="zh-cn_topic_0191813880_section419646114268"></a>

1.  检查Manager中LdapServer进程是否正常。
    1.  登录主管理节点。
    2.  执行**ps -ef | grep slapd**，查询配置文件位于“$\{BIGDATA\_HOME\}/om-0.0.1/”路径下面的LdapServer资源进程是否正常。

        判断资源正常有两个标识：

        1.  执行**sh $\{BIGDATA\_HOME\}/om-0.0.1/sbin/status-oms.sh**命令后查看到oldap的“ResHAStatus”为“Normal”。
        2.  执行**ps -ef | grep slapd**，可以查看到有端口为21750的slapd进程。

        -   是，执行[2](#zh-cn_topic_0191813880_li15577384153414)。
        -   否，执行[3](#zh-cn_topic_0191813880_li572522141314)。

2.  <a name="zh-cn_topic_0191813880_li15577384153414"></a>执行_**kill -2**_ _LdapServer进程pid_，等待20秒以后，HA会自动启动Oldap进程。观察当前OLdap资源状态是否正常。
    -   是，操作结束。
    -   否，执行[3](#zh-cn_topic_0191813880_li572522141314)。

3.  <a name="zh-cn_topic_0191813880_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813880_section17602037153553"></a>

无。

