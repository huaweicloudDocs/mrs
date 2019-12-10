# 文件错误导致上传文件到HDFS失败<a name="ZH-CN_TOPIC_0181713163"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274477_s580642532b2a4a759c7278dbb045c15c"></a>

用**hadoop dfs -put**把本地文件拷贝到HDFS上，有报错。

上传部分文件后，报错失败，从NameNode原生页面看，临时文件大小不再变化。

## 原因分析<a name="zh-cn_topic_0167274477_s941472ebe27045dea37ad9f203246918"></a>

1.  查看NameNode日志“/var/log/Bigdata/hdfs/nn/hadoop-omm-namenode-主机名.log“，发现该文件一直在被尝试写，直到最终失败。

    ```
    2015-07-13 10:05:07,847 | WARN  | org.apache.hadoop.hdfs.server.namenode.LeaseManager$Monitor@36fea922 | DIR* NameSystem.internalReleaseLease: Failed to release lease for file /hive/order/OS_ORDER._8.txt._COPYING_. Committed blocks are waiting to be minimally replicated. Try again later. | FSNamesystem.java:3936
    2015-07-13 10:05:07,847 | ERROR | org.apache.hadoop.hdfs.server.namenode.LeaseManager$Monitor@36fea922 | Cannot release the path /hive/order/OS_ORDER._8.txt._COPYING_ in the lease [Lease.  Holder: DFSClient_NONMAPREDUCE_-1872896146_1, pendingcreates: 1] | LeaseManager.java:459
    org.apache.hadoop.hdfs.protocol.AlreadyBeingCreatedException: DIR* NameSystem.internalReleaseLease: Failed to release lease for file /hive/order/OS_ORDER._8.txt._COPYING_. Committed blocks are waiting to be minimally replicated. Try again later.
    at FSNamesystem.internalReleaseLease(FSNamesystem.java:3937)
    ```

2.  根因分析：被上传的文件损坏，因此会上传失败。
3.  验证办法：cp或者scp被拷贝的文件，也会失败，确认文件本身已损坏。

## 解决办法<a name="zh-cn_topic_0167274477_sea653621d24e44cca813046b469e16a2"></a>

1.  文件本身损坏造成的此问题，采用正常文件进行上传。

