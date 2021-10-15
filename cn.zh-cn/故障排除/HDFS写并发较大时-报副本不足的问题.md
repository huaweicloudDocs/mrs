# HDFS写并发较大时，报副本不足的问题<a name="mrs_03_0291"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274525_s158e8e298d8e463baa11b441927c46e8"></a>

用户运行作业时写文件到HDFS，偶现写文件失败的情况。

操作日志如下：

```
105 | INFO  | IPC Server handler 23 on 25000 | IPC Server handler 23 on 25000, call org.apache.hadoop.hdfs.protocol.ClientProtocol.addBlock from 192.168.1.96:47728 Call#1461167 Retry#0 | Server.java:2278 
java.io.IOException: File /hive/warehouse/000000_0.835bf64f-4103 could only be replicated to 0 nodes instead of minReplication (=1).  There are 3 datanode(s) running and 3 node(s) are excluded in this operation.
```

## 原因分析<a name="zh-cn_topic_0167274525_s66462fbbe386437f923a475bfab597d6"></a>

-   HDFS写文件的预约机制：无论文件是10M还是1G，开始写的每个块都会被预约128M。如果需要写入一个10M的文件，HDFS会预约一个块来写，当文件写完后，这个块只占实际大小10M，释放多余预约的118M空间。如果需要写入一个1G的文件，HDFS还是会预约一个块来写，这个块写完后再开启下一个块，文件写完后，实际占用1G磁盘，释放多余预约的空间。

-   该异常通常是因为业务写文件的并发量太高，预约写Block的磁盘空间不足，导致写文件失败。

## 解决办法<a name="section986322561410"></a>

1.  登录HDFS的WebUI页面，进入DataNode的JMX页面。
    1.  在HDFS原生界面，选择Datanodes页面。
    2.  找到对应的DataNode节点，单击Http Address地址进入DataNode详情。
    3.  将url的“datanode.html”改为“jmx”就能获取到DataNode的JMX信息。

2.  搜索“XceiverCount”指标，当该指标的值\*Block块的大小超过DataNode磁盘的容量，就说明预约写Block的磁盘空间不足。
3.  发生该问题，通常有以下两种方法来解决：

    方法一：降低业务的并发度。

    方法二：减少业务写文件的数目，将多个文件合并成一个文件来写。


