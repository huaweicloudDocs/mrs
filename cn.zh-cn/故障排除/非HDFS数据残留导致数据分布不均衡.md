# 非HDFS数据残留导致数据分布不均衡<a name="ZH-CN_TOPIC_0183415886"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276246_s158e8e298d8e463baa11b441927c46e8"></a>

数据出现不均衡，某磁盘过满而其他磁盘未写满。

HDFS DataNode数据存储目录配置为“/export/data1/dfs--/export/data12/dfs“，看到的现象是大量数据都是存储到了“/export/data1/dfs“，其他盘的数据比较均衡。

## 原因分析<a name="zh-cn_topic_0167276246_s66462fbbe386437f923a475bfab597d6"></a>

磁盘为卸载重装，有一个目录在上次卸载时未卸载干净，即添加的磁盘，未格式化，残留历史垃圾数据。

## 解决办法<a name="zh-cn_topic_0167276246_s22f5b22d4e174f86a73231a8d12d87f9"></a>

手动清理未卸载干净的数据。

