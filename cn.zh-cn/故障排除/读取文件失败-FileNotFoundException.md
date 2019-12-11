# 读取文件失败，FileNotFoundException<a name="ZH-CN_TOPIC_0181713165"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274700_section533506231639"></a>

有MapReduce任务所有map任务均成功，但reduce任务失败，查看日志发现报异常“FileNotFoundException...No lease on...File does not exist”。

```
Error: org.apache.hadoop.ipc.RemoteException(java.io.FileNotFoundException): No lease on /user/sparkhive/warehouse/daas/dsp/output/_temporary/1/_temporary/attempt_1479799053892_17075_r_000007_0/part-r-00007 (inode 6501287): File does not exist. Holder DFSClient_attempt_1479799053892_17075_r_000007_0_-1463597952_1 does not have any open files.
at org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkLease(FSNamesystem.java:3350)
at org.apache.hadoop.hdfs.server.namenode.FSNamesystem.completeFileInternal(FSNamesystem.java:3442)
at org.apache.hadoop.hdfs.server.namenode.FSNamesystem.completeFile(FSNamesystem.java:3409)
at org.apache.hadoop.hdfs.server.namenode.NameNodeRpcServer.complete(NameNodeRpcServer.java:789)

```

## 原因分析<a name="zh-cn_topic_0167274700_section407398731639"></a>

FileNotFoundException...No lease on...File does not exist，该日志说明文件在操作的过程中被删除了。

1.  搜索HDFS的NameNode的审计日志（Active NameNode的/var/log/Bigdata/audit/hdfs/nn/hdfs-audit-namenode.log）搜索文件名，确认文件的创建时间。
2.  搜索文件创建到出现异常时间范围的NameNode的审计日志，搜索该文件是否被删除或者move到其他目录。
3.  如果该文件没有被删除或者移动，可能是该文件的父目录，或者更上层目录被删除或者移动，需要继续搜索上层目录。如本样例中，是文件的父目录的父目录被删除。

    ```
    2017-05-31 02:04:08,286 | INFO  | IPC Server handler 30 on 25000 | allowed=true      ugi=appUser@HADOOP.COM (auth:TOKEN) ip=/192.168.1.22     cmd=delete      src=/user/sparkhive/warehouse/daas/dsp/output/_temporary      dst=null    perm=null proto=rpc | FSNamesystem.java:8189
    
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如上日志说明：192.168.1.22 节点的appUser用户删除了/user/sparkhive/warehouse/daas/dsp/output/\_temporary。  
    >-   可以使用**zgrep "文件名" \*.zip**命令搜索zip包的内容。  


## 解决办法<a name="zh-cn_topic_0167274700_section122602861639"></a>

1.  需要排查业务，确认为何该文件或者文件的父目录被删除。

