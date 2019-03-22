# 对接OBS<a name="ZH-CN_TOPIC_0133461181"></a>

本章节提供MRS访问OBS的方法指导。

## Spark访问OBS<a name="section23291801617"></a>

-   通过Spark应用访问OBS。

    访问之前需要在spark客户端配置文件core-site.xml中添加“fs.s3a.access.key”和“fs.s3a.secret.key”，core-site.xml文件默认路径为：/opt/client/Spark/spark/conf/core-site.xml。

    >![](public_sys-resources/icon-notice.gif) **注意：**   
    >在文件中设置ak、sk会明文暴露在配置文件中，请谨慎使用。  

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


-   在spark-sql和spark-beeline中访问OBS。

    如果需要在spark-sql和spark-beeline中访问OBS，需要手动执行如下命令设置AK，SK。

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

-   通过命令行手动输入ak、sk访问。

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

    >![](public_sys-resources/icon-notice.gif) **注意：**   
    >在文件中设置ak、sk会明文暴露在配置文件中，请谨慎使用。  

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

