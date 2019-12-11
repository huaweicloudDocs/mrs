# JDK版本不匹配启动spark-sql，spark-shell失败<a name="ZH-CN_TOPIC_0183415851"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275545_section82729302464"></a>

JDK版本不匹配导致客户端启动spark-sql，spark-shell失败。

## 原因分析<a name="zh-cn_topic_0167275545_section6244131819465"></a>

1.  在Driver端打印异常如下：

    ```
     Exception Occurs: BadPadding 16/02/22 14:25:38 ERROR Schema: Failed initialising database. Unable to open a test connection to the given database. JDBC url = jdbc:postgresql://ip:port/sparkhivemeta, username = spark. Terminating connection pool (set lazyInit to true if you expect to start your database after your app). 
    ```

2.  Sparksql任务使用时，需要访问DBService以获取元数据信息，在客户端需要解密密文来访问，在使用过程中，用户没有按照流程操作，没有执行配置环境变量操作，且在其客户端环境变量中存在默认的jdk版本，导致在执行解密过程中调用的解密程序执行解密异常，会引起用户被锁。

## 解决办法<a name="zh-cn_topic_0167275545_section1148017564611"></a>

1.  使用**which java**命令查看默认的java命令是否是客户端的java。
2.  如果不是，请按正常的客户端执行流程。

    **source $client\_path/bigdata\_env**

    **kinit** _用户名_，然后输入用户名对应的密码，启动任务即可。


