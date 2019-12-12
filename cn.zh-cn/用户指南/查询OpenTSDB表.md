# 查询OpenTSDB表<a name="ZH-CN_TOPIC_0176639097"></a>

SELECT命令用于查询OpenTSDB表中的数据。

## 语法格式<a name="section6313185812529"></a>

```
SELECT * FROM table_name WHERE tagk=tagv LIMIT number;
```

## 关键字<a name="section1931315582526"></a>

<a name="table1817193710524"></a>
<table><thead align="left"><tr id="row42382375527"><th class="cellrowborder" valign="top" width="30%" id="mcps1.1.3.1.1"><p id="p1423823745220"><a name="p1423823745220"></a><a name="p1423823745220"></a><strong id="b22381637155219"><a name="b22381637155219"></a><a name="b22381637155219"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.1.3.1.2"><p id="p18239537115218"><a name="p18239537115218"></a><a name="p18239537115218"></a><strong id="b10239203715219"><a name="b10239203715219"></a><a name="b10239203715219"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row323913745210"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p4512182532414"><a name="p4512182532414"></a><a name="p4512182532414"></a>LIMIT</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p1523993745219"><a name="p1523993745219"></a><a name="p1523993745219"></a>对查询结果进行限制。</p>
</td>
</tr>
<tr id="row2239837105215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p96329379241"><a name="p96329379241"></a><a name="p96329379241"></a>number</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p7239103765217"><a name="p7239103765217"></a><a name="p7239103765217"></a>参数仅支持INT类型。</p>
</td>
</tr>
</tbody>
</table>

## 注意事项<a name="section1331415589523"></a>

-   所查询的表必须是已经存在的表，否则会出错。
-   查询的tagv必须是已经有的值，否则会出错。

## 示例<a name="section1231515865218"></a>

查询表opentsdb\_table中的数据。

```
SELECT * FROM opentsdb_table LIMIT 100;
SELECT * FROM opentsdb_table WHERE city='shenzhen';
```

