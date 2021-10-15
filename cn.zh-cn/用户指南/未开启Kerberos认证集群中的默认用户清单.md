# 未开启Kerberos认证集群中的默认用户清单<a name="mrs_01_0561"></a>

## 用户分类<a name="zh-cn_topic_0040967540_section1350246891412"></a>

MRS集群提供以下2类用户，请用户定期修改密码，不建议使用默认密码。

<a name="zh-cn_topic_0040967540_table5775715391436"></a>
<table><thead align="left"><tr id="zh-cn_topic_0040967540_row642250091436"><th class="cellrowborder" valign="top" width="21.5%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0040967540_p6076518391436"><a name="zh-cn_topic_0040967540_p6076518391436"></a><a name="zh-cn_topic_0040967540_p6076518391436"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="78.5%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0040967540_p5371575991436"><a name="zh-cn_topic_0040967540_p5371575991436"></a><a name="zh-cn_topic_0040967540_p5371575991436"></a>使用说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0040967540_row4045403691436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p337902391436"><a name="zh-cn_topic_0040967540_p337902391436"></a><a name="zh-cn_topic_0040967540_p337902391436"></a>系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p3798221105832"><a name="zh-cn_topic_0040967540_p3798221105832"></a><a name="zh-cn_topic_0040967540_p3798221105832"></a>用于OMS系统进程运行的用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row4047833191436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p2856068791436"><a name="zh-cn_topic_0040967540_p2856068791436"></a><a name="zh-cn_topic_0040967540_p2856068791436"></a>数据库用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="zh-cn_topic_0040967540_ul1872352891436"></a><a name="zh-cn_topic_0040967540_ul1872352891436"></a><ul id="zh-cn_topic_0040967540_ul1872352891436"><li>用于OMS数据库管理和数据访问的用户。</li><li>用于业务组件（Hive、Loader和DBservice）数据库的用户。</li></ul>
</td>
</tr>
</tbody>
</table>

## 系统用户<a name="zh-cn_topic_0040967540_section4899716991522"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   MRS集群需要使用操作系统中ldap用户，此帐号不能删除，否则可能导致集群无法正常工作。密码管理策略由操作用户维护。
>-   首次修改“ommdba“和“omm“密码需执行重置密码操作。找回密码后建议定期修改。

<a name="zh-cn_topic_0040967540_table2048716191613"></a>
<table><thead align="left"><tr id="zh-cn_topic_0040967540_row5261606891613"><th class="cellrowborder" valign="top" width="24.752475247524753%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0040967540_p602860391613"><a name="zh-cn_topic_0040967540_p602860391613"></a><a name="zh-cn_topic_0040967540_p602860391613"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="17.82178217821782%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0040967540_p2654810491613"><a name="zh-cn_topic_0040967540_p2654810491613"></a><a name="zh-cn_topic_0040967540_p2654810491613"></a>用户名称</p>
</th>
<th class="cellrowborder" valign="top" width="25.742574257425744%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0040967540_p3460826591613"><a name="zh-cn_topic_0040967540_p3460826591613"></a><a name="zh-cn_topic_0040967540_p3460826591613"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="31.683168316831683%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0040967540_p3554159991613"><a name="zh-cn_topic_0040967540_p3554159991613"></a><a name="zh-cn_topic_0040967540_p3554159991613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0040967540_row12972464111"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_a1bd8bc46f0c949e3b7b633c062298f75"><a name="zh-cn_topic_0040967540_a1bd8bc46f0c949e3b7b633c062298f75"></a><a name="zh-cn_topic_0040967540_a1bd8bc46f0c949e3b7b633c062298f75"></a>MRS集群系统管理员</p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_aa4f14604d7ef45fa9017133971804990"><a name="zh-cn_topic_0040967540_aa4f14604d7ef45fa9017133971804990"></a><a name="zh-cn_topic_0040967540_aa4f14604d7ef45fa9017133971804990"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><p id="p494738516"><a name="p494738516"></a><a name="p494738516"></a>在集群创建时由用户指定。</p>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><a name="zh-cn_topic_0040967540_ul9418182411432"></a><a name="zh-cn_topic_0040967540_ul9418182411432"></a><ul id="zh-cn_topic_0040967540_ul9418182411432"><li>MRS Manager的管理员。<p id="zh-cn_topic_0040967540_p2240466591526"><a name="zh-cn_topic_0040967540_p2240466591526"></a><a name="zh-cn_topic_0040967540_p2240466591526"></a>具有以下权限：</p>
<a name="zh-cn_topic_0040967540_ul77702491530"></a><a name="zh-cn_topic_0040967540_ul77702491530"></a><ul id="zh-cn_topic_0040967540_ul77702491530"><li>具有HDFS、ZooKeeper普通用户的权限。</li><li>具有提交、查询Mapreduce、YARN任务的权限，以及YARN队列管理权限和访问YARN WebUI的权限。</li><li>Storm中，具有提交、查询、激活、去激活、重分配、删除拓扑的权限，可以操作所有拓扑。</li><li>Kafka服务中，具有创建、删除、授权、Reassign、消费、写入、查询主题的权限。</li></ul>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row1268622981010"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p10372242151016"><a name="zh-cn_topic_0040967540_p10372242151016"></a><a name="zh-cn_topic_0040967540_p10372242151016"></a>MRS集群节点操作系统用户</p>
<p id="zh-cn_topic_0040967540_p154151742171011"><a name="zh-cn_topic_0040967540_p154151742171011"></a><a name="zh-cn_topic_0040967540_p154151742171011"></a></p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p58965223379"><a name="zh-cn_topic_0040967540_p58965223379"></a><a name="zh-cn_topic_0040967540_p58965223379"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p3896142293710"><a name="zh-cn_topic_0040967540_p3896142293710"></a><a name="zh-cn_topic_0040967540_p3896142293710"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0040967540_p168965225379"><a name="zh-cn_topic_0040967540_p168965225379"></a><a name="zh-cn_topic_0040967540_p168965225379"></a>MRS集群系统的内部运行用户。在全部节点生成，属于操作系统用户，无需设置为统一的密码。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row990821883611"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p1190851873618"><a name="zh-cn_topic_0040967540_p1190851873618"></a><a name="zh-cn_topic_0040967540_p1190851873618"></a>MRS集群节点操作系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p11908518153613"><a name="zh-cn_topic_0040967540_p11908518153613"></a><a name="zh-cn_topic_0040967540_p11908518153613"></a>root</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p290881820369"><a name="zh-cn_topic_0040967540_p290881820369"></a><a name="zh-cn_topic_0040967540_p290881820369"></a>用户设置的密码。</p>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0040967540_p390861893616"><a name="zh-cn_topic_0040967540_p390861893616"></a><a name="zh-cn_topic_0040967540_p390861893616"></a>MRS集群所属节点的登录用户。在全部节点生成，属于操作系统用户。</p>
</td>
</tr>
</tbody>
</table>

## 用户组信息<a name="zh-cn_topic_0040967540_section2451602294412"></a>

<a name="zh-cn_topic_0040967540_table4858345094426"></a>
<table><thead align="left"><tr id="zh-cn_topic_0040967540_row5992778594426"><th class="cellrowborder" valign="top" width="35%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0040967540_p6247853294426"><a name="zh-cn_topic_0040967540_p6247853294426"></a><a name="zh-cn_topic_0040967540_p6247853294426"></a>默认用户组</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0040967540_p2071216494426"><a name="zh-cn_topic_0040967540_p2071216494426"></a><a name="zh-cn_topic_0040967540_p2071216494426"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0040967540_row28535398184420"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p29665881184420"><a name="zh-cn_topic_0040967540_p29665881184420"></a><a name="zh-cn_topic_0040967540_p29665881184420"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p54126132184420"><a name="zh-cn_topic_0040967540_p54126132184420"></a><a name="zh-cn_topic_0040967540_p54126132184420"></a>admin用户的主组，在关闭Kerberos认证的集群中没有额外的权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row4814327194426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p5369114894426"><a name="zh-cn_topic_0040967540_p5369114894426"></a><a name="zh-cn_topic_0040967540_p5369114894426"></a>check_sec_ldap</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p1320083994426"><a name="zh-cn_topic_0040967540_p1320083994426"></a><a name="zh-cn_topic_0040967540_p1320083994426"></a>用于内部测试主LDAP是否工作正常。用户组随机存在，每次测试时创建，测试完成后自动删除。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row38497354184245"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p5300810518437"><a name="zh-cn_topic_0040967540_p5300810518437"></a><a name="zh-cn_topic_0040967540_p5300810518437"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p6579814618437"><a name="zh-cn_topic_0040967540_p6579814618437"></a><a name="zh-cn_topic_0040967540_p6579814618437"></a>租户系统用户组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row35929603184258"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p5111994918437"><a name="zh-cn_topic_0040967540_p5111994918437"></a><a name="zh-cn_topic_0040967540_p5111994918437"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p4707520418437"><a name="zh-cn_topic_0040967540_p4707520418437"></a><a name="zh-cn_topic_0040967540_p4707520418437"></a>MRS集群系统管理员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row820958118435"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p2519449818437"><a name="zh-cn_topic_0040967540_p2519449818437"></a><a name="zh-cn_topic_0040967540_p2519449818437"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p2748843318437"><a name="zh-cn_topic_0040967540_p2748843318437"></a><a name="zh-cn_topic_0040967540_p2748843318437"></a>MRS Manager系统查看员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row5689078018435"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p4062643718437"><a name="zh-cn_topic_0040967540_p4062643718437"></a><a name="zh-cn_topic_0040967540_p4062643718437"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p240706218437"><a name="zh-cn_topic_0040967540_p240706218437"></a><a name="zh-cn_topic_0040967540_p240706218437"></a>MRS Manager系统操作员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row1383076718431"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p991804218437"><a name="zh-cn_topic_0040967540_p991804218437"></a><a name="zh-cn_topic_0040967540_p991804218437"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p6516397618437"><a name="zh-cn_topic_0040967540_p6516397618437"></a><a name="zh-cn_topic_0040967540_p6516397618437"></a>MRS Manager系统审计员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row2884105518431"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p5857211318437"><a name="zh-cn_topic_0040967540_p5857211318437"></a><a name="zh-cn_topic_0040967540_p5857211318437"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p4672067618437"><a name="zh-cn_topic_0040967540_p4672067618437"></a><a name="zh-cn_topic_0040967540_p4672067618437"></a>MRS Manager系统管理员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row4998309794426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p4519596294426"><a name="zh-cn_topic_0040967540_p4519596294426"></a><a name="zh-cn_topic_0040967540_p4519596294426"></a>compcommon</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p4375014494426"><a name="zh-cn_topic_0040967540_p4375014494426"></a><a name="zh-cn_topic_0040967540_p4375014494426"></a>MRS集群系统内部组，用于访问集群公共资源。所有系统用户和系统运行用户默认加入此用户组。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row5410077594426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p1640472094426"><a name="zh-cn_topic_0040967540_p1640472094426"></a><a name="zh-cn_topic_0040967540_p1640472094426"></a>default_1000</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p5586241494426"><a name="zh-cn_topic_0040967540_p5586241494426"></a><a name="zh-cn_topic_0040967540_p5586241494426"></a>为租户创建的用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row12794181114303"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p164311788375"><a name="zh-cn_topic_0040967540_p164311788375"></a><a name="zh-cn_topic_0040967540_p164311788375"></a>launcher-job</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p74317810374"><a name="zh-cn_topic_0040967540_p74317810374"></a><a name="zh-cn_topic_0040967540_p74317810374"></a>MRS系统内部组，用于使用V2接口提交作业。</p>
</td>
</tr>
</tbody>
</table>

<a name="zh-cn_topic_0040967540_table211708839453"></a>
<table><thead align="left"><tr id="zh-cn_topic_0040967540_row414780159453"><th class="cellrowborder" valign="top" width="35.449999999999996%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0040967540_p108162799453"><a name="zh-cn_topic_0040967540_p108162799453"></a><a name="zh-cn_topic_0040967540_p108162799453"></a>操作系统用户组</p>
</th>
<th class="cellrowborder" valign="top" width="64.55%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0040967540_p315392209453"><a name="zh-cn_topic_0040967540_p315392209453"></a><a name="zh-cn_topic_0040967540_p315392209453"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0040967540_row321952219453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p412556129453"><a name="zh-cn_topic_0040967540_p412556129453"></a><a name="zh-cn_topic_0040967540_p412556129453"></a>wheel</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p280260249453"><a name="zh-cn_topic_0040967540_p280260249453"></a><a name="zh-cn_topic_0040967540_p280260249453"></a>MRS集群系统内部运行用户“omm”的主组。</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row555154669453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0040967540_p371687299453"><a name="zh-cn_topic_0040967540_p371687299453"></a><a name="zh-cn_topic_0040967540_p371687299453"></a>ficommon</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0040967540_p575311339453"><a name="zh-cn_topic_0040967540_p575311339453"></a><a name="zh-cn_topic_0040967540_p575311339453"></a>MRS集群系统公共组，对应“compcommon”，可以访问集群在操作系统中保存的公共资源文件。</p>
</td>
</tr>
</tbody>
</table>

## 数据库用户<a name="zh-cn_topic_0040967540_section4435701994533"></a>

MRS集群系统数据库用户包含OMS数据库用户、DBService数据库用户。

>![](public_sys-resources/icon-note.gif) **说明：** 
>数据库用户不能删除，否则可能导致集群或组件服务无法正常工作。

<a name="zh-cn_topic_0040967540_table5909699494551"></a>
<table><thead align="left"><tr id="zh-cn_topic_0040967540_row5335053194551"><th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0040967540_p6011172094551"><a name="zh-cn_topic_0040967540_p6011172094551"></a><a name="zh-cn_topic_0040967540_p6011172094551"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0040967540_p6131221094551"><a name="zh-cn_topic_0040967540_p6131221094551"></a><a name="zh-cn_topic_0040967540_p6131221094551"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="20.862086208620862%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0040967540_p1887971294551"><a name="zh-cn_topic_0040967540_p1887971294551"></a><a name="zh-cn_topic_0040967540_p1887971294551"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.933693369336936%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0040967540_p5394219694551"><a name="zh-cn_topic_0040967540_p5394219694551"></a><a name="zh-cn_topic_0040967540_p5394219694551"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0040967540_row1459050794551"><td class="cellrowborder" rowspan="2" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p3107790294551"><a name="zh-cn_topic_0040967540_p3107790294551"></a><a name="zh-cn_topic_0040967540_p3107790294551"></a>OMS数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p2538629394551"><a name="zh-cn_topic_0040967540_p2538629394551"></a><a name="zh-cn_topic_0040967540_p2538629394551"></a>ommdba</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p6238201894551"><a name="zh-cn_topic_0040967540_p6238201894551"></a><a name="zh-cn_topic_0040967540_p6238201894551"></a>dbChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0040967540_p5857122094551"><a name="zh-cn_topic_0040967540_p5857122094551"></a><a name="zh-cn_topic_0040967540_p5857122094551"></a>OMS数据库管理员用户，用于创建、启动和停止等维护操作</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row3626829494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p5536010394551"><a name="zh-cn_topic_0040967540_p5536010394551"></a><a name="zh-cn_topic_0040967540_p5536010394551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p2446842994551"><a name="zh-cn_topic_0040967540_p2446842994551"></a><a name="zh-cn_topic_0040967540_p2446842994551"></a>ChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p1296316094551"><a name="zh-cn_topic_0040967540_p1296316094551"></a><a name="zh-cn_topic_0040967540_p1296316094551"></a>OMS数据库数据访问用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row6479190094551"><td class="cellrowborder" rowspan="4" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p3211675894551"><a name="zh-cn_topic_0040967540_p3211675894551"></a><a name="zh-cn_topic_0040967540_p3211675894551"></a>DBService数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p6332914194551"><a name="zh-cn_topic_0040967540_p6332914194551"></a><a name="zh-cn_topic_0040967540_p6332914194551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p3151964194551"><a name="zh-cn_topic_0040967540_p3151964194551"></a><a name="zh-cn_topic_0040967540_p3151964194551"></a>dbserverAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0040967540_p3795574594551"><a name="zh-cn_topic_0040967540_p3795574594551"></a><a name="zh-cn_topic_0040967540_p3795574594551"></a>DBService组件中GaussDB数据库的管理员用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row1983843494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p3588156294551"><a name="zh-cn_topic_0040967540_p3588156294551"></a><a name="zh-cn_topic_0040967540_p3588156294551"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p103531994551"><a name="zh-cn_topic_0040967540_p103531994551"></a><a name="zh-cn_topic_0040967540_p103531994551"></a>HiveUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p1473320894551"><a name="zh-cn_topic_0040967540_p1473320894551"></a><a name="zh-cn_topic_0040967540_p1473320894551"></a>Hive连接DBService数据库用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row56172437155212"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p5234664155228"><a name="zh-cn_topic_0040967540_p5234664155228"></a><a name="zh-cn_topic_0040967540_p5234664155228"></a>hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p21354641155228"><a name="zh-cn_topic_0040967540_p21354641155228"></a><a name="zh-cn_topic_0040967540_p21354641155228"></a>HueUser@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p52004395155228"><a name="zh-cn_topic_0040967540_p52004395155228"></a><a name="zh-cn_topic_0040967540_p52004395155228"></a>Hue连接DBService数据库用户</p>
</td>
</tr>
<tr id="zh-cn_topic_0040967540_row31293047105213"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0040967540_p27667531105213"><a name="zh-cn_topic_0040967540_p27667531105213"></a><a name="zh-cn_topic_0040967540_p27667531105213"></a>sqoop</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0040967540_p26477538105213"><a name="zh-cn_topic_0040967540_p26477538105213"></a><a name="zh-cn_topic_0040967540_p26477538105213"></a>SqoopUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0040967540_p64305825105213"><a name="zh-cn_topic_0040967540_p64305825105213"></a><a name="zh-cn_topic_0040967540_p64305825105213"></a>Loader连接DBService数据库的用户</p>
</td>
</tr>
</tbody>
</table>

