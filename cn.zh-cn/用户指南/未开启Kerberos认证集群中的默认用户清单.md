# 未开启Kerberos认证集群中的默认用户清单<a name="ZH-CN_TOPIC_0173397674"></a>

## 用户分类<a name="section1350246891412"></a>

MRS集群提供以下2类用户，请用户定期修改密码，不建议使用默认密码。

<a name="table5775715391436"></a>
<table><thead align="left"><tr id="row642250091436"><th class="cellrowborder" valign="top" width="21.5%" id="mcps1.1.3.1.1"><p id="p6076518391436"><a name="p6076518391436"></a><a name="p6076518391436"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="78.5%" id="mcps1.1.3.1.2"><p id="p5371575991436"><a name="p5371575991436"></a><a name="p5371575991436"></a>使用说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row4045403691436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="p337902391436"><a name="p337902391436"></a><a name="p337902391436"></a>系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><p id="p3798221105832"><a name="p3798221105832"></a><a name="p3798221105832"></a>用于OMS系统进程运行的用户。</p>
</td>
</tr>
<tr id="row4047833191436"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="p2856068791436"><a name="p2856068791436"></a><a name="p2856068791436"></a>数据库用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="ul1872352891436"></a><a name="ul1872352891436"></a><ul id="ul1872352891436"><li>用于OMS数据库管理和数据访问的用户。</li><li>用于业务组件（Hive、Loader和DBservice）数据库的用户。</li></ul>
</td>
</tr>
</tbody>
</table>

## 系统用户<a name="section4899716991522"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   MRS集群需要使用操作系统中ldap用户，此帐号不能删除，否则可能导致集群无法正常工作。密码管理策略由操作用户维护。  
>-   首次修改“ommdba“和“omm“密码需执行重置密码操作。找回密码后建议定期修改。  

<a name="table2048716191613"></a>
<table><thead align="left"><tr id="row5261606891613"><th class="cellrowborder" valign="top" width="24.752475247524753%" id="mcps1.1.5.1.1"><p id="p602860391613"><a name="p602860391613"></a><a name="p602860391613"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="17.82178217821782%" id="mcps1.1.5.1.2"><p id="p2654810491613"><a name="p2654810491613"></a><a name="p2654810491613"></a>用户名称</p>
</th>
<th class="cellrowborder" valign="top" width="25.742574257425744%" id="mcps1.1.5.1.3"><p id="p3460826591613"><a name="p3460826591613"></a><a name="p3460826591613"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="31.683168316831683%" id="mcps1.1.5.1.4"><p id="p3554159991613"><a name="p3554159991613"></a><a name="p3554159991613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12972464111"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="a1bd8bc46f0c949e3b7b633c062298f75"><a name="a1bd8bc46f0c949e3b7b633c062298f75"></a><a name="a1bd8bc46f0c949e3b7b633c062298f75"></a>MRS集群系统管理员</p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="aa4f14604d7ef45fa9017133971804990"><a name="aa4f14604d7ef45fa9017133971804990"></a><a name="aa4f14604d7ef45fa9017133971804990"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><a name="ul13495342204211"></a><a name="ul13495342204211"></a><ul id="ul13495342204211"><li>针对1.8.0之前集群，初始密码为MIG2oAMCAQGhAw@IBAaIDAgwCAQGkgZ8@wgZwwVKAHMAWgAw@IBAKFJMEgABD4gA</li><li>针对1.8.0及之后集群，在集群创建时由用户指定。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><a name="ul9418182411432"></a><a name="ul9418182411432"></a><ul id="ul9418182411432"><li>针对1.8.0之前集群，MRS Manager记录集群审计日志的默认用户。</li><li>针对1.8.0及之后集群，MRS Manager的管理员。<p id="p2240466591526"><a name="p2240466591526"></a><a name="p2240466591526"></a>此外还具有以下权限：</p>
<a name="ul77702491530"></a><a name="ul77702491530"></a><ul id="ul77702491530"><li>具有HDFS、ZooKeeper普通用户的权限。</li><li>具有提交、查询Mapreduce、YARN任务的权限，以及YARN队列管理权限和访问YARN WebUI的权限。</li><li>Storm中，具有提交、查询、激活、去激活、重分配、删除拓扑的权限，可以操作所有拓扑。</li><li>Kafka服务中，具有创建、删除、授权、Reassign、消费、写入、查询主题的权限。</li></ul>
</li></ul>
</td>
</tr>
<tr id="row1268622981010"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="p10372242151016"><a name="p10372242151016"></a><a name="p10372242151016"></a>MRS集群节点操作系统用户</p>
<p id="p154151742171011"><a name="p154151742171011"></a><a name="p154151742171011"></a></p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="p58965223379"><a name="p58965223379"></a><a name="p58965223379"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><p id="p3896142293710"><a name="p3896142293710"></a><a name="p3896142293710"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><p id="p168965225379"><a name="p168965225379"></a><a name="p168965225379"></a>MRS集群系统的内部运行用户。在全部节点生成，属于操作系统用户，无需设置为统一的密码。</p>
</td>
</tr>
<tr id="row990821883611"><td class="cellrowborder" valign="top" width="24.752475247524753%" headers="mcps1.1.5.1.1 "><p id="p1190851873618"><a name="p1190851873618"></a><a name="p1190851873618"></a>MRS集群节点操作系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="17.82178217821782%" headers="mcps1.1.5.1.2 "><p id="p11908518153613"><a name="p11908518153613"></a><a name="p11908518153613"></a>root</p>
</td>
<td class="cellrowborder" valign="top" width="25.742574257425744%" headers="mcps1.1.5.1.3 "><p id="p290881820369"><a name="p290881820369"></a><a name="p290881820369"></a>用户设置的密码。</p>
<div class="note" id="note3698172111377"><a name="note3698172111377"></a><a name="note3698172111377"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p26986210379"><a name="p26986210379"></a><a name="p26986210379"></a>适用于MRS1.6.2版本（包含）及以后的集群。</p>
</div></div>
</td>
<td class="cellrowborder" valign="top" width="31.683168316831683%" headers="mcps1.1.5.1.4 "><p id="p390861893616"><a name="p390861893616"></a><a name="p390861893616"></a>MRS集群所属节点的登录用户。在全部节点生成，属于操作系统用户。</p>
</td>
</tr>
</tbody>
</table>

## 用户组信息<a name="section2451602294412"></a>

<a name="table4858345094426"></a>
<table><thead align="left"><tr id="row5992778594426"><th class="cellrowborder" valign="top" width="35%" id="mcps1.1.3.1.1"><p id="p6247853294426"><a name="p6247853294426"></a><a name="p6247853294426"></a>默认用户组</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.1.3.1.2"><p id="p2071216494426"><a name="p2071216494426"></a><a name="p2071216494426"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row28535398184420"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p29665881184420"><a name="p29665881184420"></a><a name="p29665881184420"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p54126132184420"><a name="p54126132184420"></a><a name="p54126132184420"></a>admin用户的主组，在关闭Kerberos认证的集群中没有额外的权限。</p>
</td>
</tr>
<tr id="row4814327194426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p5369114894426"><a name="p5369114894426"></a><a name="p5369114894426"></a>check_sec_ldap</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p1320083994426"><a name="p1320083994426"></a><a name="p1320083994426"></a>用于内部测试主LDAP是否工作正常。用户组随机存在，每次测试时创建，测试完成后自动删除。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="row38497354184245"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p5300810518437"><a name="p5300810518437"></a><a name="p5300810518437"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p6579814618437"><a name="p6579814618437"></a><a name="p6579814618437"></a>租户系统用户组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row35929603184258"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p5111994918437"><a name="p5111994918437"></a><a name="p5111994918437"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p4707520418437"><a name="p4707520418437"></a><a name="p4707520418437"></a>MRS集群系统管理员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row820958118435"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p2519449818437"><a name="p2519449818437"></a><a name="p2519449818437"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p2748843318437"><a name="p2748843318437"></a><a name="p2748843318437"></a>MRS Manager系统查看员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row5689078018435"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p4062643718437"><a name="p4062643718437"></a><a name="p4062643718437"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p240706218437"><a name="p240706218437"></a><a name="p240706218437"></a>MRS Manager系统操作员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row1383076718431"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p991804218437"><a name="p991804218437"></a><a name="p991804218437"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p6516397618437"><a name="p6516397618437"></a><a name="p6516397618437"></a>MRS Manager系统审计员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row2884105518431"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p5857211318437"><a name="p5857211318437"></a><a name="p5857211318437"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p4672067618437"><a name="p4672067618437"></a><a name="p4672067618437"></a>MRS Manager系统管理员组。系统内部组，仅限组件间内部使用，且仅在已启用Kerberos认证的集群中使用。</p>
</td>
</tr>
<tr id="row4998309794426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p4519596294426"><a name="p4519596294426"></a><a name="p4519596294426"></a>compcommon</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p4375014494426"><a name="p4375014494426"></a><a name="p4375014494426"></a>MRS集群系统内部组，用于访问集群公共资源。所有系统用户和系统运行用户默认加入此用户组。</p>
</td>
</tr>
<tr id="row5410077594426"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p1640472094426"><a name="p1640472094426"></a><a name="p1640472094426"></a>default_1000</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p5586241494426"><a name="p5586241494426"></a><a name="p5586241494426"></a>为租户创建的用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="row66126389172455"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p18989042172512"><a name="p18989042172512"></a><a name="p18989042172512"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p18585783172512"><a name="p18585783172512"></a><a name="p18585783172512"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限,才能访问对应Topic。</p>
</td>
</tr>
<tr id="row48150369172458"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p4519668172512"><a name="p4519668172512"></a><a name="p4519668172512"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p6503865172512"><a name="p6503865172512"></a><a name="p6503865172512"></a>添加入本组的用户，拥有所有Topic的读写权限。</p>
</td>
</tr>
<tr id="row4994691017251"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p57731175172512"><a name="p57731175172512"></a><a name="p57731175172512"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p8769247172512"><a name="p8769247172512"></a><a name="p8769247172512"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="row5162433017253"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p22733746172512"><a name="p22733746172512"></a><a name="p22733746172512"></a>storm</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p64120952172512"><a name="p64120952172512"></a><a name="p64120952172512"></a>Storm的普通用户组，属于该组的用户拥有提交拓扑和管理属于自己的拓扑的权限。</p>
</td>
</tr>
<tr id="row1262323117256"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p59207045172512"><a name="p59207045172512"></a><a name="p59207045172512"></a>stormadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p10936539172512"><a name="p10936539172512"></a><a name="p10936539172512"></a>Storm的管理员用户组，属于该组的用户拥有提交拓扑和管理所有拓扑的权限。</p>
</td>
</tr>
</tbody>
</table>

<a name="table211708839453"></a>
<table><thead align="left"><tr id="row414780159453"><th class="cellrowborder" valign="top" width="35.449999999999996%" id="mcps1.1.3.1.1"><p id="p108162799453"><a name="p108162799453"></a><a name="p108162799453"></a>操作系统用户组</p>
</th>
<th class="cellrowborder" valign="top" width="64.55%" id="mcps1.1.3.1.2"><p id="p315392209453"><a name="p315392209453"></a><a name="p315392209453"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row321952219453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="p412556129453"><a name="p412556129453"></a><a name="p412556129453"></a>wheel</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="p280260249453"><a name="p280260249453"></a><a name="p280260249453"></a>MRS集群系统内部运行用户“omm”的主组。</p>
</td>
</tr>
<tr id="row555154669453"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="p371687299453"><a name="p371687299453"></a><a name="p371687299453"></a>ficommon</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="p575311339453"><a name="p575311339453"></a><a name="p575311339453"></a>MRS集群系统公共组，对应“compcommon”，可以访问集群在操作系统中保存的公共资源文件。</p>
</td>
</tr>
</tbody>
</table>

## 数据库用户<a name="section4435701994533"></a>

MRS集群系统数据库用户包含OMS数据库用户、DBService数据库用户。

>![](public_sys-resources/icon-note.gif) **说明：**   
>数据库用户不能删除，否则可能导致集群或组件服务无法正常工作。  

<a name="table5909699494551"></a>
<table><thead align="left"><tr id="row5335053194551"><th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.1"><p id="p6011172094551"><a name="p6011172094551"></a><a name="p6011172094551"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.102110211021103%" id="mcps1.1.5.1.2"><p id="p6131221094551"><a name="p6131221094551"></a><a name="p6131221094551"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="20.862086208620862%" id="mcps1.1.5.1.3"><p id="p1887971294551"><a name="p1887971294551"></a><a name="p1887971294551"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.933693369336936%" id="mcps1.1.5.1.4"><p id="p5394219694551"><a name="p5394219694551"></a><a name="p5394219694551"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1459050794551"><td class="cellrowborder" rowspan="2" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="p3107790294551"><a name="p3107790294551"></a><a name="p3107790294551"></a>OMS数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="p2538629394551"><a name="p2538629394551"></a><a name="p2538629394551"></a>ommdba</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="p6238201894551"><a name="p6238201894551"></a><a name="p6238201894551"></a>dbChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="p5857122094551"><a name="p5857122094551"></a><a name="p5857122094551"></a>OMS数据库管理员用户，用于创建、启动和停止等维护操作</p>
</td>
</tr>
<tr id="row3626829494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p5536010394551"><a name="p5536010394551"></a><a name="p5536010394551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p2446842994551"><a name="p2446842994551"></a><a name="p2446842994551"></a>ChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p1296316094551"><a name="p1296316094551"></a><a name="p1296316094551"></a>OMS数据库数据访问用户</p>
</td>
</tr>
<tr id="row6479190094551"><td class="cellrowborder" rowspan="5" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.1 "><p id="p3211675894551"><a name="p3211675894551"></a><a name="p3211675894551"></a>DBService数据库</p>
<p id="p797965141820"><a name="p797965141820"></a><a name="p797965141820"></a></p>
</td>
<td class="cellrowborder" valign="top" width="21.102110211021103%" headers="mcps1.1.5.1.2 "><p id="p6332914194551"><a name="p6332914194551"></a><a name="p6332914194551"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="p3151964194551"><a name="p3151964194551"></a><a name="p3151964194551"></a>dbserverAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="p3795574594551"><a name="p3795574594551"></a><a name="p3795574594551"></a>DBService组件中GaussDB数据库的管理员用户</p>
</td>
</tr>
<tr id="row1983843494551"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p3588156294551"><a name="p3588156294551"></a><a name="p3588156294551"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p103531994551"><a name="p103531994551"></a><a name="p103531994551"></a>HiveUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p1473320894551"><a name="p1473320894551"></a><a name="p1473320894551"></a>Hive连接DBService数据库用户</p>
</td>
</tr>
<tr id="row56172437155212"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p5234664155228"><a name="p5234664155228"></a><a name="p5234664155228"></a>hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p21354641155228"><a name="p21354641155228"></a><a name="p21354641155228"></a>HueUser@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p52004395155228"><a name="p52004395155228"></a><a name="p52004395155228"></a>Hue连接DBService数据库用户</p>
</td>
</tr>
<tr id="row31293047105213"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p27667531105213"><a name="p27667531105213"></a><a name="p27667531105213"></a>sqoop</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p26477538105213"><a name="p26477538105213"></a><a name="p26477538105213"></a>SqoopUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p64305825105213"><a name="p64305825105213"></a><a name="p64305825105213"></a>Loader连接DBService数据库的用户</p>
</td>
</tr>
<tr id="row15979185161813"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p128161347101511"><a name="p128161347101511"></a><a name="p128161347101511"></a>ranger</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p16816154781516"><a name="p16816154781516"></a><a name="p16816154781516"></a>RangerUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p2081612477158"><a name="p2081612477158"></a><a name="p2081612477158"></a>Ranger连接DBService数据库的用户</p>
</td>
</tr>
</tbody>
</table>

