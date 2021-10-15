# Flume对接OBS文件系统<a name="mrs_01_24279"></a>

本章节适用于MRS 3.x及之后的版本。

1.  配置委托。
    1.  登录MRS控制台，在左侧导航栏选择“集群列表\> 现有集群”。
    2.  单击集群名称，进入集群详情页面。
    3.  在集群详情页的“概览”页签，单击“IAM用户同步”右侧的“单击同步”进行IAM用户同步。
    4.  单击委托右侧的“管理委托”，选择需要绑定的委托并单击“确定”进行绑定。

2.  <a name="li3279721151214"></a>创建OBS文件系统用于存放数据。
    1.  登录OBS控制台。
    2.  单击“并行文件系统”进入并行文件系统页面，单击“创建并行文件系统”。
    3.  填写文件系统名称，例如“esdk-c-test-pfs1”，其他参数请根据需要填写。单击“立即创建”等待创建完成。
    4.  在OBS控制台并行文件系统列表中，单击已新建的文件系统名称进入详情页面。
    5.  在左侧导航栏单击“文件”，单击“新建文件夹”新建testFlumeOutput文件夹。

3.  准备properties.properties文件并将上传至“/opt/flumeInput”目录。
    1.  <a name="li192551317183716"></a>在本地准备properties.properties文件，文件内容如下：

        ```
        # source
        server.sources = r1
        # channels
        server.channels = c1
        # sink
        server.sinks = obs_sink
        # ----- define net source -----
        server.sources.r1.type = seq
        server.sources.r1.spooldir = /opt/flumeInput
        # ---- defind OBS sink ----
        server.sinks.obs_sink.type = hdfs
        server.sinks.obs_sink.hdfs.path = obs://esdk-c-test-pfs1/testFlumeOutput
        server.sinks.obs_sink.hdfs.filePrefix = %[localhost]
        server.sinks.obs_sink.hdfs.useLocalTimeStamp = true
        # set file size to trigger roll
        server.sinks.obs_sink.hdfs.rollSize = 0
        server.sinks.obs_sink.hdfs.rollCount = 0
        server.sinks.obs_sink.hdfs.rollInterval = 5
        #server.sinks.obs_sink.hdfs.threadsPoolSize = 30
        server.sinks.obs_sink.hdfs.fileType = DataStream
        server.sinks.obs_sink.hdfs.writeFormat = Text
        server.sinks.obs_sink.hdfs.fileCloseByEndEvent = false
        
        # define channel
        server.channels.c1.type = memory
        server.channels.c1.capacity = 1000
        # transaction size
        server.channels.c1.transactionCapacity = 1000
        server.channels.c1.byteCapacity = 800000
        server.channels.c1.byteCapacityBufferPercentage = 20
        server.channels.c1.keep-alive = 60
        server.sources.r1.channels = c1
        server.sinks.obs_sink.channel = c1
        ```

    2.  使用**root**用户登录安装Flume客户端的节点。
    3.  新建“/opt/flumeInput”目录，并在该目录下新建一个内容自定义的txt文件。
    4.  登录FusionInsight Manager。
    5.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> Flume \> 配置”，在参数“flume.config.file”的“值”中单击“上传文件”，上传[3.a](#li192551317183716)准备的properties.properties文件，单击“保存”。

4.  在OBS系统中查看结果。
    1.  登录OBS控制台。
    2.  单击“并行文件系统”，进入[2](#li3279721151214)中创建的并行文件系统中的文件夹查看结果。


