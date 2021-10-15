# ZooKeeper上数据错乱导致ClickHouse启动失败问题<a name="mrs_03_0281"></a>

## 问题现象<a name="section13589342568"></a>

ClickHouse集群中某实例节点启动失败，该实例节点启动日志中有如下类似报错信息：

```
2021.03.15 21:01:19.816593 [ 11111 ] {} <Error> Application: DB::Exception:
The local set of parts of table DEFAULT.lineorder doesn't look like the set ofdoesn't look like the set of
parts in ZooKeeper: 59.99 million rows of 59.99 million total rows in
filesystem are suspicious. There are 30 unexpected parts with 59986052 rows
(14 of them is not just-written with 59986052 rows), 0 missing parts (with 0
blocks).: Cannot attach table `DEFAULT`.`lineorder` from metadata file
...
: while loading database
```

## 原因分析<a name="section18845443812"></a>

使用ClickHouse过程中，ClickHouse实例异常场景下，重复创建集群ReplicatedMergeTree引擎表，后续又进行删除表等操作导致ZooKeeper上的数据异常，致使ClickHouse启动失败。

## 解决办法<a name="section85111132144715"></a>

1.  备份问题节点数据库下所有表数据到其他目录。

    -   备份表数据：

        **cd /srv/BigData/data**_1_**/clickhouse/data/**_数据库名_

        **mv **_表名_** **_待备份的目录/_**data**_1_

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >如果存在多磁盘的场景，需要对**data1**到**dataN**的磁盘数据都执行相同的备份操作。


    -   备份元数据信息：

        **cd /srv/BigData/data1**_/_**clickhouse\_path/metadata**

        **mv **_表名_**.sql **_待备份的目录_

    例如，下面是备份default数据库下的表lineorder数据到**/home/backup**目录下。

    **cd /srv/BigData/data1/clickhouse/data/default**

    **mv lineorder /home/backup**/**data1**

    **cd /srv/BigData/data1/clickhouse\_path/metadata**

    **mv lineorder.sql /home/backup**

2.  登录MRS Manager页面，选择“集群 \> 服务 \> ClickHouse \> 实例”，选择对应的实例节点，单击“启动实例”，完成实例启动。
3.  实例启动成功后，使用ClickHouse客户端登录问题节点。

    **clickhouse client --host  **_clickhouse实例IP_ ** --user **_用户名_** --password** _密码_

4.  <a name="li4422174210324"></a>执行以下命令获取当前表所在的ZooKeeper路径**zookeeper\_path**和对应节点所在的副本编号**replica\_num**。

    **SELECT zookeeper\_path FROM system.replicas WHERE database = '**_数据库名_**' AND table = '**_表名_**';**

    **SELECT replica\_num,host\_name FROM system.clusters;**

5.  执行以下命令连接ZooKeeper命令行界面。

    **zkCli.sh -server **_ZooKeeper所在节点的IP_:**2181**

    获取ZooKeeper的IP地址，具体请参考[如何获取ZooKeeper地址？](https://support.huaweicloud.com/mrs_faq/mrs_03_1071.html)

6.  找到对应故障节点表数据对应的ZooKeeper路径。

    **ls ** _zookeeper\_path_**/replicas/**_replica\_num_

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >zookeeper\_path为[4](#li4422174210324)中查询到的**zookeeper\_path**值。
    >replica\_num为[4](#li4422174210324)中节点主机对应的副本编号**replica\_num**的值。

7.  执行以下命令，删除ZooKeeper上的副本数据。

    **deleteall**_ zookeeper\_path_**/replicas/**_replica\_num_

8.  使用ClickHouse客户端登录问题节点，重新执行create创建集群ReplicatedMergeTree引擎表。

    **clickhouse client --host  **_clickhouse实例IP_ ** --multiline --user **_用户名_** --password** _密码_

    **CREATE TABLE **_数据库名.表名_** ON CLUSTER **_集群名_

    ...

    **ENGINE = ReplicatedMergeTree**  ...

    其他副本节点有如下提示表已经存在的报错信息，属于正常现象，可以忽略。

    ```
    Received exception from server (version 20.8.7):
    Code: 57. DB::Exception: Received from x.x.x.x:9000. DB::Exception:
    There was an error on [x.x.x.x:9000]: Code: 57, e.displayText() =
    DB::Exception: Table DEFAULT.lineorder already exists. (version 20.8.11.17
    (official build)).
    ```

    建表成功后问题节点上表数据会自动进行同步，数据恢复完成。


