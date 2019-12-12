# 删除CarbonData表<a name="ZH-CN_TOPIC_0173178138"></a>

## 操作场景<a name="s867958339e0b4fdfaacc7000eb0377e3"></a>

用户根据业务使用情况，可以删除不再使用的Carbon表。删除表后，其所有的元数据以及表中已加载的数据都会被删除。

## 操作步骤<a name="s21b9a4ba55a54f5d9fc9bac6e5a18856"></a>

1.  运行如下命令删除表。

    **DROP TABLE  _\[IF EXISTS\] \[db\_name.\]table\_name_;**

    “db\_name“为可选参数。如果没有指定“db\_name“，那么将会删除当前数据库下名为“table\_name“的表。

    例如执行命令，删除数据库“productdb“下的表“productSalesTable“：

    **DROP TABLE productdb.productSalesTable;**

2.  执行以下命令查询表是否被删除：

    **SHOW TABLES;**


