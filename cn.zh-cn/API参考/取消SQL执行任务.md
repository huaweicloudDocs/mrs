# 取消SQL执行任务<a name="CancelSql"></a>

## 功能介绍<a name="section74857255718"></a>

在MRS集群中取消一条SQL的执行任务。MRS 1.9.2及之后版本支持本接口。

## 接口约束<a name="section7544182195712"></a>

无

## URI<a name="section1760419214575"></a>

POST /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution/\{sql\_id\}/cancel

**表 1**  路径参数

<a name="table769113285710"></a>
<table><thead align="left"><tr id="row166581222575"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p16708721572"><a name="p16708721572"></a><a name="p16708721572"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p1873502125713"><a name="p1873502125713"></a><a name="p1873502125713"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p1275517295710"><a name="p1275517295710"></a><a name="p1275517295710"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p178518245711"><a name="p178518245711"></a><a name="p178518245711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row06581221577"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p188139210571"><a name="p188139210571"></a><a name="p188139210571"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1782918213578"><a name="p1782918213578"></a><a name="p1782918213578"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p785292185715"><a name="p785292185715"></a><a name="p785292185715"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1588113210572"><a name="p1588113210572"></a><a name="p1588113210572"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row11658102145716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p6908124571"><a name="p6908124571"></a><a name="p6908124571"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p392319215570"><a name="p392319215570"></a><a name="p392319215570"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p5938142165720"><a name="p5938142165720"></a><a name="p5938142165720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1795862135718"><a name="p1795862135718"></a><a name="p1795862135718"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md">获取集群ID</a>。</p>
</td>
</tr>
<tr id="row565815214572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p698217295711"><a name="p698217295711"></a><a name="p698217295711"></a>sql_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p169433577"><a name="p169433577"></a><a name="p169433577"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p11315313576"><a name="p11315313576"></a><a name="p11315313576"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p26020314572"><a name="p26020314572"></a><a name="p26020314572"></a>SQL的执行ID，即提交SQL语句返回结果中的sql_id。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section07918355716"></a>

**表 2**  请求Header参数

<a name="zh-cn_topic_0000001074096843_HeaderParameter"></a>
<table><thead align="left"><tr id="row8100237570"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p1213115395717"><a name="p1213115395717"></a><a name="p1213115395717"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p514719315711"><a name="p514719315711"></a><a name="p514719315711"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="p01636319573"><a name="p01636319573"></a><a name="p01636319573"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p id="p121808314575"><a name="p121808314575"></a><a name="p121808314575"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row5100193175712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p20201203155710"><a name="p20201203155710"></a><a name="p20201203155710"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1721833175718"><a name="p1721833175718"></a><a name="p1721833175718"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p1924513320574"><a name="p1924513320574"></a><a name="p1924513320574"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p id="p1827123145711"><a name="p1827123145711"></a><a name="p1827123145711"></a>用户Token。</p>
<p id="p62883375710"><a name="p62883375710"></a><a name="p62883375710"></a>通过调用IAM服务获取用户Token接口获取（响应消息头中X-Subject-Token的值）。</p>
</td>
</tr>
<tr id="row1761793013572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p112881127202717"><a name="p112881127202717"></a><a name="p112881127202717"></a>Content-Type</p>
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

## 响应参数<a name="section132423185718"></a>

**状态码： 200**

**表 3**  响应Body参数

<a name="zh-cn_topic_0000001074096843_responseParameter"></a>
<table><thead align="left"><tr id="row15373932573"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p041610345710"><a name="p041610345710"></a><a name="p041610345710"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p14433173105718"><a name="p14433173105718"></a><a name="p14433173105718"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p345163185718"><a name="p345163185718"></a><a name="p345163185718"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1537323155715"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p164661838576"><a name="p164661838576"></a><a name="p164661838576"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p54844365720"><a name="p54844365720"></a><a name="p54844365720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p4504735577"><a name="p4504735577"></a><a name="p4504735577"></a>错误信息。</p>
</td>
</tr>
<tr id="row10373173125710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p852393185716"><a name="p852393185716"></a><a name="p852393185716"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p95521232573"><a name="p95521232573"></a><a name="p95521232573"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p12585203145714"><a name="p12585203145714"></a><a name="p12585203145714"></a>取消SQL的执行结果。</p>
<p id="p65981317572"><a name="p65981317572"></a><a name="p65981317572"></a>说明： 默认返回SUCCEED，对于已经结束的任务也会返回SUCCEED，只有取消正在运行的SQL时没成功才会FAILED。</p>
<p id="p6611113145717"><a name="p6611113145717"></a><a name="p6611113145717"></a>枚举值：</p>
<a name="ul66352325720"></a><a name="ul66352325720"></a><ul id="ul66352325720"><li><strong id="b56541314574"><a name="b56541314574"></a><a name="b56541314574"></a>SUCCEED：成功</strong></li><li><strong id="b12681163195715"><a name="b12681163195715"></a><a name="b12681163195715"></a>FAILED：失败</strong></li></ul>
</td>
</tr>
</tbody>
</table>

**状态码： 500**

**表 4**  响应Body参数

<a name="table187003395711"></a>
<table><thead align="left"><tr id="row170063175717"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p197251032575"><a name="p197251032575"></a><a name="p197251032575"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1274383185715"><a name="p1274383185715"></a><a name="p1274383185715"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p276417311575"><a name="p276417311575"></a><a name="p276417311575"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row137009315712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p167898317578"><a name="p167898317578"></a><a name="p167898317578"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1080573185720"><a name="p1080573185720"></a><a name="p1080573185720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p682473175713"><a name="p682473175713"></a><a name="p682473175713"></a>错误信息。</p>
</td>
</tr>
<tr id="row1670017395712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p118505317577"><a name="p118505317577"></a><a name="p118505317577"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p387218317574"><a name="p387218317574"></a><a name="p387218317574"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p28999365717"><a name="p28999365717"></a><a name="p28999365717"></a>取消SQL的执行结果。</p>
<p id="p591820375711"><a name="p591820375711"></a><a name="p591820375711"></a>说明： 默认返回SUCCEED，对于已经结束的任务也会返回SUCCEED，只有取消正在运行的SQL时没成功才会FAILED。</p>
<p id="p1993516345719"><a name="p1993516345719"></a><a name="p1993516345719"></a>枚举值：</p>
<a name="ul89503317571"></a><a name="ul89503317571"></a><ul id="ul89503317571"><li><strong id="b139632312575"><a name="b139632312575"></a><a name="b139632312575"></a>SUCCEED：成功</strong></li><li><strong id="b9980203115710"><a name="b9980203115710"></a><a name="b9980203115710"></a>FAILED：失败</strong></li></ul>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="section15989193155715"></a>

取消SQL执行任务请求示例

```
POST https://{endpoint}/v2/{project_id}/clusters/{cluster_id}/sql-execution/{sql_id}/cancel
```

## 响应示例<a name="section581449572"></a>

**状态码： 200**

取消SQL执行任务成功

```
{
  "status" : "SUCCEED"
}
```

**状态码： 500**

取消SQL执行任务失败

```
{
  "status" : "FAILED",
  "message" : "Cancel sql error"
}
```

## 状态码<a name="section153700435710"></a>

<a name="zh-cn_topic_0000001074096843_status_code"></a>
<table><thead align="left"><tr id="row12387144165714"><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p id="p640954195713"><a name="p640954195713"></a><a name="p640954195713"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p id="p114324465711"><a name="p114324465711"></a><a name="p114324465711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row83872411579"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p134614405717"><a name="p134614405717"></a><a name="p134614405717"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p15481174135714"><a name="p15481174135714"></a><a name="p15481174135714"></a>取消SQL执行任务成功</p>
</td>
</tr>
<tr id="row1338713415572"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p id="p850014445719"><a name="p850014445719"></a><a name="p850014445719"></a>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p id="p351610445715"><a name="p351610445715"></a><a name="p351610445715"></a>取消SQL执行任务失败</p>
</td>
</tr>
</tbody>
</table>

## 错误码<a name="section853424175712"></a>

请参见[错误码](错误码.md)。

