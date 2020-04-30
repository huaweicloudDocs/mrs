# 获取SQL结果<a name="ZH-CN_TOPIC_0183401342"></a>

## 功能介绍<a name="section4408504619327"></a>

在MRS集群中查询SparkSql和SparkScript两种类型作业的SQL语句运行完成后返回的查询结果。

## URI<a name="section10186656193217"></a>

-   URI格式

    GET /v2/\{project\_id\}/clusters/\{cluster\_id\}/job-executions/\{job\_execution\_id\}/sql-result

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
    <tr id="zh-cn_topic_0176790808_row121835121146"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0176790808_p218419125412"><a name="zh-cn_topic_0176790808_p218419125412"></a><a name="zh-cn_topic_0176790808_p218419125412"></a>job_execution_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0176790808_p16184161212420"><a name="zh-cn_topic_0176790808_p16184161212420"></a><a name="zh-cn_topic_0176790808_p16184161212420"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0176790808_p121844121440"><a name="zh-cn_topic_0176790808_p121844121440"></a><a name="zh-cn_topic_0176790808_p121844121440"></a>作业ID。获取方法，请参见<a href="获取MRS集群信息.md#section247234143612">获取作业ID</a>。</p>
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
<tbody><tr id="zh-cn_topic_0177065250_row8387056194027"><td class="cellrowborder" valign="top" width="25.06%" headers="mcps1.2.4.1.1 "><p id="p199501699424"><a name="p199501699424"></a><a name="p199501699424"></a>sql-results</p>
</td>
<td class="cellrowborder" valign="top" width="24.94%" headers="mcps1.2.4.1.2 "><p id="p1949129154215"><a name="p1949129154215"></a><a name="p1949129154215"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p99471893420"><a name="p99471893420"></a><a name="p99471893420"></a>SQL语句查询结果。</p>
</td>
</tr>
</tbody>
</table>

## 示例<a name="section1210015461189"></a>

-   请求示例

    ```
    {
    	"job_name": "111",
    	"job_type": "SparkSql",
    	"arguments": [
                 "create table src_wordcount (id int,name string);
                  show tables;
                  insert INTO src_wordcount VALUES (1, 'a');
                  insert INTO src_wordcount VALUES (2, 'b');SELECT * FROM src_wordcount;"
                      ],
    	"properties": {}
    }
    ```

-   响应示例
    -   成功示例

        ```
        {
        	"sql_results": {
        		"0": [{
        			"result": "succeed"
        		}],
        		"1": [{
        			"database": "default",
        			"isTemporary": "false",
        			"tableName": "src_wordcount"
        		}],
        		"2": [{
        			"result": "succeed"
        		}],
        		"3": [{
        			"result": "succeed"
        		}],
        		"4": [{
        			"name": "a",
        			"id": "1"
        		}, {
        			"name": "b",
        			"id": "2"
        		}]
        	}
        }
        ```

    -   失败示例

        ```
        {
        "error_msg":"收集SQL作业结果失败",
        "error_code":"0172"
        }
        ```



## 状态码<a name="section4391766619434"></a>

状态码请参见[状态码](状态码.md)。

