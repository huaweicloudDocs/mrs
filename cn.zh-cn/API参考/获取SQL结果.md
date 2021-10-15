# 获取SQL结果<a name="GetSqlResultWithJob"></a>

## 功能介绍<a name="section2394191317325"></a>

在MRS集群中查询SparkSql和SparkScript两种类型作业的SQL语句运行完成后返回的查询结果。

## 接口约束<a name="section14398151393210"></a>

无

## URI<a name="section1039961317323"></a>

GET /v2/\{project\_id\}/clusters/\{cluster\_id\}/job-executions/\{job\_execution\_id\}/sql-result

**表 1**  路径参数

<a name="table640391383219"></a>
<table><thead align="left"><tr id="row19402201314328"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p540451363215"><a name="p540451363215"></a><a name="p540451363215"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p154054137323"><a name="p154054137323"></a><a name="p154054137323"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p12407141393219"><a name="p12407141393219"></a><a name="p12407141393219"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p240818138325"><a name="p240818138325"></a><a name="p240818138325"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row140201373213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p84091613163216"><a name="p84091613163216"></a><a name="p84091613163216"></a>job_execution_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p154124134323"><a name="p154124134323"></a><a name="p154124134323"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2042491314323"><a name="p2042491314323"></a><a name="p2042491314323"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p2425113123216"><a name="p2425113123216"></a><a name="p2425113123216"></a>作业ID。获取方法，请参见<a href="获取MRS集群信息.md">获取作业ID</a>。</p>
</td>
</tr>
<tr id="row940281313321"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p15427713133215"><a name="p15427713133215"></a><a name="p15427713133215"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1842715131321"><a name="p1842715131321"></a><a name="p1842715131321"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1742911131325"><a name="p1742911131325"></a><a name="p1742911131325"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p14301913193212"><a name="p14301913193212"></a><a name="p14301913193212"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row840231373218"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p2043181311325"><a name="p2043181311325"></a><a name="p2043181311325"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p164323135323"><a name="p164323135323"></a><a name="p164323135323"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p164331913163210"><a name="p164331913163210"></a><a name="p164331913163210"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p5434613133214"><a name="p5434613133214"></a><a name="p5434613133214"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md">获取集群ID</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section194345131325"></a>

**表 2**  请求Header参数

<a name="zh-cn_topic_0000001073526613_HeaderParameter"></a>
<table><thead align="left"><tr id="row443631311320"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1044151363215"><a name="p1044151363215"></a><a name="p1044151363215"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p144361383218"><a name="p144361383218"></a><a name="p144361383218"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p174441713183211"><a name="p174441713183211"></a><a name="p174441713183211"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p4445121310327"><a name="p4445121310327"></a><a name="p4445121310327"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12436613123217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p14461813123216"><a name="p14461813123216"></a><a name="p14461813123216"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p18446151311325"><a name="p18446151311325"></a><a name="p18446151311325"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p844741383220"><a name="p844741383220"></a><a name="p844741383220"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p144851353213"><a name="p144851353213"></a><a name="p144851353213"></a>用户Token。</p>
<p id="p4448101318328"><a name="p4448101318328"></a><a name="p4448101318328"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row1080194595612"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
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

## 响应参数<a name="section17449141319323"></a>

**状态码： 200**

**表 3**  响应Body参数

<a name="zh-cn_topic_0000001073526613_responseParameter"></a>
<table><thead align="left"><tr id="row24521013143210"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p1045701313329"><a name="p1045701313329"></a><a name="p1045701313329"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1145915136322"><a name="p1145915136322"></a><a name="p1145915136322"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p18460101393211"><a name="p18460101393211"></a><a name="p18460101393211"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row645271318321"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p74606139323"><a name="p74606139323"></a><a name="p74606139323"></a>sql_results</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p74614132327"><a name="p74614132327"></a><a name="p74614132327"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1046211313322"><a name="p1046211313322"></a><a name="p1046211313322"></a>SQL语句查询结果。</p>
</td>
</tr>
</tbody>
</table>

**状态码： 500**

**表 4**  响应Body参数

<a name="table17463913123210"></a>
<table><thead align="left"><tr id="row746518137321"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p11467313123220"><a name="p11467313123220"></a><a name="p11467313123220"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1246861373210"><a name="p1246861373210"></a><a name="p1246861373210"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1246813136324"><a name="p1246813136324"></a><a name="p1246813136324"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18465111320326"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1047271316327"><a name="p1047271316327"></a><a name="p1047271316327"></a>sql_results</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p447321363216"><a name="p447321363216"></a><a name="p447321363216"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1247571316325"><a name="p1247571316325"></a><a name="p1247571316325"></a>SQL语句查询结果。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section154761413143212"></a>

获取SQL结果请求示例

```
GET https://{endpoint}/v2/{project_id}/clusters/{cluster_id}/job-executions/{job_execution_id}/sql-result
```

## 响应示例<a name="section248010132329"></a>

**状态码： 200**

获取SQL结果成功

```
{
  "sql_results" : {
    "0" : [ {
      "result" : "succeed"
    } ],
    "1" : [ {
      "database" : "default",
      "isTemporary" : "false",
      "tableName" : "src_wordcount"
    } ],
    "2" : [ {
      "result" : "succeed"
    } ],
    "3" : [ {
      "result" : "succeed"
    } ],
    "4" : [ {
      "name" : "a",
      "id" : "1"
    }, {
      "name" : "b",
      "id" : "2"
    } ]
  }
}
```

**状态码： 500**

收集SQL作业结果失败

```
{
  "error_msg" : "收集SQL作业结果失败",
  "error_code" : "0172"
}
```

## 状态码<a name="section195147135325"></a>

<a name="zh-cn_topic_0000001073526613_status_code"></a>
<table><thead align="left"><tr id="row651918130329"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p155201513183215"><a name="p155201513183215"></a><a name="p155201513183215"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p85211313173219"><a name="p85211313173219"></a><a name="p85211313173219"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13519101373210"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p10522113193211"><a name="p10522113193211"></a><a name="p10522113193211"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p1052313136328"><a name="p1052313136328"></a><a name="p1052313136328"></a>获取SQL结果成功</p>
</td>
</tr>
<tr id="row251941383217"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p6524101315321"><a name="p6524101315321"></a><a name="p6524101315321"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p452513130321"><a name="p452513130321"></a><a name="p452513130321"></a>收集SQL作业结果失败</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section1652615133321"></a>

请参见[错误码](错误码.md)。

