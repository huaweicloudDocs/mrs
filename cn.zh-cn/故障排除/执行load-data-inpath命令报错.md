# 执行load data inpath命令报错<a name="ZH-CN_TOPIC_0207461480"></a>

## 问题现象<a name="zh-cn_topic_0167274496_s3daa76df58db43fcb4ff7a1f5dc4e283"></a>

执行load data inpath报如下错误：

-   错误1：

    ```
    HiveAccessControlException Permission denied. Principal [name=user1, type=USER] does not have following privileges on Object [type=DFS_URI, name=hdfs://hacluster/tmp/input/mapdata] for operation LOAD : [OBJECT OWNERSHIP]
    ```

-   错误2：

    ```
    HiveAccessControlException Permission denied. Principal [name=user1, type=USER] does not have following privileges on Object [type=DFS_URI, name=hdfs://hacluster/tmp/input/mapdata] for operation LOAD : [INSERT, DELETE]
    ```

-   错误3：

    ```
    SemanticException [Error 10028]: Line 1:17 Path is not legal ''file:///tmp/input/mapdata'': Move from: file:/tmp/input/mapdata to: hdfs://hacluster/user/hive/warehouse/tmp1 is not valid. Please check that values for params "default.fs.name" and "hive.metastore.warehouse.dir" do not conflict.
    ```


## 原因分析<a name="zh-cn_topic_0167274496_section722414093311"></a>

当前登录的用户不具备操作此目录的权限或者文件目录格式不正确。

## 解决方案<a name="zh-cn_topic_0167274496_s794759951c8b4ebb90544ffa4f0f521f"></a>

Hive对load data inpath命令有如下权限要求，请对照下述要求是否满足：

-   文件的owner需要为执行命令的用户。
-   当前用户需要对该文件有读、写权限。
-   当前用户需要对该文件的目录有执行权限。
-   由于load操作会将该文件移动到表对应的目录中，所以要求当前用户需要对表的对应目录有写权限。
-   要求文件的格式与表指定的存储格式相同。如创建表时指定stored as rcfile，但是文件格式为txt，则不符合要求。
-   文件必须是HDFS上的文件，不可以用file://的形式指定本地文件系统上的文件。
-   文件名不能以下横线（\_）或点（.）开头，以这些开头的文件会被忽略。

    如下所示，如果用户test\_hive load数据，正确的权限如下：

    ```
    [root@192-168-1-18 duan]# hdfs dfs -ls /tmp/input2
    16/03/21 14:45:07 INFO hdfs.PeerCache: SocketCache disabled.
    Found 1 items
    -rw-r--r--   3 test_hive hive          6 2016-03-21 14:44 /tmp/input2/input.txt
    ```


