# 使用MRS客户端操作OpenTSDB指标数据<a name="ZH-CN_TOPIC_0176678775"></a>

用户可以根据业务需要，在MRS集群的客户端中进行交互式操作。启用Kerberos认证的集群，需要操作的用户属于“opentsdb，hbase，opentsdbgroup和supergroup”组且拥有HBase权限。

## 前提条件<a name="section482010192610"></a>

-   获取用户“admin”帐号密码。“admin”密码在创建MRS集群时由用户指定。
-   已更新客户端，具体请参见[更新客户端](更新客户端.md)。

## 使用客户端<a name="section137578192714"></a>

1.  如果当前集群已启用Kerberos认证，登录MRS Manager页面，创建属于“opentsdb，hbase，opentsdbgroup和supergroup”组且拥有HBase权限的用户，例如创建用户为opentsdbuser，具体请参考[准备开发用户](https://support.huaweicloud.com/devg-mrs/mrs_06_0361.html)。如果当前集群未启用Kerberos认证，则无需执行此步骤。
2.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则登录该节点使用客户端，具体参见[更新客户端](更新客户端.md)。

3.  执行以下命令切换用户。

    **sudo su - omm**

4.  执行以下命令，切换到客户端目录，例如“/opt/client”。

    **cd /opt/client**

5.  执行以下命令，配置环境变量。

    **source bigdata\_env**

6.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。
    -   当用户为“人机”用户时：执行**kinit opentsdbuser**认证用户
    -   当用户为“机机”用户时：下载用户认证凭据文件，保存并解压获取用户的user.keytab文件与krb5.conf文件，进入解压后的user.keytab目录下，执行**kinit -kt user.keytab opentsdbuser**认证用户

7.  操作Opentsdb数据，具体请参见[操作数据](#section46629451460)。

## 操作数据<a name="section46629451460"></a>

-   查看帮助

    执行**tsdb**命令打印出当前opentsdb所支持的所有命令。如，fsck, import, mkmetric, query, tsd, scan, search, uid, version。

    回显信息：

    ```
    tsdb: error: unknown command ''
    usage: tsdb <command> [args]
    Valid commands: fsck, import, mkmetric, query, tsd, scan, search, uid, version
    ```

-   创建OpenTSDB指标

    执行**tsdb mkmetric**命令创建指标。例如执行**tsdb mkmetric sys.cpu.user**命令创建名为sys.cpu.user的指标。

    回显信息：

    ```
    Start run net.opentsdb.tools.UidManager, args: assign metrics sys.cpu.user
    metrics sys.cpu.user: [0, 0, 6]
    ```

-   向OpenTSDB指标中导入数据
    1.  准备作指标文件，例如包含如下信息的importData.txt文件。

        sys.cpu.user 1356998400 41 host=web01 cpu=0

        sys.cpu.user 1356998401 42 host=web01 cpu=0

        sys.cpu.user 1356998402 44 host=web01 cpu=0

        sys.cpu.user 1356998403 47 host=web01 cpu=0

        sys.cpu.user 1356998404 42 host=web01 cpu=0

        sys.cpu.user 1356998405 42 host=web01 cpu=0

    2.  执行**tsdb import**命令导入指标数据。例如执行**tsdb import importData.txt**命令导入importData.txt文件。

        ```
        Start run net.opentsdb.tools.TextImporter, args: importData.txt
        2019-06-26
        15:45:22,091 INFO  [main] TextImporter:
        reading from file:importData.txt
        2019-06-26
        15:45:22,102 INFO  [main] TextImporter:
        Processed importData.txt in 11 ms, 6 data points (545.5 points/s)
        2019-06-26
        15:45:22,102 INFO  [main] TextImporter:
        Total: imported 6 data points in 0.012s (504.0 points/s)
        ```


-   查询OpenTSDB指标

    执行**tsdb uid metrics**命令获取当前OpenTSDB中存入的指标。例如执行**tsdb uid metrics sys.cpu.user**命令查询sys.cpu.user的数据。

    回显信息：

    ```
    Start run net.opentsdb.tools.UidManager, args: metrics sys.cpu.user
    metrics sys.cpu.user: [0, 0, 6]
    ```

    如需获得更多信息，请执行**tsdb uid**命令。

    ```
    Start run net.opentsdb.tools.UidManager, args:
    Not enough arguments
    Usage: uid <subcommand> args
    Sub commands:
      grep [kind] <RE>: Finds matching IDs.
      assign <kind> <name> [names]: Assign an ID for the given name(s).
      rename <kind> <name> <newname>: Renames this UID.
      delete <kind> <name>: Deletes this UID.
      fsck: [fix] [delete_unknown] Checks the consistency of UIDs.
            fix            - Fix errors. By default errors are logged.
            delete_unknown - Remove columns with unknown qualifiers.
                             The "fix" flag must be supplied as well.
      [kind] <name>: Lookup the ID of this name.
      [kind] <ID>: Lookup the name of this ID.
      metasync: Generates missing TSUID and UID meta entries, updates created timestamps
      metapurge: Removes meta data entries from the UID table
      treesync: Process all timeseries meta objects through tree rules
      treepurge <id> [definition]: Purge a tree and/or the branches from storage. Provide an integer Tree ID and                                                       optionally add "true" to delete the tree definition
    Example values for [kind]: metrics, tagk (tag name), tagv (tag value).
      --config=PATH    Path to a configuration file (default: Searches for file see docs).
      --idwidth=N      Number of bytes on which the UniqueId is encoded.
      --ignore-case    Ignore case distinctions when matching a regexp.
      --table=TABLE    Name of the HBase table where to store the time series (default: tsdb).
      --uidtable=TABLE Name of the HBase table to use for Unique IDs (default: tsdb-uid).
      --verbose        Print more logging messages and not just errors.
      --zkbasedir=PATH Path under which is the znode for the -ROOT- region (default: /hbase).
      --zkquorum=SPEC  Specification of the ZooKeeper quorum to use (default: localhost).
      -i               Short for --ignore-case.
      -v               Short for --verbose.
    ```

-   扫描Opentsdb的指标数据

    执行**tsdb query**命令批量查询导入的指标数据，命令格式如下： tsdb query <START-DATE\> <END-DATE\> <aggregator\> <metric\> <tagk=tagv\>，例如执行**tsdb query 0 1h-ago sum sys.cpu.user host=web01**

    ```
    Start run net.opentsdb.tools.CliQuery, args: 0 1h-ago sum sys.cpu.user host=web01
    sys.cpu.user 1356998400000 41 {host=web01, cpu=0}
    sys.cpu.user 1356998401000 42 {host=web01, cpu=0}
    sys.cpu.user 1356998402000 44 {host=web01, cpu=0}
    sys.cpu.user 1356998403000 47 {host=web01, cpu=0}
    sys.cpu.user 1356998404000 42 {host=web01, cpu=0}
    sys.cpu.user 1356998405000 42 {host=web01, cpu=0}
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    ><START-DATE\>:要查询指标的起始时间点。  
    ><END-DATE\>:要查询指标的结束时间点。  
    ><aggregator\>:查询数据的聚合方式。  
    ><metric\>:所需查询的指标名称。  
    ><tagk=tagv\>:标签的key和value。  

-   删除录入的Opentsdb指标

    执行命令**tsdb uid delete**命令删除录入的指标及值。例如删除sys.cpu.user指标可执行命令**tsdb uid delete metrics sys.cpu.user**。

    ```
    Start run net.opentsdb.tools.UidManager, args: delete metrics sys.cpu.user
    ```


