# s3a方式访问OBS<a name="ZH-CN_TOPIC_0173178868"></a>

本章节提供MRS使用原生s3方式访问OBS的方法指导。

## Spark访问OBS<a name="section23291801617"></a>

-   通过Spark应用访问OBS。

    访问之前需要在spark客户端配置文件core-site.xml中添加“fs.s3a.access.key”和“fs.s3a.secret.key”，core-site.xml文件默认路径为：/opt/client/Spark/spark/conf/core-site.xml。

    >![](public_sys-resources/icon-notice.gif) **须知：**   
    >在文件中设置AK/SK会明文暴露在配置文件中，请谨慎使用。AK和SK获取方法请参见[AK/SK认证](https://support.huaweicloud.com/api-mrs/mrs_02_0009.html)。  

    ```
    <property>
        <name>fs.s3a.access.key</name>
        <value>ak</value>
    </property>
    <property>
        <name>fs.s3a.secret.key</name>
        <value>sk</value>
    </property>
    ```

    访问OBS的url如下，其中s3a为前缀，obs-mrsdemo为桶名。

    ```
    s3a://obs-mrsdemo/input/NEWS.txt
    ```


-   在spark-sql和spark-beeline中访问OBS。

    如果需要在spark-sql和spark-beeline中访问OBS，需要手动执行如下命令设置AK/SK。

    ```
    set fs.s3a.access.key=ak;
    set fs.s3a.secret.key=sk;
    ```

    示例：

    ```
    0: jdbc:hive2://ha-cluster/default> set fs.s3a.access.key=xxxxxxxxxxx;
    1 row selected (1.322 seconds)
    0: jdbc:hive2://ha-cluster/default> set fs.s3a.secret.key=xxxxxxxxxxxxxxxxxxxxx;
    1 row selected (0.083 seconds)
    0: jdbc:hive2://ha-cluster/default> create table test(id int) location 's3a://obs-demo-input/table/';
    +---------+--+
    | Result  |
    +---------+--+
    +---------+--+
    No rows selected (1.816 seconds)
    ```


## HDFS访问OBS<a name="section178178171469"></a>

-   通过命令行手动输入AK/SK访问。

    ```
    hadoop fs -Dfs.s3a.access.key=ak -Dfs.s3a.secret.key=sk -ls "s3a://obs-bucket"
    ```

-   修改HDFS客户端配置文件core-site.xml，添加“fs.s3a.access.key”和“fs.s3a.secret.key”，core-site.xml文件默认客户端路径为：/opt/client/HDFS/hadoop/etc/hadoop/core-site.xml。

    ```
    <property>
        <name>fs.s3a.access.key</name>
        <value>ak</value>
    </property>
    <property>
        <name>fs.s3a.secret.key</name>
        <value>sk</value>
    </property>
    ```

    >![](public_sys-resources/icon-notice.gif) **须知：**   
    >在文件中设置AK/SK会明文暴露在配置文件中，请谨慎使用。AK和SK获取方法请参见[AK/SK认证](https://support.huaweicloud.com/api-mrs/mrs_02_0009.html)。  

    添加配置后无需手动添加ak、sk即可访问OBS。

    ```
     hadoop fs -ls "s3a://obs-bucket"
    ```


## Hive访问OBS<a name="section989576583"></a>

在hive beeline里面手动设置以下参数即可访问OBS。

```
set fs.s3a.access.key=ak;
set fs.s3a.secret.key=sk;
set metaconf:fs.s3a.access.key=ak;
set metaconf:fs.s3a.secret.key=sk;
```

示例：

```
0: jdbc:hive2://10.10.10.10:10000/> set fs.s3a.access.key=xxxxxxxxxxxxxxxx;
No rows affected (0.015 seconds)
0: jdbc:hive2://10.10.10.10:10000/> set fs.s3a.secret.key=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx;
No rows affected (0.017 seconds)
0: jdbc:hive2://10.10.10.10:10000/> set metaconf:fs.s3a.access.key=xxxxxxxxxxxxxxxx;
No rows affected (0.019 seconds)
0: jdbc:hive2://10.10.10.10:10000/> set metaconf:fs.s3a.secret.key=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx;
No rows affected (0.003 seconds)
0: jdbc:hive2://10.10.10.10:10000/> create table aa(id string)location 's3a://obs-demo-input/table/';
No rows affected (1.024 seconds)
```

>![](public_sys-resources/icon-note.gif) **说明：**   
>当前Hive使用OBS存储时，同一张表中，不支持分区和表存储位置处于不同的桶中。  
>例如：创建分区表指定存储位置为OBS桶1下的文件夹，此时修改表分区存储位置的操作将不会生效，在实际插入数据时以表存储位置为准。  
>1.  创建分区表并指定表存储路径。  
>    ```  
>    create table table_name(id int,name string,company string) partitioned by(dt date) row format delimited fields terminated by ',' stored as textfile location "obs://OBS桶1/桶下文件夹";  
>    ```  
>2.  修改此表分区位置到另外一个桶下，此时该修改不会生效。  
>    ```  
>    alter table table_name partition(dt date) set location "obs://OBS桶2/桶下文件夹";  
>    ```  

## Presto访问OBS<a name="section1842192119379"></a>

1.  登录集群详情页面，选择“组件管理 \> Presto \> 服务配置”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理 \> Presto \> 服务配置”。  

2.  参数类别设置为“全部配置”。
3.  搜索并配置如下参数。
    -   hive.s3.aws-access-key配置为用户ak
    -   hive.s3.aws-secret-key配置为用户sk
    -   hive.s3.endpoint配置为OBS桶的Endpoint

4.  搜索core.site.customized.configs参数，添加自定义参数：
    -   fs.s3a.access.key配置为用户ak
    -   fs.s3a.secret.key配置为用户sk

5.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Presto服务。
6.  选择“组件管理 \> Hive \> 服务配置”。
7.  参数类别设置为“全部配置”。
8.  搜索core.site.customized.configs参数，添加自定义参数：
    -   fs.s3a.access.key配置为用户ak
    -   fs.s3a.secret.key配置为用户sk
    -   fs.s3a.endpoint配置为OBS桶的Endpoint

9.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。
10. 在Presto客户端中执行语句创建schema，指定location为OBS路径，例如：

    **CREATE SCHEMA hive.demo WITH \(location = 's3a://obs-demo/presto-demo/'\);**

11. 在该schema中建表，该表的数据即存储在OBS桶内，例如：

    **CREATE TABLE hive.demo.demo\_table WITH \(format = 'ORC'\) AS SELECT \* FROM tpch.sf1.customer;**


