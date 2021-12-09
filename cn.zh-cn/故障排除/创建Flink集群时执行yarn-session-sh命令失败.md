# 创建Flink集群时执行yarn-session.sh命令失败<a name="mrs_03_0135"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274939_section370710207470"></a>

创建Fllink集群时，执行yarn-session.sh命令卡住一段时间后报错：

```
2018-09-20 22:51:16,842 | WARN  | [main] | Unable to get ClusterClient status from Application Client | org.apache.flink.yarn.YarnClusterClient (YarnClusterClient.java:253) 
org.apache.flink.util.FlinkException: Could not connect to the leading JobManager. Please check that the JobManager is running.
	at org.apache.flink.client.program.ClusterClient.getJobManagerGateway(ClusterClient.java:861)
	at org.apache.flink.yarn.YarnClusterClient.getClusterStatus(YarnClusterClient.java:248)
	at org.apache.flink.yarn.YarnClusterClient.waitForClusterToBeReady(YarnClusterClient.java:516)
	at org.apache.flink.yarn.cli.FlinkYarnSessionCli.run(FlinkYarnSessionCli.java:717)
	at org.apache.flink.yarn.cli.FlinkYarnSessionCli$1.call(FlinkYarnSessionCli.java:514)
	at org.apache.flink.yarn.cli.FlinkYarnSessionCli$1.call(FlinkYarnSessionCli.java:511)
	at java.security.AccessController.doPrivileged(Native Method)
	at javax.security.auth.Subject.doAs(Subject.java:422)
	at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1729)
	at org.apache.flink.runtime.security.HadoopSecurityContext.runSecured(HadoopSecurityContext.java:41)
	at org.apache.flink.yarn.cli.FlinkYarnSessionCli.main(FlinkYarnSessionCli.java:511)
Caused by: org.apache.flink.runtime.leaderretrieval.LeaderRetrievalException: Could not retrieve the leader gateway.
	at org.apache.flink.runtime.util.LeaderRetrievalUtils.retrieveLeaderGateway(LeaderRetrievalUtils.java:79)
	at org.apache.flink.client.program.ClusterClient.getJobManagerGateway(ClusterClient.java:856)
	... 10 common frames omitted
Caused by: java.util.concurrent.TimeoutException: Futures timed out after [10000 milliseconds]
```

## 可能原因<a name="zh-cn_topic_0167274939_section27469961718"></a>

Flink开启了SSL通信加密，却没有正确的配置SSL证书。

## 解决办法<a name="zh-cn_topic_0167274939_section27114831816"></a>

针对MRS 2.x及之前版本，操作如下：

方法1：

关闭Flink SSL通信加密，修改客户端配置文件**conf/flink-conf.yaml**。

```
security.ssl.internal.enabled: false
```

方法2：

开启Flink SSL通信加密，security.ssl.internal.enabled 保持默认。正确配置SSL：

-   配置keystore或truststore文件路径为**相对路径**时，Flink Client执行命令的目录需要可以直接访问该相对路径

    ```
    security.ssl.internal.keystore: ssl/flink.keystore
    security.ssl.internal.truststore: ssl/flink.truststore
    ```

    在Flink的CLI yarn-session.sh命令中增加“-t“选项来传输keystore和truststore文件到各个执行节点。如：

    ```
    yarn-session.sh -t ssl/ 2
    ```


-   配置keystore或truststore文件路径为**绝对路径**时，需要在Flink Client以及各个节点的该绝对路径上放置keystore或truststore文件。

    ```
    security.ssl.internal.keystore: /opt/client/Flink/flink/conf/flink.keystore
    security.ssl.internal.truststore: /opt/client/Flink/flink/conf/flink.truststore
    ```


针对MRS3.x及之后版本，操作如下：

方法1：

关闭Flink SSL通信加密，修改客户端配置文件**conf/flink-conf.yaml**。

```
security.ssl.enabled: false
```

方法2：

开启Flink SSL通信加密，security.ssl.enabled 保持默认。正确配置SSL：

-   配置keystore或truststore文件路径为**相对路径**时，Flink Client执行命令的目录需要可以直接访问该相对路径

    ```
    security.ssl.keystore: ssl/flink.keystore
    security.ssl.truststore: ssl/flink.truststore
    ```

    在Flink的CLI yarn-session.sh命令中增加“-t“选项来传输keystore和truststore文件到各个执行节点。如：

    ```
    yarn-session.sh -t ssl/ 2
    ```


-   配置keystore或truststore文件路径为**绝对路径**时，需要在Flink Client以及各个节点的该绝对路径上放置keystore或truststore文件。

    ```
    security.ssl.keystore: /opt/Bigdata/client/Flink/flink/conf/flink.keystore
    security.ssl.truststore: /opt/Bigdata/client/Flink/flink/conf/flink.truststore
    ```


