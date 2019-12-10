# 业务拓扑配置GC参数不生效<a name="ZH-CN_TOPIC_0183502590"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275339_section12510183122915"></a>

业务拓扑代码中配置参数topology.worker.childopts不生效，关键日志如下：

```
[main] INFO b.s.StormSubmitter - Uploading topology jar /opt/jar/example.jar to assigned location: /srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-8d3b778d-69ea-4fbe-ba88-01aa2036d753.jar
Start uploading file '/opt/jar/example.jar' to '/srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-8d3b778d-69ea-4fbe-ba88-01aa2036d753.jar' (65574612 bytes)
[==================================================] 65574612 / 65574612
File '/opt/jar/example.jar' uploaded to '/srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-8d3b778d-69ea-4fbe-ba88-01aa2036d753.jar' (65574612 bytes)
[main] INFO b.s.StormSubmitter - Successfully uploaded topology jar to assigned location: /srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-8d3b778d-69ea-4fbe-ba88-01aa2036d753.jar
[main] INFO b.s.StormSubmitter - Submitting topology word-count in distributed mode with conf {"topology.worker.childopts":"-Xmx4096m","storm.zookeeper.topology.auth.scheme":"digest","storm.zookeeper.topology.auth.payload":"-5915065013522446406:-6421330379815193999","topology.workers":1}
[main] INFO b.s.StormSubmitter - Finished submitting topology: word-count
```

通过ps -ef | grep worker命令查看worker进程信息如下：

![](figures/zh-cn_image_0167276209.png)

## 原因分析<a name="zh-cn_topic_0167275339_section115913122917"></a>

1.  由于topology.worker.gc.childopts、topology.worker.childopts和worker.gc.childopts\(服务端参数\)有优先级，优先级大小为：topology.worker.gc.childopts \> worker.gc.childopts \> topology.worker.childopts。
2.  如果设置了客户端参数topology.worker.childopts，则该参数会与服务端参数worker.gc.childopts共同配置，但是后面的相同参数会将前面的覆盖掉，如上面图有两个-Xmx，-Xmx1G会覆盖掉-Xmx4096m。
3.  如果配置了topology.worker.gc.childopts则服务端参数worker.gc.childopts会被替换。

## 解决办法<a name="zh-cn_topic_0167275339_section125121723202911"></a>

1.  如果想要修改拓扑的JVM参数可以在命令中直接修改topology.worker.gc.childopts这个参数或者在服务端修改该参数，当topology.worker.gc.childopts为 "-Xms4096m -Xmx4096m -XX:+UseG1GC -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=10 -XX:GCLogFileSize=1M"时，效果如下：

    ```
    [main-SendThread(187.7.61.88:24002)] INFO o.a.s.s.o.a.z.ClientCnxn - Socket connection established, initiating session, client: /187.7.61.88:44694, server: 187.7.61.88/187.7.61.88:24002
    [main-SendThread(187.7.61.88:24002)] INFO o.a.s.s.o.a.z.ClientCnxn - Session establishment complete on server 187.7.61.88/187.7.61.88:24002, sessionid = 0x16037a6e5f092575, negotiated timeout = 40000
    [main-EventThread] INFO o.a.s.s.o.a.c.f.s.ConnectionStateManager - State change: CONNECTED
    [main] INFO b.s.u.StormBoundedExponentialBackoffRetry - The baseSleepTimeMs [1000] the maxSleepTimeMs [1000] the maxRetries [1]
    [main] INFO o.a.s.s.o.a.z.Login - successfully logged in.
    [main-EventThread] INFO o.a.s.s.o.a.z.ClientCnxn - EventThread shut down for session: 0x16037a6e5f092575
    [main] INFO o.a.s.s.o.a.z.ZooKeeper - Session: 0x16037a6e5f092575 closed
    [main] INFO b.s.StormSubmitter - Uploading topology jar /opt/jar/example.jar to assigned location: /srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-86855b6b-133e-478d-b415-fa96e63e553f.jar
    Start uploading file '/opt/jar/example.jar' to '/srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-86855b6b-133e-478d-b415-fa96e63e553f.jar' (74143745 bytes)
    [==================================================] 74143745 / 74143745
    File '/opt/jar/example.jar' uploaded to '/srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-86855b6b-133e-478d-b415-fa96e63e553f.jar' (74143745 bytes)
    [main] INFO b.s.StormSubmitter - Successfully uploaded topology jar to assigned location: /srv/BigData/streaming/stormdir/nimbus/inbox/stormjar-86855b6b-133e-478d-b415-fa96e63e553f.jar
    [main] INFO b.s.StormSubmitter - Submitting topology word-count in distributed mode with conf {"storm.zookeeper.topology.auth.scheme":"digest","storm.zookeeper.topology.auth.payload":"-7360002804241426074:-6868950379453400421","topology.worker.gc.childopts":"-Xms4096m -Xmx4096m -XX:+UseG1GC -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=10 -XX:GCLogFileSize=1M","topology.workers":1}
    [main] INFO b.s.StormSubmitter - Finished submitting topology: word-count
    ```

2.  通过ps -ef | grep worker命令查看worker进程信息如下：

    ![](figures/zh-cn_image_0167276533.png)


