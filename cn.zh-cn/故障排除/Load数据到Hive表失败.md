# Load数据到Hive表失败<a name="ZH-CN_TOPIC_0210454018"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274921_s20deae74a71143aeabad239c7a22f024"></a>

用户在建表成功后，通过Load命令往此表导入数据，但导入操作中遇到如下问题：

```
.......
> LOAD DATA INPATH '/user/tester1/hive-data/data.txt' INTO TABLE employees_info;
Error: Error while compiling statement: FAILED: SemanticException Unable to load data to destination table. Error: The file that you are trying to load does not match the file format of the destination table. (state=42000,code=40000)
..........
```

## 原因分析<a name="zh-cn_topic_0167274921_s7dfa4353c00142a991338a71eaf7d6ad"></a>

1.  经分析，发现在建表时没有指定存储格式，所以采用了缺省存储格式RCFile。
2.  在导入数据时，被导入数据格式是TEXTFILE格式，最终导致此问题。

## 解决办法<a name="zh-cn_topic_0167274921_section1213444410221"></a>

属于应用侧问题，解决办法有多种。只要保证表所指定存储格式和被导入数据格式是一致的，可以根据实际情况采用合适方法。

-   方法1：

    可以在建表时指定存储格式，例如：**CREATE TABLE IF NOT EXISTS employees\_info\(name STRING,age INT\) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;**指定被导入数据格式为TEXTFILE。

-   方法2：

    被导入数据存储格式不能为TEXTFILE，而应为RCFile。


