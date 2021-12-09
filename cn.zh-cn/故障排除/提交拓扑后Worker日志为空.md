# 提交拓扑后Worker日志为空<a name="mrs_03_0098"></a>

## 现象描述<a name="zh-cn_topic_0167276160_sd2de281c3a2e46329e3c488c1b54fd23"></a>

在Eclipse中远程提交拓扑成功之后，无法在Storm WebUI查看拓扑的详细信息，并且每个拓扑的Bolt和Spout所在Worker节点在一直变化。查看Worker日志，日志内容为空。

## 可能原因<a name="zh-cn_topic_0167276160_s857ea6f1c1e445dab07996a583d322cd"></a>

Worker进程启动失败，触发Nimbus重新分配任务，在其他Supervisor上启动Worker。由于Worker启动失败后会继续重启，导致Worker节点在一直变化，且Worker日志内容为空。Worker进程启动失败的可能原因有两个：

-   提交的Jar包中包含“storm.yaml”文件。

    Storm规定，每个“classpath”中只能包含一个“storm.yaml”文件，如果多于一个那么就会产生异常。使用Storm客户端提交拓扑，由于客户端“classpath”配置和Eclipse远程提交方式“classpath”不一样，客户端会自动加载用户的Jar包到“classpath”，从而使“classpath”中存在两个“storm.yaml”文件。

-   Worker进程初始化时间较长，超过Storm集群设置Worker启动超时时间，导致Worker被Kill从而一直进行重分配。

## 定位思路<a name="zh-cn_topic_0167276160_s08977f806d574ddc92c4b3a9e9f62513"></a>

1.  使用Storm客户端提交拓扑，检查出重复“storm.yaml”问题。
2.  重新打包Jar包，然后再提交拓扑。
3.  修改Storm集群关于Worker启动超时参数。

## 处理步骤<a name="zh-cn_topic_0167276160_sfdd95f4762754714880a6fdff9182355"></a>

1.  使用Eclipse远程提交拓扑后Worker日志为空，则使用Storm客户端，提交拓扑对应的Jar包，查看提示信息。

    例如，Jar包中包含两个不同路径下的“storm.yaml”文件，系统显示以下信息：

    ```
    Exception in thread "main" java.lang.ExceptionInInitializerError 
      at com.huawei.streaming.storm.example.WordCountTopology.createConf(WordCountTopology.java:132) 
      at com.huawei.streaming.storm.example.WordCountTopology.remoteSubmit(WordCountTopology.java:120) 
      at com.huawei.streaming.storm.example.WordCountTopology.main(WordCountTopology.java:101) 
     Caused by: java.lang.RuntimeException: Found multiple storm.yaml resources. You're probably bundling the Storm jars with your topology jar. [jar:file:/opt/huawei/fi_client/Streaming/streaming-0.9.2/bin/stormDemo.jar!/storm.yaml, file:/opt/huawei/fi_client/Streaming/streaming-0.9.2/conf/storm.yaml] 
      at backtype.storm.utils.Utils.findAndReadConfigFile(Utils.java:151) 
      at backtype.storm.utils.Utils.readStormConfig(Utils.java:206) 
      at backtype.storm.utils.Utils.<(Utils.java:70)>
    ```

2.  重新打包Jar包，且不能包含“storm.yaml”文件、“log4j”和“slf4j-log4j”相关的Jar包。
3.  使用IntelliJ IDEA远程提交新打包的Jar包。
4.  查看是否可以在WebUI查看拓扑的详细信息和Worker日志内容。
5.  在Manager页面修改Storm集群关于Worker启动超时参数（参数说明请参考[参考信息](#zh-cn_topic_0167276160_s10dcc60f00124c78a719d4bf23021008)），保存并重启Storm服务。
    -   MRS Manager界面操作入口：登录MRS Manager，依次选择 “服务管理 \> Storm\> 配置”。
    -   FusionInsight Manager界面操作入口：登录FusionInsight Manager，选择“集群 \> 待操作集群的名称 \> 服务 \> Storm \> 配置"

6.  重新提交待运行的Jar包。

## 参考信息<a name="zh-cn_topic_0167276160_s10dcc60f00124c78a719d4bf23021008"></a>

1.  nimbus.task.launch.secs和supervisor.worker.start.timeout.secs这两个参数分别代表nimbus端和supervisor端对于拓扑启动的超时容忍时间，一般nimbus.task.launch.secs的值要大于等于supervisor.worker.start.timeout.secs的值（建议相等或略大，如果超出太多会影响任务重分配的效率）。
    -   nimbus.task.launch.secs：nimbus在超过该参数配置的时间内没有收到拓扑的task发的心跳时，会将该拓扑重新分配（分配给别的supervisor），同时会刷新zk中的任务信息，supervisor读到zk中的任务信息并且与自己当前所启动的拓扑进行比较，如果存在拓扑已经不属于自己，那么则会删除该拓扑的元数据，也就是/srv/Bigdata/streaming\_data/stormdir/supervisor/stormdist/\{worker-id\}目录。

    -   supervisor.worker.start.timeout.secs：supervisor启动worker后，在该参数配置的时间内没有收到worker的心跳时，supervisor会主动停掉worker，等待worker的重新调度，一般在业务启动时间较长时适当增加该参数的值，保证worker能启动成功。

        如果supervisor.worker.start.timeout.secs配置的值比nimbus.task.launch.secs的值大，那么则会出现supervisor的容忍时间没到，仍然继续让worker启动，而nimbus却认定该业务启动超时，将该业务分配给了其他主机，这时supervisor的后台线程发现任务不一致，删除了拓扑的元数据，导致接下来worker在启动过程中要读取stormconf.ser时，发现该文件已经不存在了，就会抛出FileNotFoundException。

2.  nimbus.task.timeout.secs和supervisor.worker.timeout.secs这两个参数则分别代表nimbus端和supervisor端对于拓扑运行过程中心跳上报的超时容忍时间，一般nimbus.task.timeout.secs的值要大于等于supervisor.worker.timeout.secs的值（建议相等或略大），原理同上。

