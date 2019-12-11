# Beeline报Failed to execute session hooks: over max connections错误<a name="ZH-CN_TOPIC_0210454012"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276433_section842971116813"></a>

HiveServer连接的最大连接数默认为200，当超过200时，Beeline会报Failed to execute session hooks: over max connections

```
beeline> [root@172-27-16-38 c70client]# beeline
Connecting to jdbc:hive2://129.188.82.38:24002,129.188.82.36:24002,129.188.82.35:24002/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2;sasl.qop=auth-conf;auth=KERBEROS;principal=hive/hadoop.hadoop.com@HADOOP.COM
Debug is  true storeKey false useTicketCache true useKeyTab false doNotPrompt false ticketCache is null isInitiator true KeyTab is null refreshKrb5Config is false principal is null tryFirstPass is false useFirstPass is false storePass is false clearPass is false
Acquire TGT from Cache
Principal is admin@HADOOP.COM
Commit Succeeded 

Error: Failed to execute session hooks: over max connections. (state=,code=0)
Beeline version 1.2.1 by Apache Hive
```

查看hiveserver日志\(/var/log/Bigdata/hive/hiveserver/hive.log\)报over max connections错误

```
2018-05-03 04:31:56,728 | WARN  | HiveServer2-Handler-Pool: Thread-137 | Error opening session:  | org.apache.hive.service.cli.thrift.ThriftCLIService.OpenSession(ThriftCLIService.java:542)
org.apache.hive.service.cli.HiveSQLException: Failed to execute session hooks: over max connections.
	at org.apache.hive.service.cli.session.SessionManager.openSession(SessionManager.java:322)
	at org.apache.hive.service.cli.CLIService.openSessionWithImpersonation(CLIService.java:189)
	at org.apache.hive.service.cli.thrift.ThriftCLIService.getSessionHandle(ThriftCLIService.java:663)
	at org.apache.hive.service.cli.thrift.ThriftCLIService.OpenSession(ThriftCLIService.java:527)
	at org.apache.hive.service.cli.thrift.TCLIService$Processor$OpenSession.getResult(TCLIService.java:1257)
	at org.apache.hive.service.cli.thrift.TCLIService$Processor$OpenSession.getResult(TCLIService.java:1242)
	at org.apache.thrift.ProcessFunction.process(ProcessFunction.java:39)
	at org.apache.thrift.TBaseProcessor.process(TBaseProcessor.java:39)
	at org.apache.hadoop.hive.thrift.HadoopThriftAuthBridge$Server$TUGIAssumingProcessor.process(HadoopThriftAuthBridge.java:710)
	at org.apache.thrift.server.TThreadPoolServer$WorkerProcess.run(TThreadPoolServer.java:286)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	at java.lang.Thread.run(Thread.java:745)
Caused by: org.apache.hive.service.cli.HiveSQLException: over max connections.
	at org.apache.hadoop.hive.transporthook.SessionControllerTsaslTransportHook.checkTotalSessionNumber(SessionControllerTsaslTransportHook.java:208)
	at org.apache.hadoop.hive.transporthook.SessionControllerTsaslTransportHook.postOpen(SessionControllerTsaslTransportHook.java:163)
	at org.apache.hadoop.hive.transporthook.SessionControllerTsaslTransportHook.run(SessionControllerTsaslTransportHook.java:134)
	at org.apache.hive.service.cli.session.SessionManager.executeSessionHooks(SessionManager.java:432)
	at org.apache.hive.service.cli.session.SessionManager.openSession(SessionManager.java:314)
	... 12 more
```

## 原因分析<a name="zh-cn_topic_0167276433_section724010302087"></a>

1.  业务量大导致连接HiveServer单个节点最大连接数超过了200，需要调大连接HiveServer实例的最大连接数。

## 解决办法<a name="zh-cn_topic_0167276433_section17326135612212"></a>

1.  登录MRS Manager页面，访问“服务管理 \> Hive \> 服务配置 \> 参数类别（选择全部配置）”，搜索hive.server.session.control.maxconnections配置项。
2.  修改hive.server.session.control.maxconnections配置的值到合适值，不能超过1000。
3.  保存配置并重启受影响的服务或者实例。

