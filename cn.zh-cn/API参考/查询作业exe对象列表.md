# 查询作业exe对象列表<a name="GetJobExeList"></a>

## 功能介绍<a name="section155689492325"></a>

查询所有作业的exe对象列表。该接口不兼容Sahara。

## 接口约束<a name="section135746490326"></a>

无

## URI<a name="section5581194943213"></a>

GET /v1.1/\{project\_id\}/job-exes

**表 1**  路径参数

<a name="table1359054911323"></a>
<table><thead align="left"><tr id="row195871349203214"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p13592144910328"><a name="p13592144910328"></a><a name="p13592144910328"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p13595194915324"><a name="p13595194915324"></a><a name="p13595194915324"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p19598194923213"><a name="p19598194923213"></a><a name="p19598194923213"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2060074920327"><a name="p2060074920327"></a><a name="p2060074920327"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row105871049143220"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p46031349133210"><a name="p46031349133210"></a><a name="p46031349133210"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1360611492323"><a name="p1360611492323"></a><a name="p1360611492323"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p136093493327"><a name="p136093493327"></a><a name="p136093493327"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1613349163210"><a name="p1613349163210"></a><a name="p1613349163210"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  Query参数

<a name="table361964916322"></a>
<table><thead align="left"><tr id="row19616114917321"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p11621549133219"><a name="p11621549133219"></a><a name="p11621549133219"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p17624134963219"><a name="p17624134963219"></a><a name="p17624134963219"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p146291849113218"><a name="p146291849113218"></a><a name="p146291849113218"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p106321449183219"><a name="p106321449183219"></a><a name="p106321449183219"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1461619494320"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2635949113215"><a name="p2635949113215"></a><a name="p2635949113215"></a>page_size</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1563794973216"><a name="p1563794973216"></a><a name="p1563794973216"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1464017492322"><a name="p1464017492322"></a><a name="p1464017492322"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p18643549113217"><a name="p18643549113217"></a><a name="p18643549113217"></a>分页查询每页返回的最大作业数量。</p>
<p id="p1464694943213"><a name="p1464694943213"></a><a name="p1464694943213"></a>取值范围：[1～100]</p>
</td>
</tr>
<tr id="row261634918325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p9648349183211"><a name="p9648349183211"></a><a name="p9648349183211"></a>current_page</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p19652749133213"><a name="p19652749133213"></a><a name="p19652749133213"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p166553497321"><a name="p166553497321"></a><a name="p166553497321"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p3658164911325"><a name="p3658164911325"></a><a name="p3658164911325"></a>当前查询页码。</p>
</td>
</tr>
<tr id="row1361613493324"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p36618493329"><a name="p36618493329"></a><a name="p36618493329"></a>job_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p166647497325"><a name="p166647497325"></a><a name="p166647497325"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p26671849163220"><a name="p26671849163220"></a><a name="p26671849163220"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p46704495324"><a name="p46704495324"></a><a name="p46704495324"></a>作业名称。</p>
</td>
</tr>
<tr id="row14616164903212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p18673114953210"><a name="p18673114953210"></a><a name="p18673114953210"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1467614492325"><a name="p1467614492325"></a><a name="p1467614492325"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p186799491322"><a name="p186799491322"></a><a name="p186799491322"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p9682114993219"><a name="p9682114993219"></a><a name="p9682114993219"></a>集群编号。</p>
</td>
</tr>
<tr id="row5616174943219"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8685349143210"><a name="p8685349143210"></a><a name="p8685349143210"></a>state</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p168864915325"><a name="p168864915325"></a><a name="p168864915325"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p176921149153211"><a name="p176921149153211"></a><a name="p176921149153211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p146968492329"><a name="p146968492329"></a><a name="p146968492329"></a>作业状态编码：</p>
<a name="ul4700124915320"></a><a name="ul4700124915320"></a><ul id="ul4700124915320"><li>-1：Terminated表示已终止的作业状态</li><li>2：Running表示运行中的作业状态</li><li>3：Completed表示已完成的作业状态</li><li>4：Abnormal表示异常的作业状态</li></ul>
</td>
</tr>
<tr id="row361664993210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1171994983214"><a name="p1171994983214"></a><a name="p1171994983214"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8722849143216"><a name="p8722849143216"></a><a name="p8722849143216"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2725349103219"><a name="p2725349103219"></a><a name="p2725349103219"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p47281649183212"><a name="p47281649183212"></a><a name="p47281649183212"></a>作业执行对象的编号</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section147311149193214"></a>

**表 3**  请求Header参数

<a name="zh-cn_topic_0000001073886706_HeaderParameter"></a>
<table><thead align="left"><tr id="row107354492324"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p15740164953216"><a name="p15740164953216"></a><a name="p15740164953216"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p77441349123214"><a name="p77441349123214"></a><a name="p77441349123214"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1374744933219"><a name="p1374744933219"></a><a name="p1374744933219"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p1275184913326"><a name="p1275184913326"></a><a name="p1275184913326"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18735184943215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p117542049123213"><a name="p117542049123213"></a><a name="p117542049123213"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8758949103213"><a name="p8758949103213"></a><a name="p8758949103213"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p16761164915325"><a name="p16761164915325"></a><a name="p16761164915325"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p157648494329"><a name="p157648494329"></a><a name="p157648494329"></a>用户Token。</p>
<p id="p207666493328"><a name="p207666493328"></a><a name="p207666493328"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row1285019177110"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
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

## 响应参数<a name="section57701849153212"></a>

**状态码： 200**

**表 4**  响应Body参数

<a name="zh-cn_topic_0000001073886706_responseParameter"></a>
<table><thead align="left"><tr id="row177654983217"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p5781174913321"><a name="p5781174913321"></a><a name="p5781174913321"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11784104943211"><a name="p11784104943211"></a><a name="p11784104943211"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1787749123211"><a name="p1787749123211"></a><a name="p1787749123211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19776749123210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p579116497326"><a name="p579116497326"></a><a name="p579116497326"></a>totalRecord</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p379419497329"><a name="p379419497329"></a><a name="p379419497329"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p0799174913328"><a name="p0799174913328"></a><a name="p0799174913328"></a>作业列表总数。</p>
</td>
</tr>
<tr id="row137762492327"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p280314495321"><a name="p280314495321"></a><a name="p280314495321"></a>job_executions</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16807949133211"><a name="p16807949133211"></a><a name="p16807949133211"></a>Map&lt;String,Array&lt;<a href="#zh-cn_topic_0000001073886706_response_JobExeResult">JobExeResult</a>&gt;&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16810104933215"><a name="p16810104933215"></a><a name="p16810104933215"></a>作业列表</p>
</td>
</tr>
</tbody>
</table>

**表 5**  JobExeResult

<a name="zh-cn_topic_0000001073886706_response_JobExeResult"></a>
<table><thead align="left"><tr id="row2815204916328"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p78211449133212"><a name="p78211449133212"></a><a name="p78211449133212"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1482514923215"><a name="p1482514923215"></a><a name="p1482514923215"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p582984916324"><a name="p582984916324"></a><a name="p582984916324"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3815549173215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p11832549183215"><a name="p11832549183215"></a><a name="p11832549183215"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1683654915322"><a name="p1683654915322"></a><a name="p1683654915322"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p198400499326"><a name="p198400499326"></a><a name="p198400499326"></a>作业ID。</p>
</td>
</tr>
<tr id="row10815194953213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1184364913328"><a name="p1184364913328"></a><a name="p1184364913328"></a>create_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13846849183217"><a name="p13846849183217"></a><a name="p13846849183217"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p385094914324"><a name="p385094914324"></a><a name="p385094914324"></a>作业创建时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row1981515497328"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p3853194963219"><a name="p3853194963219"></a><a name="p3853194963219"></a>update_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13856154918325"><a name="p13856154918325"></a><a name="p13856154918325"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1886054915324"><a name="p1886054915324"></a><a name="p1886054915324"></a>作业更新时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row3815549123210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p14865649103218"><a name="p14865649103218"></a><a name="p14865649103218"></a>tenant_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9868184973211"><a name="p9868184973211"></a><a name="p9868184973211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1287315495323"><a name="p1287315495323"></a><a name="p1287315495323"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row15815449173215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6877184933215"><a name="p6877184933215"></a><a name="p6877184933215"></a>job_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1988054963220"><a name="p1988054963220"></a><a name="p1988054963220"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1888364993215"><a name="p1888364993215"></a><a name="p1888364993215"></a>作业ID。</p>
</td>
</tr>
<tr id="row12815124917323"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p10886134923216"><a name="p10886134923216"></a><a name="p10886134923216"></a>job_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1988964917320"><a name="p1988964917320"></a><a name="p1988964917320"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p20893184943216"><a name="p20893184943216"></a><a name="p20893184943216"></a>作业名称。</p>
</td>
</tr>
<tr id="row3815049183218"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p108969495327"><a name="p108969495327"></a><a name="p108969495327"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15900184917329"><a name="p15900184917329"></a><a name="p15900184917329"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16903649183214"><a name="p16903649183214"></a><a name="p16903649183214"></a>作业执行开始时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row681584914325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8906144903210"><a name="p8906144903210"></a><a name="p8906144903210"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14909174983215"><a name="p14909174983215"></a><a name="p14909174983215"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13912154915320"><a name="p13912154915320"></a><a name="p13912154915320"></a>作业执行结束时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row1681594917320"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1491534923211"><a name="p1491534923211"></a><a name="p1491534923211"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16918349143215"><a name="p16918349143215"></a><a name="p16918349143215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p09217495321"><a name="p09217495321"></a><a name="p09217495321"></a>作业所属集群ID。</p>
</td>
</tr>
<tr id="row1781517496325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1492420499329"><a name="p1492420499329"></a><a name="p1492420499329"></a>group_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1892717498325"><a name="p1892717498325"></a><a name="p1892717498325"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1593118499328"><a name="p1593118499328"></a><a name="p1593118499328"></a>作业执行组ID</p>
</td>
</tr>
<tr id="row281564917325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p79341649153214"><a name="p79341649153214"></a><a name="p79341649153214"></a>jar_path</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p99371149123215"><a name="p99371149123215"></a><a name="p99371149123215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p59408497329"><a name="p59408497329"></a><a name="p59408497329"></a>执行程序jar包或sql文件地址。</p>
</td>
</tr>
<tr id="row48151249193220"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p13943124913329"><a name="p13943124913329"></a><a name="p13943124913329"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1194674913214"><a name="p1194674913214"></a><a name="p1194674913214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p494914495328"><a name="p494914495328"></a><a name="p494914495328"></a>数据输入地址。</p>
</td>
</tr>
<tr id="row168161849193218"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p19952549183219"><a name="p19952549183219"></a><a name="p19952549183219"></a>output</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p595554983214"><a name="p595554983214"></a><a name="p595554983214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p109581249113210"><a name="p109581249113210"></a><a name="p109581249113210"></a>数据输出地址。</p>
</td>
</tr>
<tr id="row8816114953218"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1396124915326"><a name="p1396124915326"></a><a name="p1396124915326"></a>job_log</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p11963194993213"><a name="p11963194993213"></a><a name="p11963194993213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2967164911329"><a name="p2967164911329"></a><a name="p2967164911329"></a>作业日志存储地址</p>
</td>
</tr>
<tr id="row1081624913215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p5970114916322"><a name="p5970114916322"></a><a name="p5970114916322"></a>job_type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7974164917325"><a name="p7974164917325"></a><a name="p7974164917325"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p10979649183219"><a name="p10979649183219"></a><a name="p10979649183219"></a>作业类型码。</p>
<a name="ul17984154919328"></a><a name="ul17984154919328"></a><ul id="ul17984154919328"><li>1：MapReduce</li><li>2：Spark</li><li>3：Hive Script</li><li>4：HiveSQL（当前不支持）</li><li>5：DistCp</li><li>6：Spark Script</li><li>7：Spark SQL（该接口当前不支持</li></ul>
</td>
</tr>
<tr id="row1081615491325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1615450193218"><a name="p1615450193218"></a><a name="p1615450193218"></a>file_action</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p518205011326"><a name="p518205011326"></a><a name="p518205011326"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p62117508322"><a name="p62117508322"></a><a name="p62117508322"></a>导入导出数据。</p>
</td>
</tr>
<tr id="row1816114919322"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p162425003219"><a name="p162425003219"></a><a name="p162425003219"></a>arguments</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p192710504325"><a name="p192710504325"></a><a name="p192710504325"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4331550173210"><a name="p4331550173210"></a><a name="p4331550173210"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。该参数可为空。</p>
</td>
</tr>
<tr id="row98161949153217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1136195011321"><a name="p1136195011321"></a><a name="p1136195011321"></a>hql</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p23935011321"><a name="p23935011321"></a><a name="p23935011321"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p8436506325"><a name="p8436506325"></a><a name="p8436506325"></a>HQL脚本语句。</p>
</td>
</tr>
<tr id="row8816149103212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p174725016328"><a name="p174725016328"></a><a name="p174725016328"></a>job_state</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1251115063219"><a name="p1251115063219"></a><a name="p1251115063219"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12552050193220"><a name="p12552050193220"></a><a name="p12552050193220"></a>作业状态编码：</p>
<a name="ul1459150193212"></a><a name="ul1459150193212"></a><ul id="ul1459150193212"><li>-1：Terminated表示已终止的作业状态</li><li>2：Running表示运行中的作业状态</li><li>3：Completed表示已完成的作业状态</li><li>4：Abnormal表示异常的作业状态</li></ul>
</td>
</tr>
<tr id="row8816114910321"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1575165043212"><a name="p1575165043212"></a><a name="p1575165043212"></a>job_final_status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p197913507326"><a name="p197913507326"></a><a name="p197913507326"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1282165020324"><a name="p1282165020324"></a><a name="p1282165020324"></a>作业最终状态码。</p>
<a name="ul1085125043217"></a><a name="ul1085125043217"></a><ul id="ul1085125043217"><li>0：未完成</li><li>1：执行错误，终止执行</li><li>2：执行完成并且成功</li><li>3：已取消</li></ul>
</td>
</tr>
<tr id="row12816104913325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p181011550203215"><a name="p181011550203215"></a><a name="p181011550203215"></a>hive_script_path</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p12104550153216"><a name="p12104550153216"></a><a name="p12104550153216"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p10107950183220"><a name="p10107950183220"></a><a name="p10107950183220"></a>Hive脚本地址。</p>
</td>
</tr>
<tr id="row1081684910321"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8110650163217"><a name="p8110650163217"></a><a name="p8110650163217"></a>create_by</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p511345011324"><a name="p511345011324"></a><a name="p511345011324"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14116135063214"><a name="p14116135063214"></a><a name="p14116135063214"></a>创建作业的用户ID。</p>
</td>
</tr>
<tr id="row4816104910328"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p61196503328"><a name="p61196503328"></a><a name="p61196503328"></a>finished_step</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1312265043212"><a name="p1312265043212"></a><a name="p1312265043212"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1312525019320"><a name="p1312525019320"></a><a name="p1312525019320"></a>当前已完成的步骤数。</p>
</td>
</tr>
<tr id="row108171349113210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p41291350193210"><a name="p41291350193210"></a><a name="p41291350193210"></a>job_main_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p121321750163213"><a name="p121321750163213"></a><a name="p121321750163213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p813415503328"><a name="p813415503328"></a><a name="p813415503328"></a>作业主ID。</p>
</td>
</tr>
<tr id="row68171949163211"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p101371250163217"><a name="p101371250163217"></a><a name="p101371250163217"></a>job_step_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p121417501326"><a name="p121417501326"></a><a name="p121417501326"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p21451750173216"><a name="p21451750173216"></a><a name="p21451750173216"></a>作业步骤ID。</p>
</td>
</tr>
<tr id="row2817174915325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p81498507322"><a name="p81498507322"></a><a name="p81498507322"></a>postpone_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1515245003214"><a name="p1515245003214"></a><a name="p1515245003214"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15156650113218"><a name="p15156650113218"></a><a name="p15156650113218"></a>延迟时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row1081744923214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p7159650173218"><a name="p7159650173218"></a><a name="p7159650173218"></a>step_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1416265023213"><a name="p1416265023213"></a><a name="p1416265023213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1516695083215"><a name="p1516695083215"></a><a name="p1516695083215"></a>作业步骤名。</p>
</td>
</tr>
<tr id="row68171049193212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p11169115010327"><a name="p11169115010327"></a><a name="p11169115010327"></a>step_num</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p21721750113216"><a name="p21721750113216"></a><a name="p21721750113216"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p0175950153212"><a name="p0175950153212"></a><a name="p0175950153212"></a>步骤数量。</p>
</td>
</tr>
<tr id="row0817114918329"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p517845013324"><a name="p517845013324"></a><a name="p517845013324"></a>task_num</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14181125033214"><a name="p14181125033214"></a><a name="p14181125033214"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1918410504329"><a name="p1918410504329"></a><a name="p1918410504329"></a>任务数量。</p>
</td>
</tr>
<tr id="row781724913325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1418855033217"><a name="p1418855033217"></a><a name="p1418855033217"></a>update_by</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1819185013218"><a name="p1819185013218"></a><a name="p1819185013218"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p8194155053216"><a name="p8194155053216"></a><a name="p8194155053216"></a>更新作业的用户ID。</p>
</td>
</tr>
<tr id="row98171949143214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p161971503322"><a name="p161971503322"></a><a name="p161971503322"></a>spend_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10200165003210"><a name="p10200165003210"></a><a name="p10200165003210"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p182045505322"><a name="p182045505322"></a><a name="p182045505322"></a>作业执行持续时间，单位：秒。</p>
</td>
</tr>
<tr id="row118178492324"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p42071509326"><a name="p42071509326"></a><a name="p42071509326"></a>step_seq</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p152101450123214"><a name="p152101450123214"></a><a name="p152101450123214"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7214145017323"><a name="p7214145017323"></a><a name="p7214145017323"></a>步骤序列号。</p>
</td>
</tr>
<tr id="row08171449173212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16217750163220"><a name="p16217750163220"></a><a name="p16217750163220"></a>progress</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20220850183213"><a name="p20220850183213"></a><a name="p20220850183213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19223850143213"><a name="p19223850143213"></a><a name="p19223850143213"></a>作业执行进度。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section17226115012324"></a>

查询作业exe对象列表请求示例

```
GET https://{endpoint}/v1.1/{project_id}/job-exes?page_size=10&current_page=1&state=3&job_name=myfirstjob&cluster_id=20ca8601-72a2-4570-b788-2a20fec81a95
```

## 响应示例<a name="section12401509320"></a>

**状态码： 200**

查询作业exe对象列表成功。

```
{
  "totalRecord" : "14",
  "job_executions" : [ {
    "id" : "669476bd-89d2-45aa-8f1a-872d16de377e",
    "create_at" : "1484641003707",
    "update_at" : "1484641003707",
    "tenant_id" : "3f99e3319a8943ceb15c584f3325d064",
    "job_id" : "",
    "job_name" : "myfirstjob",
    "start_time" : "1484641003707",
    "end_time" : null,
    "cluster_id" : "2b460e01-3351-4170-b0a7-57b9dd5ffef3",
    "group_id" : "669476bd-89d2-45aa-8f1a-872d16de377e",
    "jar_path" : "s3a://jp-test1/program/hadoop-mapreduce-examples-2.4.1.jar",
    "input" : "s3a://jp-test1/input/",
    "output" : "s3a://jp-test1/output/",
    "job_log" : "s3a://jp-test1/joblogs/",
    "job_type" : "1",
    "file_action" : "",
    "arguments" : "wordcount",
    "hql" : "",
    "job_state" : "2",
    "job_final_status" : "1",
    "hive_script_path" : null,
    "create_by" : "3f99e3319a8943ceb15c584f3325d064",
    "finished_step" : "0",
    "job_main_id" : "",
    "job_step_id" : "",
    "postpone_at" : "1484641003174",
    "step_name" : "",
    "step_num" : "0",
    "task_num" : "0",
    "update_by" : "3f99e3319a8943ceb15c584f3325d064",
    "spend_time" : null,
    "step_seq" : "222",
    "progress" : "first progress"
  } ]
}
```

## 状态码<a name="section12685155183215"></a>

<a name="zh-cn_topic_0000001073886706_status_code"></a>
<table><thead align="left"><tr id="row1532019508328"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p3688551123210"><a name="p3688551123210"></a><a name="p3688551123210"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p8689151143215"><a name="p8689151143215"></a><a name="p8689151143215"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1032012508328"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p569019518323"><a name="p569019518323"></a><a name="p569019518323"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p14692165183214"><a name="p14692165183214"></a><a name="p14692165183214"></a>查询作业exe对象列表成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section1969325117326"></a>

请参见[错误码](错误码.md)。

