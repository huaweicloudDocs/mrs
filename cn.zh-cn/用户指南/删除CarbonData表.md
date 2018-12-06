# 删除CarbonData表<a name="ZH-CN_TOPIC_0057181211"></a>

## 操作场景<a name="zh-cn_topic_0056202765_section44389809164252"></a>

用户根据业务使用情况，可以删除不再使用的Carbon表。删除表后，其所有的元数据以及表中已加载的数据都会被删除。

## 操作步骤<a name="zh-cn_topic_0056202765_section182005916432"></a>

1.  运行如下命令删除表。

    **DROP TABLE  _\[IF EXISTS\] \[db\_name.\]table\_name_;**

    “db\_name“为可选参数。如果没有指定“db\_name“，那么将会删除当前数据库下名为“table\_name“的表。

    例如执行命令，删除数据库“productdb“下的表“productSalesTable“：

    **DROP TABLE productdb.productSalesTable;**

2.  执行以下命令查询表是否被删除：

    **SHOW TABLES;**


