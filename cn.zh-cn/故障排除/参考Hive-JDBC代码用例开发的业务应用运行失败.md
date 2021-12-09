# 参考Hive JDBC代码用例开发的业务应用运行失败<a name="mrs_03_0194"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275480_s20deae74a71143aeabad239c7a22f024"></a>

用户参考Hive组件的“jdbc-examples”样例工程，完成其自身业务应用开发后，运行此应用失败。应用侧报如下异常：

```
..........

2017-05-11 14:33:52.174 ERROR   --- [           main] o.a.thrift.transport.TSaslTransport      : SASL negotiation failure
javax.security.sasl.SaslException: GSS initiate failed
at com.sun.security.sasl.gsskerb.GssKrb5Client.evaluateChallenge(Unknown Source)
at org.apache.thrift.transport.TSaslClientTransport.handleSaslStartMessage(TSaslClientTransport.java:94)
at org.apache.thrift.transport.TSaslTransport.open(TSaslTransport.java:271)
at org.apache.thrift.transport.TSaslClientTransport.open(TSaslClientTransport.java:37)
at org.apache.hadoop.hive.thrift.client.TUGIAssumingTransport$1.run(TUGIAssumingTransport.java:52)
at org.apache.hadoop.hive.thrift.client.TUGIAssumingTransport$1.run(TUGIAssumingTransport.java:49)
at java.security.AccessController.doPrivileged(Native Method)
at javax.security.auth.Subject.doAs(Unknown Source)
at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1711)
at org.apache.hadoop.hive.thrift.client.TUGIAssumingTransport.open(TUGIAssumingTransport.java:49)
at org.apache.hive.jdbc.HiveConnection.openTransport(HiveConnection.java:260)
at org.apache.hive.jdbc.HiveConnection.createClient(HiveConnection.java:213)
at org.apache.hive.jdbc.HiveConnection.<init>(HiveConnection.java:178)
at org.apache.hive.jdbc.HiveDriver.connect(HiveDriver.java:105)
at java.sql.DriverManager.getConnection(Unknown Source)
at java.sql.DriverManager.getConnection(Unknown Source)
at com.huawei.bigdata.hive.example.JDBCExample.main(JDBCExample.java:107)
Caused by: org.ietf.jgss.GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)
at sun.security.jgss.krb5.Krb5InitCredential.getInstance(Unknown Source)
at sun.security.jgss.krb5.Krb5MechFactory.getCredentialElement(Unknown Source)
at sun.security.jgss.krb5.Krb5MechFactory.getMechanismContext(Unknown Source)
at sun.security.jgss.GSSManagerImpl.getMechanismContext(Unknown Source)
at sun.security.jgss.GSSContextImpl.initSecContext(Unknown Source)
at sun.security.jgss.GSSContextImpl.initSecContext(Unknown Source)
... 17 common frames omitted
......
```

## 原因分析<a name="zh-cn_topic_0167275480_s7dfa4353c00142a991338a71eaf7d6ad"></a>

1.  初步分析怀疑是没有完成kerberos认证就去进行业务交互。
2.  深入分析日志发现日志上虽然有打印“com.huawei.bigdata.security.LoginUtil  - Login success!!!!!!!!!!!!!!”，但没打印“org.apache.hadoop.security.UserGroupInformation      : Login successful...”。

    分析源码，发现：

    ```
    /*      */   @InterfaceAudience.Public
    /*      */   @InterfaceStability.Evolving
    /*      */   public static synchronized void loginUserFromKeytab(String user, String path)
    /*      */     throws IOException
    /*      */   {
    /*  958 */     if (!isSecurityEnabled()) {
    /*  959 */       return;
    /*      */     }
    ......
    ```

3.  分析“isSecurityEnabled\(\)”，发现是否要发起认证，还需要判断configuration中是否有配置“hadoop.security.authentication”为“kerberos”。

    本Hive业务应用确实没有正确设置此配置，所以被认为不需要做kerberos认证。

    分析Hive组件的“jdbc-examples”样例工程，它不存在类似问题，是因为在此工程的classpath路径下，存在core-site.xml配置文件，此配置文件上设置“hadoop.security.authentication”为“kerberos”。


## 解决办法<a name="zh-cn_topic_0167275480_section1213444410221"></a>

属于用户使用不当。对于本业务应用来说，若要解决此问题，可以参考如下几种办法：

-   方法1：

    直接参考Hive组件的“jdbc-examples”样例工程，将core-site.xml配置文件放在classpath路径下。

-   方法2：

    在代码中，显式加载配置文件core-site.xml，例如：

    ```
    ......
        conf = new Configuration();
        String userdir = System.getProperty("user.dir") + File.separator + "conf" + File.separator;
        conf.addResource(new Path(userdir + "core-site.xml"));
    ......
    ```

-   方法3：

    在代码中，设置“hadoop.security.authentication”为“kerberos”，例如：

    ```
    ......    
        CONF = new Configuration();
        CONF.set("hadoop.security.authentication", "kerberos");
    ......
    ```


