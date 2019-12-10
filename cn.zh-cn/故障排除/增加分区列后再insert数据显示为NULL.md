# 增加分区列后再insert数据显示为NULL<a name="ZH-CN_TOPIC_0205107314"></a>

## 问题现象<a name="zh-cn_topic_0167275647_s8417d2e55ed749d790b7c904712c7845"></a>

1.  执行如下命令创建表

    ```
    create table test_table(
    col1 string,
    col2 string
    )
    PARTITIONED BY(p1 string)
    STORED AS orc tblproperties('orc.compress'='SNAPPY');
    ```

2.  修改表结构，添加分区并插入数据

    ```
    alter table test_table add partition(p1='a');
    insert into test_table partition(p1='a') select col1,col2 from temp_table;
    ```

3.  修改表结构，添加列并插入数据

    ```
    alter table test_table add columns(col3 string);
    insert into test_table partition(p1='a') select col1,col2,col3 from temp_table;
    ```

4.  查询test\_table表数据，返回结果中列col3的值全为NULL

    ```
    select * from test_table where p1='a' 
    ```

5.  新添加表分区，并插入数据

    ```
    alter table test_table add partition(p1='b');
    insert into test_table partition(p1='b') select col1,col2,col3 from temp_table; 
    ```

6.  查询test\_table表数据，返回结果中列col3有不为NULL的值

    ```
    select * from test_table where p1='b'
    ```


## 原因分析<a name="zh-cn_topic_0167275647_section72531409719"></a>

在alter table时默认选项为RESTRICT，RESTRICT只会更改元数据，不会修改在此操作之前创建的partition的表结构，而只会修改在此之后创建的新的partition，所以查询时旧的partition中的值全为NULL。

## 处理步骤<a name="zh-cn_topic_0167275647_sc2de4893c94244bcaeafec2ea59aa16a"></a>

add column时加入cascade关键字即可，例如：

```
alter table test_table add columns(col3 string) cascade;
```

