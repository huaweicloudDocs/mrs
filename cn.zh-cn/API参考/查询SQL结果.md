# 查询SQL结果<a name="GetSqlResult"></a>

## 功能介绍<a name="section2582184865619"></a>

在MRS集群中查询一条SQL的执行结果。MRS 1.9.2及之后版本支持本接口。

## 接口约束<a name="section862420489569"></a>

无

## URI<a name="section86661948165614"></a>

GET /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution/\{sql\_id\}

**表 1**  路径参数

<a name="table11716144835617"></a>
<table><thead align="left"><tr id="row176981048205612"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p11732134885616"><a name="p11732134885616"></a><a name="p11732134885616"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p5755948185611"><a name="p5755948185611"></a><a name="p5755948185611"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1277504814566"><a name="p1277504814566"></a><a name="p1277504814566"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p3799204817563"><a name="p3799204817563"></a><a name="p3799204817563"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8698114845612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p28141648155610"><a name="p28141648155610"></a><a name="p28141648155610"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1183064810567"><a name="p1183064810567"></a><a name="p1183064810567"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p484984813567"><a name="p484984813567"></a><a name="p484984813567"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p887617485564"><a name="p887617485564"></a><a name="p887617485564"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row1369854820561"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1290564818568"><a name="p1290564818568"></a><a name="p1290564818568"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p129293483561"><a name="p129293483561"></a><a name="p129293483561"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p17950648135614"><a name="p17950648135614"></a><a name="p17950648135614"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p797714484567"><a name="p797714484567"></a><a name="p797714484567"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md">获取集群ID</a>。</p>
</td>
</tr>
<tr id="row15698184825611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p8996648195618"><a name="p8996648195618"></a><a name="p8996648195618"></a>sql_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p014194975616"><a name="p014194975616"></a><a name="p014194975616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2291349155619"><a name="p2291349155619"></a><a name="p2291349155619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p656184975613"><a name="p656184975613"></a><a name="p656184975613"></a>SQL的执行ID，即提交SQL语句返回结果中的sql_id。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section138644919563"></a>

**表 2**  请求Header参数

<a name="zh-cn_topic_0000001073886710_HeaderParameter"></a>
<table><thead align="left"><tr id="row91111493565"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p141493495561"><a name="p141493495561"></a><a name="p141493495561"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p11801749195612"><a name="p11801749195612"></a><a name="p11801749195612"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1820434910564"><a name="p1820434910564"></a><a name="p1820434910564"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p172231749205616"><a name="p172231749205616"></a><a name="p172231749205616"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1411274915615"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p4239104965619"><a name="p4239104965619"></a><a name="p4239104965619"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p15256204919564"><a name="p15256204919564"></a><a name="p15256204919564"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p727154918566"><a name="p727154918566"></a><a name="p727154918566"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p92921349105614"><a name="p92921349105614"></a><a name="p92921349105614"></a>用户Token。</p>
<p id="p20306104911564"><a name="p20306104911564"></a><a name="p20306104911564"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row183014213574"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
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

## 响应参数<a name="section15334134916564"></a>

**状态码： 200**

**表 3**  响应Body参数

<a name="zh-cn_topic_0000001073886710_responseParameter"></a>
<table><thead align="left"><tr id="row15365949195611"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1739584995611"><a name="p1739584995611"></a><a name="p1739584995611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p10411154925610"><a name="p10411154925610"></a><a name="p10411154925610"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p154251849105611"><a name="p154251849105611"></a><a name="p154251849105611"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row9365049125615"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1144644914566"><a name="p1144644914566"></a><a name="p1144644914566"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p54621749125619"><a name="p54621749125619"></a><a name="p54621749125619"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p3476164916567"><a name="p3476164916567"></a><a name="p3476164916567"></a>SQL的执行id。执行select、show和desc语句时才会生成id，其他操作id为空</p>
</td>
</tr>
<tr id="row14365134985616"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p649294955618"><a name="p649294955618"></a><a name="p649294955618"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p175111049205615"><a name="p175111049205615"></a><a name="p175111049205615"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p11531144935614"><a name="p11531144935614"></a><a name="p11531144935614"></a>错误信息。</p>
</td>
</tr>
<tr id="row17365114935620"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1355164935616"><a name="p1355164935616"></a><a name="p1355164935616"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p856774918566"><a name="p856774918566"></a><a name="p856774918566"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1558384911561"><a name="p1558384911561"></a><a name="p1558384911561"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="row1536514913567"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1260724916562"><a name="p1260724916562"></a><a name="p1260724916562"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p9627349135610"><a name="p9627349135610"></a><a name="p9627349135610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p16645194910563"><a name="p16645194910563"></a><a name="p16645194910563"></a>SQL的执行状态。</p>
<a name="ul12669154985618"></a><a name="ul12669154985618"></a><ul id="ul12669154985618"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="row1236534920561"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p168234492560"><a name="p168234492560"></a><a name="p168234492560"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1183774905620"><a name="p1183774905620"></a><a name="p1183774905620"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p9853114985611"><a name="p9853114985611"></a><a name="p9853114985611"></a>SQL查询语句的最终结果归档路径。</p>
<p id="p108673496568"><a name="p108673496568"></a><a name="p108673496568"></a>说明： 只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</td>
</tr>
<tr id="row133654494569"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p588218495563"><a name="p588218495563"></a><a name="p588218495563"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1289634916565"><a name="p1289634916565"></a><a name="p1289634916565"></a>Array&lt;Array&lt;String&gt;&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p19112493567"><a name="p19112493567"></a><a name="p19112493567"></a>SQL的执行结果。</p>
<p id="p16923124916560"><a name="p16923124916560"></a><a name="p16923124916560"></a>说明： 只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</td>
</tr>
</tbody>
</table>

**状态码： 500**

**表 4**  响应Body参数

<a name="table7947174985614"></a>
<table><thead align="left"><tr id="row294884912565"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p096910496564"><a name="p096910496564"></a><a name="p096910496564"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p17985184913560"><a name="p17985184913560"></a><a name="p17985184913560"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p13999549195615"><a name="p13999549195615"></a><a name="p13999549195615"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16948194985619"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p201316504568"><a name="p201316504568"></a><a name="p201316504568"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p734550175612"><a name="p734550175612"></a><a name="p734550175612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p85885016563"><a name="p85885016563"></a><a name="p85885016563"></a>SQL的执行id。执行select、show和desc语句时才会生成id，其他操作id为空</p>
</td>
</tr>
<tr id="row3948114912561"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p18723503564"><a name="p18723503564"></a><a name="p18723503564"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p186135045614"><a name="p186135045614"></a><a name="p186135045614"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p191031250175614"><a name="p191031250175614"></a><a name="p191031250175614"></a>错误信息。</p>
</td>
</tr>
<tr id="row12948104910568"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p211815011567"><a name="p211815011567"></a><a name="p211815011567"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1313720501561"><a name="p1313720501561"></a><a name="p1313720501561"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1915820505568"><a name="p1915820505568"></a><a name="p1915820505568"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="row39482498566"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p817525015569"><a name="p817525015569"></a><a name="p817525015569"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p19191750115618"><a name="p19191750115618"></a><a name="p19191750115618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p102189508569"><a name="p102189508569"></a><a name="p102189508569"></a>SQL的执行状态。</p>
<a name="ul1325405014561"></a><a name="ul1325405014561"></a><ul id="ul1325405014561"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="row15948134918562"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p2422850175618"><a name="p2422850175618"></a><a name="p2422850175618"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p6436195013564"><a name="p6436195013564"></a><a name="p6436195013564"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1045165020565"><a name="p1045165020565"></a><a name="p1045165020565"></a>SQL查询语句的最终结果归档路径。</p>
<p id="p15463650165615"><a name="p15463650165615"></a><a name="p15463650165615"></a>说明： 只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</td>
</tr>
<tr id="row1994864911567"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1047875013565"><a name="p1047875013565"></a><a name="p1047875013565"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p10503115005614"><a name="p10503115005614"></a><a name="p10503115005614"></a>Array&lt;Array&lt;String&gt;&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p952817502566"><a name="p952817502566"></a><a name="p952817502566"></a>SQL的执行结果。</p>
<p id="p755117508564"><a name="p755117508564"></a><a name="p755117508564"></a>说明： 只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section115771050135610"></a>

查询SQL结果请求示例

```
GET https://{endpoint}/v2/{project_id}/clusters/{cluster_id}/sql-execution/{sql_id}
```

## 响应示例<a name="section268155015613"></a>

**状态码： 200**

查询SQL结果成功

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

查询SQL结果失败

```
{
  "sql_id" : "20190909_011820_00151_xxxxx",
  "message" : "line 1:1: Table 'hive.default.t1' already exists",
  "statement" : "show tables",
  "status" : "FAILED"
}
```

## 状态码<a name="section385951175617"></a>

<a name="zh-cn_topic_0000001073886710_status_code"></a>
<table><thead align="left"><tr id="row1210355155617"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p16123851165619"><a name="p16123851165619"></a><a name="p16123851165619"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p17146145145619"><a name="p17146145145619"></a><a name="p17146145145619"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10103135125619"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p16160135112562"><a name="p16160135112562"></a><a name="p16160135112562"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p13175145110561"><a name="p13175145110561"></a><a name="p13175145110561"></a>查询SQL结果成功</p>
</td>
</tr>
<tr id="row4103145175616"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p16196185145617"><a name="p16196185145617"></a><a name="p16196185145617"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1921275175619"><a name="p1921275175619"></a><a name="p1921275175619"></a>查询SQL结果失败</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section023355105616"></a>

请参见[错误码](错误码.md)。

