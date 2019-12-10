# 取消SQL执行任务<a name="ZH-CN_TOPIC_0192504945"></a>

## 功能介绍<a name="section4408504619327"></a>

在MRS集群中取消一条SQL的执行任务。

## URI<a name="section10186656193217"></a>

-   URI格式

    POST  /v2/\{project\_id\}/clusters/\{cluster\_id\}/sql-execution/\{sql\_id\}/cancel

-   参数说明

    **表 1**  URI参数说明

    <a name="table49499141194754"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_row33700024194754"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p16571835194812"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p16571835194812"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p16571835194812"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p141410194812"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p141410194812"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p141410194812"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p11454278194812"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p11454278194812"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p11454278194812"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_row39786771142917"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1503055142917"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1503055142917"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1503055142917"></a>project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p54638598142917"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p54638598142917"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p54638598142917"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p63650338142917"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p63650338142917"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p63650338142917"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_row3457216201210"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p194589160122"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p194589160122"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p194589160122"></a>cluster_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p045813165125"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p045813165125"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p045813165125"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1845891641218"><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1845891641218"></a><a name="zh-cn_topic_0192504944_zh-cn_topic_0176790808_p1845891641218"></a>集群ID。获取方法，请参见<a href="获取MRS集群信息.md#section177891315153619">获取集群ID</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0192504944_zh-cn_topic_0176790808_row121835121146"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0192504944_p967461817429"><a name="zh-cn_topic_0192504944_p967461817429"></a><a name="zh-cn_topic_0192504944_p967461817429"></a>sql_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0192504944_p46749186427"><a name="zh-cn_topic_0192504944_p46749186427"></a><a name="zh-cn_topic_0192504944_p46749186427"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0192504944_p16674131884215"><a name="zh-cn_topic_0192504944_p16674131884215"></a><a name="zh-cn_topic_0192504944_p16674131884215"></a>SQL的执行ID，即<a href="提交SQL语句.md">提交SQL语句</a>返回结果中的sql_id。</p>
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
<table><thead align="left"><tr id="zh-cn_topic_0177065250_row8843854193927"><th class="cellrowborder" valign="top" width="25.06%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0177065250_p45263556193927"><a name="zh-cn_topic_0177065250_p45263556193927"></a><a name="zh-cn_topic_0177065250_p45263556193927"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="24.94%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0177065250_p1907984993927"><a name="zh-cn_topic_0177065250_p1907984993927"></a><a name="zh-cn_topic_0177065250_p1907984993927"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0177065250_p17473879193927"><a name="zh-cn_topic_0177065250_p17473879193927"></a><a name="zh-cn_topic_0177065250_p17473879193927"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0177065250_row8387056194027"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p250631134919"><a name="p250631134919"></a><a name="p250631134919"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p18506141110497"><a name="p18506141110497"></a><a name="p18506141110497"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p250615113490"><a name="p250615113490"></a><a name="p250615113490"></a>取消SQL的执行结果。</p>
<a name="ul18690201744915"></a><a name="ul18690201744915"></a><ul id="ul18690201744915"><li>SUCCEED：成功</li><li>FAILED：失败</li></ul>
<div class="note" id="note6200185214912"><a name="note6200185214912"></a><a name="note6200185214912"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1420185211492"><a name="p1420185211492"></a><a name="p1420185211492"></a>默认返回SUCCEED，对于已经结束的任务也会返回SUCCEED，只有取消正在运行的SQL时没成功才会FAILED。</p>
</div></div>
</td>
</tr>
<tr id="row184660816491"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p250641124916"><a name="p250641124916"></a><a name="p250641124916"></a>message</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p450691104917"><a name="p450691104917"></a><a name="p450691104917"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p15506151174918"><a name="p15506151174918"></a><a name="p15506151174918"></a>错误信息。</p>
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
            "status":"SUCCEED"
         }
        ```

    -   失败示例

        ```
        { 
            "status":"FAILED",
            "message":"Cancel sql error"
         }
        ```



## 状态码<a name="section4391766619434"></a>

状态码请参见[状态码](状态码.md)。

