# 提交拓扑失败，提示Failed to check principle for keytab<a name="ZH-CN_TOPIC_0183415881"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274757_s8c5a413588744f3ea1320d012fdb73cb"></a>

使用MRS流式安全集群，主要安装ZooKeeper、Storm、Kafka等。

定义拓扑访问HDFS、HBase等组件，使用客户端命令，提交Topology失败。

## 可能原因<a name="zh-cn_topic_0167274757_section51259467103320"></a>

-   提交拓扑中没有包含用户的keytab文件。
-   提交拓扑中包含keytab和提交用户不一致。
-   客户端/tmp目录下已存在user.keytab，且宿主非运行用户。

## 原因分析<a name="zh-cn_topic_0167274757_section2251282011336"></a>

1.  查看日志发现异常信息Can not found user.keytab in storm.jar。具体信息如下：

    ```
    [main] INFO  b.s.StormSubmitter - Get principle for stream@HADOOP.COM success
    [main] ERROR b.s.StormSubmitter - Can not found user.keytab in storm.jar.
    Exception in thread "main" java.lang.RuntimeException: Failed to check principle for keytab
    at backtype.storm.StormSubmitter.submitTopologyAs(StormSubmitter.java:219)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:292)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:176)
    at com.huawei.streaming.storm.example.hbase.SimpleHBaseTopology.main(SimpleHBaseTopology.java:77)
    ```

    查看提交的拓扑运行Jar，发现没有包含keytab文件。

2.  查看日志发现异常信息The submit user is invalid,the principle is 。具体信息如下：

    ```
    [main] INFO  b.s.StormSubmitter - Get principle for stream@HADOOP.COM success
    [main] WARN  b.s.s.a.k.ClientCallbackHandler - Could not login: the client is being asked for a password, but the  client code does not currently support obtaining a password from the user. Make sure that the client is configured to use a ticket cache (using the JAAS configuration setting 'useTicketCache=true)' and restart the client. If you still get this message after that, the TGT in the ticket cache has expired and must be manually refreshed. To do so, first determine if you are using a password or a keytab. If the former, run kinit in a Unix shell in the environment of the user who is running this client using the command 'kinit <princ>' (where <princ> is the name of the client's Kerberos principal). If the latter, do 'kinit -k -t <keytab> <princ>' (where <princ> is the name of the Kerberos principal, and <keytab> is the location of the keytab file). After manually refreshing your cache, restart this client. If you continue to see this message after manually refreshing your cache, ensure that your KDC host's clock is in sync with this host's clock.
    [main] ERROR b.s.StormSubmitter - The submit user is invalid,the principle is : stream@HADOOP.COM
    Exception in thread "main" java.lang.RuntimeException: Failed to check principle for keytab
    at backtype.storm.StormSubmitter.submitTopologyAs(StormSubmitter.java:219)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:292)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:176)
    at com.huawei.streaming.storm.example.hbase.SimpleHBaseTopology.main(SimpleHBaseTopology.java:77)
    ```

    业务提交拓扑时使用的认证用户为stream，但是在拓扑提交过程中提示submit user是无效用户，表明内部校验失败。

3.  查看提交的拓扑运行Jar，发现包含keytab文件。

    查看user.keytab文件，发现principal为zmk\_kafka.

    ![](figures/zh-cn_image_0167275075.jpg)

    发现认证用户和user.keytab文件中principal不对应。

4.  查看日志发现异常信息Delete the tmp keytab file failed，the keytab file is ：/tmp/user.keytab，具体信息如下：

    ```
    [main] WARN b.s.StormSubmitter - Delete the tmp keytab file failed, the keytab file is : /tmp/user.keytab
    [main] ERROR b.s.StormSubmitter - The submit user is invalid,the principle is : hbase1@HADOOP.COM
    Exception in thread "main" java.lang.RuntimeException: Failed to check principle for keytab
    at backtype.storm.StormSubmitter.submitTopologyAs(StormSubmitter.java:213)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:286)
    at backtype.storm.StormSubmitter.submitTopology(StormSubmitter.java:170)
    at com.touchstone.storm.cmcc.CmccDataHbaseTopology.main(CmccDataHbaseTopology.java:183)
    ```

    查看系统/tmp目录，发现存在user.keytab文件，且文件宿主非运行用户。


## 解决办法<a name="zh-cn_topic_0167274757_section896511911216"></a>

-   提交拓扑时携带用户user.keytab文件。
-   提交拓扑时的用户需要和user.keytab文件用户一致。
-   删除/tmp目录下不对应的user.keytab文件。

