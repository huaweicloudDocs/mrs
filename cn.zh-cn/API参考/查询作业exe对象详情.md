# 查询作业exe对象详情<a name="GetJobExes"></a>

## 功能介绍<a name="section17416650153217"></a>

查询指定作业的exe对象详细信息。该接口不兼容Sahara。

## 接口约束<a name="section18424185033213"></a>

无

## URI<a name="section1043119506322"></a>

GET /v1.1/\{project\_id\}/job-exes/\{job\_exe\_id\}

**表 1**  路径参数

<a name="table1744035083216"></a>
<table><thead align="left"><tr id="row94371508323"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p104421450113213"><a name="p104421450113213"></a><a name="p104421450113213"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p3445195015321"><a name="p3445195015321"></a><a name="p3445195015321"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1044825043215"><a name="p1044825043215"></a><a name="p1044825043215"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p2451750123210"><a name="p2451750123210"></a><a name="p2451750123210"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row74376501324"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1454105023219"><a name="p1454105023219"></a><a name="p1454105023219"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2457165013218"><a name="p2457165013218"></a><a name="p2457165013218"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p3460145016329"><a name="p3460145016329"></a><a name="p3460145016329"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p20463145014328"><a name="p20463145014328"></a><a name="p20463145014328"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row84374501321"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14466135010329"><a name="p14466135010329"></a><a name="p14466135010329"></a>job_exe_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p446945020321"><a name="p446945020321"></a><a name="p446945020321"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p174725502329"><a name="p174725502329"></a><a name="p174725502329"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p84768503326"><a name="p84768503326"></a><a name="p84768503326"></a>作业ID。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section1648005063220"></a>

**表 2**  请求Header参数

<a name="zh-cn_topic_0000001074096839_HeaderParameter"></a>
<table><thead align="left"><tr id="row248355073212"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1948835013218"><a name="p1948835013218"></a><a name="p1948835013218"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p349105003214"><a name="p349105003214"></a><a name="p349105003214"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p9494205043218"><a name="p9494205043218"></a><a name="p9494205043218"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p349710501325"><a name="p349710501325"></a><a name="p349710501325"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1648355023217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p7500125063217"><a name="p7500125063217"></a><a name="p7500125063217"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1450355020321"><a name="p1450355020321"></a><a name="p1450355020321"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1450610507323"><a name="p1450610507323"></a><a name="p1450610507323"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p105091350163216"><a name="p105091350163216"></a><a name="p105091350163216"></a>用户Token。</p>
<p id="p1851135003210"><a name="p1851135003210"></a><a name="p1851135003210"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row1478712611118"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
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

## 响应参数<a name="section351515509329"></a>

**状态码： 200**

**表 3**  响应Body参数

<a name="zh-cn_topic_0000001074096839_responseParameter"></a>
<table><thead align="left"><tr id="row7522145015329"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1529165033211"><a name="p1529165033211"></a><a name="p1529165033211"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p16533115013215"><a name="p16533115013215"></a><a name="p16533115013215"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p2537175019329"><a name="p2537175019329"></a><a name="p2537175019329"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7522550123213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p754065093214"><a name="p754065093214"></a><a name="p754065093214"></a>job_execution</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p135431150173218"><a name="p135431150173218"></a><a name="p135431150173218"></a><a href="#zh-cn_topic_0000001074096839_response_JobExeResult">JobExeResult</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p9547145023217"><a name="p9547145023217"></a><a name="p9547145023217"></a>作业详细信息。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  JobExeResult

<a name="zh-cn_topic_0000001074096839_response_JobExeResult"></a>
<table><thead align="left"><tr id="row5551185093214"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p165592050123212"><a name="p165592050123212"></a><a name="p165592050123212"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11562135053215"><a name="p11562135053215"></a><a name="p11562135053215"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p145661650183219"><a name="p145661650183219"></a><a name="p145661650183219"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row2055165053219"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1656914507329"><a name="p1656914507329"></a><a name="p1656914507329"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p35721450183214"><a name="p35721450183214"></a><a name="p35721450183214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p2575115010325"><a name="p2575115010325"></a><a name="p2575115010325"></a>作业ID。</p>
</td>
</tr>
<tr id="row4552750163211"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p257845015323"><a name="p257845015323"></a><a name="p257845015323"></a>create_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20582450153220"><a name="p20582450153220"></a><a name="p20582450153220"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14585115013328"><a name="p14585115013328"></a><a name="p14585115013328"></a>作业创建时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row125521450183215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p3588155053211"><a name="p3588155053211"></a><a name="p3588155053211"></a>update_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1591350203216"><a name="p1591350203216"></a><a name="p1591350203216"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p55931050143210"><a name="p55931050143210"></a><a name="p55931050143210"></a>作业更新时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row2055220507326"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p659605033217"><a name="p659605033217"></a><a name="p659605033217"></a>tenant_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1060112504320"><a name="p1060112504320"></a><a name="p1060112504320"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p13605195013322"><a name="p13605195013322"></a><a name="p13605195013322"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row18552185013213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15608115083215"><a name="p15608115083215"></a><a name="p15608115083215"></a>job_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p0611135093214"><a name="p0611135093214"></a><a name="p0611135093214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p661455083216"><a name="p661455083216"></a><a name="p661455083216"></a>作业ID。</p>
</td>
</tr>
<tr id="row155225015325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1617165010321"><a name="p1617165010321"></a><a name="p1617165010321"></a>job_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p116207504329"><a name="p116207504329"></a><a name="p116207504329"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p962305017328"><a name="p962305017328"></a><a name="p962305017328"></a>作业名称。</p>
</td>
</tr>
<tr id="row1655285015324"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p362715010323"><a name="p362715010323"></a><a name="p362715010323"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p136303505323"><a name="p136303505323"></a><a name="p136303505323"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p106331450193217"><a name="p106331450193217"></a><a name="p106331450193217"></a>作业执行开始时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row14552450133220"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p14635350183212"><a name="p14635350183212"></a><a name="p14635350183212"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1639145018328"><a name="p1639145018328"></a><a name="p1639145018328"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1164295018328"><a name="p1164295018328"></a><a name="p1164295018328"></a>作业执行结束时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row8552185023214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p166451550183214"><a name="p166451550183214"></a><a name="p166451550183214"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p56482050123212"><a name="p56482050123212"></a><a name="p56482050123212"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1765235015323"><a name="p1765235015323"></a><a name="p1765235015323"></a>作业所属集群ID。</p>
</td>
</tr>
<tr id="row955275033217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1465655093218"><a name="p1465655093218"></a><a name="p1465655093218"></a>group_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p365985073212"><a name="p365985073212"></a><a name="p365985073212"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p566215053218"><a name="p566215053218"></a><a name="p566215053218"></a>作业执行组ID</p>
</td>
</tr>
<tr id="row255212509328"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1866535093219"><a name="p1866535093219"></a><a name="p1866535093219"></a>jar_path</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p146681350113210"><a name="p146681350113210"></a><a name="p146681350113210"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p20670175083219"><a name="p20670175083219"></a><a name="p20670175083219"></a>执行程序jar包或sql文件地址。</p>
</td>
</tr>
<tr id="row17552145017327"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6673165093213"><a name="p6673165093213"></a><a name="p6673165093213"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9676950153211"><a name="p9676950153211"></a><a name="p9676950153211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1680550123211"><a name="p1680550123211"></a><a name="p1680550123211"></a>数据输入地址。</p>
</td>
</tr>
<tr id="row05521350163215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p868335010325"><a name="p868335010325"></a><a name="p868335010325"></a>onput</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p068645013326"><a name="p068645013326"></a><a name="p068645013326"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p56896504321"><a name="p56896504321"></a><a name="p56896504321"></a>数据输出地址。</p>
</td>
</tr>
<tr id="row15553125093218"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p16693650163211"><a name="p16693650163211"></a><a name="p16693650163211"></a>job_log</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p969605073213"><a name="p969605073213"></a><a name="p969605073213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p36981050173219"><a name="p36981050173219"></a><a name="p36981050173219"></a>作业日志存储地址</p>
</td>
</tr>
<tr id="row9553135073215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p3701165003220"><a name="p3701165003220"></a><a name="p3701165003220"></a>job_type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p117053506328"><a name="p117053506328"></a><a name="p117053506328"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1570835016321"><a name="p1570835016321"></a><a name="p1570835016321"></a>作业类型码。</p>
<a name="ul18713165083216"></a><a name="ul18713165083216"></a><ul id="ul18713165083216"><li>1：MapReduce</li><li>2：Spark</li><li>3：Hive Script</li><li>4：HiveSQL（当前不支持）</li><li>5：DistCp</li><li>6：Spark Script</li><li>7：Spark SQL（该接口当前不支持</li></ul>
</td>
</tr>
<tr id="row055365023217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p8737105063220"><a name="p8737105063220"></a><a name="p8737105063220"></a>file_action</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1474013504325"><a name="p1474013504325"></a><a name="p1474013504325"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7743950193215"><a name="p7743950193215"></a><a name="p7743950193215"></a>导入导出数据。</p>
</td>
</tr>
<tr id="row85531750203210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p207461850103211"><a name="p207461850103211"></a><a name="p207461850103211"></a>arguments</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p147491150113211"><a name="p147491150113211"></a><a name="p147491150113211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1675395033219"><a name="p1675395033219"></a><a name="p1675395033219"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。该参数可为空。</p>
</td>
</tr>
<tr id="row155318505326"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2075665016323"><a name="p2075665016323"></a><a name="p2075665016323"></a>hql</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p147601450153217"><a name="p147601450153217"></a><a name="p147601450153217"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p976419505325"><a name="p976419505325"></a><a name="p976419505325"></a>HQL脚本语句。</p>
</td>
</tr>
<tr id="row1553450133210"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1376895043210"><a name="p1376895043210"></a><a name="p1376895043210"></a>job_state</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1771115013211"><a name="p1771115013211"></a><a name="p1771115013211"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p197741250173215"><a name="p197741250173215"></a><a name="p197741250173215"></a>作业状态编码：</p>
<a name="ul17781650133215"></a><a name="ul17781650133215"></a><ul id="ul17781650133215"><li>-1：Terminated表示已终止的作业状态</li><li>2：Running表示运行中的作业状态</li><li>3：Completed表示已完成的作业状态</li><li>4：Abnormal表示异常的作业状态</li></ul>
</td>
</tr>
<tr id="row2553175083216"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p20793250123213"><a name="p20793250123213"></a><a name="p20793250123213"></a>job_final_status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1079625014320"><a name="p1079625014320"></a><a name="p1079625014320"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1280011505325"><a name="p1280011505325"></a><a name="p1280011505325"></a>作业最终状态码。</p>
<a name="ul880365083217"></a><a name="ul880365083217"></a><ul id="ul880365083217"><li>0：未完成</li><li>1：执行错误，终止执行</li><li>2：执行完成并且成功</li><li>3：已取消</li></ul>
</td>
</tr>
<tr id="row2553145017322"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15819165083211"><a name="p15819165083211"></a><a name="p15819165083211"></a>hive_script_path</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1822150183212"><a name="p1822150183212"></a><a name="p1822150183212"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p14824205083219"><a name="p14824205083219"></a><a name="p14824205083219"></a>Hive脚本地址。</p>
</td>
</tr>
<tr id="row45538508329"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p48271350163218"><a name="p48271350163218"></a><a name="p48271350163218"></a>create_by</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15831155019323"><a name="p15831155019323"></a><a name="p15831155019323"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p15833205019324"><a name="p15833205019324"></a><a name="p15833205019324"></a>创建作业的用户ID。</p>
</td>
</tr>
<tr id="row155531950103216"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p28361350153216"><a name="p28361350153216"></a><a name="p28361350153216"></a>finished_step</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p168401506329"><a name="p168401506329"></a><a name="p168401506329"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3843155019322"><a name="p3843155019322"></a><a name="p3843155019322"></a>当前已完成的步骤数。</p>
</td>
</tr>
<tr id="row13553650113212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p884645011324"><a name="p884645011324"></a><a name="p884645011324"></a>job_main_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p18545508323"><a name="p18545508323"></a><a name="p18545508323"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p7857165014329"><a name="p7857165014329"></a><a name="p7857165014329"></a>作业主ID。</p>
</td>
</tr>
<tr id="row1355345053220"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1486075073213"><a name="p1486075073213"></a><a name="p1486075073213"></a>job_step_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p188636501329"><a name="p188636501329"></a><a name="p188636501329"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11866175017325"><a name="p11866175017325"></a><a name="p11866175017325"></a>作业步骤ID。</p>
</td>
</tr>
<tr id="row6553135011325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p586995011329"><a name="p586995011329"></a><a name="p586995011329"></a>postpone_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p2872350183219"><a name="p2872350183219"></a><a name="p2872350183219"></a>Long</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1087535063211"><a name="p1087535063211"></a><a name="p1087535063211"></a>延迟时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row2554175019323"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p14878150143212"><a name="p14878150143212"></a><a name="p14878150143212"></a>step_name</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p0882750133210"><a name="p0882750133210"></a><a name="p0882750133210"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p18885175019323"><a name="p18885175019323"></a><a name="p18885175019323"></a>作业步骤名。</p>
</td>
</tr>
<tr id="row4554250193217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p108881950143215"><a name="p108881950143215"></a><a name="p108881950143215"></a>step_num</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p489165033217"><a name="p489165033217"></a><a name="p489165033217"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p168961250173216"><a name="p168961250173216"></a><a name="p168961250173216"></a>步骤数量。</p>
</td>
</tr>
<tr id="row15541450103216"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p38991050183211"><a name="p38991050183211"></a><a name="p38991050183211"></a>task_num</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14902185011320"><a name="p14902185011320"></a><a name="p14902185011320"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1990545023217"><a name="p1990545023217"></a><a name="p1990545023217"></a>任务数量。</p>
</td>
</tr>
<tr id="row145547503325"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15909185012321"><a name="p15909185012321"></a><a name="p15909185012321"></a>update_by</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1691365033210"><a name="p1691365033210"></a><a name="p1691365033210"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p8917450163210"><a name="p8917450163210"></a><a name="p8917450163210"></a>更新作业的用户ID。</p>
</td>
</tr>
<tr id="row185541950143213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p99201508321"><a name="p99201508321"></a><a name="p99201508321"></a>spend_time</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p8922195015322"><a name="p8922195015322"></a><a name="p8922195015322"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p17926155014327"><a name="p17926155014327"></a><a name="p17926155014327"></a>作业执行持续时间，单位：秒。</p>
</td>
</tr>
<tr id="row1455485013324"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1593075013218"><a name="p1593075013218"></a><a name="p1593075013218"></a>step_seq</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p7932195043212"><a name="p7932195043212"></a><a name="p7932195043212"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p69351850143213"><a name="p69351850143213"></a><a name="p69351850143213"></a>步骤序列号。</p>
</td>
</tr>
<tr id="row1455435013323"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p9938115019323"><a name="p9938115019323"></a><a name="p9938115019323"></a>progress</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p15942205010323"><a name="p15942205010323"></a><a name="p15942205010323"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p179451750143213"><a name="p179451750143213"></a><a name="p179451750143213"></a>作业执行进度。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section209491650163211"></a>

查询作业exe对象详情请求示例

```
GET https://{endpoint}/v1.1/{project_id}/job-exes/{job_exe_id}
```

## 响应示例<a name="section159621650203215"></a>

**状态码： 200**

查询作业exe对象详情成功。

```
{
  "job_execution" : {
    "id" : "632863d5-15d4-4691-9dc1-1a72340cb097",
    "create_at" : "1484240559176",
    "update_at" : "1484240559176",
    "tenant_id" : "3f99e3319a8943ceb15c584f3325d064",
    "job_id" : "632863d5-15d4-4691-9dc1-1a72340cb097",
    "job_name" : "hive_script",
    "start_time" : "1484240559176",
    "end_time" : null,
    "cluster_id" : "8b1d55f6-150e-45e2-8347-b2ca608d366b",
    "group_id" : "632863d5-15d4-4691-9dc1-1a72340cb097",
    "jar_path" : "s3a://jp-test1/program/Hivescript.sql",
    "input" : "s3a://jp-test1/input/",
    "output" : "s3a://jp-test1/output/",
    "job_log" : "s3a://jp-test1/joblogs/",
    "job_type" : "3",
    "file_action" : "",
    "arguments" : "wordcount",
    "hql" : null,
    "job_state" : "3",
    "job_final_status" : "1",
    "hive_script_path" : "s3a://jp-test1/program/Hivescript.sql",
    "create_by" : "3f99e3319a8943ceb15c584f3325d064",
    "finished_step" : "0",
    "job_main_id" : "",
    "job_step_id" : "",
    "postpone_at" : "1484240558705",
    "step_name" : "",
    "step_num" : "0",
    "task_num" : "0",
    "update_by" : "3f99e3319a8943ceb15c584f3325d064",
    "spend_time" : null,
    "step_seq" : "222",
    "progress" : "first progress"
  }
}
```

## 状态码<a name="section571617519324"></a>

<a name="zh-cn_topic_0000001074096839_status_code"></a>
<table><thead align="left"><tr id="row18620516323"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p1971815143217"><a name="p1971815143217"></a><a name="p1971815143217"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p12720115133213"><a name="p12720115133213"></a><a name="p12720115133213"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row17861051133217"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p207211351143210"><a name="p207211351143210"></a><a name="p207211351143210"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1722125111321"><a name="p1722125111321"></a><a name="p1722125111321"></a>查询作业exe对象详情成功。</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section13723551153213"></a>

请参见[错误码](错误码.md)。

