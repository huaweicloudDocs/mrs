# hive任务运行过程中失败，重试成功<a name="ZH-CN_TOPIC_0210454005"></a>

## 问题现象<a name="zh-cn_topic_0167275611_s279271d9ef1f448c82bf851fcc361636"></a>

当hive任务在正常运行时失败，在客户端报出错误，类似的错误打印时：

```
Error:Invalid OperationHandler:OperationHander [opType=EXECUTE_STATEMENT,getHandleIdentifier()=XXX](state=,code=0)
```

而此任务提交到yarn上的mapreduce任务运行成功。

![](figures/zh-cn_image_0167275477.png)

## 原因分析<a name="zh-cn_topic_0167275611_s2be99397c5de4111a414f6fbd0fb7c2f"></a>

出错的集群有两个hiveserver实例，首先查看其中一个hiveserver日志发现里面的报错与客户端中的错误一样均是Error:Invalid OperationHandler，查看另一个hiveserver发现在出错的时间段此实例有如下类似START\_UP的打印，说明那段时间进程被停止过，后来又启动成功，提交的任务本来连接的是重启过的hiveserver实例，当这个实例被停止后，任务进程连接到另一个健康的hiveserver上导致报错。

```
2017-02-15 14:40:11,309 | INFO  | main | STARTUP_MSG:
/************************************************************
STARTUP_MSG: Starting HiveServer2
STARTUP_MSG:   host = XXX-120-85-154/XXX.120.85.154
STARTUP_MSG:   args = []
STARTUP_MSG:   version = 1.3.0
```

## 解决办法<a name="zh-cn_topic_0167275611_sd6477f1effc345f1abf9f4286dc8eb07"></a>

重新提交一次任务即可，保证在任务执行期间不手动重启hiveserver进程。

