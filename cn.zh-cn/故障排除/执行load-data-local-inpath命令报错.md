# 执行load data local inpath命令报错<a name="mrs_03_0162"></a>

## 问题现象<a name="zh-cn_topic_0167275418_s91ac7cf658f74a3b8df14d7dec078fbc"></a>

执行load data local inpath报如下错误：

-   错误1：

    ```
    HiveAccessControlException Permission denied. Principal [name=user1, type=USER] does not have following privileges on Object [type=LOCAL_URI, name=file:/tmp/input/mapdata] for operation LOAD : [SELECT, INSERT, DELETE]
    ```

-   错误2：

    ```
    HiveAccessControlException Permission denied. Principal [name=user1, type=USER] does not have following privileges on Object [type=LOCAL_URI, name=file:/tmp/input/mapdata] for operation LOAD : [OBJECT OWNERSHIP]
    ```

-   错误3：

    ```
    SemanticException Line 1:23 Invalid path ''/tmp/input/mapdata'': No files matching path file:/tmp/input/mapdata  
    ```


## 原因分析<a name="zh-cn_topic_0167275418_section1645144113716"></a>

当前登录的用户不具备操作此目录的权限或者在HiveServer所在节点上没有此目录。

## 解决方案<a name="zh-cn_topic_0167275418_scb87efd2dd7d4352b547c9163f68269f"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>通常不建议使用本地文件加载数据到hive表。 建议先将本地文件放入HDFS，然后从集群中加载数据。

Hive对load data local inpath命令有如下权限要求，请对照下述要求是否满足：

-   由于所有的命令都是发送到主HiveServer上去执行的，所以要求此文件在HiveServer节点上。
-   HiveServer进程是以操作系统上的omm用户启动的，所以要求omm用户对此文件有读权限，对此文件的目录有读、执行权限。
-   文件的owner需要为执行命令的用户。
-   当前用户需要对该文件有读、写权限。
-   要求文件的格式与表指定的存储格式相同。如创建表时指定stored as rcfile，但是文件格式为txt，则不符合要求。
-   文件名不能以下横线（\_）或点（.）开头，以这些开头的文件会被忽略。

