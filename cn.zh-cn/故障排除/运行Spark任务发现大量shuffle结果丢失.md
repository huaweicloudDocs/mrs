# 运行Spark任务发现大量shuffle结果丢失<a name="mrs_03_0274"></a>

## 用户问题<a name="section18305143583116"></a>

Spark任务运行失败，查看任务日志发现大量打印shuffle文件丢失。

## 问题现象<a name="section117424454313"></a>

Spark任务运行失败，查看任务日志发现大量打印shuffle文件丢失。

## 原因分析<a name="section1237061220324"></a>

spark运行的时候会将临时产生的shuffle文件放在executor的临时目录中，方便后面获取。

而当某个executor异常退出时，NodeManager会把这个executor所在的container临时目录删除，随后其他executor再来申请这个executor的shuffle结果就会报文件找不到。

因此，遇到这样的问题需要确认是否executor异常退出，可以根据spark任务页面的executors便签页查看是否有dead状态的executor，查看各个dead状态的executor日志，确认异常退出的原因（其中可能有部分executor退出原因就是因为shuffle文件找不到，需要找到最早异常退出的executor）。

常见的异常退出：

-   executor发生OOM
-   executor运行时出现多个task任务失败
-   executor所在节点被清理

## 处理步骤<a name="section133471835103619"></a>

根据executor异常退出的实际原因调整或者修改任务参数或代码，重新运行Spark任务即可。

