# 样例：使用Flume监控OBS目录并上传文件到HDFS<a name="ZH-CN_TOPIC_0076492296"></a>

## 操作场景<a name="zh-cn_topic_0076120434_section13507962172159"></a>

Flume监控指定OBS目录，并将文件上传到HDFS。

## 前提条件<a name="zh-cn_topic_0076120434_section23899914172238"></a>

-   已创建流集群。
-   已在客户端节点安装Flume客户端，请参见[安装Flume客户端](安装Flume客户端.md#ZH-CN_TOPIC_0069282319)。
-   已配置网络，使客户端节点与流集群互通；且与HDFS集群节点互通，包括master节点和core节点。
-   客户端节点可解析OBS服务域名。

## 操作步骤<a name="zh-cn_topic_0076120434_section13552161172344"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>非安全集群不需要执行步骤2-4。  

1.  从HDFS集群客户端拷贝**core-site.xml**、**hdfs-site.xml**文件到Flume客户端节点，“Flume客户端安装目录/fusioninsight-flume-1.6.0/conf“目录中，并在Manager界面上的Flume服务配置中上传这两个文件。

    通常可以在HDFS客户端安装目录“/HDFS/hadoop/etc/hadoop/“下找到**core-site.xml**、**hdfs-site.xml**文件。

    文件需要以Flume客户端安装用户身份保存，例如**root**用户。

2.  <a name="zh-cn_topic_0076120434_li25330219174848"></a>从HDFS集群下载用户的认证凭据。
    1.  在MRS Manager，单击“系统设置“。
    2.  在“权限配置“区域，单击“用户管理“。
    3.  在用户列表中选择需要的用户，单击后面的“更多--“下载用户凭据。
    4.  解压下载的用户凭据文件，获取**krb5.conf**和**user.keytab**文件。

3.  将[上一步](#zh-cn_topic_0076120434_li25330219174848)获得的**krb5.conf**和**user.keytab**拷贝到Flume客户端节点的“Flume客户端安装目录/fusioninsight-flume-1.6.0/conf“目录中。文件需要以Flume客户端安装用户身份保存，例如**root**用户。
4.  修改Flume客户端配置文件“flume-env.sh“。

    执行以下命令，编辑配置文件“flume-env.sh“。

    **vi  _Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/flume-env.sh**

    在“-XX:+UseCMSCompactAtFullCollection“后面，增加以下内容：

    ```
    -Djava.security.krb5.conf=Flume客户端安装目录/fusioninsight-flume-1.6.0/conf/krb5.conf 
    ```

    请根据实际情况，修改“Flume客户端安装目录“，然后保存并退出配置文件。

5.  将HDFS集群的“/etc/hosts“文件中**host**匹配相关内容添加到Flume客户端节点的“/etc/hosts“文件。
6.  重启Flume客户端。

    假设Flume客户端安装路径为“/opt/FlumeClient“，请执行以下命令，重启Flume客户端：

    **cd /opt/FlumeClient/fusioninsight-flume-1.6.0/bin**

    **./flume-manage.sh restart**

7.  使用Flume客户端加密工具加密SK，详细操作请参见[使用Flume客户端加密工具](使用Flume客户端加密工具.md#ZH-CN_TOPIC_0069282320)。
8.  执行以下命令，修改Flume客户端配置文件“properties.properties“。

    **vi  _Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/properties.properties**

    将以下内容保存到文件“properties.properties“中：

    ```
    client.sources = obs
    client.channels = flume
    client.sinks = hdfs
    
    client.sources.obs.type=org.apache.flume.source.s3.OBSSource
    client.sources.obs.bucketName = obs-nemon-sink
    client.sources.obs.prefix = obs-source/
    client.sources.obs.accessKey = AK 
    client.sources.obs.secretKey = SK 
    client.sources.obs.backingDir = /tmp/obs/
    client.sources.obs.endPoint = obs.eu-de.huawei.com
    client.sources.obs.basenameHeader = true
    client.sources.obs.basenameHeaderKey = basename
    client.sources.obs.channels = flume 
    
    client.channels.flume.type = memory
    client.channels.flume.capacity = 10000
    client.channels.flume.transactionCapacity = 1000
    client.channels.flume.channelfullcount = 10
    client.channels.flume.keep-alive = 3
    client.channels.flume.byteCapacity = 
    client.channels.flume.byteCapacityBufferPercentage = 20
    
    
    client.sinks.hdfs.type = hdfs
    client.sinks.hdfs.hdfs.path = hdfs://hacluster/tmp
    client.sinks.hdfs.montime = 
    client.sinks.hdfs.hdfs.filePrefix = over_%{basename}
    client.sinks.hdfs.hdfs.fileSuffix = 
    client.sinks.hdfs.hdfs.inUsePrefix = 
    client.sinks.hdfs.hdfs.inUseSuffix = .tmp
    client.sinks.hdfs.hdfs.idleTimeout = 0
    client.sinks.hdfs.hdfs.batchSize = 1000
    client.sinks.hdfs.hdfs.codeC =  
    client.sinks.hdfs.hdfs.fileType = DataStream
    client.sinks.hdfs.hdfs.maxOpenFiles = 5000
    client.sinks.hdfs.hdfs.writeFormat = Writable
    client.sinks.hdfs.hdfs.callTimeout = 10000
    client.sinks.hdfs.hdfs.threadsPoolSize = 10
    client.sinks.hdfs.hdfs.rollTimerPoolSize = 1
    client.sinks.hdfs.hdfs.kerberosPrincipal = admin
    client.sinks.hdfs.hdfs.kerberosKeytab = /opt/FlumeClient/fusioninsight-flume-1.6.0/conf/user.keytab
    client.sinks.hdfs.hdfs.round = false
    client.sinks.hdfs.hdfs.roundUnit = second
    client.sinks.hdfs.hdfs.useLocalTimeStamp = false
    client.sinks.hdfs.hdfs.failcount = 10
    client.sinks.hdfs.hdfs.fileCloseByEndEvent = true
    client.sinks.hdfs.hdfs.rollInterval = 30
    client.sinks.hdfs.hdfs.rollSize = 1024
    client.sinks.hdfs.hdfs.rollCount = 10
    client.sinks.hdfs.hdfs.batchCallTimeout = 0
    client.sinks.hdfs.serializer.appendNewline = true
    client.sinks.hdfs.channel = flume 
    ```

    请根据实际情况，修改以下参数，然后保存并退出。

    -   “bucketName“
    -   “prefix“
    -   “backingDir“
    -   “endPoint“
    -   “accessKey“

        AK值。需要替换成实际值。

    -   “sercretKey“

        SK值。需要替换成实际值，SK是加密后的。

    -   “kerberosPrincipal“

        安全集群需要配置，用户名

    -   “kerberosKeytab“

        安全集群需要配置，用户认证文件，需要写绝对路径。


9.  Flume客户端将自动加载“properties.properties“的内容。

    当“bucketName“下的“prefix“目录生成新的日志文件，文件内容将发送到OBS。


