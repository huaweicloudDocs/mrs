# Hive执行msck repair table table\_name报错<a name="mrs_03_0282"></a>

## 现象描述<a name="sf1abf88b8ef94803be8a4eca63c1c9bc"></a>

Hive执行msck repair table table\_name报错：FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.DDLTask \(state=08S01,code=1\)。

## 可能原因<a name="se70deb3b2f3c439f8042adbd53d2f2bc"></a>

查看HiveServer日志/var/log/Bigdata/hive/hiveserver/hive.log，发现目录名不符合分区格式。

![](figures/zh-cn_image_0000001107893654.png)

## 处理步骤<a name="section5134183965612"></a>

-   方法一：删除错误的文件或目录。
-   方法二：执行set hive.msck.path.validation=skip，跳过无效的目录。

