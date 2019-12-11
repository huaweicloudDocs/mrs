# 集群上下电之后HBase启动失败<a name="ZH-CN_TOPIC_0187794915"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276008_sf76e408f8ea44020bf3de33c280bc079"></a>

集群的ECS关机重启后，HBase启动失败。

## 原因分析<a name="zh-cn_topic_0167276008_s2d857902554344b38f9d1ff9130b2ce3"></a>

查看HMaster的运行日志，发现有报大量的如下错误：

```
2018-03-26 11:10:54,185 | INFO  | hadoopc1h3,21300,1522031630949_splitLogManager__ChoreService_1 | total tasks = 1 unassigned = 0 tasks={/hbase/splitWAL/WALs%2Fhadoopc1h1%2C213
02%2C1520214023667-splitting%2Fhadoopc1h1%252C21302%252C1520214023667.default.1520584926990=last_update = 1522033841041 last_version = 34255 cur_worker_name = hadoopc1h3,21302,
1520943011826 status = in_progress incarnation = 3 resubmits = 3 batch = installed = 1 done = 0 error = 0} | org.apache.hadoop.hbase.master.SplitLogManager$TimeoutMonitor.chore
(SplitLogManager.java:745)
2018-03-26 11:11:00,185 | INFO  | hadoopc1h3,21300,1522031630949_splitLogManager__ChoreService_1 | total tasks = 1 unassigned = 0 tasks={/hbase/splitWAL/WALs%2Fhadoopc1h1%2C213
02%2C1520214023667-splitting%2Fhadoopc1h1%252C21302%252C1520214023667.default.1520584926990=last_update = 1522033841041 last_version = 34255 cur_worker_name = hadoopc1h3,21302,
1520943011826 status = in_progress incarnation = 3 resubmits = 3 batch = installed = 1 done = 0 error = 0} | org.apache.hadoop.hbase.master.SplitLogManager$TimeoutMonitor.chore
(SplitLogManager.java:745)
2018-03-26 11:11:06,185 | INFO  | hadoopc1h3,21300,1522031630949_splitLogManager__ChoreService_1 | total tasks = 1 unassigned = 0 tasks={/hbase/splitWAL/WALs%2Fhadoopc1h1%2C213
02%2C1520214023667-splitting%2Fhadoopc1h1%252C21302%252C1520214023667.default.1520584926990=last_update = 1522033841041 last_version = 34255 cur_worker_name = hadoopc1h3,21302,
1520943011826 status = in_progress incarnation = 3 resubmits = 3 batch = installed = 1 done = 0 error = 0} | org.apache.hadoop.hbase.master.SplitLogManager$TimeoutMonitor.chore
(SplitLogManager.java:745)
2018-03-26 11:11:10,787 | INFO  | RpcServer.reader=9,bindAddress=hadoopc1h3,port=21300 | Kerberos principal name is hbase/hadoop.hadoop.com@HADOOP.COM | org.apache.hadoop.hbase
.ipc.RpcServer$Connection.readPreamble(RpcServer.java:1532)
2018-03-26 11:11:12,185 | INFO  | hadoopc1h3,21300,1522031630949_splitLogManager__ChoreService_1 | total tasks = 1 unassigned = 0 tasks={/hbase/splitWAL/WALs%2Fhadoopc1h1%2C213
02%2C1520214023667-splitting%2Fhadoopc1h1%252C21302%252C1520214023667.default.1520584926990=last_update = 1522033841041 last_version = 34255 cur_worker_name = hadoopc1h3,21302,
1520943011826 status = in_progress incarnation = 3 resubmits = 3 batch = installed = 1 done = 0 error = 0} | org.apache.hadoop.hbase.master.SplitLogManager$TimeoutMonitor.chore
(SplitLogManager.java:745)
2018-03-26 11:11:18,185 | INFO  | hadoopc1h3,21300,1522031630949_splitLogManager__ChoreService_1 | total tasks = 1 unassigned = 0 tasks={/hbase/splitWAL/WALs%2Fhadoopc1h1%2C213
02%2C1520214023667-splitting%2Fhadoopc1h1%252C21302%252C1520214023667.default.1520584926990=last_update = 1522033841041 last_version = 34255 cur_worker_name = hadoopc1h3,21302,
1520943011826 status = in_progress incarnation = 3 resubmits = 3 batch = installed = 1 done = 0 error = 0} | org.apache.hadoop.hbase.master.SplitLogManager$TimeoutMonitor.chore
(SplitLogManager.java:745)
```

节点上下电，RegionServer的wal分裂失败导致。

## 解决办法<a name="zh-cn_topic_0167276008_section1455043221018"></a>

1.  停止HBase组件。
2.  通过hdfs  fsck命令检查/hbase/WALs文件的健康状态。

    **hdfs fsck  /hbase/WALs**

    输出如下表示文件都正常，如果有异常则需要先处理异常的文件，再执行后面的操作。

    ```
    The filesystem under path '/hbase/WALs' is HEALTHY
    ```

3.  备份/hbase/WALs文件。

    **hdfs dfs -mv /hbase/WALs /hbase/WALs\_old**

4.  新建/hbase/WALs目录。

    **hdfs dfs –mkdir /hbase/WALs**

    必须保证路径权限是hbase:hadoop。

5.  启动HBase组件。

