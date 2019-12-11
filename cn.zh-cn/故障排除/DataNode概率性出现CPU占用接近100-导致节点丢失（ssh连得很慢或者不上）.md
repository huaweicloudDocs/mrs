# DataNode概率性出现CPU占用接近100%，导致节点丢失（ssh连得很慢或者不上）<a name="ZH-CN_TOPIC_0181713098"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275979_sf00c5d8acaed4b30b03d6a5f5964e80e"></a>

DataNode概率性出现CPU占用接近100%，导致节点丢失。

**图 1**  DataNode出现CPU占用接近100%<a name="zh-cn_topic_0167275979_fig468359184318"></a>  
![](figures/DataNode出现CPU占用接近100.png "DataNode出现CPU占用接近100")

## 原因分析<a name="zh-cn_topic_0167275979_sd7bf317d97af43e69bf0fb5045e0a0b5"></a>

1.  DataNode有许多写失败的日志。

    **图 2**  DataNode写失败的日志<a name="zh-cn_topic_0167275979_fig3461779911"></a>  
    ![](figures/DataNode写失败的日志.png "DataNode写失败的日志")

2.  短时间内写入大量文件导致这种情况，因此DataNode内存不足。

    **图 3**  写入大量文件导致DataNode内存不足<a name="zh-cn_topic_0167275979_fig1585813501917"></a>  
    ![](figures/写入大量文件导致DataNode内存不足.png "写入大量文件导致DataNode内存不足")


## 解决办法<a name="zh-cn_topic_0167275979_s7f1531949a644c3ba2aafb9e744d235b"></a>

1.  检查DataNode内存配置，以及机器剩余内存是否充足。
2.  增加DataNode内存，并重启DataNode。

