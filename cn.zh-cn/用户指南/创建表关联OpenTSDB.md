# 创建表关联OpenTSDB<a name="ZH-CN_TOPIC_0176639095"></a>

## 功能描述<a name="section14297175215515"></a>

MRS的Spark实现了访问OpenTSDB的Datasource，能够在Spark中创建关联表，查询和插入OpenTSDB数据。

使用CREATE TABLE命令创建表并关联OpenTSDB上已有的metric。

>![](public_sys-resources/icon-note.gif) **说明：**   
>若OpenTSDB上不存在metric，查询对应的表会报错。  

## 语法格式<a name="section7314752195113"></a>

```
CREATE TABLE [IF NOT EXISTS] OPENTSDB_TABLE_NAME   USING OPENTSDB OPTIONS (
'metric' = 'METRIC_NAME',
'tags' = 'TAG1,TAG2'
);
```

## 关键字<a name="section1432961213524"></a>

<a name="table103551812185212"></a>
<table><thead align="left"><tr id="row1442312125528"><th class="cellrowborder" valign="top" width="30%" id="mcps1.1.3.1.1"><p id="p194231112205210"><a name="p194231112205210"></a><a name="p194231112205210"></a><strong id="b242310129525"><a name="b242310129525"></a><a name="b242310129525"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.1.3.1.2"><p id="p54231712175216"><a name="p54231712175216"></a><a name="p54231712175216"></a><strong id="b11423151217520"><a name="b11423151217520"></a><a name="b11423151217520"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row1842411285212"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p12424212145211"><a name="p12424212145211"></a><a name="p12424212145211"></a>metric</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p74241012185219"><a name="p74241012185219"></a><a name="p74241012185219"></a>所创建的表对应的OpenTSDB中的指标名称。</p>
</td>
</tr>
<tr id="row16424612185210"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p16424612135220"><a name="p16424612135220"></a><a name="p16424612135220"></a>tags</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p19424161275219"><a name="p19424161275219"></a><a name="p19424161275219"></a>metric对应的标签，用于归类、过滤、快速检索等操作。可以是1个到8个，以“,”分隔，包括对应metric下所有tagk的值。</p>
</td>
</tr>
</tbody>
</table>

## 注意事项<a name="section15363201265210"></a>

创建表时，不需要指定timestamp和value字段，系统会根据指定的tags自动构建字段，包含以下字段，其中TAG1和TAG2由tags指定。

-   TAG1 String
-   TAG2 String
-   timestamp Timestamp
-   value double

## 示例<a name="section11370151213522"></a>

创建opentsdb\_table表并关联到OpenTSDB组件的city.temp这个metric。

```
CREATE table opentsdb_table using opentsdb OPTIONS ('metric'='city.temp',  'tags'='city,location');
```

