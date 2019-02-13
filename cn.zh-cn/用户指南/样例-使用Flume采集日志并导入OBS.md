# 样例：使用Flume采集日志并导入OBS<a name="ZH-CN_TOPIC_0076492295"></a>

## 操作场景<a name="zh-cn_topic_0076109470_section13507962172159"></a>

Flume支持将采集的日志信息导入到OBS。

## 前提条件<a name="zh-cn_topic_0076109470_section23899914172238"></a>

-   已创建流集群。
-   已在日志生成节点安装Flume客户端，请参见[安装Flume客户端](安装Flume客户端.md#ZH-CN_TOPIC_0069282319)。
-   已配置网络，使日志生成节点与流集群互通。
-   日志节点可解析OBS服务域名。具体请参见[在虚拟私有云的其他节点使用客户端](在虚拟私有云的其他节点使用客户端.md)。

## 操作步骤<a name="zh-cn_topic_0076109470_section13552161172344"></a>

1.  创建core-site.xml文件，保存到Flume客户端的“conf”目录中。

    参数文件内容示例：

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <configuration>
    <property>
    <name>fs.s3a.connection.ssl.enabled</name>
    <value>true</value>
    </property>
    <property>
    <name>fs.s3a.endpoint</name>
    <value></value>
    </property>
    </configuration>
    ```

    “fs.s3a.endpoint”的值为OBS访问地址，需要和MRS在相同的Region，可能是域名或者IP地址形式。可以通过访问MRS Manager，选择“服务管理 \> Flume \> 服务配置”，参数类别选择“全部配置”，在“S3service”中查看“s3service.s3-endpoint”的值。

2.  使用Flume客户端加密工具加密SK，详细步骤请参考[使用Flume客户端加密工具](使用Flume客户端加密工具.md#ZH-CN_TOPIC_0069282320)。
3.  执行以下命令，修改Flume客户端配置文件“properties.properties“。

    **vi  _Flume客户端安装目录_/fusioninsight-flume-1.6.0/conf/properties.properties**

    将以下内容添加并保存到文件中：

    ```
    client.sources = linux
    client.channels = flume
    client.sinks = obs
    
    client.sources.linux.type = spooldir
    client.sources.linux.spoolDir = /tmp/nemon
    client.sources.linux.montime = 
    client.sources.linux.fileSuffix = .COMPLETED
    client.sources.linux.deletePolicy = never
    client.sources.linux.trackerDir = .flumespool
    client.sources.linux.ignorePattern = ^$
    client.sources.linux.batchSize = 1000
    client.sources.linux.inputCharset = UTF-8
    client.sources.linux.selector.type = replicating
    client.sources.linux.fileHeader = false
    client.sources.linux.fileHeaderKey = file
    client.sources.linux.basenameHeader = true
    client.sources.linux.basenameHeaderKey = basename
    client.sources.linux.deserializer = LINE
    client.sources.linux.deserializer.maxBatchLine = 1
    client.sources.linux.deserializer.maxLineLength = 2048
    client.sources.linux.channels = flume
    
    client.channels.flume.type = memory
    client.channels.flume.capacity = 10000
    client.channels.flume.transactionCapacity = 1000
    client.channels.flume.channelfullcount = 10
    client.channels.flume.keep-alive = 3
    client.channels.flume.byteCapacity = 
    client.channels.flume.byteCapacityBufferPercentage = 20
    
    client.sinks.obs.type = hdfs
    client.sinks.obs.hdfs.path = s3a://AK:SK@obs-nemon-sink/obs-sink
    client.sinks.obs.montime = 
    client.sinks.obs.hdfs.filePrefix = obs_%{basename}
    client.sinks.obs.hdfs.fileSuffix = 
    client.sinks.obs.hdfs.inUsePrefix = 
    client.sinks.obs.hdfs.inUseSuffix = .tmp
    client.sinks.obs.hdfs.idleTimeout = 0
    client.sinks.obs.hdfs.batchSize = 1000
    client.sinks.obs.hdfs.codeC =  
    client.sinks.obs.hdfs.fileType = DataStream
    client.sinks.obs.hdfs.maxOpenFiles = 5000
    client.sinks.obs.hdfs.writeFormat = Writable
    client.sinks.obs.hdfs.callTimeout = 1000000
    client.sinks.obs.hdfs.threadsPoolSize = 10
    client.sinks.obs.hdfs.rollTimerPoolSize = 1
    client.sinks.obs.hdfs.round = false
    client.sinks.obs.hdfs.roundUnit = second
    client.sinks.obs.hdfs.useLocalTimeStamp = false
    client.sinks.obs.hdfs.failcount = 10
    client.sinks.obs.hdfs.fileCloseByEndEvent = true
    client.sinks.obs.hdfs.rollInterval = 30
    client.sinks.obs.hdfs.rollSize = 1024
    client.sinks.obs.hdfs.rollCount = 10
    client.sinks.obs.hdfs.batchCallTimeout = 0
    client.sinks.obs.serializer.appendNewline = true
    client.sinks.obs.channel = flume 
    ```

    请根据实际情况，修改以下参数，然后保存并退出。

    -   “spoolDir“
    -   “trackerDir“
    -   “hdfs.path“，其中的AK和SK需要替换成实际值，SK是加密后的内容。obs-nemon-sink为OBS桶名，obs-sink为文件名。

4.  Flume客户端将自动加载“properties.properties“的内容。

    当“spoolDir“生成新的日志文件，文件内容将发送到OBS。


