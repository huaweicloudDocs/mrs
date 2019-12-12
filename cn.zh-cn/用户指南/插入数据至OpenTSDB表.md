# 插入数据至OpenTSDB表<a name="ZH-CN_TOPIC_0176639096"></a>

## 功能描述<a name="section2167437125214"></a>

使用INSERT INTO命令将表中的数据插入到已关联的OpenTSDB metric中。

## 语法格式<a name="section41681537155216"></a>

```
INSERT INTO TABLE_NAME SELECT * FROM SRC_TABLE;
INSERT INTO TABLE_NAME VALUES(XXX);
```

## 关键字<a name="section5170183716527"></a>

<a name="table1817193710524"></a>
<table><thead align="left"><tr id="row42382375527"><th class="cellrowborder" valign="top" width="30%" id="mcps1.1.3.1.1"><p id="p1423823745220"><a name="p1423823745220"></a><a name="p1423823745220"></a><strong id="b22381637155219"><a name="b22381637155219"></a><a name="b22381637155219"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.1.3.1.2"><p id="p18239537115218"><a name="p18239537115218"></a><a name="p18239537115218"></a><strong id="b10239203715219"><a name="b10239203715219"></a><a name="b10239203715219"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row323913745210"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p15239133735214"><a name="p15239133735214"></a><a name="p15239133735214"></a>TABLE_NAME</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p1523993745219"><a name="p1523993745219"></a><a name="p1523993745219"></a>所关联的OpenTSDB表名。</p>
</td>
</tr>
<tr id="row2239837105215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.1.3.1.1 "><p id="p11239153785212"><a name="p11239153785212"></a><a name="p11239153785212"></a>SRC_TABLE</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.1.3.1.2 "><p id="p7239103765217"><a name="p7239103765217"></a><a name="p7239103765217"></a>获取数据的表名，普通表即可。</p>
</td>
</tr>
</tbody>
</table>

## 注意事项<a name="section13175153785212"></a>

-   插入的数据不能为null；插入的数据相同，会覆盖原数据；插入的数据只有value值不同，也会覆盖原数据。
-   不支持INSERT OVERWRITE语法。
-   不建议对同一张表并发插入数据，因为有一定概率发生并发冲突，导致插入失败。
-   时间戳格式只支持yyyy-MM-dd hh:mm:ss。

## 示例<a name="section7179937145212"></a>

在opentsdb\_table表中插入数据。

```
insert into opentsdb_table values('shenzhen','futian','2018-05-03 00:00:00',21);
```

