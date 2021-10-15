# 客户端写文件close失败<a name="mrs_03_0081"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276038_sd90676c0ec6d4f35884c312c769390c4"></a>

客户端写文件close失败，客户端提示数据块没有足够副本数。

客户端日志：

```
2015-05-27 19:00:52.811 [pool-2-thread-3] ERROR: /tsp/nedata/collect/UGW/ugwufdr/20150527/10/6_20150527105000_20150527105500_SR5S14_1432723806338_128_11.pkg.tmp1432723806338 close hdfs sequence file fail (SequenceFileInfoChannel.java:444)
java.io.IOException: Unable to close file because the last block does not have enough number of replicas.
at org.apache.hadoop.hdfs.DFSOutputStream.completeFile(DFSOutputStream.java:2160)
at org.apache.hadoop.hdfs.DFSOutputStream.close(DFSOutputStream.java:2128)
at org.apache.hadoop.fs.FSDataOutputStream$PositionCache.close(FSDataOutputStream.java:70)
at org.apache.hadoop.fs.FSDataOutputStream.close(FSDataOutputStream.java:103)
at com.huawei.pai.collect2.stream.SequenceFileInfoChannel.close(SequenceFileInfoChannel.java:433)
at com.huawei.pai.collect2.stream.SequenceFileWriterToolChannel$FileCloseTask.call(SequenceFileWriterToolChannel.java:804)
at com.huawei.pai.collect2.stream.SequenceFileWriterToolChannel$FileCloseTask.call(SequenceFileWriterToolChannel.java:792)
at java.util.concurrent.FutureTask.run(FutureTask.java:262)
at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
at java.lang.Thread.run(Thread.java:745)
```

## 原因分析<a name="zh-cn_topic_0167276038_s003d893d7fc948339359bb0358df0f84"></a>

1.  HDFS客户端开始写Block。

    例如：HDFS客户端是在2015-05-27 18:50:24,232开始写/20150527/10/6\_20150527105000\_20150527105500\_SR5S14\_1432723806338\_128\_11.pkg.tmp1432723806338的。其中分配的块是blk\_1099105501\_25370893。

    ```
    2015-05-27 18:50:24,232 | INFO  | IPC Server handler 30 on 25000 | BLOCK* allocateBlock: /20150527/10/6_20150527105000_20150527105500_SR5S14_1432723806338_128_11.pkg.tmp1432723806338. BP-1803470917-192.168.57.33-1428597734132 blk_1099105501_25370893{blockUCState=UNDER_CONSTRUCTION, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-b2d7b7d0-f410-4958-8eba-6deecbca2f87:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-76bd80e7-ad58-49c6-bf2c-03f91caf750f:NORMAL|RBW]]} | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.saveAllocatedBlock(FSNamesystem.java:3166)
    ```

2.  写完之后HDFS客户端调用了fsync。

    ```
    2015-05-27 19:00:22,717 | INFO  | IPC Server handler 22 on 25000 | BLOCK* fsync: 20150527/10/6_20150527105000_20150527105500_SR5S14_1432723806338_128_11.pkg.tmp1432723806338 for DFSClient_NONMAPREDUCE_-120525246_15 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.fsync(FSNamesystem.java:3805)
    ```

3.  HDFS客户端调用close关闭文件，NameNode收到客户端的close请求之后就会检查最后一个块的完成状态，只有当有足够的DataNode上报了块完成才可用关闭文件，检查块完成的状态是通过checkFileProgress函数检查的，打印如下：

    ```
    2015-05-27 19:00:27,603 | INFO  | IPC Server handler 44 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    2015-05-27 19:00:28,005 | INFO  | IPC Server handler 45 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    2015-05-27 19:00:28,806 | INFO  | IPC Server handler 63 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    2015-05-27 19:00:30,408 | INFO  | IPC Server handler 43 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    2015-05-27 19:00:33,610 | INFO  | IPC Server handler 37 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    2015-05-27 19:00:40,011 | INFO  | IPC Server handler 37 on 25000 | BLOCK* checkFileProgress: blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} has not reached minimal replication 1 | org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkFileProgress(FSNamesystem.java:3197)
    ```

4.  NameNode打印了多次checkFileProgress是由于HDFS客户端多次尝试close文件，但是由于当前状态不满足要求，导致close失败， HDFS客户端retry的次数是由参数dfs.client.block.write.locateFollowingBlock.retries决定的，该参数默认是5，所以在NameNode的日志中看到了6次checkFileProgress打印。
5.  但是再过0.5s之后，DataNode就上报块已经成功写入。

    ```
    2015-05-27 19:00:40,608 | INFO  | IPC Server handler 60 on 25000 | BLOCK* addStoredBlock: blockMap updated: 192.168.10.21:25009 is added to blk_1099105501_25370893{blockUCState=COMMITTED, primaryNodeIndex=-1, replicas=[ReplicaUnderConstruction[[DISK]DS-ef5fd3c9-5088-4813-ae9a-34a0714ec3a3:NORMAL|RBW], ReplicaUnderConstruction[[DISK]DS-f863e30f-ce5b-48cc-9cca-72f64c558adc:NORMAL|RBW]]} size 11837530 | org.apache.hadoop.hdfs.server.blockmanagement.BlockManager.logAddStoredBlock(BlockManager.java:2393)
    2015-05-27 19:00:48,297 | INFO  | IPC Server handler 37 on 25000 | BLOCK* addStoredBlock: blockMap updated: 192.168.10.10:25009 is added to blk_1099105501_25370893 size 11837530 | org.apache.hadoop.hdfs.server.blockmanagement.BlockManager.logAddStoredBlock(BlockManager.java:2393)
    ```

6.  DataNode上报块写成功通知延迟的原因可能有：网络瓶颈导致、CPU瓶颈导致。
7.  如果此时再次调用close或者close的retry的次数增多，那么close都将返回成功。建议适当增大参数dfs.client.block.write.locateFollowingBlock.retries的值，默认值为5次，尝试的时间间隔为400ms、800ms、1600ms、3200ms、6400ms，12800ms，那么close函数最多需要25.2秒才能返回。

## 解决办法<a name="zh-cn_topic_0167276038_s9443cea47d1b4038b41bc68b70401408"></a>

1.  规避办法：

    可以通过调整客户端参数dfs.client.block.write.locateFollowingBlock.retries的值来增加retry的次数，可以将值设置为6，那么中间睡眠等待的时间为400ms、800ms、1600ms、3200ms、6400ms、12800ms，也就是说close函数最多要50.8秒才能返回。


## 备注说明<a name="zh-cn_topic_0167276038_s43ddab449746409b8f87f125b94792f8"></a>

一般出现上述现象，说明集群负载很大，通过调整参数只是临时规避这个问题，建议还是降低集群负载。例如：避免把所有CPU都分配MR跑任务。

