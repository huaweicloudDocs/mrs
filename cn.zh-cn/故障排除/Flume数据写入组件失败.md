# Flume数据写入组件失败<a name="ZH-CN_TOPIC_0181626573"></a>

## 问题现象<a name="zh-cn_topic_0167275855_section15297192419276"></a>

Flume进程启动后，Flume数据无法写入到对应组件。（以下以服务端写入到HDFS为例）

## 原因分析<a name="zh-cn_topic_0167275855_section11464274299"></a>

1.  HDFS未启动或故障。查看Flume运行日志：

    ```
    2019-02-26 11:16:33,564 | ERROR | [SinkRunner-PollingRunner-DefaultSinkProcessor] |  opreation the hdfs file errors.  | org.apache.flume.sink.hdfs.HDFSEventSink.process(HDFSEventSink.java:414)
    2019-02-26 11:16:33,747 | WARN  | [hdfs-CCCC-call-runner-4] |  A failover has occurred since the start of call #32795 ClientNamenodeProtocolTranslatorPB.getFileInfo over 192-168-13-88/192.168.13.88:25000  | org.apache.hadoop.io.retry.RetryInvocationHandler$ProxyDescriptor.failover(RetryInvocationHandler.java:220)
    2019-02-26 11:16:33,748 | ERROR | [hdfs-CCCC-call-runner-4] |  execute hdfs error. {}  | org.apache.flume.sink.hdfs.HDFSEventSink$3.call(HDFSEventSink.java:744)
    java.net.ConnectException: Call From 192-168-12-221/192.168.12.221 to 192-168-13-88:25000 failed on connection exception: java.net.ConnectException: Connection refused; For more details see:  http://wiki.apache.org/hadoop/ConnectionRefused
    ```

2.  hdfs sink未启动。查看Flume运行日志，发现“ flume current metrics”中并没有sink信息：

    ```
    2019-02-26 11:46:05,501 | INFO  | [pool-22-thread-1] |  flume current metrics:{"CHANNEL.BBBB":{"ChannelCapacity":"10000","ChannelFillPercentage":"0.0","Type":"CHANNEL","ChannelStoreSize":"0","EventProcessTimedelta":"0","EventTakeSuccessCount":"0","ChannelSize":"0","EventTakeAttemptCount":"0","StartTime":"1551152734999","EventPutAttemptCount":"0","EventPutSuccessCount":"0","StopTime":"0"},"SOURCE.AAAA":{"AppendBatchAcceptedCount":"0","EventAcceptedCount":"0","AppendReceivedCount":"0","MonTime":"0","StartTime":"1551152735503","AppendBatchReceivedCount":"0","EventReceivedCount":"0","Type":"SOURCE","TotalFilesCount":"1001","SizeAcceptedCount":"0","UpdateTime":"605410241202740","AppendAcceptedCount":"0","OpenConnectionCount":"0","MovedFilesCount":"1001","StopTime":"0"}}  | org.apache.flume.node.Application.getRestartComps(Application.java:467)
    ```


## 解决办法<a name="zh-cn_topic_0167275855_section2676132610357"></a>

1.  若Flume数据写入的组件未启动，启动对应组件；若组件异常，请联系MRS服务技术支持。
2.  sink未启动，检查配置文件是否配置正确，若配置错误，则正确修改配置文件后重启Flume进程，如果配置正确，则查看日志错误信息，根据具体错误信息指定解决办法。

