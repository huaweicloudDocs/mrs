# 提交SQL语句<a name="ExecuteSql"></a>

## 功能介绍<a name="section5749143719563"></a>

在MRS集群中提交并执行一条SQL语句。MRS 1.9.2及之后版本支持本接口。

## 接口约束<a name="section87781437135610"></a>

无

## URI<a name="section1981520377565"></a>

POST /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution

**表 1**  路径参数

<a name="table08651037175614"></a>
<table><thead align="left"><tr id="row48511376562"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p14872143718567"><a name="p14872143718567"></a><a name="p14872143718567"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p13890537105619"><a name="p13890537105619"></a><a name="p13890537105619"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1190753712568"><a name="p1190753712568"></a><a name="p1190753712568"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p19921133712561"><a name="p19921133712561"></a><a name="p19921133712561"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1851143713567"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1393411372563"><a name="p1393411372563"></a><a name="p1393411372563"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p11947837155615"><a name="p11947837155615"></a><a name="p11947837155615"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p99615378567"><a name="p99615378567"></a><a name="p99615378567"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14977123725617"><a name="p14977123725617"></a><a name="p14977123725617"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row13851837185613"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p99921037195613"><a name="p99921037195613"></a><a name="p99921037195613"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p176238115611"><a name="p176238115611"></a><a name="p176238115611"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p162012388569"><a name="p162012388569"></a><a name="p162012388569"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1238203835619"><a name="p1238203835619"></a><a name="p1238203835619"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md">获取集群ID</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section1458163875618"></a>

**表 2**  请求Header参数

<a name="zh-cn_topic_0000001074494780_HeaderParameter"></a>
<table><thead align="left"><tr id="row12734383561"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1596838115612"><a name="p1596838115612"></a><a name="p1596838115612"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p511116386560"><a name="p511116386560"></a><a name="p511116386560"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p512833845615"><a name="p512833845615"></a><a name="p512833845615"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p191424385560"><a name="p191424385560"></a><a name="p191424385560"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row674113815611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p13158173835616"><a name="p13158173835616"></a><a name="p13158173835616"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p51771938195614"><a name="p51771938195614"></a><a name="p51771938195614"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p419811387561"><a name="p419811387561"></a><a name="p419811387561"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p621383885614"><a name="p621383885614"></a><a name="p621383885614"></a>用户Token。</p>
<p id="p7225153885619"><a name="p7225153885619"></a><a name="p7225153885619"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row11948118185719"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p323853522718"><a name="p323853522718"></a><a name="p323853522718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p923823512276"><a name="p923823512276"></a><a name="p923823512276"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1498118421334"><a name="p1498118421334"></a><a name="p1498118421334"></a>发送的实体的MIME类型。</p>
<p id="p18288172762711"><a name="p18288172762711"></a><a name="p18288172762711"></a>推荐用户默认使用application/json; charset=utf-8。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="zh-cn_topic_0000001074494780_requestParameter"></a>
<table><thead align="left"><tr id="row62361938185616"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p22601038185617"><a name="p22601038185617"></a><a name="p22601038185617"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1727493817565"><a name="p1727493817565"></a><a name="p1727493817565"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1428763845615"><a name="p1428763845615"></a><a name="p1428763845615"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p14305193815616"><a name="p14305193815616"></a><a name="p14305193815616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16236143865617"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p531916389566"><a name="p531916389566"></a><a name="p531916389566"></a>sql_type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14333203825616"><a name="p14333203825616"></a><a name="p14333203825616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p13347193805611"><a name="p13347193805611"></a><a name="p13347193805611"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1036373895617"><a name="p1036373895617"></a><a name="p1036373895617"></a>SQL类型。目前仅支持“presto”类型的SQL。</p>
<p id="p637619385567"><a name="p637619385567"></a><a name="p637619385567"></a>说明： 只有包含Presto组件的集群才能提交执行presto类型的SQL。</p>
</td>
</tr>
<tr id="row1823673814569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p939123812568"><a name="p939123812568"></a><a name="p939123812568"></a>sql_content</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p940416384569"><a name="p940416384569"></a><a name="p940416384569"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p15420133835611"><a name="p15420133835611"></a><a name="p15420133835611"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1243611380566"><a name="p1243611380566"></a><a name="p1243611380566"></a>待执行的SQL语句。</p>
<p id="p64481738135615"><a name="p64481738135615"></a><a name="p64481738135615"></a>说明： 目前仅支持执行单条语句，语句中不包含“;”。</p>
</td>
</tr>
<tr id="row152361438175610"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p9463173813565"><a name="p9463173813565"></a><a name="p9463173813565"></a>database</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p124824383561"><a name="p124824383561"></a><a name="p124824383561"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p449993855619"><a name="p449993855619"></a><a name="p449993855619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p3515173814567"><a name="p3515173814567"></a><a name="p3515173814567"></a>执行SQL所在的数据库，默认为default。</p>
</td>
</tr>
<tr id="row123614386569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8538193865611"><a name="p8538193865611"></a><a name="p8538193865611"></a>archive_path</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p65583388565"><a name="p65583388565"></a><a name="p65583388565"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p657714382563"><a name="p657714382563"></a><a name="p657714382563"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p15597133815614"><a name="p15597133815614"></a><a name="p15597133815614"></a>SQL执行结果的转储文件夹。</p>
<p id="p96131538185617"><a name="p96131538185617"></a><a name="p96131538185617"></a>说明： 只有select语句才会转储查询的结果。当前仅支持转储到OBS中。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section363963845613"></a>

**状态码： 200**

**表 4**  响应Body参数

<a name="zh-cn_topic_0000001074494780_responseParameter"></a>
<table><thead align="left"><tr id="row767915386563"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p8701438175611"><a name="p8701438175611"></a><a name="p8701438175611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p197151038195611"><a name="p197151038195611"></a><a name="p197151038195611"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p57439389568"><a name="p57439389568"></a><a name="p57439389568"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row167923855611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2759238135616"><a name="p2759238135616"></a><a name="p2759238135616"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p2780173817565"><a name="p2780173817565"></a><a name="p2780173817565"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1679513382568"><a name="p1679513382568"></a><a name="p1679513382568"></a>SQL的执行id。执行select、show和desc语句时才会生成id，其他操作id为空</p>
</td>
</tr>
<tr id="row86791383569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1681133810569"><a name="p1681133810569"></a><a name="p1681133810569"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1482683810564"><a name="p1482683810564"></a><a name="p1482683810564"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19840838195617"><a name="p19840838195617"></a><a name="p19840838195617"></a>错误信息。</p>
</td>
</tr>
<tr id="row1967918385569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1485933805610"><a name="p1485933805610"></a><a name="p1485933805610"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p12872173819564"><a name="p12872173819564"></a><a name="p12872173819564"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p18887193845617"><a name="p18887193845617"></a><a name="p18887193845617"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="row26791238165612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1290623818560"><a name="p1290623818560"></a><a name="p1290623818560"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10921133818560"><a name="p10921133818560"></a><a name="p10921133818560"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19937123813561"><a name="p19937123813561"></a><a name="p19937123813561"></a>SQL的执行状态。</p>
<a name="ul59741438125616"></a><a name="ul59741438125616"></a><ul id="ul59741438125616"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="row96791738105610"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p714913965619"><a name="p714913965619"></a><a name="p714913965619"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15164203985616"><a name="p15164203985616"></a><a name="p15164203985616"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1017963914569"><a name="p1017963914569"></a><a name="p1017963914569"></a>SQL查询语句的最终结果归档路径。</p>
<p id="p14194183935618"><a name="p14194183935618"></a><a name="p14194183935618"></a>说明： 只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</td>
</tr>
<tr id="row1267913382562"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18208113911564"><a name="p18208113911564"></a><a name="p18208113911564"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18224163913564"><a name="p18224163913564"></a><a name="p18224163913564"></a>Array&lt;Array&lt;String&gt;&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p824220393564"><a name="p824220393564"></a><a name="p824220393564"></a>SQL的执行结果。</p>
<p id="p625463925612"><a name="p625463925612"></a><a name="p625463925612"></a>说明： 只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</td>
</tr>
</tbody>
</table>

**状态码： 500**

**表 5**  响应Body参数

<a name="table12771539135618"></a>
<table><thead align="left"><tr id="row15278839145620"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p11304163911564"><a name="p11304163911564"></a><a name="p11304163911564"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p33181039205612"><a name="p33181039205612"></a><a name="p33181039205612"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1333583985610"><a name="p1333583985610"></a><a name="p1333583985610"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row227853912563"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p0350039165615"><a name="p0350039165615"></a><a name="p0350039165615"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1436714395560"><a name="p1436714395560"></a><a name="p1436714395560"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p173857392569"><a name="p173857392569"></a><a name="p173857392569"></a>SQL的执行id。执行select、show和desc语句时才会生成id，其他操作id为空</p>
</td>
</tr>
<tr id="row727893965612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p14401113913562"><a name="p14401113913562"></a><a name="p14401113913562"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p12414123915562"><a name="p12414123915562"></a><a name="p12414123915562"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4437123945610"><a name="p4437123945610"></a><a name="p4437123945610"></a>错误信息。</p>
</td>
</tr>
<tr id="row627893995612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p84581639125617"><a name="p84581639125617"></a><a name="p84581639125617"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p17471173935618"><a name="p17471173935618"></a><a name="p17471173935618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p448623935616"><a name="p448623935616"></a><a name="p448623935616"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="row12278103919565"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p750843985617"><a name="p750843985617"></a><a name="p750843985617"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p152593913563"><a name="p152593913563"></a><a name="p152593913563"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2546103917568"><a name="p2546103917568"></a><a name="p2546103917568"></a>SQL的执行状态。</p>
<a name="ul1578123915560"></a><a name="ul1578123915560"></a><ul id="ul1578123915560"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="row14278163914569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1745133955618"><a name="p1745133955618"></a><a name="p1745133955618"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p376063945612"><a name="p376063945612"></a><a name="p376063945612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p57778399565"><a name="p57778399565"></a><a name="p57778399565"></a>SQL查询语句的最终结果归档路径。</p>
<p id="p11792239135610"><a name="p11792239135610"></a><a name="p11792239135610"></a>说明： 只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</td>
</tr>
<tr id="row72781539175612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8806173965614"><a name="p8806173965614"></a><a name="p8806173965614"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16822113912568"><a name="p16822113912568"></a><a name="p16822113912568"></a>Array&lt;Array&lt;String&gt;&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p483973985619"><a name="p483973985619"></a><a name="p483973985619"></a>SQL的执行结果。</p>
<p id="p085120393564"><a name="p085120393564"></a><a name="p085120393564"></a>说明： 只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section20867163916560"></a>

提交SQL语句请求示例

```
POST https://{endpoint}/v2/{project_id}/clusters/{cluster_id}/sql-execution

{
  "sql_type" : "presto",
  "sql_content" : "show tables",
  "database" : "default",
  "archive_path" : "obs://my-bucket/path"
}
```

## 响应示例<a name="section1730114065618"></a>

**状态码： 200**

提交SQL语句成功

```
{
  "sql_id" : "20190909_011820_00151_xxxxx",
  "statement" : "show tables",
  "status" : "FINISHED",
  "result_location" : " obs://my_bucket/uuid_date/xxxx.csv",
  "content" : [ null, "t1", null, "t2", null, "t3" ]
}
```

**状态码： 500**

提交SQL语句成功

```
{
  "sql_id" : "20190909_011820_00151_xxxxx",
  "message" : "line 1:1: Table 'hive.default.t1' already exists",
  "statement" : "show tables",
  "status" : "FAILED"
}
```

## 状态码<a name="section1233120405567"></a>

<a name="zh-cn_topic_0000001074494780_status_code"></a>
<table><thead align="left"><tr id="row83461740145620"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p173591540195614"><a name="p173591540195614"></a><a name="p173591540195614"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p6375540185618"><a name="p6375540185618"></a><a name="p6375540185618"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row034634065611"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p1338964045613"><a name="p1338964045613"></a><a name="p1338964045613"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p34033400568"><a name="p34033400568"></a><a name="p34033400568"></a>提交SQL语句成功</p>
</td>
</tr>
<tr id="row1034674018560"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p1041820402564"><a name="p1041820402564"></a><a name="p1041820402564"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p643454065616"><a name="p643454065616"></a><a name="p643454065616"></a>提交SQL语句成功</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section10449540115610"></a>

请参见[错误码](错误码.md)。

