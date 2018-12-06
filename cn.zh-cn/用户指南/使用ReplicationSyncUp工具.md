# 使用ReplicationSyncUp工具<a name="ZH-CN_TOPIC_0109194054"></a>

**前提条件**

1.  ReplicationSyncUp工具仅在MRS1.7及其以后版本中支持。
2.  主备集群已经安装并且启动。
3.  主备集群上的时间必须一致，而且主备集群上的NTP服务必须使用同一个时间源。
4.  当主集群HBase服务关闭时，Zookeeper和HDFS服务应该启动并运行。
5.  该工具应该由启动HBase进程的系统用户运行。
6.  如果处于安全模式，请确保备用集群的HBase系统用户具有主集群HDFS的读取权限。因为它将更新HBase系统Zookeeper节点和HDFS文件。
7.  主集群HBase故障后，主集群的zookeeper，文件系统和网络依然可用。

**场景介绍**

Replication机制可以使用WAL将一个集群的状态与另一个集群的状态保持同步。启用HBase备份后，若主集群出现故障，ReplicationSyncUp工具会使用来自zookeeper的信息将主集群中的启用HBase备份功能的数据增量同步到备集群中。数据同步完成后，备集群可以作为主集群使用。

**参数配置**

<a name="table97621948102914"></a>
<table><thead align="left"><tr id="row148111348112918"><th class="cellrowborder" valign="top" width="38.77612238776123%" id="mcps1.1.4.1.1"><p id="p081194818292"><a name="p081194818292"></a><a name="p081194818292"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="46.93530646935306%" id="mcps1.1.4.1.2"><p id="p178111048152916"><a name="p178111048152916"></a><a name="p178111048152916"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="14.288571142885711%" id="mcps1.1.4.1.3"><p id="p28111248202914"><a name="p28111248202914"></a><a name="p28111248202914"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="row0811548202919"><td class="cellrowborder" valign="top" width="38.77612238776123%" headers="mcps1.1.4.1.1 "><p id="p16811144892911"><a name="p16811144892911"></a><a name="p16811144892911"></a>hbase.replication.bulkload.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="46.93530646935306%" headers="mcps1.1.4.1.2 "><p id="p82782193210"><a name="p82782193210"></a><a name="p82782193210"></a>是否开启批量加载数据复制功能。参数值类型为Boolean。开启批量加载数据复制功能后该参数须在主集群中设置为true。</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.1.4.1.3 "><p id="p58112487293"><a name="p58112487293"></a><a name="p58112487293"></a>false</p>
</td>
</tr>
<tr id="row198111948192913"><td class="cellrowborder" valign="top" width="38.77612238776123%" headers="mcps1.1.4.1.1 "><p id="p16811184832912"><a name="p16811184832912"></a><a name="p16811184832912"></a>hbase.replication.cluster.id</p>
</td>
<td class="cellrowborder" valign="top" width="46.93530646935306%" headers="mcps1.1.4.1.2 "><p id="p0811104813298"><a name="p0811104813298"></a><a name="p0811104813298"></a>源HBase集群ID。开启批量加载数据复制功能是必须设置该参数，在源集群定义。参数值类型为String。</p>
</td>
<td class="cellrowborder" valign="top" width="14.288571142885711%" headers="mcps1.1.4.1.3 "><p id="p6811248112917"><a name="p6811248112917"></a><a name="p6811248112917"></a>-</p>
</td>
</tr>
</tbody>
</table>

**工具使用**

在主集群client上输入如下命令使用：

**hbase org.apache.hadoop.hbase.replication.regionserver.ReplicationSyncUp -Dreplication.sleep.before.failover=1**

>![](public_sys-resources/icon-note.gif) **说明：**   
>replication.sleep.before.failover是指在RegionServer启动失败时备份其剩余数据前需要的休眠时间。由于30秒（默认值）的睡眠时间没有任何意义，因此将其设置为1（s），使备份过程更快触发。  

**注意事项**

1. 当主集群关闭时，此工具将从zookeeper节点（RS znode）获得WAL的处理进度以及WAL的处理队列，并将未复制的队列复制到备集群中。

2.每个主集群的RegionServer在备集群zookeeper上的replication 节点下都有自己的znode。它包含每个对等集群的一个znode。

3.当Regionserver故障时，主集群的每个Regionserver都会通过watcher收到通知，并尝试锁定故障regionserver的znode，包含它的队列。成功创建的RS会将所有队列转移到自己队列的znode下。队列传输后，它们将从旧位置删除。

4.在主集群关闭期间，ReplicationSyncUp工具将使用来自zookeeper节点的信息同步主备集群的数据，并且rs znode的wals将被移动到备集群下。

**限制和约束**

如果备集群处于关闭状态或关闭了对等关系，该工具正常运行，只有该对等关系复制不会发生。

