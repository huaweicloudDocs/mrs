# Hive元数据<a name="mrs_01_0446"></a>

## Hive元数据备份<a name="section1744543016545"></a>

Hive表数据存储在HDFS上，表数据及表数据的元数据由HDFS统一按数据目录进行迁移。而Hive表的元数据根据集群的不同配置，可以存储在不同类型的关系型数据库中（如MySQL，PostgreSQL，Oracle等）。本指导导出的Hive表元数据即存储在关系型数据库中的Hive表的描述信息。

业界主流大数据发行版均支持Sqoop的安装，如果是自建的社区版大数据集群，可下载社区版Sqoop进行安装。借助Sqoop来解耦导出的元数据与关系型数据库的强依赖，将Hive元数据导出到HDFS上，与表数据一同迁移后进行恢复。步骤如下：

1.  在源集群上下载并安装Sqoop工具。请参见[http://sqoop.apache.org/](http://sqoop.apache.org/)。
2.  下载相应关系型数据库的jdbc驱动放置到$Sqoop\_Home/lib目录。
3.  执行如下命令导出所有Hive元数据表。所有导出数据保存在HDFS上的/user/<_user\_name_\>/<_table\_name_\>目录。

    ```
    $Sqoop_Home/bin/sqoop import --connect jdbc:<driver_type>://<ip>:<port>/<database> --table <table_name> --username <user> -password <passwd> -m 1
    ```

    其中，各参数的含义如下。

    -   _$Sqoop\_Home_：Sqoop的安装目录
    -   <_driver\_type_\>：数据库类型
    -   <_ip\>_：源集群数据库的IP地址
    -   <_port\>：_源集群数据库的端口号
    -   <_table\_name_\>：待导出的表名称
    -   <_user_\>：用户名
    -   <_passwd_\>：用户密码


## Hive元数据恢复<a name="section14357913301"></a>

在目的集群中安装并使用Sqoop命令将导出的Hive元数据导入MRS集群DBService。

```
$Sqoop_Home/bin/sqoop export --connect jdbc:postgresql://<ip>:20051/hivemeta --table <table_name> --username hive -password <passwd> --export-dir <export_from>
```

其中，各参数的含义如下。

-   _$Sqoop\_Home_：目的集群上Sqoop的安装目录
-   <_ip\>_：目的集群上数据库的IP地址
-   <_table\_name_\>：待恢复的表名称
-   <_passwd_\>：hive用户的密码
-   <_export\_from_\>：元数据在目的集群的HDFS地址。

