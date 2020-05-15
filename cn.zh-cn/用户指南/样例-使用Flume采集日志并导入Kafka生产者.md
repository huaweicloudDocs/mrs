# 样例：使用Flume采集日志并导入Kafka生产者<a name="ZH-CN_TOPIC_0173179068"></a>

## 操作场景<a name="s6020f8e1de5644d2becca6a1c9dd7b98"></a>

Flume支持将采集的日志信息导入到Kafka。

## 前提条件<a name="sdd14a34b7dc44c2ab9cabb19599a033a"></a>

-   已创建启用Kerberos认证的流集群。
-   已在日志生成节点安装Flume客户端，请参见[安装Flume客户端](安装Flume客户端.md)。
-   已配置网络，使日志生成节点与流集群互通。

## 操作步骤<a name="s1f8b9b2a99104941860eb2956cc0057c"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>普通集群不需要执行步骤1-6，直接从步骤7开始即可。  

1.  将Master1节点上的认证服务器配置文件，复制到安装Flume客户端的节点，保存到Flume客户端中“Flume客户端安装目录/fusioninsight-flume-1.6.0/conf“目录。
    -   针对MRS 1.8.0之前版本，文件完整路径为“/opt/Bigdata/FusionInsight/etc/1\_X\_KerberosClient/kdc.conf“
    -   针对MRS 1.8.5及之后版本，文件完整路径为“/opt/Bigdata/MRS\_Current/1\_X\_KerberosClient/etc/kdc.conf“

        其中“XXX“为MRS版本号，“X“为随机生成的数字，请根据实际情况修改。同时文件需要以Flume客户端安装用户身份保存，例如**root**用户。

2.  登录MRS管理控制台，单击集群名称进入集群详情页，选择“组件管理 \> Flume \> 实例”，查看任一部署Flume角色节点的“业务IP地址“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理  \>  Flume  \>  实例“，查看任一部署Flume角色节点的“业务IP地址“。  

3.  将此节点上的用户认证文件，复制到安装Flume客户端的节点，保存到Flume客户端中“Flume客户端安装目录/fusioninsight-flume-1.6.0/conf“目录。
    -   针对MRS 1.8.0之前版本，文件完整路径为“/opt/Bigdata/FusionInsight/FusionInsight-Flume-1.6.0/flume/conf/flume.keytab“
    -   针对MRS 1.8.5及之后版本，文件完整路径为“/opt/Bigdata/MRS\_XXX/install/FusionInsight-Flume-1.6.0/flume/conf/flume.keytab“

        其中“XXX“为MRS版本号，请根据实际情况修改。同时文件需要以Flume客户端安装用户身份保存，例如**root**用户。

4.  将此节点上的配置文件“jaas.conf“，复制到安装Flume客户端的节点，保存到Flume客户端中“conf“目录。
    -   针对MRS 1.8.0之前版本，文件完整路径为“/opt/Bigdata/FusionInsight/etc/1\_X\_Flume/jaas.conf“
    -   针对MRS 1.8.5及之后版本，文件完整路径为“/opt/Bigdata/MRS\_Current/1\_X\_Flume/etc/jaas.conf“

        其中“XXX“为MRS版本号，“X“为随机生成的数字，请根据实际情况修改。同时文件需要以Flume客户端安装用户身份保存，例如**root**用户。

5.  登录安装Flume客户端节点，切换到客户端安装目录，执行以下命令修改文件：

    **vi conf/jaas.conf**

    修改参数“keyTab“定义的用户认证文件完整路径即步骤3中保存用户认证文件的目录：“Flume客户端安装目录/fusioninsight-flume-1.6.0/conf“目录，然后保存并退出。

6.  执行以下命令，修改Flume客户端配置文件“flume-env.sh“：

    **vi  _Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/flume-env.sh**

    在“-XX:+UseCMSCompactAtFullCollection“后面，增加以下内容：

    ```
    -Djava.security.krb5.conf=Flume客户端安装目录/fusioninsight-flume-1.6.0/conf/kdc.conf -Djava.security.auth.login.config=Flume客户端安装目录/fusioninsight-flume-1.6.0/conf/jaas.conf -Dzookeeper.request.timeout=120000
    ```

    例如：**"-XX:+UseCMSCompactAtFullCollection -Djava.security.krb5.conf=_Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/kdc.conf -Djava.security.auth.login.config=_Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/jaas.conf -Dzookeeper.request.timeout=120000"**

    请根据实际情况，修改“Flume客户端安装目录“，然后保存并退出。

7.  假设Flume客户端安装路径为“/opt/FlumeClient“，执行以下命令，重启Flume客户端：

    **cd /opt/FlumeClient/fusioninsight-flume-1.6.0/bin**

    **./flume-manage.sh restart**

8.  执行以下命令，修改Flume客户端配置文件“properties.properties“。

    **vi  _Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/properties.properties**

    将以下内容保存到文件中：

    ```
    #########################################################################################
    client.sources = static_log_source  
    client.channels = static_log_channel 
    client.sinks = kafka_sink
    #########################################################################################
    #LOG_TO_HDFS_ONLINE_1
    
    client.sources.static_log_source.type = spooldir
    client.sources.static_log_source.spoolDir = PATH
    client.sources.static_log_source.fileSuffix = .COMPLETED
    client.sources.static_log_source.ignorePattern = ^$
    client.sources.static_log_source.trackerDir = PATH
    client.sources.static_log_source.maxBlobLength = 16384
    client.sources.static_log_source.batchSize = 51200
    client.sources.static_log_source.inputCharset = UTF-8
    client.sources.static_log_source.deserializer = LINE
    client.sources.static_log_source.selector.type = replicating
    client.sources.static_log_source.fileHeaderKey = file
    client.sources.static_log_source.fileHeader = false
    client.sources.static_log_source.basenameHeader = true
    client.sources.static_log_source.basenameHeaderKey = basename
    client.sources.static_log_source.deletePolicy = never
    
    client.channels.static_log_channel.type = file
    client.channels.static_log_channel.dataDirs = PATH
    client.channels.static_log_channel.checkpointDir = PATH
    client.channels.static_log_channel.maxFileSize = 2146435071
    client.channels.static_log_channel.capacity = 1000000
    client.channels.static_log_channel.transactionCapacity = 612000
    client.channels.static_log_channel.minimumRequiredSpace = 524288000
    
    client.sinks.kafka_sink.type = org.apache.flume.sink.kafka.KafkaSink
    client.sinks.kafka_sink.kafka.topic = flume_test
    client.sinks.kafka_sink.kafka.bootstrap.servers = XXX.XXX.XXX.XXX:21007,XXX.XXX.XXX.XXX:21007,XXX.XXX.XXX.XXX:21007
    client.sinks.kafka_sink.flumeBatchSize = 1000
    client.sinks.kafka_sink.kafka.producer.type = sync
    client.sinks.kafka_sink.kafka.security.protocol  = SASL_PLAINTEXT
    client.sinks.kafka_sink.kafka.kerberos.domain.name = hadoop.XXX.com
    client.sinks.kafka_sink.requiredAcks = 0
    
    client.sources.static_log_source.channels = static_log_channel
    client.sinks.kafka_sink.channel = static_log_channel
    ```

    请根据实际情况，修改以下参数，然后保存并退出。

    -   spoolDir
    -   trackerDir
    -   dataDirs
    -   checkpointDir
    -   topic

        如果kafka中该topic不存在，默认情况下会自动创建该topic。

    -   kafka.bootstrap.servers

        默认情况下，安全集群对应端口21007，普通集群对应端口9092。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >MRS 1.6.2及以下版本，普通集群对应端口21005.详见[开源组件端口列表](开源组件端口列表.md)  

    -   kafka.security.protocol

        安全集群请配置为SASL\_PLAINTEXT，普通集群请配置为PLAINTEXT。

    -   “kafka.kerberos.domain.name“

        普通集群无需配置此参数。安全集群对应此参数的值为Kafka集群中“kerberos.domain.name”对应的值。

        -   针对MRS 1.8.0之前版本，具体可到Borker实例所在节点上查看“/opt/Bigdata/FusionInsight/etc/1\_8X\_Broker/server.properties“
        -   针对MRS 1.8.5及之后版本，具体可到Borker实例所在节点上查看“/opt/Bigdata/MRS\_Current/1\_X\_Broker/etc/server.properties“

            其中“XXX“为MRS版本号，“X“为随机生成的数字，请根据实际情况修改。同时文件需要以Flume客户端安装用户身份保存，例如**root**用户。


9.  Flume客户端将自动加载“properties.properties“的内容。

    当“spoolDir“生成新的日志文件，文件内容将发送到Kafka生产者，并支持Kafka消费者消费。


