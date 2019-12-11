# HDFS容量使用达到100%，导致上层服务HBase、Spark等上报服务不可用<a name="ZH-CN_TOPIC_0170935296"></a>

## 用户问题<a name="section18305143583116"></a>

集群的HDFS容量使用达到100%，HDFS服务状态为只读，导致上层服务HBase、Spark等上报服务不可用告警。

## 问题现象<a name="section117424454313"></a>

HDFS使用容量100%，磁盘容量只使用85%左右，HDFS服务状态为只读，导致上层服务HBase、Spark等上报服务不可用。

## 原因分析<a name="section1237061220324"></a>

当前NodeManager和DataNode共数据盘使用，MRS默认预留15%的数据磁盘空间给非HDFS使用，可通过HDFS参数**dfs.datanode.du.reserved.percentage**修改百分比来控制具体的磁盘占比。

当HDFS磁盘使用100%之后，可通过降低**dfs.datanode.du.reserved.percentage**百分比来恢复业务，再进行磁盘扩容。

## 处理步骤<a name="section177802364523"></a>

1.  登录集群任意Master节点。
2.  执行**source /opt/client/bigdata\_env**命令，初始化环境变量。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果是安全集群，则需要执行**kinit -kt <keytab file\> <pricipal name\>**  进行认证。  

3.  执行**hdfs dfs –put ./startDetail.log /tmp**命令，测试HDFS写文件失败。

    ```
    19/05/12 10:07:32 WARN hdfs.DataStreamer: DataStreamer Exception
    org.apache.hadoop.ipc.RemoteException(java.io.IOException): File /tmp/startDetail.log._COPYING_ could only be replicated to 0 nodes instead of minReplication (=1).  There are 3 datanode(s) running and no node(s) are excluded in this operation.
    ```

4.  执行**hdfs dfsadmin -report**命令，检查HDFS使用容量，发现已经达到100%。

    ```
    Configured Capacity: 5389790579100 (4.90 TB)
    Present Capacity: 5067618628404 (4.61 TB)
    DFS Remaining: 133350196 (127.17 MB)
    DFS Used: 5067485278208 (4.61 TB)
    DFS Used%: 100.00%
    Under replicated blocks: 10
    Blocks with corrupt replicas: 0
    Missing blocks: 0
    Missing blocks (with replication factor 1): 0
    Pending deletion blocks: 0
    ```

5.  当HDFS使用容量达到100%时，通过HDFS参数**dfs.datanode.du.reserved.percentage**修改百分比来控制具体的磁盘占比。
    1.  登录MRS Manager页面，选择“服务管理”\>“HDFS”\>“服务配置”。
    2.  “参数类别“选择“全部配置“，在搜索框中搜索**dfs.datanode.du.reserved.percentage**。
    3.  修改此参数的取值为“10“。

6.  修改完成后，扩容Core节点的磁盘个数。详细请参考[MRS集群添加新磁盘](MRS集群添加新磁盘.md)。

