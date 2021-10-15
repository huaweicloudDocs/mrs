# RegionServer实例异常，处于Restoring状态<a name="mrs_03_0143"></a>

## 问题背景<a name="zh-cn_topic_0167276416_sf76e408f8ea44020bf3de33c280bc079"></a>

HBase启动失败，RegionServer一直处于Restoring状态。

## 原因分析<a name="zh-cn_topic_0167276416_s2d857902554344b38f9d1ff9130b2ce3"></a>

查看异常的RegionServer实例的运行日志（/var/log/Bigdata/hbase/rs/hbase-omm-XXX.log），发现显示以下打印信息ClockOutOfSyncException...，Reported time is too far out of sync with master

```
2017-09-18 11:16:23,636 | FATAL | regionserver21302 | Master rejected startup because clock is out of sync | org.apache.hadoop.hbase.regionserver.HRegionServer.reportForDuty(HRegionServer.java:2059)
org.apache.hadoop.hbase.ClockOutOfSyncException: org.apache.hadoop.hbase.ClockOutOfSyncException: Server nl-bi-fi-datanode-24-65,21302,1505726180086 has been rejected; Reported time is too far out of sync with master.  Time difference of 152109ms > max allowed of 30000ms
at org.apache.hadoop.hbase.master.ServerManager.checkClockSkew(ServerManager.java:354)
...

...
2017-09-18 11:16:23,858 | ERROR | main | Region server exiting | org.apache.hadoop.hbase.regionserver.HRegionServerCommandLine.start(HRegionServerCommandLine.java:70)
java.lang.RuntimeException: HRegionServer Aborted

```

该日志说明异常的RegionServer实例和HMaster实例的时差大于允许的时差值30s（由参数hbase.regionserver.maxclockskew控制，默认30000ms），导致RegionServer实例异常。

## 解决办法<a name="zh-cn_topic_0167276416_sed4194588b214662be5341d4a1f9ecbd"></a>

调整异常节点时间，确保节点间时差小于30s。

