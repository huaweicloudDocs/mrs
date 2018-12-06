# Kerberos认证集群中的默认用户清单<a name="ZH-CN_TOPIC_0050661062"></a>

## 用户分类<a name="zh-cn_topic_0039905375_section1350246891412"></a>

MRS集群提供以下3类用户，请用户定期修改密码，不建议使用默认密码。

<a name="zh-cn_topic_0039905375_table5775715391436"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row642250091436"><th class="cellrowborder" valign="top" width="21.5%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0039905375_p6076518391436"><a name="zh-cn_topic_0039905375_p6076518391436"></a><a name="zh-cn_topic_0039905375_p6076518391436"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="78.5%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0039905375_p5371575991436"><a name="zh-cn_topic_0039905375_p5371575991436"></a><a name="zh-cn_topic_0039905375_p5371575991436"></a>使用说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row4045403691436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p337902391436"><a name="zh-cn_topic_0039905375_p337902391436"></a><a name="zh-cn_topic_0039905375_p337902391436"></a>系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="zh-cn_topic_0039905375_ul2384601491436"></a><a name="zh-cn_topic_0039905375_ul2384601491436"></a><ul id="zh-cn_topic_0039905375_ul2384601491436"><li>通过MRS Manager创建，是MRS集群操作运维与业务场景中主要使用的用户，包含两种类型：<a name="zh-cn_topic_0039905375_ul2293894691436"></a><a name="zh-cn_topic_0039905375_ul2293894691436"></a><ul id="zh-cn_topic_0039905375_ul2293894691436"><li>“人机”用户：用于在MRS Manager的操作运维场景，以及在组件客户端操作的场景。</li><li>“机机”用户：用于MRS集群应用开发的场景。</li></ul>
</li><li>用于OMS系统进程运行的用户。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3922484291436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5880583791436"><a name="zh-cn_topic_0039905375_p5880583791436"></a><a name="zh-cn_topic_0039905375_p5880583791436"></a>系统内部用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p1624131791436"><a name="zh-cn_topic_0039905375_p1624131791436"></a><a name="zh-cn_topic_0039905375_p1624131791436"></a>MRS集群提供的用于进程通信、保存用户组信息和关联用户权限的内部用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4047833191436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p2856068791436"><a name="zh-cn_topic_0039905375_p2856068791436"></a><a name="zh-cn_topic_0039905375_p2856068791436"></a>数据库用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="zh-cn_topic_0039905375_ul1872352891436"></a><a name="zh-cn_topic_0039905375_ul1872352891436"></a><ul id="zh-cn_topic_0039905375_ul1872352891436"><li>用于OMS数据库管理和数据访问的用户。</li><li>用于业务组件（Hive、Hue、Loader和DBservice）数据库的用户。</li></ul>
</td>
</tr>
</tbody>
</table>

## 系统用户<a name="zh-cn_topic_0039905375_section4899716991522"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   MRS集群需要使用操作系统中ldap用户，此帐号不能删除，否则可能导致集群无法正常工作。密码管理策略由操作用户维护。  
>-   首次修改“ommdba“和“omm“用户需要执行重置密码操作。找回密码后建议定期修改。  

<a name="zh-cn_topic_0039905375_table2048716191613"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row5261606891613"><th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0039905375_p602860391613"><a name="zh-cn_topic_0039905375_p602860391613"></a><a name="zh-cn_topic_0039905375_p602860391613"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0039905375_p2654810491613"><a name="zh-cn_topic_0039905375_p2654810491613"></a><a name="zh-cn_topic_0039905375_p2654810491613"></a>用户名称</p>
</th>
<th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0039905375_p3460826591613"><a name="zh-cn_topic_0039905375_p3460826591613"></a><a name="zh-cn_topic_0039905375_p3460826591613"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.730000000000004%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0039905375_p3554159991613"><a name="zh-cn_topic_0039905375_p3554159991613"></a><a name="zh-cn_topic_0039905375_p3554159991613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row2951092391613"><td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p1209398491613"><a name="zh-cn_topic_0039905375_p1209398491613"></a><a name="zh-cn_topic_0039905375_p1209398491613"></a>MRS集群系统管理员</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2595444291613"><a name="zh-cn_topic_0039905375_p2595444291613"></a><a name="zh-cn_topic_0039905375_p2595444291613"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3191050591613"><a name="zh-cn_topic_0039905375_p3191050591613"></a><a name="zh-cn_topic_0039905375_p3191050591613"></a>在集群创建时由用户指定。</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p5228284691613"><a name="zh-cn_topic_0039905375_p5228284691613"></a><a name="zh-cn_topic_0039905375_p5228284691613"></a>MRS Manager的管理员。</p>
<p id="p2240466591526"><a name="p2240466591526"></a><a name="p2240466591526"></a>此外还具有以下权限：</p>
<a name="ul77702491530"></a><a name="ul77702491530"></a><ul id="ul77702491530"><li>具有HDFS、ZooKeeper普通用户的权限。</li><li>具有提交、查询Mapreduce、YARN任务的权限，以及YARN队列管理权限和访问YARN WebUI的权限。</li><li>Storm中，具有提交、查询、激活、去激活、重分配、删除拓扑的权限，可以操作所有拓扑。</li><li>Kafka服务中，具有创建、删除、授权、Reassign、消费、写入、查询主题的权限。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row2103859791613"><td class="cellrowborder" rowspan="2" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p5841586591613"><a name="zh-cn_topic_0039905375_p5841586591613"></a><a name="zh-cn_topic_0039905375_p5841586591613"></a>MRS集群节点操作系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p776857791613"><a name="zh-cn_topic_0039905375_p776857791613"></a><a name="zh-cn_topic_0039905375_p776857791613"></a>ommdba</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3400838291613"><a name="zh-cn_topic_0039905375_p3400838291613"></a><a name="zh-cn_topic_0039905375_p3400838291613"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p5913467291613"><a name="zh-cn_topic_0039905375_p5913467291613"></a><a name="zh-cn_topic_0039905375_p5913467291613"></a>创建MRS集群系统数据库的用户。在管理节点生成，属于操作系统用户，无需设置为统一的密码。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row102437291613"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p1002157391613"><a name="zh-cn_topic_0039905375_p1002157391613"></a><a name="zh-cn_topic_0039905375_p1002157391613"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5196772491613"><a name="zh-cn_topic_0039905375_p5196772491613"></a><a name="zh-cn_topic_0039905375_p5196772491613"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4720845591613"><a name="zh-cn_topic_0039905375_p4720845591613"></a><a name="zh-cn_topic_0039905375_p4720845591613"></a>MRS集群系统的内部运行用户。在全部节点生成，属于操作系统用户，无需设置为统一的密码。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row61051706104714"><td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p46241193104714"><a name="zh-cn_topic_0039905375_p46241193104714"></a><a name="zh-cn_topic_0039905375_p46241193104714"></a>MRS集群作业运行用户</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p54549185104714"><a name="zh-cn_topic_0039905375_p54549185104714"></a><a name="zh-cn_topic_0039905375_p54549185104714"></a>yarn_user</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p56407849104714"><a name="zh-cn_topic_0039905375_p56407849104714"></a><a name="zh-cn_topic_0039905375_p56407849104714"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p5633033104714"><a name="zh-cn_topic_0039905375_p5633033104714"></a><a name="zh-cn_topic_0039905375_p5633033104714"></a>MRS集群执行作业的内部用户。在Core节点生成。</p>
</td>
</tr>
</tbody>
</table>

## 系统内部用户<a name="zh-cn_topic_0039905375_section2666743891758"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>以下系统内部用户不能删除，否则可能导致集群或组件无法正常工作。  

<a name="zh-cn_topic_0039905375_table5360730491813"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row5525661591813"><th class="cellrowborder" valign="top" width="20.47%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0039905375_p1657240491813"><a name="zh-cn_topic_0039905375_p1657240491813"></a><a name="zh-cn_topic_0039905375_p1657240491813"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="26.479999999999997%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0039905375_p1518296591813"><a name="zh-cn_topic_0039905375_p1518296591813"></a><a name="zh-cn_topic_0039905375_p1518296591813"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="13.83%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0039905375_p2588103591813"><a name="zh-cn_topic_0039905375_p2588103591813"></a><a name="zh-cn_topic_0039905375_p2588103591813"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="39.22%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0039905375_p2004840691813"><a name="zh-cn_topic_0039905375_p2004840691813"></a><a name="zh-cn_topic_0039905375_p2004840691813"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row6391399691813"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p4354815091813"><a name="zh-cn_topic_0039905375_p4354815091813"></a><a name="zh-cn_topic_0039905375_p4354815091813"></a>Kerberos管理员</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p3698261391813"><a name="zh-cn_topic_0039905375_p3698261391813"></a><a name="zh-cn_topic_0039905375_p3698261391813"></a>kadmin/admin</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4438689091813"><a name="zh-cn_topic_0039905375_p4438689091813"></a><a name="zh-cn_topic_0039905375_p4438689091813"></a>KAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p3702603591813"><a name="zh-cn_topic_0039905375_p3702603591813"></a><a name="zh-cn_topic_0039905375_p3702603591813"></a>用于增加、删除、修改及查询Kerberos上的用户帐号。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row972336591813"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p4157758191813"><a name="zh-cn_topic_0039905375_p4157758191813"></a><a name="zh-cn_topic_0039905375_p4157758191813"></a>OMS Kerberos管理员</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6008810691813"><a name="zh-cn_topic_0039905375_p6008810691813"></a><a name="zh-cn_topic_0039905375_p6008810691813"></a>kadmin/admin</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4060063691813"><a name="zh-cn_topic_0039905375_p4060063691813"></a><a name="zh-cn_topic_0039905375_p4060063691813"></a>KAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p2569773291813"><a name="zh-cn_topic_0039905375_p2569773291813"></a><a name="zh-cn_topic_0039905375_p2569773291813"></a>用于增加、删除、修改及查询OMS Kerberos上的用户帐号。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5655620991813"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p2038332091813"><a name="zh-cn_topic_0039905375_p2038332091813"></a><a name="zh-cn_topic_0039905375_p2038332091813"></a>LDAP管理员</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5410584391813"><a name="zh-cn_topic_0039905375_p5410584391813"></a><a name="zh-cn_topic_0039905375_p5410584391813"></a>cn=root,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4965648391813"><a name="zh-cn_topic_0039905375_p4965648391813"></a><a name="zh-cn_topic_0039905375_p4965648391813"></a>LdapChangeMe@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p4976320891813"><a name="zh-cn_topic_0039905375_p4976320891813"></a><a name="zh-cn_topic_0039905375_p4976320891813"></a>用于增加、删除、修改及查询LDAP用户帐号信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4658417891813"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p2502827891813"><a name="zh-cn_topic_0039905375_p2502827891813"></a><a name="zh-cn_topic_0039905375_p2502827891813"></a>OMS LDAP管理员</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6225553691813"><a name="zh-cn_topic_0039905375_p6225553691813"></a><a name="zh-cn_topic_0039905375_p6225553691813"></a>cn=root,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3402559891813"><a name="zh-cn_topic_0039905375_p3402559891813"></a><a name="zh-cn_topic_0039905375_p3402559891813"></a>LdapChangeMe@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p3786886591813"><a name="zh-cn_topic_0039905375_p3786886591813"></a><a name="zh-cn_topic_0039905375_p3786886591813"></a>用于增加、删除、修改及查询OMS LDAP用户帐号信息。</p>
</td>
</tr>
<tr id="row16225016154640"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="p39157918154640"><a name="p39157918154640"></a><a name="p39157918154640"></a>LDAP用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="p17674760154640"><a name="p17674760154640"></a><a name="p17674760154640"></a>cn=pg_search_dn,ou=Users,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="p22369438154640"><a name="p22369438154640"></a><a name="p22369438154640"></a>pg_search_dn@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="p67094090154640"><a name="p67094090154640"></a><a name="p67094090154640"></a>用于查询LDAP中存储的用户和用户组信息。</p>
</td>
</tr>
<tr id="row35037151154640"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="p19437003154640"><a name="p19437003154640"></a><a name="p19437003154640"></a>OMS LDAP用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="p30893444154640"><a name="p30893444154640"></a><a name="p30893444154640"></a>cn=pg_search_dn,ou=Users,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="p19341041154640"><a name="p19341041154640"></a><a name="p19341041154640"></a>pg_search_dn@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="p23120507154640"><a name="p23120507154640"></a><a name="p23120507154640"></a>用于查询OMS LDAP中存储的用户和用户组信息。</p>
</td>
</tr>
<tr id="row063815344713"><td class="cellrowborder" rowspan="2" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="p79977146477"><a name="p79977146477"></a><a name="p79977146477"></a>LDAP管理帐户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="p4639536471"><a name="p4639536471"></a><a name="p4639536471"></a>cn=krbkdc,ou=Users,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="p14639133194716"><a name="p14639133194716"></a><a name="p14639133194716"></a>LdapChangeMe@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="p76395384713"><a name="p76395384713"></a><a name="p76395384713"></a>用于查询Kerberos组件认证帐户信息。</p>
</td>
</tr>
<tr id="row78831673477"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p4883973472"><a name="p4883973472"></a><a name="p4883973472"></a>cn=krbadmin,ou=Users,dc=hadoop,dc=com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p98833784711"><a name="p98833784711"></a><a name="p98833784711"></a>LdapChangeMe@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p788312734716"><a name="p788312734716"></a><a name="p788312734716"></a>用于增加、删除、修改及查询Kerberos组件认证帐户信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4892632611738"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p360949511738"><a name="zh-cn_topic_0039905375_p360949511738"></a><a name="zh-cn_topic_0039905375_p360949511738"></a>MRS集群查询用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2393371711738"><a name="zh-cn_topic_0039905375_p2393371711738"></a><a name="zh-cn_topic_0039905375_p2393371711738"></a>executor</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p5958293511738"><a name="zh-cn_topic_0039905375_p5958293511738"></a><a name="zh-cn_topic_0039905375_p5958293511738"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p6148845411738"><a name="zh-cn_topic_0039905375_p6148845411738"></a><a name="zh-cn_topic_0039905375_p6148845411738"></a>用于在MRS管理控制台查询启用Kerberos认证的集群信息。</p>
</td>
</tr>
<tr id="row153983532101"><td class="cellrowborder" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="p1839985313106"><a name="p1839985313106"></a><a name="p1839985313106"></a>MRS集群组件查询用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="p1939965313109"><a name="p1939965313109"></a><a name="p1939965313109"></a>knox</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="p6399953101010"><a name="p6399953101010"></a><a name="p6399953101010"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="p339915321016"><a name="p339915321016"></a><a name="p339915321016"></a>用于MRS管理控制台查询组件信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4296949792445"><td class="cellrowborder" rowspan="29" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6564563192445"><a name="zh-cn_topic_0039905375_p6564563192445"></a><a name="zh-cn_topic_0039905375_p6564563192445"></a>组件运行用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6340788292445"><a name="zh-cn_topic_0039905375_p6340788292445"></a><a name="zh-cn_topic_0039905375_p6340788292445"></a>hdfs</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p1126761092445"><a name="zh-cn_topic_0039905375_p1126761092445"></a><a name="zh-cn_topic_0039905375_p1126761092445"></a>Hdfs@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p1956917693029"><a name="zh-cn_topic_0039905375_p1956917693029"></a><a name="zh-cn_topic_0039905375_p1956917693029"></a>HDFS系统管理员，用户权限：</p>
<a name="zh-cn_topic_0039905375_ol4747349693036"></a><a name="zh-cn_topic_0039905375_ol4747349693036"></a><ol id="zh-cn_topic_0039905375_ol4747349693036"><li>文件系统操作权限：<a name="zh-cn_topic_0039905375_ul1160663193056"></a><a name="zh-cn_topic_0039905375_ul1160663193056"></a><ul id="zh-cn_topic_0039905375_ul1160663193056"><li>查看、修改、创建文件</li><li>查看、创建目录</li><li>查看、修改文件属组</li><li>查看、设置用户磁盘配额</li></ul>
</li><li>HDFS管理操作权限：<a name="zh-cn_topic_0039905375_ul495740629315"></a><a name="zh-cn_topic_0039905375_ul495740629315"></a><ul id="zh-cn_topic_0039905375_ul495740629315"><li>查看webUI页面状态</li><li>查看、设置HDFS主备状态</li><li>进入、退出HDFS安全模式</li><li>检查HDFS文件系统</li></ul>
</li></ol>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row787279192452"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p2199514592452"><a name="zh-cn_topic_0039905375_p2199514592452"></a><a name="zh-cn_topic_0039905375_p2199514592452"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2608987392452"><a name="zh-cn_topic_0039905375_p2608987392452"></a><a name="zh-cn_topic_0039905375_p2608987392452"></a>Hbase@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4515077293126"><a name="zh-cn_topic_0039905375_p4515077293126"></a><a name="zh-cn_topic_0039905375_p4515077293126"></a>HBase系统管理员，用户权限：</p>
<a name="zh-cn_topic_0039905375_ul4893231993137"></a><a name="zh-cn_topic_0039905375_ul4893231993137"></a><ul id="zh-cn_topic_0039905375_ul4893231993137"><li>集群管理权限: 表的Enable、Disable操作，触发MajorCompact，ACL操作</li><li>授权或回收权限，集群关闭等操作相关的权限</li><li>表管理权限: 建表、修改表、删除表等操作权限</li><li>数据管理权限：表级别、列族级别以及列级别的数据读写权限</li><li>访问HBase WebUI的权限</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1720200792452"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p1428632492452"><a name="zh-cn_topic_0039905375_p1428632492452"></a><a name="zh-cn_topic_0039905375_p1428632492452"></a>mapred</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p4859926192452"><a name="zh-cn_topic_0039905375_p4859926192452"></a><a name="zh-cn_topic_0039905375_p4859926192452"></a>Mapred@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4387389993156"><a name="zh-cn_topic_0039905375_p4387389993156"></a><a name="zh-cn_topic_0039905375_p4387389993156"></a>MapReduce系统管理员，用户权限：</p>
<a name="zh-cn_topic_0039905375_ul497516859322"></a><a name="zh-cn_topic_0039905375_ul497516859322"></a><ul id="zh-cn_topic_0039905375_ul497516859322"><li>提交、停止和查看MapReduce任务的权限</li><li>修改Yarn配置参数的权限</li><li>访问Yarn、MapReduce WebUI的权限</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4184534392452"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6416197092452"><a name="zh-cn_topic_0039905375_p6416197092452"></a><a name="zh-cn_topic_0039905375_p6416197092452"></a>spark</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5989395692452"><a name="zh-cn_topic_0039905375_p5989395692452"></a><a name="zh-cn_topic_0039905375_p5989395692452"></a>Spark@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3736819293438"><a name="zh-cn_topic_0039905375_p3736819293438"></a><a name="zh-cn_topic_0039905375_p3736819293438"></a>Spark系统管理员，用户权限：</p>
<a name="zh-cn_topic_0039905375_ul2674375693459"></a><a name="zh-cn_topic_0039905375_ul2674375693459"></a><ul id="zh-cn_topic_0039905375_ul2674375693459"><li>访问Spark WebUI的权限</li><li>提交Spark任务的权限</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row2336659492452"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p772789692452"><a name="zh-cn_topic_0039905375_p772789692452"></a><a name="zh-cn_topic_0039905375_p772789692452"></a>oms/manager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p3553436292452"><a name="zh-cn_topic_0039905375_p3553436292452"></a><a name="zh-cn_topic_0039905375_p3553436292452"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p475841792452"><a name="zh-cn_topic_0039905375_p475841792452"></a><a name="zh-cn_topic_0039905375_p475841792452"></a>用于Controller和NodeAgent认证的用户，拥有“supergroup”组权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3072790293512"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6467739193512"><a name="zh-cn_topic_0039905375_p6467739193512"></a><a name="zh-cn_topic_0039905375_p6467739193512"></a>backup/manager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p1901528093512"><a name="zh-cn_topic_0039905375_p1901528093512"></a><a name="zh-cn_topic_0039905375_p1901528093512"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p387575093512"><a name="zh-cn_topic_0039905375_p387575093512"></a><a name="zh-cn_topic_0039905375_p387575093512"></a>用于运行备份恢复任务的用户，拥有“supergroup”组权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row602936293512"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p325794593512"><a name="zh-cn_topic_0039905375_p325794593512"></a><a name="zh-cn_topic_0039905375_p325794593512"></a>hdfs/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p3476054793512"><a name="zh-cn_topic_0039905375_p3476054793512"></a><a name="zh-cn_topic_0039905375_p3476054793512"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p1152972994043"><a name="zh-cn_topic_0039905375_p1152972994043"></a><a name="zh-cn_topic_0039905375_p1152972994043"></a>HDFS系统启动用户，用户权限：</p>
<a name="zh-cn_topic_0039905375_ol6149284794043"></a><a name="zh-cn_topic_0039905375_ol6149284794043"></a><ol id="zh-cn_topic_0039905375_ol6149284794043"><li>文件系统操作权限：<a name="zh-cn_topic_0039905375_ul6319022794043"></a><a name="zh-cn_topic_0039905375_ul6319022794043"></a><ul id="zh-cn_topic_0039905375_ul6319022794043"><li>查看、修改、创建文件</li><li>查看、创建目录</li><li>查看、修改文件属组</li><li>查看、设置用户磁盘配额</li></ul>
</li><li>HDFS管理操作权限：<a name="zh-cn_topic_0039905375_ul5273852494043"></a><a name="zh-cn_topic_0039905375_ul5273852494043"></a><ul id="zh-cn_topic_0039905375_ul5273852494043"><li>查看webUI页面状态</li><li>查看、设置HDFS主备状态</li><li>进入、退出HDFS安全模式</li><li>检查HDFS文件系统</li></ul>
</li></ol>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6685251293512"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6259636293512"><a name="zh-cn_topic_0039905375_p6259636293512"></a><a name="zh-cn_topic_0039905375_p6259636293512"></a>mapred/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5559821393512"><a name="zh-cn_topic_0039905375_p5559821393512"></a><a name="zh-cn_topic_0039905375_p5559821393512"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p1064966894013"><a name="zh-cn_topic_0039905375_p1064966894013"></a><a name="zh-cn_topic_0039905375_p1064966894013"></a>MapReduce系统启动用户，用户权限：</p>
<a name="zh-cn_topic_0039905375_ul1260352794016"></a><a name="zh-cn_topic_0039905375_ul1260352794016"></a><ul id="zh-cn_topic_0039905375_ul1260352794016"><li>提交、停止和查看MapReduce任务的权限</li><li>修改Yarn配置参数的权限</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1957862293512"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p5624261593512"><a name="zh-cn_topic_0039905375_p5624261593512"></a><a name="zh-cn_topic_0039905375_p5624261593512"></a>mr_zk/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p4326756293512"><a name="zh-cn_topic_0039905375_p4326756293512"></a><a name="zh-cn_topic_0039905375_p4326756293512"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p798294693512"><a name="zh-cn_topic_0039905375_p798294693512"></a><a name="zh-cn_topic_0039905375_p798294693512"></a>用于MapReduce访问ZooKeeper。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1227306493544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p3231083393544"><a name="zh-cn_topic_0039905375_p3231083393544"></a><a name="zh-cn_topic_0039905375_p3231083393544"></a>hbase/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6158608293544"><a name="zh-cn_topic_0039905375_p6158608293544"></a><a name="zh-cn_topic_0039905375_p6158608293544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p381898593544"><a name="zh-cn_topic_0039905375_p381898593544"></a><a name="zh-cn_topic_0039905375_p381898593544"></a>HBase系统启动过程用于内部组件之间认证的用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1938531693544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p185469193544"><a name="zh-cn_topic_0039905375_p185469193544"></a><a name="zh-cn_topic_0039905375_p185469193544"></a>hbase/zkclient.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2192870193544"><a name="zh-cn_topic_0039905375_p2192870193544"></a><a name="zh-cn_topic_0039905375_p2192870193544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p5991570893544"><a name="zh-cn_topic_0039905375_p5991570893544"></a><a name="zh-cn_topic_0039905375_p5991570893544"></a>安全集群下，HBase做ZooKeeper认证时使用的用</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5470457193544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p2113446193544"><a name="zh-cn_topic_0039905375_p2113446193544"></a><a name="zh-cn_topic_0039905375_p2113446193544"></a>thrift/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p1628826393544"><a name="zh-cn_topic_0039905375_p1628826393544"></a><a name="zh-cn_topic_0039905375_p1628826393544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p2998656693544"><a name="zh-cn_topic_0039905375_p2998656693544"></a><a name="zh-cn_topic_0039905375_p2998656693544"></a>ThriftServer系统启动用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row557568193544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p2093787493544"><a name="zh-cn_topic_0039905375_p2093787493544"></a><a name="zh-cn_topic_0039905375_p2093787493544"></a>thrift/&lt;hostname&gt;</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p154824593544"><a name="zh-cn_topic_0039905375_p154824593544"></a><a name="zh-cn_topic_0039905375_p154824593544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p2459708493544"><a name="zh-cn_topic_0039905375_p2459708493544"></a><a name="zh-cn_topic_0039905375_p2459708493544"></a>ThriftServer系统访问HBase的用户，拥有HBase所有NameSpace和表的读、写、执行、创建和管理的权限。<em id="zh-cn_topic_0039905375_i4158711811536"><a name="zh-cn_topic_0039905375_i4158711811536"></a><a name="zh-cn_topic_0039905375_i4158711811536"></a>&lt;hostname&gt;</em>表示集群中安装ThriftServer节点的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4837754693544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p337919093544"><a name="zh-cn_topic_0039905375_p337919093544"></a><a name="zh-cn_topic_0039905375_p337919093544"></a>hive/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2494252193544"><a name="zh-cn_topic_0039905375_p2494252193544"></a><a name="zh-cn_topic_0039905375_p2494252193544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p6172277093855"><a name="zh-cn_topic_0039905375_p6172277093855"></a><a name="zh-cn_topic_0039905375_p6172277093855"></a>Hive系统启动过程用于内部组件之间认证的用户，用户权限：</p>
<a name="zh-cn_topic_0039905375_ol475630309394"></a><a name="zh-cn_topic_0039905375_ol475630309394"></a><ol id="zh-cn_topic_0039905375_ol475630309394"><li>Hive管理员权限：<a name="zh-cn_topic_0039905375_ul1743798993914"></a><a name="zh-cn_topic_0039905375_ul1743798993914"></a><ul id="zh-cn_topic_0039905375_ul1743798993914"><li>数据库的创建、删除、修改</li><li>表的创建、查询、修改、删除</li><li>数据的查询、插入、加载</li></ul>
</li><li>HDFS文件操作权限：<a name="zh-cn_topic_0039905375_ul2104079093917"></a><a name="zh-cn_topic_0039905375_ul2104079093917"></a><ul id="zh-cn_topic_0039905375_ul2104079093917"><li>查看、修改、创建文件</li><li>查看、创建目录</li><li>查看、修改文件属组</li></ul>
</li><li>提交、停止MapReduce任务的权限</li></ol>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row63933993544"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6607071793544"><a name="zh-cn_topic_0039905375_p6607071793544"></a><a name="zh-cn_topic_0039905375_p6607071793544"></a>spark/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p3382586593544"><a name="zh-cn_topic_0039905375_p3382586593544"></a><a name="zh-cn_topic_0039905375_p3382586593544"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p248978693544"><a name="zh-cn_topic_0039905375_p248978693544"></a><a name="zh-cn_topic_0039905375_p248978693544"></a>Spark系统启动用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6432043693641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p1330235493641"><a name="zh-cn_topic_0039905375_p1330235493641"></a><a name="zh-cn_topic_0039905375_p1330235493641"></a>spark_zk/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p3522416393641"><a name="zh-cn_topic_0039905375_p3522416393641"></a><a name="zh-cn_topic_0039905375_p3522416393641"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p4991602493641"><a name="zh-cn_topic_0039905375_p4991602493641"></a><a name="zh-cn_topic_0039905375_p4991602493641"></a>用于Spark访问ZooKeeper。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5591037693641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p1312267393641"><a name="zh-cn_topic_0039905375_p1312267393641"></a><a name="zh-cn_topic_0039905375_p1312267393641"></a>zookeeper/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6429718693641"><a name="zh-cn_topic_0039905375_p6429718693641"></a><a name="zh-cn_topic_0039905375_p6429718693641"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p752336993641"><a name="zh-cn_topic_0039905375_p752336993641"></a><a name="zh-cn_topic_0039905375_p752336993641"></a>Zookeeper系统启动用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5845251693641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p4178102793641"><a name="zh-cn_topic_0039905375_p4178102793641"></a><a name="zh-cn_topic_0039905375_p4178102793641"></a>zkcli/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5272300593641"><a name="zh-cn_topic_0039905375_p5272300593641"></a><a name="zh-cn_topic_0039905375_p5272300593641"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3655474893641"><a name="zh-cn_topic_0039905375_p3655474893641"></a><a name="zh-cn_topic_0039905375_p3655474893641"></a>登录ZooKeeper服务器用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1987797016124"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p17461212161210"><a name="zh-cn_topic_0039905375_p17461212161210"></a><a name="zh-cn_topic_0039905375_p17461212161210"></a>kafka/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5072031161210"><a name="zh-cn_topic_0039905375_p5072031161210"></a><a name="zh-cn_topic_0039905375_p5072031161210"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p8181404161210"><a name="zh-cn_topic_0039905375_p8181404161210"></a><a name="zh-cn_topic_0039905375_p8181404161210"></a>Kafka系统进行安全认证的用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3212805916123"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p58663747161210"><a name="zh-cn_topic_0039905375_p58663747161210"></a><a name="zh-cn_topic_0039905375_p58663747161210"></a>storm/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p54143060161210"><a name="zh-cn_topic_0039905375_p54143060161210"></a><a name="zh-cn_topic_0039905375_p54143060161210"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p23511705161210"><a name="zh-cn_topic_0039905375_p23511705161210"></a><a name="zh-cn_topic_0039905375_p23511705161210"></a>Storm系统启动用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3208492116122"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p27272785161210"><a name="zh-cn_topic_0039905375_p27272785161210"></a><a name="zh-cn_topic_0039905375_p27272785161210"></a>storm_zk/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p61612009161210"><a name="zh-cn_topic_0039905375_p61612009161210"></a><a name="zh-cn_topic_0039905375_p61612009161210"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p24516817161210"><a name="zh-cn_topic_0039905375_p24516817161210"></a><a name="zh-cn_topic_0039905375_p24516817161210"></a>用于Worker进程访问ZooKeeper。</p>
</td>
</tr>
<tr id="row4184957485321"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p3437235685321"><a name="p3437235685321"></a><a name="p3437235685321"></a>loader/hadoop.hadoop.com</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p3269742685321"><a name="p3269742685321"></a><a name="p3269742685321"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p3124581685321"><a name="p3124581685321"></a><a name="p3124581685321"></a>Loader系统启动与Kerberos认证用户。</p>
</td>
</tr>
<tr id="row4224963918324"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p4470243418324"><a name="p4470243418324"></a><a name="p4470243418324"></a>HTTP/&lt;hostname&gt;</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p6412741618324"><a name="p6412741618324"></a><a name="p6412741618324"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p2693821418324"><a name="p2693821418324"></a><a name="p2693821418324"></a>用于连接各组件的HTTP接口，&lt;hostname&gt;表示集群中节点主机名。</p>
</td>
</tr>
<tr id="row6216963585436"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p257569485436"><a name="p257569485436"></a><a name="p257569485436"></a>flume</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p730467485436"><a name="p730467485436"></a><a name="p730467485436"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p5480768585436"><a name="p5480768585436"></a><a name="p5480768585436"></a>Flume系统启动用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3036671593641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p4639814193641"><a name="zh-cn_topic_0039905375_p4639814193641"></a><a name="zh-cn_topic_0039905375_p4639814193641"></a>check_ker_M</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p1239866393641"><a name="zh-cn_topic_0039905375_p1239866393641"></a><a name="zh-cn_topic_0039905375_p1239866393641"></a>系统随机生成</p>
</td>
<td class="cellrowborder" rowspan="5" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p6436646193815"><a name="zh-cn_topic_0039905375_p6436646193815"></a><a name="zh-cn_topic_0039905375_p6436646193815"></a>Kerberos内部功能用户，不能删除，不支持密码修改，未安装Kerberos服务的节点无法使用内部帐户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1635818893720"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6272821993720"><a name="zh-cn_topic_0039905375_p6272821993720"></a><a name="zh-cn_topic_0039905375_p6272821993720"></a>K/M</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p4829470793720"><a name="zh-cn_topic_0039905375_p4829470793720"></a><a name="zh-cn_topic_0039905375_p4829470793720"></a>系统随机生成</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3498950193720"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6326061993720"><a name="zh-cn_topic_0039905375_p6326061993720"></a><a name="zh-cn_topic_0039905375_p6326061993720"></a>kadmin/changepw</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5170905293720"><a name="zh-cn_topic_0039905375_p5170905293720"></a><a name="zh-cn_topic_0039905375_p5170905293720"></a>系统随机生成</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3542073793641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p6288149093641"><a name="zh-cn_topic_0039905375_p6288149093641"></a><a name="zh-cn_topic_0039905375_p6288149093641"></a>kadmin/history</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p4727042193641"><a name="zh-cn_topic_0039905375_p4727042193641"></a><a name="zh-cn_topic_0039905375_p4727042193641"></a>系统随机生成</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6151194693641"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p3488722293641"><a name="zh-cn_topic_0039905375_p3488722293641"></a><a name="zh-cn_topic_0039905375_p3488722293641"></a>krbtgt/HADOOP.COM</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p5383935393641"><a name="zh-cn_topic_0039905375_p5383935393641"></a><a name="zh-cn_topic_0039905375_p5383935393641"></a>系统随机生成</p>
</td>
</tr>
</tbody>
</table>

## 用户组信息<a name="zh-cn_topic_0039905375_section2451602294412"></a>

<a name="zh-cn_topic_0039905375_table4858345094426"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row5992778594426"><th class="cellrowborder" valign="top" width="35%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0039905375_p6247853294426"><a name="zh-cn_topic_0039905375_p6247853294426"></a><a name="zh-cn_topic_0039905375_p6247853294426"></a>默认用户组</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0039905375_p2071216494426"><a name="zh-cn_topic_0039905375_p2071216494426"></a><a name="zh-cn_topic_0039905375_p2071216494426"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row6417085794426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5109105994426"><a name="zh-cn_topic_0039905375_p5109105994426"></a><a name="zh-cn_topic_0039905375_p5109105994426"></a>hadoop</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p6677200194426"><a name="zh-cn_topic_0039905375_p6677200194426"></a><a name="zh-cn_topic_0039905375_p6677200194426"></a>将用户加入此用户组，可获得所有Yarn队列的任务提交权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3982303394426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p2411298794426"><a name="zh-cn_topic_0039905375_p2411298794426"></a><a name="zh-cn_topic_0039905375_p2411298794426"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p2971813094426"><a name="zh-cn_topic_0039905375_p2971813094426"></a><a name="zh-cn_topic_0039905375_p2971813094426"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row2686759394426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5040111794426"><a name="zh-cn_topic_0039905375_p5040111794426"></a><a name="zh-cn_topic_0039905375_p5040111794426"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p3636114394426"><a name="zh-cn_topic_0039905375_p3636114394426"></a><a name="zh-cn_topic_0039905375_p3636114394426"></a>将用户加入此用户组，可以使用Hive。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5106871894426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5441094194426"><a name="zh-cn_topic_0039905375_p5441094194426"></a><a name="zh-cn_topic_0039905375_p5441094194426"></a>spark</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p3813936194426"><a name="zh-cn_topic_0039905375_p3813936194426"></a><a name="zh-cn_topic_0039905375_p3813936194426"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1807940494426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p3761075094426"><a name="zh-cn_topic_0039905375_p3761075094426"></a><a name="zh-cn_topic_0039905375_p3761075094426"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p484018194426"><a name="zh-cn_topic_0039905375_p484018194426"></a><a name="zh-cn_topic_0039905375_p484018194426"></a>将用户加入此用户组，可获得HBase、HDFS和Yarn的管理员权限，并可以使用Hive。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4814327194426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5369114894426"><a name="zh-cn_topic_0039905375_p5369114894426"></a><a name="zh-cn_topic_0039905375_p5369114894426"></a>check_sec_ldap</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p1320083994426"><a name="zh-cn_topic_0039905375_p1320083994426"></a><a name="zh-cn_topic_0039905375_p1320083994426"></a>用于内部测试主LDAP是否工作正常。用户组随机存在，每次测试时创建，测试完成后自动删除。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6263501494426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p4075391594426"><a name="zh-cn_topic_0039905375_p4075391594426"></a><a name="zh-cn_topic_0039905375_p4075391594426"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p2472859894426"><a name="zh-cn_topic_0039905375_p2472859894426"></a><a name="zh-cn_topic_0039905375_p2472859894426"></a>租户系统用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5685944494426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p6374617894426"><a name="zh-cn_topic_0039905375_p6374617894426"></a><a name="zh-cn_topic_0039905375_p6374617894426"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p1623546194426"><a name="zh-cn_topic_0039905375_p1623546194426"></a><a name="zh-cn_topic_0039905375_p1623546194426"></a>MRS集群系统管理员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4000397394426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p330046794426"><a name="zh-cn_topic_0039905375_p330046794426"></a><a name="zh-cn_topic_0039905375_p330046794426"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p4531562394426"><a name="zh-cn_topic_0039905375_p4531562394426"></a><a name="zh-cn_topic_0039905375_p4531562394426"></a>MRS Manager系统查看员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4668686194426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p2764259694426"><a name="zh-cn_topic_0039905375_p2764259694426"></a><a name="zh-cn_topic_0039905375_p2764259694426"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p3492654594426"><a name="zh-cn_topic_0039905375_p3492654594426"></a><a name="zh-cn_topic_0039905375_p3492654594426"></a>MRS Manager系统操作员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1047785794426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p2574314494426"><a name="zh-cn_topic_0039905375_p2574314494426"></a><a name="zh-cn_topic_0039905375_p2574314494426"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p5487118994426"><a name="zh-cn_topic_0039905375_p5487118994426"></a><a name="zh-cn_topic_0039905375_p5487118994426"></a>MRS Manager系统审计员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1538133194426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p5229563694426"><a name="zh-cn_topic_0039905375_p5229563694426"></a><a name="zh-cn_topic_0039905375_p5229563694426"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p5115584994426"><a name="zh-cn_topic_0039905375_p5115584994426"></a><a name="zh-cn_topic_0039905375_p5115584994426"></a>MRS Manager系统管理员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row4998309794426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p4519596294426"><a name="zh-cn_topic_0039905375_p4519596294426"></a><a name="zh-cn_topic_0039905375_p4519596294426"></a>compcommon</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p4375014494426"><a name="zh-cn_topic_0039905375_p4375014494426"></a><a name="zh-cn_topic_0039905375_p4375014494426"></a>MRS系统内部组，用于访问集群公共资源。所有系统用户和系统运行用户默认加入此用户组。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row5410077594426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p1640472094426"><a name="zh-cn_topic_0039905375_p1640472094426"></a><a name="zh-cn_topic_0039905375_p1640472094426"></a>default_1000</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p5586241494426"><a name="zh-cn_topic_0039905375_p5586241494426"></a><a name="zh-cn_topic_0039905375_p5586241494426"></a>为租户创建的用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6187792116183"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p59973933161837"><a name="zh-cn_topic_0039905375_p59973933161837"></a><a name="zh-cn_topic_0039905375_p59973933161837"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p26050429161837"><a name="zh-cn_topic_0039905375_p26050429161837"></a><a name="zh-cn_topic_0039905375_p26050429161837"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限,才能访问对应Topic。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6260633816188"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p66063607161837"><a name="zh-cn_topic_0039905375_p66063607161837"></a><a name="zh-cn_topic_0039905375_p66063607161837"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p49551911161837"><a name="zh-cn_topic_0039905375_p49551911161837"></a><a name="zh-cn_topic_0039905375_p49551911161837"></a>添加入本组的用户，拥有所有Topic的读写权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row32950161813"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p18774402161837"><a name="zh-cn_topic_0039905375_p18774402161837"></a><a name="zh-cn_topic_0039905375_p18774402161837"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p44331580161837"><a name="zh-cn_topic_0039905375_p44331580161837"></a><a name="zh-cn_topic_0039905375_p44331580161837"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row30812576161818"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p38358772161837"><a name="zh-cn_topic_0039905375_p38358772161837"></a><a name="zh-cn_topic_0039905375_p38358772161837"></a>storm</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p20052851161837"><a name="zh-cn_topic_0039905375_p20052851161837"></a><a name="zh-cn_topic_0039905375_p20052851161837"></a>Storm的普通用户组，属于该组的用户拥有提交拓扑和管理属于自己的拓扑的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row30961050161831"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p55905211161837"><a name="zh-cn_topic_0039905375_p55905211161837"></a><a name="zh-cn_topic_0039905375_p55905211161837"></a>stormadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p32028232161837"><a name="zh-cn_topic_0039905375_p32028232161837"></a><a name="zh-cn_topic_0039905375_p32028232161837"></a>Storm的管理员用户组，属于该组的用户拥有提交拓扑和管理所有拓扑的权限。</p>
</td>
</tr>
</tbody>
</table>

<a name="zh-cn_topic_0039905375_table211708839453"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row414780159453"><th class="cellrowborder" valign="top" width="35.449999999999996%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0039905375_p108162799453"><a name="zh-cn_topic_0039905375_p108162799453"></a><a name="zh-cn_topic_0039905375_p108162799453"></a>操作系统用户组</p>
</th>
<th class="cellrowborder" valign="top" width="64.55%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0039905375_p315392209453"><a name="zh-cn_topic_0039905375_p315392209453"></a><a name="zh-cn_topic_0039905375_p315392209453"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row321952219453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p412556129453"><a name="zh-cn_topic_0039905375_p412556129453"></a><a name="zh-cn_topic_0039905375_p412556129453"></a>wheel</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p280260249453"><a name="zh-cn_topic_0039905375_p280260249453"></a><a name="zh-cn_topic_0039905375_p280260249453"></a>MRS集群系统内部运行用户“omm”的主组。</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row555154669453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p371687299453"><a name="zh-cn_topic_0039905375_p371687299453"></a><a name="zh-cn_topic_0039905375_p371687299453"></a>ficommon</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p575311339453"><a name="zh-cn_topic_0039905375_p575311339453"></a><a name="zh-cn_topic_0039905375_p575311339453"></a>MRS集群系统公共组，对应“compcommon”，可以访问集群在操作系统中保存的公共资源文件。</p>
</td>
</tr>
</tbody>
</table>

## 数据库用户<a name="zh-cn_topic_0039905375_section4435701994533"></a>

MRS集群系统数据库用户包含OMS数据库用户、DBService数据库用户。

>![](public_sys-resources/icon-note.gif) **说明：**   
>数据库用户不能删除，否则可能导致集群或组件服务无法正常工作。  

<a name="zh-cn_topic_0039905375_table5909699494551"></a>
<table><thead align="left"><tr id="zh-cn_topic_0039905375_row5335053194551"><th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0039905375_p6011172094551"><a name="zh-cn_topic_0039905375_p6011172094551"></a><a name="zh-cn_topic_0039905375_p6011172094551"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0039905375_p6131221094551"><a name="zh-cn_topic_0039905375_p6131221094551"></a><a name="zh-cn_topic_0039905375_p6131221094551"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="20.862086208620862%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0039905375_p1887971294551"><a name="zh-cn_topic_0039905375_p1887971294551"></a><a name="zh-cn_topic_0039905375_p1887971294551"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.933693369336936%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0039905375_p5394219694551"><a name="zh-cn_topic_0039905375_p5394219694551"></a><a name="zh-cn_topic_0039905375_p5394219694551"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0039905375_row1459050794551"><td class="cellrowborder" rowspan="2" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p3107790294551"><a name="zh-cn_topic_0039905375_p3107790294551"></a><a name="zh-cn_topic_0039905375_p3107790294551"></a>OMS数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2538629394551"><a name="zh-cn_topic_0039905375_p2538629394551"></a><a name="zh-cn_topic_0039905375_p2538629394551"></a>ommdba</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p6238201894551"><a name="zh-cn_topic_0039905375_p6238201894551"></a><a name="zh-cn_topic_0039905375_p6238201894551"></a>dbChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p5857122094551"><a name="zh-cn_topic_0039905375_p5857122094551"></a><a name="zh-cn_topic_0039905375_p5857122094551"></a>OMS数据库管理员用户，用于创建、启动和停止等维护操作</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row3626829494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p5536010394551"><a name="zh-cn_topic_0039905375_p5536010394551"></a><a name="zh-cn_topic_0039905375_p5536010394551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p2446842994551"><a name="zh-cn_topic_0039905375_p2446842994551"></a><a name="zh-cn_topic_0039905375_p2446842994551"></a>ChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p1296316094551"><a name="zh-cn_topic_0039905375_p1296316094551"></a><a name="zh-cn_topic_0039905375_p1296316094551"></a>OMS数据库数据访问用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row6479190094551"><td class="cellrowborder" rowspan="4" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p3211675894551"><a name="zh-cn_topic_0039905375_p3211675894551"></a><a name="zh-cn_topic_0039905375_p3211675894551"></a>DBService数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p6332914194551"><a name="zh-cn_topic_0039905375_p6332914194551"></a><a name="zh-cn_topic_0039905375_p6332914194551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p3151964194551"><a name="zh-cn_topic_0039905375_p3151964194551"></a><a name="zh-cn_topic_0039905375_p3151964194551"></a>dbserverAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0039905375_p3795574594551"><a name="zh-cn_topic_0039905375_p3795574594551"></a><a name="zh-cn_topic_0039905375_p3795574594551"></a>DBService组件中GaussDB数据库的管理员用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row1983843494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p3588156294551"><a name="zh-cn_topic_0039905375_p3588156294551"></a><a name="zh-cn_topic_0039905375_p3588156294551"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p103531994551"><a name="zh-cn_topic_0039905375_p103531994551"></a><a name="zh-cn_topic_0039905375_p103531994551"></a>HiveUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p1473320894551"><a name="zh-cn_topic_0039905375_p1473320894551"></a><a name="zh-cn_topic_0039905375_p1473320894551"></a>Hive连接DBService数据库用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0039905375_row36847765111044"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0039905375_p32062047111044"><a name="zh-cn_topic_0039905375_p32062047111044"></a><a name="zh-cn_topic_0039905375_p32062047111044"></a>hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p46889049111044"><a name="zh-cn_topic_0039905375_p46889049111044"></a><a name="zh-cn_topic_0039905375_p46889049111044"></a>HueUser@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0039905375_p39916652111044"><a name="zh-cn_topic_0039905375_p39916652111044"></a><a name="zh-cn_topic_0039905375_p39916652111044"></a>Hue连接DBService数据库用户</p>
</td>
</tr>
<tr id="row35344708105120"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p35509001105120"><a name="p35509001105120"></a><a name="p35509001105120"></a>sqoop</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p57656838105120"><a name="p57656838105120"></a><a name="p57656838105120"></a>SqoopUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p39692320105120"><a name="p39692320105120"></a><a name="p39692320105120"></a>Loader连接DBService数据库的用户</p>
</td>
</tr>
</tbody>
</table>

