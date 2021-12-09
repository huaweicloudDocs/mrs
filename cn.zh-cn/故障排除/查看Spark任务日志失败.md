# 查看Spark任务日志失败<a name="mrs_03_0287"></a>

## 问题现象<a name="section117424454313"></a>

-   任务运行中查看日志失败
-   任务运行完成，但是查看不到日志

## 原因分析<a name="section1237061220324"></a>

-   问题1：可能原因是MapReduce服务异常
-   问题2：可能原因如下：
    -   Spark的JobHistory服务异常。
    -   日志太大，NodeManager在做日志汇聚的时候出现超时。
    -   HDFS存放日志目录权限异常（默认/tmp/logs/用户名/logs）。
    -   日志已被清理（spark的JobHistory默认存放7天的eventLog，配置项为spark.history.fs.cleaner.maxAge；MapReduce默认存放15天的任务日志，配置项为mapreduce.jobhistory.max-age-ms）。
    -   如果yarn页面上也找不到，可能是被yarn清理了（默认存放10000个历史任务，配置项为yarn.resourcemanager.max-completed-applications）。


## 处理步骤<a name="section16530919173311"></a>

-   问题1：确认MapReduce服务是否正常，如果异常，尝试重启服务。如果还是不能恢复，需要查看后台JobhistoryServer日志。
-   问题2：依次排查可能的情况：
    1.  查看Spark的JobHistory是否运行正常；
    2.  通过查看yarn的app详情页面，确认日志文件是否过大，如果日志汇聚失败，页面的“Log Aggregation Status:”应该显示为失败或者超时；
    3.  查看对应目录权限是否异常；
    4.  查看目录下是否有对应的appid文件（spark的eventlog存放目录：MRS 3.x及以后版本的目录是hdfs://hacluster/spark2xJobHistory2x，MRS 3.x以前版本的目录是hdfs://hacluster/sparkJobHistory，任务运行日志存放目录是hdfs://hacluster/tmp/logs/用户名/logs）;
    5.  查看appid和当前作业的id是否超过历史记录最大值。


