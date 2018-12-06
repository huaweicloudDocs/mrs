# Kerberos认证集群中的用户与权限<a name="ZH-CN_TOPIC_0050661065"></a>

## 概述<a name="zh-cn_topic_0043021163_section2380567811551"></a>

-   **MRS集群用户**

    MRS Manager中的安全帐号，包含用户名、密码等属性，MRS集群的使用者通过这类用户访问集群中的资源。每个启用Kerberos认证的MRS集群可以有多个用户。

-   **MRS集群角色**

    用户在实际使用MRS集群时需根据业务场景获取访问资源的权限，访问资源的权限是定义到MRS集群对象上的。集群的角色就是包含一个或者多个权限的集合。例如，HDFS中某个目录的访问权限，需要在指定的目录上配置，并保存在角色中。


MRS Manager支持MRS集群用户权限管理功能，使权限管理与用户管理更加直观、易用。

-   权限管理：使用RBAC（Role-Based Access Control）方式，即基于角色授予权限，形成权限的集合。用户通过分配一个或多个已授权的角色取得对应的权限。
-   用户管理：使用Manager统一管理MRS集群用户，并通过Kerberos协议认证用户，LDAP协议存储用户信息。

## 权限管理<a name="zh-cn_topic_0043021163_section1289689211625"></a>

MRS集群提供的权限包括MRS Manager和各组件（例如HDFS、HBase、Hive和Yarn等）的操作维护权限，在实际应用时需根据业务场景为各用户分别配置不同权限。为了提升权限管理的易用性，MRS Manager引入角色的功能，通过选取指定的权限并统一授予角色，以权限集合的形式实现了权限集中查看和管理，提升了权限管理的易用性和用户体验。

角色可以理解为集中一个或多个权限的逻辑体，角色被授予指定的权限，用户通过绑定角色获得对应的权限。

一个角色可以有多个权限，一个用户可以绑定多个角色。

-   角色1：授予操作权限A和B，用户a和用户b通过绑定角色1取得对应的权限。
-   角色2：授予操作权限C，用户c和用户d通过绑定角色2取得对应的权限。
-   角色3：授予操作权限D和F，用户a通过绑定配角色3取得对应的权限。

例如，MRS集群用户绑定了管理员角色，那么这个用户成为MRS集群的管理员用户。

MRS Manager界面显示系统默认创建的角色如[表1](#zh-cn_topic_0043021163_table52563166113718)所示。

**表 1**  Manager默认角色与描述

<a name="zh-cn_topic_0043021163_table52563166113718"></a>
<table><thead align="left"><tr id="zh-cn_topic_0043021163_row17438475113718"><th class="cellrowborder" valign="top" width="30.5%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0043021163_p3230390113718"><a name="zh-cn_topic_0043021163_p3230390113718"></a><a name="zh-cn_topic_0043021163_p3230390113718"></a><strong id="zh-cn_topic_0043021163_b50894640114316"><a name="zh-cn_topic_0043021163_b50894640114316"></a><a name="zh-cn_topic_0043021163_b50894640114316"></a>默认角色</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.5%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0043021163_p60335050113718"><a name="zh-cn_topic_0043021163_p60335050113718"></a><a name="zh-cn_topic_0043021163_p60335050113718"></a><strong id="zh-cn_topic_0043021163_b28825136114316"><a name="zh-cn_topic_0043021163_b28825136114316"></a><a name="zh-cn_topic_0043021163_b28825136114316"></a>角色描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0043021163_row55300845113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p50183498113718"><a name="zh-cn_topic_0043021163_p50183498113718"></a><a name="zh-cn_topic_0043021163_p50183498113718"></a>default</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p38331527113718"><a name="zh-cn_topic_0043021163_p38331527113718"></a><a name="zh-cn_topic_0043021163_p38331527113718"></a>为租户创建的角色。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row9439425113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p26395954113718"><a name="zh-cn_topic_0043021163_p26395954113718"></a><a name="zh-cn_topic_0043021163_p26395954113718"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p57697495113718"><a name="zh-cn_topic_0043021163_p57697495113718"></a><a name="zh-cn_topic_0043021163_p57697495113718"></a>Manager管理员，具有Manager的管理权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row49515408113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p51325151113718"><a name="zh-cn_topic_0043021163_p51325151113718"></a><a name="zh-cn_topic_0043021163_p51325151113718"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p63696599113718"><a name="zh-cn_topic_0043021163_p63696599113718"></a><a name="zh-cn_topic_0043021163_p63696599113718"></a>Manager审计员，具有查看和管理审计信息的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row36398481113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p62595864113718"><a name="zh-cn_topic_0043021163_p62595864113718"></a><a name="zh-cn_topic_0043021163_p62595864113718"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p37100252113718"><a name="zh-cn_topic_0043021163_p37100252113718"></a><a name="zh-cn_topic_0043021163_p37100252113718"></a>Manager操作员，具有除租户管理、配置管理和集群管理功能以外的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row65466816113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p1211881113718"><a name="zh-cn_topic_0043021163_p1211881113718"></a><a name="zh-cn_topic_0043021163_p1211881113718"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p31053571113718"><a name="zh-cn_topic_0043021163_p31053571113718"></a><a name="zh-cn_topic_0043021163_p31053571113718"></a>Manager查看员，具有查看系统概览，服务，主机，告警，审计日志等信息的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row11046690113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p22366696113718"><a name="zh-cn_topic_0043021163_p22366696113718"></a><a name="zh-cn_topic_0043021163_p22366696113718"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p66871922113718"><a name="zh-cn_topic_0043021163_p66871922113718"></a><a name="zh-cn_topic_0043021163_p66871922113718"></a>系统管理员，具有Manager的管理权限及所有服务管理员的所有权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row64976388113718"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p28596080113718"><a name="zh-cn_topic_0043021163_p28596080113718"></a><a name="zh-cn_topic_0043021163_p28596080113718"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p34581140113718"><a name="zh-cn_topic_0043021163_p34581140113718"></a><a name="zh-cn_topic_0043021163_p34581140113718"></a>Manager租户管理页面查看角色，具有Manager“租户管理”页面查看权限。</p>
</td>
</tr>
</tbody>
</table>

通过MRS Manager创建角色时支持对Manager和组件进行授权管理，如[表2](#zh-cn_topic_0043021163_table734810114141)所示。

**表 2**  Manager与组件授权管理

<a name="zh-cn_topic_0043021163_table734810114141"></a>
<table><thead align="left"><tr id="zh-cn_topic_0043021163_row37513948114141"><th class="cellrowborder" valign="top" width="30.5%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0043021163_p18730914114141"><a name="zh-cn_topic_0043021163_p18730914114141"></a><a name="zh-cn_topic_0043021163_p18730914114141"></a><strong id="zh-cn_topic_0043021163_b65109519114313"><a name="zh-cn_topic_0043021163_b65109519114313"></a><a name="zh-cn_topic_0043021163_b65109519114313"></a>授权类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.5%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0043021163_p40809065114141"><a name="zh-cn_topic_0043021163_p40809065114141"></a><a name="zh-cn_topic_0043021163_p40809065114141"></a><strong id="zh-cn_topic_0043021163_b39379673114313"><a name="zh-cn_topic_0043021163_b39379673114313"></a><a name="zh-cn_topic_0043021163_b39379673114313"></a>授权描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0043021163_row17199960114141"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p51019544114141"><a name="zh-cn_topic_0043021163_p51019544114141"></a><a name="zh-cn_topic_0043021163_p51019544114141"></a>Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p14937434114141"><a name="zh-cn_topic_0043021163_p14937434114141"></a><a name="zh-cn_topic_0043021163_p14937434114141"></a>Manager访问与登录权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row219178114141"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p17753419114141"><a name="zh-cn_topic_0043021163_p17753419114141"></a><a name="zh-cn_topic_0043021163_p17753419114141"></a>HBase</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p28740829114141"><a name="zh-cn_topic_0043021163_p28740829114141"></a><a name="zh-cn_topic_0043021163_p28740829114141"></a>HBase管理员权限设置和表、列族授权。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row57340871114141"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p14099013114141"><a name="zh-cn_topic_0043021163_p14099013114141"></a><a name="zh-cn_topic_0043021163_p14099013114141"></a>HDFS</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p1169415114141"><a name="zh-cn_topic_0043021163_p1169415114141"></a><a name="zh-cn_topic_0043021163_p1169415114141"></a>HDFS中的目录和文件授权。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row5169418114149"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p46524763114149"><a name="zh-cn_topic_0043021163_p46524763114149"></a><a name="zh-cn_topic_0043021163_p46524763114149"></a>Hive</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0043021163_ul48139190114219"></a><a name="zh-cn_topic_0043021163_ul48139190114219"></a><ul id="zh-cn_topic_0043021163_ul48139190114219"><li>Hive Admin Privilege<p id="zh-cn_topic_0043021163_p59361260114221"><a name="zh-cn_topic_0043021163_p59361260114221"></a><a name="zh-cn_topic_0043021163_p59361260114221"></a>Hive管理员权限。</p>
</li><li>Hive Read Write Privileges<p id="zh-cn_topic_0043021163_p52106194114222"><a name="zh-cn_topic_0043021163_p52106194114222"></a><a name="zh-cn_topic_0043021163_p52106194114222"></a>Hive数据表管理权限，可设置与管理已创建的表的数据操作权限。</p>
</li></ul>
</td>
</tr>
<tr id="row3228907510047"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="p6527826910047"><a name="p6527826910047"></a><a name="p6527826910047"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="p5304845610047"><a name="p5304845610047"></a><a name="p5304845610047"></a>存储策略管理员权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row13858501114149"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p57617649114149"><a name="zh-cn_topic_0043021163_p57617649114149"></a><a name="zh-cn_topic_0043021163_p57617649114149"></a>Yarn</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0043021163_ul20531139114212"></a><a name="zh-cn_topic_0043021163_ul20531139114212"></a><ul id="zh-cn_topic_0043021163_ul20531139114212"><li>Cluster Admin Operations<p id="zh-cn_topic_0043021163_p43821164114215"><a name="zh-cn_topic_0043021163_p43821164114215"></a><a name="zh-cn_topic_0043021163_p43821164114215"></a>Yarn管理员权限。</p>
</li><li>Scheduler Queue<p id="zh-cn_topic_0043021163_p29524702114215"><a name="zh-cn_topic_0043021163_p29524702114215"></a><a name="zh-cn_topic_0043021163_p29524702114215"></a>队列资源管理。</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 用户管理<a name="zh-cn_topic_0043021163_section8888400114348"></a>

支持Kerberos认证的MRS集群使用Kerberos协议和LDAP（Lightweight Directory Access Protocol）协议来配合工作，实现用户管理：

-   Kerberos用于在用户登录MRS Manager与使用组件客户端时认证用户身份，未启用Kerberos认证的集群则不认证用户身份。
-   LDAP用于存储用户记录、用户组信息与权限信息等用户信息。

MRS集群支持在MRS Manager执行创建用户或者修改用户等任务时，系统自动完成更新Kerberos和LDAP的用户数据，用户登录MRS Manager或使用组件客户端时，系统自动完成认证用户身份和获取用户信息。这样一方面保证了用户管理的安全性，另一方面简化了用户管理的操作任务。MRS Manager还提供了用户组功能，可对单个或多个用户进行分类管理：

-   用户组为一批用户的集合，可对用户进行分类管理。系统中的用户可以单独存在也可以加入到某个用户组中。
-   对已分配角色的用户组来说，当用户添加到该组时，用户组分配的角色权限将授权给用户。

MRS Manager界面显示系统默认创建的用户组如所示。

**表 3**  Manager默认用户组与描述

<a name="zh-cn_topic_0043021163_table4192888914739"></a>
<table><thead align="left"><tr id="zh-cn_topic_0043021163_row1165911814739"><th class="cellrowborder" valign="top" width="30.693069306930692%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0043021163_p486451514739"><a name="zh-cn_topic_0043021163_p486451514739"></a><a name="zh-cn_topic_0043021163_p486451514739"></a><strong id="zh-cn_topic_0043021163_b248510514747"><a name="zh-cn_topic_0043021163_b248510514747"></a><a name="zh-cn_topic_0043021163_b248510514747"></a>用户组名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.3069306930693%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0043021163_p5848142014739"><a name="zh-cn_topic_0043021163_p5848142014739"></a><a name="zh-cn_topic_0043021163_p5848142014739"></a><strong id="zh-cn_topic_0043021163_b6681131014747"><a name="zh-cn_topic_0043021163_b6681131014747"></a><a name="zh-cn_topic_0043021163_b6681131014747"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0043021163_row3937457814739"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p3522422014739"><a name="zh-cn_topic_0043021163_p3522422014739"></a><a name="zh-cn_topic_0043021163_p3522422014739"></a>hadoop</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p3458955414739"><a name="zh-cn_topic_0043021163_p3458955414739"></a><a name="zh-cn_topic_0043021163_p3458955414739"></a>将用户加入此用户组，可获得所有Yarn队列的任务提交权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row4287053814739"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p4996155014739"><a name="zh-cn_topic_0043021163_p4996155014739"></a><a name="zh-cn_topic_0043021163_p4996155014739"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p2035377914739"><a name="zh-cn_topic_0043021163_p2035377914739"></a><a name="zh-cn_topic_0043021163_p2035377914739"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row3017088214739"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p2792241614739"><a name="zh-cn_topic_0043021163_p2792241614739"></a><a name="zh-cn_topic_0043021163_p2792241614739"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p4712323414739"><a name="zh-cn_topic_0043021163_p4712323414739"></a><a name="zh-cn_topic_0043021163_p4712323414739"></a>将用户加入此用户组，可以使用Hive。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043021163_row1655753414739"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043021163_p6609186814739"><a name="zh-cn_topic_0043021163_p6609186814739"></a><a name="zh-cn_topic_0043021163_p6609186814739"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043021163_p5184109514739"><a name="zh-cn_topic_0043021163_p5184109514739"></a><a name="zh-cn_topic_0043021163_p5184109514739"></a>将用户加入此用户组，可获得HBase、HDFS和Yarn的管理员权限，并可以使用Hive。</p>
</td>
</tr>
<tr id="row4213721515591"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p4369061915591"><a name="p4369061915591"></a><a name="p4369061915591"></a>flume</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p4927928715591"><a name="p4927928715591"></a><a name="p4927928715591"></a>普通用户组。添加到该用户组的用户无任何额外权限。</p>
</td>
</tr>
<tr id="row25758293172716"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p59914707172716"><a name="p59914707172716"></a><a name="p59914707172716"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p67054959172716"><a name="p67054959172716"></a><a name="p67054959172716"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限,才能访问对应Topic。</p>
</td>
</tr>
<tr id="row63807695172720"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p17144598172720"><a name="p17144598172720"></a><a name="p17144598172720"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p45064911172720"><a name="p45064911172720"></a><a name="p45064911172720"></a>添加入本组的用户，拥有所有Topic的读写权限。</p>
</td>
</tr>
<tr id="row19151905172724"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p24563126172724"><a name="p24563126172724"></a><a name="p24563126172724"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p51132992172724"><a name="p51132992172724"></a><a name="p51132992172724"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="row6240879172730"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p8235702172730"><a name="p8235702172730"></a><a name="p8235702172730"></a>storm</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p47040623172730"><a name="p47040623172730"></a><a name="p47040623172730"></a>Storm的普通用户组，属于该组的用户拥有提交拓扑和管理属于自己的拓扑的权限。</p>
</td>
</tr>
<tr id="row39302212172734"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p2038471172734"><a name="p2038471172734"></a><a name="p2038471172734"></a>stormadmin</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p66085272172734"><a name="p66085272172734"></a><a name="p66085272172734"></a>Storm的管理员用户组，属于该组的用户拥有提交拓扑和管理所有拓扑的权限。</p>
</td>
</tr>
</tbody>
</table>

启用Kerberos认证的MRS集群默认创建“admin“用户帐号，用于集群管理员维护集群。

## 流程概述<a name="zh-cn_topic_0043021163_section2852318214857"></a>

在实际业务中，MRS集群用户需要先明确大数据的业务场景，规划集群用户对应的权限。然后在Manager界面创建角色，并设置角色包含的权限以匹配业务的需求。如果需要统一管理单个或多个相同业务场景中的用户，MRS Manager提供了用户组的功能，管理员可以创建用户组。

>![](public_sys-resources/icon-note.gif) **说明：**   
>如果角色设置HDFS、HBase、Hive或Yarn各组件的权限，仅可以使用组件自身功能。如果还需要使用MRS Manager，请在角色中添加对应的Manager权限。  

**图 1**  创建用户流程示意<a name="zh-cn_topic_0043021163_fig62902698143821"></a>  
![](figures/创建用户流程示意.jpg "创建用户流程示意")

