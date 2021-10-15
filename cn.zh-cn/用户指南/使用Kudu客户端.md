# 使用Kudu客户端<a name="mrs_01_24192"></a>

Kudu是专为Apache Hadoop平台开发的列式存储管理器。Kudu具有Hadoop生态系统应用程序的共同技术特性：可水平扩展，并支持高可用性操作。

## 前提条件<a name="zh-cn_topic_0264266725_section10207153362919"></a>

已安装集群客户端，例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

## 操作步骤<a name="zh-cn_topic_0264266725_section10873172642318"></a>

1.  以客户端安装用户，登录安装客户端的节点。
2.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

3.  执行以下命令配置环境变量。

    **source bigdata\_env**

4.  运行Kudu命令行工具。

    直接执行Kudu组件的命令行工具，查看帮助。

    **kudu -h**

    回显信息如下：

    ```
    Usage: ./kudu <command> [<args>]
     
    <command> can be one of the following:
             cluster   Operate on a Kudu cluster
            diagnose   Diagnostic tools for Kudu servers and clusters
                  fs   Operate on a local Kudu filesystem
                 hms   Operate on remote Hive Metastores
       local_replica   Operate on local tablet replicas via the local filesystem
              master   Operate on a Kudu Master
                 pbc   Operate on PBC (protobuf container) files
                perf   Measure the performance of a Kudu cluster
      remote_replica   Operate on remote tablet replicas on a Kudu Tablet Server
               table   Operate on Kudu tables
              tablet   Operate on remote Kudu tablets
                test   Various test actions
             tserver   Operate on a Kudu Tablet Server
                 wal   Operate on WAL (write-ahead log) files
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >kudu命令行工具不提供DDL、DML等操作，但提供针对cluster、master、tserver、fs、table等的细化查询功能。

    **常用操作：**

    -   查看当前集群下有哪些表。

        **./kudu table list  _KuduMaster实例IP1:7051, KuduMaster实例IP2:7051, KuduMaster实例IP3:7051_**

    -   查询Kudu服务KuduMaster实例的配置信息。

        **./kudu master get\_flags  _KuduMaster实例IP:7051_**

    -   查询表的schema。

        **./kudu table describe  _KuduMaster实例IP1:7051, KuduMaster实例IP2:7051, KuduMaster实例IP3:7051_ _tablename_**

    -   删除表。

        **./kudu table delete  _KuduMaster实例IP1:7051, KuduMaster实例IP2:7051, KuduMaster实例IP3:7051_ _tablename_**

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >KuduMaster实例IP获取方式：在集群详情页面，选择“组件管理 \> Kudu \> 实例”，获取角色KuduMaster的IP地址。



