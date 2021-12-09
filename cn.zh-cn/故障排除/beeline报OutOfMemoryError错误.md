# beeline报OutOfMemoryError错误<a name="mrs_03_0188"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275532_section1880842318311"></a>

beeline客户端查询大量数据时，报OutOFMemoryError：Java heap space，具体报错信息如下：

```
org.apache.thrift.TException: Error in calling method FetchResults
	at org.apache.hive.jdbc.HiveConnection$SynchronizedHandler.invoke(HiveConnection.java:1514)
	at com.sun.proxy.$Proxy4.FetchResults(Unknown Source)
	at org.apache.hive.jdbc.HiveQueryResultSet.next(HiveQueryResultSet.java:358)
	at org.apache.hive.beeline.BufferedRows.<init>(BufferedRows.java:42)
	at org.apache.hive.beeline.BeeLine.print(BeeLine.java:1856)
	at org.apache.hive.beeline.Commands.execute(Commands.java:873)
	at org.apache.hive.beeline.Commands.sql(Commands.java:714)
	at org.apache.hive.beeline.BeeLine.dispatch(BeeLine.java:1035)
	at org.apache.hive.beeline.BeeLine.execute(BeeLine.java:821)
	at org.apache.hive.beeline.BeeLine.begin(BeeLine.java:778)
	at org.apache.hive.beeline.BeeLine.mainWithInputRedirection(BeeLine.java:486)
	at org.apache.hive.beeline.BeeLine.main(BeeLine.java:469)
Caused by: java.lang.OutOfMemoryError: Java heap space
	at com.sun.crypto.provider.CipherCore.doFinal(CipherCore.java:959)
	at com.sun.crypto.provider.CipherCore.doFinal(CipherCore.java:824)
	at com.sun.crypto.provider.AESCipher.engineDoFinal(AESCipher.java:436)
	at javax.crypto.Cipher.doFinal(Cipher.java:2223)
	at sun.security.krb5.internal.crypto.dk.AesDkCrypto.decryptCTS(AesDkCrypto.java:414)
	at sun.security.krb5.internal.crypto.dk.AesDkCrypto.decryptRaw(AesDkCrypto.java:291)
	at sun.security.krb5.internal.crypto.Aes256.decryptRaw(Aes256.java:86)
	at sun.security.jgss.krb5.CipherHelper.aes256Decrypt(CipherHelper.java:1397)
	at sun.security.jgss.krb5.CipherHelper.decryptData(CipherHelper.java:576)
	at sun.security.jgss.krb5.WrapToken_v2.getData(WrapToken_v2.java:130)
	at sun.security.jgss.krb5.WrapToken_v2.getData(WrapToken_v2.java:105)
	at sun.security.jgss.krb5.Krb5Context.unwrap(Krb5Context.java:1058)
	at sun.security.jgss.GSSContextImpl.unwrap(GSSContextImpl.java:403)
	at com.sun.security.sasl.gsskerb.GssKrb5Base.unwrap(GssKrb5Base.java:77)
	at org.apache.thrift.transport.TSaslTransport$SaslParticipant.unwrap(TSaslTransport.java:559)
	at org.apache.thrift.transport.TSaslTransport.readFrame(TSaslTransport.java:462)
	at org.apache.thrift.transport.TSaslTransport.read(TSaslTransport.java:435)
	at org.apache.thrift.transport.TSaslClientTransport.read(TSaslClientTransport.java:37)
	at org.apache.thrift.transport.TTransport.readAll(TTransport.java:86)
	at org.apache.hadoop.hive.thrift.TFilterTransport.readAll(TFilterTransport.java:62)
	at org.apache.thrift.protocol.TBinaryProtocol.readAll(TBinaryProtocol.java:429)
	at org.apache.thrift.protocol.TBinaryProtocol.readI32(TBinaryProtocol.java:318)
	at org.apache.thrift.protocol.TBinaryProtocol.readMessageBegin(TBinaryProtocol.java:219)
	at org.apache.thrift.TServiceClient.receiveBase(TServiceClient.java:77)
	at org.apache.hive.service.cli.thrift.TCLIService$Client.recv_FetchResults(TCLIService.java:505)
	at org.apache.hive.service.cli.thrift.TCLIService$Client.FetchResults(TCLIService.java:492)
	at sun.reflect.GeneratedMethodAccessor2.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hive.jdbc.HiveConnection$SynchronizedHandler.invoke(HiveConnection.java:1506)
	at com.sun.proxy.$Proxy4.FetchResults(Unknown Source)
	at org.apache.hive.jdbc.HiveQueryResultSet.next(HiveQueryResultSet.java:358)
Error: Error retrieving next row (state=,code=0)
```

## 原因分析<a name="zh-cn_topic_0167275532_section538710503012"></a>

-   客户查询大量数据，数据量过大。
-   客户在检索数据时使用**select \* from table\_name;**，进行全表查询，表内数据过多。
-   beeline默认启动内存128M，查询时返回结果集过大，导致beeline无法承载导致。

## 解决办法<a name="zh-cn_topic_0167275532_section373872513569"></a>

1.  执行**select count\(\*\) from table\_name;**前确认需要查询的数据量大小，确认是否需要在beeline中显示如此数量级的数据。
2.  如数量在一定范围内需要显示，请调整hive客户端的jvm参数， 在hive客户端目录/Hive下的component\_env中添加export HIVE\_OPTS=-Xmx1024M\(具体数值请根据业务调整\)，并重新执行**source **_客户端目录_**/bigdata\_env**配置环境变量。

