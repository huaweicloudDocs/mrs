# 查看Flume客户端日志<a name="ZH-CN_TOPIC_0076492294"></a>

## 操作场景<a name="zh-cn_topic_0076346527_section61077795164654"></a>

查看日志以便定位问题。

## 前提条件<a name="zh-cn_topic_0076346527_section46180360164835"></a>

Flume客户端已经正确安装。

## 操作步骤<a name="zh-cn_topic_0076346527_section11276049165016"></a>

1.  进入Flume客户端日志目录，默认为“/var/log/Bigdata“。
2.  执行如下命令查看日志文件列表。

    **ls -lR flume-client-\***

    日志文件示例如下：

    ```
    flume-client-1/flume:
    total 7672
    -rw-------. 1 root root       0 Sep  8 19:43 Flume-audit.log
    -rw-------. 1 root root 1562037 Sep 11 06:05 FlumeClient.2017-09-11_04-05-09.[1].log.zip
    -rw-------. 1 root root 6127274 Sep 11 14:47 FlumeClient.log
    -rw-------. 1 root root    2935 Sep  8 22:20 flume-root-20170908202009-pid72456-gc.log.0.current
    -rw-------. 1 root root    2935 Sep  8 22:27 flume-root-20170908202634-pid78789-gc.log.0.current
    -rw-------. 1 root root    4382 Sep  8 22:47 flume-root-20170908203137-pid84925-gc.log.0.current
    -rw-------. 1 root root    4390 Sep  8 23:46 flume-root-20170908204918-pid103920-gc.log.0.current
    -rw-------. 1 root root    3196 Sep  9 10:12 flume-root-20170908215351-pid44372-gc.log.0.current
    -rw-------. 1 root root    2935 Sep  9 10:13 flume-root-20170909101233-pid55119-gc.log.0.current
    -rw-------. 1 root root    6441 Sep  9 11:10 flume-root-20170909101631-pid59301-gc.log.0.current
    -rw-------. 1 root root       0 Sep  9 11:10 flume-root-20170909111009-pid119477-gc.log.0.current
    -rw-------. 1 root root   92896 Sep 11 13:24 flume-root-20170909111126-pid120689-gc.log.0.current
    -rw-------. 1 root root    5588 Sep 11 14:46 flume-root-20170911132445-pid42259-gc.log.0.current
    -rw-------. 1 root root    2576 Sep 11 13:24 prestartDetail.log
    -rw-------. 1 root root    3303 Sep 11 13:24 startDetail.log
    -rw-------. 1 root root    1253 Sep 11 13:24 stopDetail.log
    
    flume-client-1/monitor:
    total 8
    -rw-------. 1 root root  141 Sep  8 19:43 flumeMonitorChecker.log
    -rw-------. 1 root root 2946 Sep 11 13:24 flumeMonitor.log
    ```

    其中**FlumeClient.log**即为Flume客户端的运行日志。


