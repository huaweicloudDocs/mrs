# 节点剩余内存不足导致HBase启动失败<a name="ZH-CN_TOPIC_0181626540"></a>

## 问题现象<a name="zh-cn_topic_0167275175_sf76e408f8ea44020bf3de33c280bc079"></a>

HBase的RegionServer服务一直是Concerning状态。

## 原因分析<a name="zh-cn_topic_0167275175_s2d857902554344b38f9d1ff9130b2ce3"></a>

1.  查看RegionServer的日志（“/var/log/Bigdata/hbase/rs/hbase-omm-XXX.out“），发现显示以下打印信息：

    ```
    There is insufficient memory for the Java Runtime Environment to continue.
    ```

2.  使用**free**指令查看，该节点确实没有足够内存。

## 解决办法<a name="zh-cn_topic_0167275175_sed4194588b214662be5341d4a1f9ecbd"></a>

1.  现场进行排查内存不足原因，确认是否有某些进程占用过多内存，或者由于服务器自身内存不足。

