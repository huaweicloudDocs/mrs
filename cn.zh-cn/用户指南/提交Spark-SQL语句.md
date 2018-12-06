# 提交Spark SQL语句<a name="ZH-CN_TOPIC_0021633632"></a>

本章节介绍Spark SQL的基本使用方法，在MRS管理控制台提交Spark SQL语句查询和分析数据。如果同时需要提交多条语句并执行，使用“;“分隔不同语句。

## 背景信息<a name="section5888004181153"></a>

如果SQL语句涉及敏感信息，请使用Spark Script提交。

## 操作步骤<a name="section1616959510853"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群“，选中一个运行中的集群并单击集群名，进入集群信息页面。
3.  单击“作业管理“，进入“作业管理“页签。
4.  选择“Spark SQL“，进入Spark SQL作业页面。
5.  输入创建表的Spark SQL语句。

    输入Spark SQL语句时，总字符数应当小于或等于10000字符，否则会提交语句失败。

    语法格式：

    **CREATE** \[EXTERNAL\] **TABLE** \[IF NOT EXISTS\] _table\_name_ \[\(col\_name data\_type \[COMMENT col\_comment\], ...\)\] \[COMMENT table\_comment\] \[PARTITIONED **BY** \(col\_name data\_type \[COMMENT col\_comment\], ...\)\] \[CLUSTERED **BY** \(col\_name, col\_name, ...\) \[SORTED **BY** \(col\_name \[ASC|DESC\], ...\)\] INTO num\_buckets BUCKETS\] \[ROW FORMAT row\_format\] \[STORED **AS**  file\_format\] \[LOCATION hdfs\_path\];

    创建表样例存在以下两种方式。

    方式一：创建一个src\_data表，每行写入一条数据，数据存储在“/user/guest/input“目录下。

    **create external table** _src\_data_**\(line string\) row format delimited fields terminated by '\\\\n' stored as textfile location** '_/user/guest/input/_';

    方式二：创建一个表src\_data1，将数据load到src\_data1表中。

    **create table** _src\_data1_ **\(eid int, name String, salary String, destination String\) row format delimited fields terminated by ',' ;**

    **load data inpath** '/tttt/test.txt' **into table** src\_data1;

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >采用方式二时，OBS上的数据不支持直接load到新建的表中。  

6.  输入查询表的Spark SQL语句。

    语法格式：

    **SELECT** col\_name FROM table\_name;

    查询表样例：

    **select \* from src\_data;**

7.  输入删除表的Spark SQL语句。

    语法格式：

    **DROP TABLE** \[IF EXISTS\] table\_name;

    删除表样例：

    **drop table src\_data;**

8.  单击“检查“，检查输入语句的语法是否正确。
9.  单击“提交“。

    Spark SQL语句提交后，执行成功或失败会在“执行结果“中展示，执行结果详情可在“查询结果集“中查看。


