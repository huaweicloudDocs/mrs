# ALM-27001 DBService服务不可用<a name="alm_27001"></a>

## 告警解释<a name="zh-cn_topic_0191813879_section48728718"></a>

告警模块按30秒周期检测DBService服务状态。当DBService服务不可用时产生该告警。

DBService服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0191813879_section35905280"></a>

<a name="zh-cn_topic_0191813879_table60151347"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813879_row54597003"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813879_p60281111"><a name="zh-cn_topic_0191813879_p60281111"></a><a name="zh-cn_topic_0191813879_p60281111"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813879_p50931783"><a name="zh-cn_topic_0191813879_p50931783"></a><a name="zh-cn_topic_0191813879_p50931783"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813879_p31833731"><a name="zh-cn_topic_0191813879_p31833731"></a><a name="zh-cn_topic_0191813879_p31833731"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813879_row28395444"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813879_p18329666"><a name="zh-cn_topic_0191813879_p18329666"></a><a name="zh-cn_topic_0191813879_p18329666"></a>27001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813879_p8307988"><a name="zh-cn_topic_0191813879_p8307988"></a><a name="zh-cn_topic_0191813879_p8307988"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813879_p1858451"><a name="zh-cn_topic_0191813879_p1858451"></a><a name="zh-cn_topic_0191813879_p1858451"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813879_section54712068"></a>

<a name="zh-cn_topic_0191813879_table16316838"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813879_row11041789"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813879_p21969731"><a name="zh-cn_topic_0191813879_p21969731"></a><a name="zh-cn_topic_0191813879_p21969731"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813879_p34717793"><a name="zh-cn_topic_0191813879_p34717793"></a><a name="zh-cn_topic_0191813879_p34717793"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813879_row60677888"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813879_p15961928"><a name="zh-cn_topic_0191813879_p15961928"></a><a name="zh-cn_topic_0191813879_p15961928"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813879_p17847776"><a name="zh-cn_topic_0191813879_p17847776"></a><a name="zh-cn_topic_0191813879_p17847776"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813879_row26412257"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813879_p59018101"><a name="zh-cn_topic_0191813879_p59018101"></a><a name="zh-cn_topic_0191813879_p59018101"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813879_p15736877"><a name="zh-cn_topic_0191813879_p15736877"></a><a name="zh-cn_topic_0191813879_p15736877"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813879_row7414170"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813879_p63676932"><a name="zh-cn_topic_0191813879_p63676932"></a><a name="zh-cn_topic_0191813879_p63676932"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813879_p57557895"><a name="zh-cn_topic_0191813879_p57557895"></a><a name="zh-cn_topic_0191813879_p57557895"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813879_section22646572"></a>

数据库服务不可用，无法对上层服务提供数据入库、查询等功能，使部分服务异常。

## 可能原因<a name="zh-cn_topic_0191813879_section2492560"></a>

-   浮动IP不存在。
-   没有主DBServer实例。
-   主备DBServer进程都异常。

## 处理步骤<a name="zh-cn_topic_0191813879_section22433040"></a>

1.  检查集群环境中是否存在浮动IP。
    1.  登录MRS集群详情页面，选择“组件管理”。
    2.  单击“DBService \> 实例”。
    3.  查看是否有主实例存在。
        -   是，执行[1.d](#zh-cn_topic_0191813879_step111)。
        -   否，执行[2.a](#zh-cn_topic_0191813879_step88)。

    4.  <a name="zh-cn_topic_0191813879_step111"></a>选择主DBServer实例，记录IP地址。
    5.  登录上述IP所在主机，执行**ifconfig**命令查看DBService的浮动IP在该节点是否存在。
        -   是，执行[1.f](#zh-cn_topic_0191813879_checkfloatip)。
        -   否，执行[2.a](#zh-cn_topic_0191813879_step88)。

    6.  <a name="zh-cn_topic_0191813879_checkfloatip"></a>执行**ping** _浮动IP__地址_命令检查DBService的浮动IP的状态，是否能ping通。
        -   是，执行[1.g](#zh-cn_topic_0191813879_findfloatip)。
        -   否，执行[2.a](#zh-cn_topic_0191813879_step88)。

    7.  <a name="zh-cn_topic_0191813879_findfloatip"></a>登录DBService浮动IP所在主机，执行**ifconfig** _interface_ **down**命令删除浮动IP地址。
    8.  单击“组件管理 \> DBService \> 更多 \> 重启服务”重启DBService服务，检查是否启动成功。
        -   是，执行[1.i](#zh-cn_topic_0191813879_resumealarm1)。
        -   否，执行[2.a](#zh-cn_topic_0191813879_step88)。

    9.  <a name="zh-cn_topic_0191813879_resumealarm1"></a>等待约两分钟，查看告警列表中的DBService服务不可用告警是否恢复。
        -   是，处理完毕。
        -   否，执行[步骤13](#zh-cn_topic_0191813879_loginact)。

2.  检查主DBServer实例状态。
    1.  <a name="zh-cn_topic_0191813879_step88"></a>选择角色状态异常的DBServer实例，记录IP地址。
    2.  在“告警管理”页面，查看是否有上述IP所在主机DBServer实例ALM-12007 进程故障告警产生。
        -   是，执行[2.c](#zh-cn_topic_0191813879_alarm27001)。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

    3.  <a name="zh-cn_topic_0191813879_alarm27001"></a>按ALM-12007 进程故障提供的步骤处理该告警。
    4.  等待5分钟，查看告警列表中的DBService服务不可用告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

3.  检查主备DBServer数据库进程状态。
    1.  <a name="zh-cn_topic_0191813879_loginact"></a>登录DBService浮动IP所在主机，执行**sudo su - root**和**su - omm**命令切换至**omm**用户，使用**cd $\{BIGDATA\_HOME\}/FusionInsight/dbservice/**进入DBService服务的安装目录。
    2.  执行**sh sbin/status-dbserver.sh**命令查看DBService的主备HA进程状态，状态是否查询成功。
        -   是，执行[3.c](#zh-cn_topic_0191813879_loginactive)。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

    3.  <a name="zh-cn_topic_0191813879_loginactive"></a>查看主备HA进程是否都处于abnormal状态。
        -   是，执行[3.d](#zh-cn_topic_0191813879_recoverdb)。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

    4.  <a name="zh-cn_topic_0191813879_recoverdb"></a>单击“组件管理 \> DBService \> 更多 \> 重启服务”重启DBService服务，检查是否启动成功。
        -   是，执行[3.e](#zh-cn_topic_0191813879_resumealarm)。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

    5.  <a name="zh-cn_topic_0191813879_resumealarm"></a>等待约两分钟，查看告警列表中的DBService服务不可用告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813879_li572522141314)。

4.  <a name="zh-cn_topic_0191813879_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813879_section570775"></a>

无。

