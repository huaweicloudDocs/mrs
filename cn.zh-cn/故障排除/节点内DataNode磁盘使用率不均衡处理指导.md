# 节点内DataNode磁盘使用率不均衡处理指导<a name="ZH-CN_TOPIC_0183415888"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276528_sd1dc17fee2214ed9867d242a14f38d7d"></a>

单个节点内DataNode的各磁盘使用率不均匀。

例如：

```
189-39-235-71:~ # df -h
Filesystem  Size  Used Avail Use% Mounted on
/dev/xvda  360G  92G   250G  28% /
/dev/xvdb  700G  900G   200G  78% /srv/BigData/hadoop/data1
/dev/xvdc  700G  900G   200G  78% /srv/BigData/hadoop/data2
/dev/xvdd  700G  900G   200G  78% /srv/BigData/hadoop/data3
/dev/xvde  700G  900G   200G  78% /srv/BigData/hadoop/data4
/dev/xvdf  10G   900G   890G  2% /srv/BigData/hadoop/data5
189-39-235-71:~ #  
```

## 可能原因<a name="zh-cn_topic_0167276528_sf4a7e0ba1ac14d3cb1db306143d1b51c"></a>

部分磁盘故障，更换为新盘，因此新盘使用率低。

增加了磁盘个数，如原先4个数据盘，现扩容为5个数据盘。

## 原因分析<a name="zh-cn_topic_0167276528_s36d0a1c802044398ada37b44f5dced4e"></a>

DataNode节点内写block磁盘时，有2种策略“轮询”和“优先写剩余磁盘空间多的磁盘”，默认是“轮询”。

参数说明：dfs.datanode.fsdataset.volume.choosing.policy

可选值：

-   轮询：org.apache.hadoop.hdfs.server.datanode.fsdataset.RoundRobinVolumeChoosingPolicy
-   优先写剩余空间多的磁盘： org.apache.hadoop.hdfs.server.datanode.fsdataset.AvailableSpaceVolumeChoosingPolicy

## 解决办法<a name="zh-cn_topic_0167276528_s72ccbb40aaab4b2d8bdeebae39f52199"></a>

将DataNode选择磁盘策略的参数 dfs.datanode.fsdataset.volume.choosing.policy 的值改为

org.apache.hadoop.hdfs.server.datanode.fsdataset.AvailableSpaceVolumeChoosingPolicy

让DataNode根据磁盘剩余空间大小，优先选择磁盘剩余空间多的节点存储数据副本。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   针对新写入到本DataNode的数据会优先写磁盘剩余空间多的磁盘。  
>-   部分磁盘使用率较高，依赖业务逐渐删除在HDFS中的数据（老化数据）来逐渐降低。  

