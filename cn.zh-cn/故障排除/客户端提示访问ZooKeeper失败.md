# 客户端提示访问ZooKeeper失败<a name="mrs_03_0172"></a>

## 问题现象<a name="zh-cn_topic_0167276080_s4062da02d4d340ed9dbd38c42c5a7475"></a>

安全集群中，HiveServer服务正常的情况下，通过jdbc接口连接HiveServer执行sql时报出ZooKeeper认证异常"The ZooKeeper client is AuthFailed"，如下：

```
14/05/19 10:52:00 WARN utils.HAClientUtilDummyWatcher: The ZooKeeper client is AuthFailed
 14/05/19 10:52:00 INFO utils.HiveHAClientUtil: Exception thrown while reading data from znode.The possible reason may be connectionless. This is recoverable. Retrying.. 
 14/05/19 10:52:16 WARN utils.HAClientUtilDummyWatcher: The ZooKeeper client is AuthFailed 
 14/05/19 10:52:32 WARN utils.HAClientUtilDummyWatcher: The ZooKeeper client is AuthFailed 
 14/05/19 10:52:32 ERROR st.BasicTestCase: Exception: Could not establish connection to active hiveserver 
 java.sql.SQLException: Could not establish connection to active hiveserver
```

或者报出无法读取"Hiveserver2 configs from ZooKeeper"，如下：

```
Exception in thread "main" java.sql.SQLException: org.apache.hive.jdbc.ZooKeeperHiveClientException: Unable to read HiveServer2 configs from ZooKeeper
at org.apache.hive.jdbc.HiveConnection.<init>(HiveConnection.java:144)
at org.apache.hive.jdbc.HiveDriver.connect(HiveDriver.java:105)
at java.sql.DriverManager.getConnection(DriverManager.java:664)
at java.sql.DriverManager.getConnection(DriverManager.java:247)
at JDBCExample.main(JDBCExample.java:82)
Caused by: org.apache.hive.jdbc.ZooKeeperHiveClientException: Unable to read HiveServer2 configs from ZooKeeper
at org.apache.hive.jdbc.ZooKeeperHiveClientHelper.configureConnParams(ZooKeeperHiveClientHelper.java:100)
at org.apache.hive.jdbc.Utils.configureConnParams(Utils.java:509)
at org.apache.hive.jdbc.Utils.parseURL(Utils.java:429)
at org.apache.hive.jdbc.HiveConnection.<init>(HiveConnection.java:142)
... 4 more
Caused by: org.apache.zookeeper.KeeperException$ConnectionLossException: KeeperErrorCode = ConnectionLoss for /hiveserver2
at org.apache.zookeeper.KeeperException.create(KeeperException.java:99)
at org.apache.zookeeper.KeeperException.create(KeeperException.java:51)
at org.apache.zookeeper.ZooKeeper.getChildren(ZooKeeper.java:2374)
at org.apache.curator.framework.imps.GetChildrenBuilderImpl$3.call(GetChildrenBuilderImpl.java:214)
at org.apache.curator.framework.imps.GetChildrenBuilderImpl$3.call(GetChildrenBuilderImpl.java:203)
at org.apache.curator.RetryLo，op.callWithRetry(RetryLoop.java:107)
at org.apache.curator.framework.imps.GetChildrenBuilderImpl.pathInForeground(GetChildrenBuilderImpl.java:200)
at org.apache.curator.framework.imps.GetChildrenBuilderImpl.forPath(GetChildrenBuilderImpl.java:191)
at org.apache.curator.framework.imps.GetChildrenBuilderImpl.forPath(GetChildrenBuilderImpl.java:38)
```

## 可能原因<a name="zh-cn_topic_0167276080_sde58cdd386c74b8c940eb2114143b0a3"></a>

-   客户端连接HiveServer时，HiveServer的地址是从ZooKeeper中自动获取，当ZooKeeper连接认证异常时，无法从ZooKeeper中获取正确的HiveServer地址。
-   在连接zookeeper认证时，需要客户端传入krb5.conf，principal，keytab等相关信息。认证失败有如下几种：
    -   user.keytab路径写错。
    -   user.principal写错。
    -   集群做过切换域名操作但客户端拼接url时使用旧的principal。
    -   有防火墙相关设置，导致客户端本身无法通过kerberos认证，Kerberos需要开放的端口有21730\(TCP\)、21731\(TCP/UDP\)、21732\(TCP/UDP\)。


## 解决方案<a name="zh-cn_topic_0167276080_sf8f53c018c784bab9ca84e6d32b5d35d"></a>

1.  确保用户可以正常读取客户端节点相关路径下的user.keytab文件。
2.  确保用户的user.principal与指定的keytab文件对应。

    可通过**klist -kt keytabpath/user.keytab**查看。

3.  如果集群有做过切换域名操作，需要保证url中使用的principal字段是新域名。

    如默认为hive/hadoop.hadoop.com@HADOOP.COM，当集群有切换域名的操作时，该字段需要进行相关修改。如域名为abc.com时，则此处应填写hive/hadoop.abc.com@ABC.COM。

4.  确保可以正常的认证连接HiveServer。

    在客户端执行以下命令

    **source $\{client\_home\}/bigdata\_env**

    **kinit** _username_

    然后再使用客户端执行**beeline**，确保可以正常运行。


