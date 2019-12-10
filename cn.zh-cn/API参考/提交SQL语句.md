# 提交SQL语句<a name="ZH-CN_TOPIC_0192504943"></a>

## 功能介绍<a name="section4408504619327"></a>

在MRS集群中提交并执行一条SQL语句。MRS 2.0.5及之后版本支持本接口。

## URI<a name="section10186656193217"></a>

-   URI格式

    POST  /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution

-   参数说明

    **表 1**  URI参数说明

    <a name="table49499141194754"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0176790808_row33700024194754"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0176790808_p16571835194812"><a name="zh-cn_topic_0176790808_p16571835194812"></a><a name="zh-cn_topic_0176790808_p16571835194812"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0176790808_p141410194812"><a name="zh-cn_topic_0176790808_p141410194812"></a><a name="zh-cn_topic_0176790808_p141410194812"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0176790808_p11454278194812"><a name="zh-cn_topic_0176790808_p11454278194812"></a><a name="zh-cn_topic_0176790808_p11454278194812"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0176790808_row39786771142917"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0176790808_p1503055142917"><a name="zh-cn_topic_0176790808_p1503055142917"></a><a name="zh-cn_topic_0176790808_p1503055142917"></a>project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0176790808_p54638598142917"><a name="zh-cn_topic_0176790808_p54638598142917"></a><a name="zh-cn_topic_0176790808_p54638598142917"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0176790808_p63650338142917"><a name="zh-cn_topic_0176790808_p63650338142917"></a><a name="zh-cn_topic_0176790808_p63650338142917"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0176790808_row3457216201210"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0176790808_p194589160122"><a name="zh-cn_topic_0176790808_p194589160122"></a><a name="zh-cn_topic_0176790808_p194589160122"></a>cluster_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0176790808_p045813165125"><a name="zh-cn_topic_0176790808_p045813165125"></a><a name="zh-cn_topic_0176790808_p045813165125"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0176790808_p1845891641218"><a name="zh-cn_topic_0176790808_p1845891641218"></a><a name="zh-cn_topic_0176790808_p1845891641218"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md#section177891315153619">获取集群ID</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 请求消息<a name="section673761354213"></a>

**表 2**  请求参数说明

<a name="table718317711336"></a>
<table><thead align="left"><tr id="row1018318753315"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p1818367143313"><a name="p1818367143313"></a><a name="p1818367143313"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p05712238338"><a name="p05712238338"></a><a name="p05712238338"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p3183167173320"><a name="p3183167173320"></a><a name="p3183167173320"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p151839714333"><a name="p151839714333"></a><a name="p151839714333"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row818413783313"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p2739195963320"><a name="p2739195963320"></a><a name="p2739195963320"></a>sql_type</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p873913592335"><a name="p873913592335"></a><a name="p873913592335"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p147393591333"><a name="p147393591333"></a><a name="p147393591333"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p17739175913337"><a name="p17739175913337"></a><a name="p17739175913337"></a>SQL类型。目前仅支持“presto”类型的SQL。</p>
<div class="note" id="note97250467342"><a name="note97250467342"></a><a name="note97250467342"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p13726144614345"><a name="p13726144614345"></a><a name="p13726144614345"></a>只有包含Presto组件的集群才能提交执行presto类型的SQL。</p>
</div></div>
</td>
</tr>
<tr id="row107561512336"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p173915916331"><a name="p173915916331"></a><a name="p173915916331"></a>sql_content</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p10739115923315"><a name="p10739115923315"></a><a name="p10739115923315"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1973915915334"><a name="p1973915915334"></a><a name="p1973915915334"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p973995933312"><a name="p973995933312"></a><a name="p973995933312"></a>待执行的SQL语句。</p>
<div class="note" id="note75421712163617"><a name="note75421712163617"></a><a name="note75421712163617"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1554317128365"><a name="p1554317128365"></a><a name="p1554317128365"></a>目前仅支持执行单条语句，语句中不包含“;”。</p>
</div></div>
</td>
</tr>
<tr id="row460852183316"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1173918594332"><a name="p1173918594332"></a><a name="p1173918594332"></a>database</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p373975920339"><a name="p373975920339"></a><a name="p373975920339"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p19739259123319"><a name="p19739259123319"></a><a name="p19739259123319"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p14739125993319"><a name="p14739125993319"></a><a name="p14739125993319"></a>执行SQL所在的数据库，默认为default。</p>
</td>
</tr>
<tr id="row10385195283318"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p173995933316"><a name="p173995933316"></a><a name="p173995933316"></a>archive_path</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p167391159103310"><a name="p167391159103310"></a><a name="p167391159103310"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p12740059153317"><a name="p12740059153317"></a><a name="p12740059153317"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p574085918334"><a name="p574085918334"></a><a name="p574085918334"></a>SQL执行结果的转储文件夹。</p>
<div class="note" id="note129817113717"><a name="note129817113717"></a><a name="note129817113717"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p103010713377"><a name="p103010713377"></a><a name="p103010713377"></a>只有select语句才会转储查询的结果。当前仅支持转储到OBS中。</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section775516131425"></a>

**表 3**  响应参数说明

<a name="table12040613193927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0177065250_row8843854193927"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0177065250_p45263556193927"><a name="zh-cn_topic_0177065250_p45263556193927"></a><a name="zh-cn_topic_0177065250_p45263556193927"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="24.94%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0177065250_p1907984993927"><a name="zh-cn_topic_0177065250_p1907984993927"></a><a name="zh-cn_topic_0177065250_p1907984993927"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0177065250_p17473879193927"><a name="zh-cn_topic_0177065250_p17473879193927"></a><a name="zh-cn_topic_0177065250_p17473879193927"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0177065250_row8387056194027"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p13371162611389"><a name="p13371162611389"></a><a name="p13371162611389"></a>sql_id</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p123711626143819"><a name="p123711626143819"></a><a name="p123711626143819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p12371202623814"><a name="p12371202623814"></a><a name="p12371202623814"></a>SQL的执行ID。</p>
</td>
</tr>
<tr id="row04111663819"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p19371102619383"><a name="p19371102619383"></a><a name="p19371102619383"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p1237112619387"><a name="p1237112619387"></a><a name="p1237112619387"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p113712267381"><a name="p113712267381"></a><a name="p113712267381"></a>错误信息。</p>
</td>
</tr>
<tr id="row12221316163813"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p17371526153820"><a name="p17371526153820"></a><a name="p17371526153820"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p20371132623814"><a name="p20371132623814"></a><a name="p20371132623814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1537152653818"><a name="p1537152653818"></a><a name="p1537152653818"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="row1941301612382"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p1437222613384"><a name="p1437222613384"></a><a name="p1437222613384"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p037292620383"><a name="p037292620383"></a><a name="p037292620383"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p17372142620383"><a name="p17372142620383"></a><a name="p17372142620383"></a>SQL的执行状态。</p>
<a name="ul99208573388"></a><a name="ul99208573388"></a><ul id="ul99208573388"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="row4616316143820"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p337282643816"><a name="p337282643816"></a><a name="p337282643816"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p10372526203814"><a name="p10372526203814"></a><a name="p10372526203814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p8372426123813"><a name="p8372426123813"></a><a name="p8372426123813"></a>SQL查询语句的最终结果归档路径。</p>
<div class="note" id="note88976412399"><a name="note88976412399"></a><a name="note88976412399"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1689984111393"><a name="p1689984111393"></a><a name="p1689984111393"></a>只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</div></div>
</td>
</tr>
<tr id="row10848151618387"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p1037216265382"><a name="p1037216265382"></a><a name="p1037216265382"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p123726263385"><a name="p123726263385"></a><a name="p123726263385"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p133721326103811"><a name="p133721326103811"></a><a name="p133721326103811"></a>SQL的执行结果。</p>
<div class="note" id="note939175614390"><a name="note939175614390"></a><a name="note939175614390"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p542165615391"><a name="p542165615391"></a><a name="p542165615391"></a>只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## 示例<a name="section1210015461189"></a>

-   请求示例

    ```
    {
        "sql_type":"presto", 
        "sql_content":"show tables", 
        "database":"default", 
        "archive_path":"obs://my-bucket/path"
     }
    ```

-   响应示例
    -   成功示例

        ```
        {
            "sql_id":"20190909_011820_00151_xxxxx", 
            "statement":"show tables",
            "status":”FINISHED”,
            "result_location":" obs://my_bucket/uuid_date/xxxx.csv",  
            "content":[
               ["t1"],["t2"],["t3"]   
              ] 
         }
        ```

    -   失败示例

        ```
        { 
            "sql_id":"20190909_011820_00151_xxxxx", 
            "message":"line 1:1: Table 'hive.default.t1' already exists",
            "statement":"show tables",
            "status":”FAILED”
         }
        ```



## 状态码<a name="section4391766619434"></a>

状态码请参见[状态码](状态码.md)。

