# hive执行删除表失败<a name="mrs_03_0268"></a>

## 用户问题<a name="section18305143583116"></a>

hive表删除失败

## 问题现象<a name="section117424454313"></a>

hive创建的二级分区表有两万多个分区，导致用户在执行**truncate table $\{TableName\},drop table $\{TableName\}**时失败。

## 原因分析<a name="section1237061220324"></a>

删除文件操作是单线程串行执行的，hive分区数过多导致在元数据数据库会保存大量元数据信息，在执行删表语句时删除元数据就要用很长时间，最终在规定时间内删除不完，就会导致操作失败。

## 处理步骤<a name="section731018431300"></a>

1.  如果是内部表可以先通过**alter table $\{TableName\} set TBLPROPERTIES\('EXTERNAL'='true'\)**来将内部表转成外部表，这样hive删除的时候只删除元数据省去了删除hdfs数据的时间。
2.  如果要用相同的表名可以先将表结构用**show create table $\{TableName\}**来导出表结构，再用**ALTER TABLE $\{TableName\} RENAME TO $\{new\_table\_name\};**来将表重命名。这样就可以新建一个和原来一样表。
3.  执行**hdfs dfs –rm –r –f $\{hdfs\_path\}**在hdfs上删除表数据。
4.  在hive中用**alter table $\{Table\_Name\} drop partition \($\{PartitionName\}<’XXXX’, $\{PartitionName\}\>’XXXX’\);**删除分区\(具体删除条件可灵活处理\),减少文件数。
5.  删除分区少于一千个后，直接用**drop table $\{TableName\}**删掉表即可。

## 建议与总结<a name="section8898183420"></a>

hive分区虽然可以提高查询效率,但要避免分区不合理导致出现大量小文件的问题,要提前规划好分区策略.

