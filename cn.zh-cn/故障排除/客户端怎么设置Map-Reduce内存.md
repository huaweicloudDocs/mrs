# 客户端怎么设置Map/Reduce内存？<a name="mrs_03_0152"></a>

## 问题现象<a name="zh-cn_topic_0167274550_section1861111131114"></a>

客户端怎么设置Map/Reduce内存？

## 处理步骤<a name="zh-cn_topic_0167274550_se557d36e41b246bba30ab6f202adab38"></a>

Hive在执行SQL语句前，可以通过set命令来设置Map/Reduce相关客户端参数。

以下为与Map/Reduce内存相关的参数：

```
set mapreduce.map.memory.mb=4096;// 每个Map Task需要的内存量
set mapreduce.map.java.opts=-Xmx3276M; // 每个Map Task 的JVM最大使用内存
set mapreduce.reduce.memory.mb=4096; // 每个Reduce Task需要的内存量
set mapreduce.reduce.java.opts=-Xmx3276M; // 每个Reduce Task 的JVM最大使用内存
set mapred.child.java.opts=-Xms1024M -Xmx3584M;//此参数为全局参数，既对Map和Reduce统一设置
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>参数设置只对当前session有效。

