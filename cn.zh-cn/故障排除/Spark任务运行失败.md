# Spark任务运行失败<a name="mrs_03_0285"></a>

## 问题现象<a name="section117424454313"></a>

-   报错显示executor出现OOM
-   失败的task信息显示失败原因是lost task xxx

## 原因分析<a name="section1237061220324"></a>

-   问题1：一般出现executor OOM，都是因为数据量过大，也有可能是因为同一个executor上面同时运行的task太多。
-   问题2：有些task运行失败会报上述错误。当看到这个报错的时候，需要确认的是丢失的这个task在哪个节点上面运行，一般的情况是这个丢失的task异常退出导致的。

## 处理步骤<a name="section16530919173311"></a>

-   问题1：
    -   对于数据量过大，需要调整executor的内存大小的，使用--executor-memory指定内存大小；
    -   对于同时运行的task太多，主要看--executor-cores设置的vcore数量。

-   问题2：需要在相应的task的日志里面查找异常原因。如果有OOM的情况，请参照问题1。

