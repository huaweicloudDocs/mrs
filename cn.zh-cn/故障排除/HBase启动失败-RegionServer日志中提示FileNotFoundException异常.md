# HBase启动失败，RegionServer日志中提示FileNotFoundException异常<a name="mrs_03_0117"></a>

## 问题背景<a name="zh-cn_topic_0167276046_sf76e408f8ea44020bf3de33c280bc079"></a>

HBase启动失败，RegionServer一直处于Restoring状态。

## 原因分析<a name="zh-cn_topic_0167276046_s2d857902554344b38f9d1ff9130b2ce3"></a>

1.  查看RegionServer的日志（/var/log/Bigdata/hbase/rs/hbase-omm-XXX.log），发现显示以下打印信息：

    ```
     | ERROR | RS_OPEN_REGION-ab-dn01:21302-2 | ABORTING region server ab-dn01,21302,1487663269375: The coprocessor org.apache.kylin.storage.hbase.cube.v2.coprocessor.endpoint.CubeVisitService threw java.io.FileNotFoundException: File does not exist: hdfs://hacluster/kylin/kylin_metadata/coprocessor/kylin-coprocessor-1.6.0-SNAPSHOT-0.jar | org.apache.hadoop.hbase.regionserver.HRegionServer.abort(HRegionServer.java:2123)
    java.io.FileNotFoundException: File does not exist: hdfs://hacluster/kylin/kylin_metadata/coprocessor/kylin-coprocessor-1.6.0-SNAPSHOT-0.jar
    at org.apache.hadoop.hdfs.DistributedFileSystem$25.doCall(DistributedFileSystem.java:1399)
    at org.apache.hadoop.hdfs.DistributedFileSystem$25.doCall(DistributedFileSystem.java:1391)
    at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
    at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1391)
    at org.apache.hadoop.fs.FileUtil.copy(FileUtil.java:340)
    at org.apache.hadoop.fs.FileUtil.copy(FileUtil.java:292)
    at org.apache.hadoop.fs.FileSystem.copyToLocalFile(FileSystem.java:2038)
    at org.apache.hadoop.fs.FileSystem.copyToLocalFile(FileSystem.java:2007)
    at org.apache.hadoop.fs.FileSystem.copyToLocalFile(FileSystem.java:1983)
    at org.apache.hadoop.hbase.util.CoprocessorClassLoader.init(CoprocessorClassLoader.java:168)
    at org.apache.hadoop.hbase.util.CoprocessorClassLoader.getClassLoader(CoprocessorClassLoader.java:250)
    at org.apache.hadoop.hbase.coprocessor.CoprocessorHost.load(CoprocessorHost.java:224)
    at org.apache.hadoop.hbase.regionserver.RegionCoprocessorHost.loadTableCoprocessors(RegionCoprocessorHost.java:365)
    at org.apache.hadoop.hbase.regionserver.RegionCoprocessorHost.<init>(RegionCoprocessorHost.java:227)
    at org.apache.hadoop.hbase.regionserver.HRegion.<init>(HRegion.java:783)
    at org.apache.hadoop.hbase.regionserver.HRegion.<init>(HRegion.java:689)
    at sun.reflect.GeneratedConstructorAccessor22.newInstance(Unknown Source)
    at sun.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
    at java.lang.reflect.Constructor.newInstance(Constructor.java:423)
    at org.apache.hadoop.hbase.regionserver.HRegion.newHRegion(HRegion.java:6312)
    at org.apache.hadoop.hbase.regionserver.HRegion.openHRegion(HRegion.java:6622)
    at org.apache.hadoop.hbase.regionserver.HRegion.openHRegion(HRegion.java:6594)
    at org.apache.hadoop.hbase.regionserver.HRegion.openHRegion(HRegion.java:6550)
    at org.apache.hadoop.hbase.regionserver.HRegion.openHRegion(HRegion.java:6501)
    at org.apache.hadoop.hbase.regionserver.handler.OpenRegionHandler.openRegion(OpenRegionHandler.java:363)
    at org.apache.hadoop.hbase.regionserver.handler.OpenRegionHandler.process(OpenRegionHandler.java:129)
    at org.apache.hadoop.hbase.executor.EventHandler.run(EventHandler.java:129)
    at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
    at java.lang.Thread.run(Thread.java:745)
    ```

2.  使用客户端hdfs命令查看，如下文件不存在。

    hdfs://hacluster/kylin/kylin\_metadata/coprocessor/kylin-coprocessor-1.6.0-SNAPSHOT-0.jar

3.  HBase在配置协处理器时，一定要保证对应的jar包路径没有问题，否则HBase会无法启动。

## 解决办法<a name="zh-cn_topic_0167276046_sed4194588b214662be5341d4a1f9ecbd"></a>

使用Kylin对接MRS，确保Kylin相关jar包存在。

