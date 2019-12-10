# 查询SQL结果<a name="ZH-CN_TOPIC_0192504944"></a>

## 功能介绍<a name="section4408504619327"></a>

在MRS集群中查询一条SQL的执行结果。MRS 2.0.5及之后版本支持本接口。

## URI<a name="section10186656193217"></a>

-   URI格式

    GET  /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution/\{sql\_id\}

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
    <tr id="zh-cn_topic_0176790808_row121835121146"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p967461817429"><a name="p967461817429"></a><a name="p967461817429"></a>sql_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p46749186427"><a name="p46749186427"></a><a name="p46749186427"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p16674131884215"><a name="p16674131884215"></a><a name="p16674131884215"></a>SQL的执行ID，即<a href="提交SQL语句.md">提交SQL语句</a>返回结果中的sql_id。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 请求消息<a name="section673761354213"></a>

**请求参数**

无。

## 响应参数<a name="section775516131425"></a>

**表 2**  响应参数说明

<a name="table12040613193927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0192504943_zh-cn_topic_0177065250_row8843854193927"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p45263556193927"><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p45263556193927"></a><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p45263556193927"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="24.94%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p1907984993927"><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p1907984993927"></a><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p1907984993927"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p17473879193927"><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p17473879193927"></a><a name="zh-cn_topic_0192504943_zh-cn_topic_0177065250_p17473879193927"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0192504943_zh-cn_topic_0177065250_row8387056194027"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p13371162611389"><a name="zh-cn_topic_0192504943_p13371162611389"></a><a name="zh-cn_topic_0192504943_p13371162611389"></a>sql_id</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p123711626143819"><a name="zh-cn_topic_0192504943_p123711626143819"></a><a name="zh-cn_topic_0192504943_p123711626143819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p12371202623814"><a name="zh-cn_topic_0192504943_p12371202623814"></a><a name="zh-cn_topic_0192504943_p12371202623814"></a>SQL的执行ID。</p>
</td>
</tr>
<tr id="zh-cn_topic_0192504943_row04111663819"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p19371102619383"><a name="zh-cn_topic_0192504943_p19371102619383"></a><a name="zh-cn_topic_0192504943_p19371102619383"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p1237112619387"><a name="zh-cn_topic_0192504943_p1237112619387"></a><a name="zh-cn_topic_0192504943_p1237112619387"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p113712267381"><a name="zh-cn_topic_0192504943_p113712267381"></a><a name="zh-cn_topic_0192504943_p113712267381"></a>错误信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0192504943_row12221316163813"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p17371526153820"><a name="zh-cn_topic_0192504943_p17371526153820"></a><a name="zh-cn_topic_0192504943_p17371526153820"></a>statement</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p20371132623814"><a name="zh-cn_topic_0192504943_p20371132623814"></a><a name="zh-cn_topic_0192504943_p20371132623814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p1537152653818"><a name="zh-cn_topic_0192504943_p1537152653818"></a><a name="zh-cn_topic_0192504943_p1537152653818"></a>执行的SQL语句。</p>
</td>
</tr>
<tr id="zh-cn_topic_0192504943_row1941301612382"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p1437222613384"><a name="zh-cn_topic_0192504943_p1437222613384"></a><a name="zh-cn_topic_0192504943_p1437222613384"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p037292620383"><a name="zh-cn_topic_0192504943_p037292620383"></a><a name="zh-cn_topic_0192504943_p037292620383"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p17372142620383"><a name="zh-cn_topic_0192504943_p17372142620383"></a><a name="zh-cn_topic_0192504943_p17372142620383"></a>SQL的执行状态。</p>
<a name="zh-cn_topic_0192504943_ul99208573388"></a><a name="zh-cn_topic_0192504943_ul99208573388"></a><ul id="zh-cn_topic_0192504943_ul99208573388"><li>QUEUED</li><li>WAITING_FOR_RESOURCES</li><li>PLANNING</li><li>STARTING</li><li>RUNNING</li><li>FINISHING</li><li>FINISHED</li><li>FAILED</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0192504943_row4616316143820"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p337282643816"><a name="zh-cn_topic_0192504943_p337282643816"></a><a name="zh-cn_topic_0192504943_p337282643816"></a>result_location</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p10372526203814"><a name="zh-cn_topic_0192504943_p10372526203814"></a><a name="zh-cn_topic_0192504943_p10372526203814"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p8372426123813"><a name="zh-cn_topic_0192504943_p8372426123813"></a><a name="zh-cn_topic_0192504943_p8372426123813"></a>SQL查询语句的最终结果归档路径。</p>
<div class="note" id="zh-cn_topic_0192504943_note88976412399"><a name="zh-cn_topic_0192504943_note88976412399"></a><a name="zh-cn_topic_0192504943_note88976412399"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0192504943_p1689984111393"><a name="zh-cn_topic_0192504943_p1689984111393"></a><a name="zh-cn_topic_0192504943_p1689984111393"></a>只有select的语句才会在将SQL的执行结果转储到result_location中。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0192504943_row10848151618387"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504943_p1037216265382"><a name="zh-cn_topic_0192504943_p1037216265382"></a><a name="zh-cn_topic_0192504943_p1037216265382"></a>content</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504943_p123726263385"><a name="zh-cn_topic_0192504943_p123726263385"></a><a name="zh-cn_topic_0192504943_p123726263385"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504943_p133721326103811"><a name="zh-cn_topic_0192504943_p133721326103811"></a><a name="zh-cn_topic_0192504943_p133721326103811"></a>SQL的执行结果。</p>
<div class="note" id="zh-cn_topic_0192504943_note939175614390"><a name="zh-cn_topic_0192504943_note939175614390"></a><a name="zh-cn_topic_0192504943_note939175614390"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0192504943_p542165615391"><a name="zh-cn_topic_0192504943_p542165615391"></a><a name="zh-cn_topic_0192504943_p542165615391"></a>只有非select的语句才会在content中返回结果，如果SQL中没有结果，content为空。</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## 示例<a name="section1210015461189"></a>

-   请求示例

    无。

-   响应示例
    -   成功示例

        ```
        {
            "sql_id":"20190909_011820_00151_xxxxx ", 
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

