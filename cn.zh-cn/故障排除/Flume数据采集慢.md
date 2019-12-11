# Flume数据采集慢<a name="ZH-CN_TOPIC_0181626575"></a>

## 问题现象<a name="zh-cn_topic_0167275068_section58661538152716"></a>

Flume启动后，Flume数据采集慢。

## 原因分析<a name="zh-cn_topic_0167275068_section1545115823317"></a>

1.  Flume堆内存设置不合理，导致Flume进程一直处于频繁GC。查看Flume运行日志：

    ```
    2019-02-26T13:06:20.666+0800: 1085673.512: [Full GC:[CMS: 3849339k->3843458K(3853568K), 2.5817610 secs] 4153654K->3843458K(4160256K), [CMS Perm : 27335K->27335K(45592K),2.5820080 SECS] [Times: user=2.63, sys0.00, real=2.59 secs]
    ```

2.  用户业务配置的Spooldir source的deletePolicy策略是立即删除（immediate）。

## 解决办法<a name="zh-cn_topic_0167275068_section1424514428358"></a>

1.  适当调大堆内存（xmx）的值。
2.  将Spooldir source的deletePolicy策略更改为永不删除（never）。

