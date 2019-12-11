# 安装客户端执行命令错误，提示IllegalConfigurationException: Error while parsing YAML configuration file :"security.kerberos.login.keytab"<a name="ZH-CN_TOPIC_0187615915"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276112_section370710207470"></a>

客户端安装成功，执行客户端命令例如yarn-session.sh命令报错，提示IllegalConfigurationException: Error while parsing YAML configuration file : "security.kerberos.login.keytab: "

```
[root@8-5-131-10 bin]# yarn-session.sh
2018-10-25 01:22:06,454 | ERROR | [main] | Error while trying to split key and value in configuration file /opt/flinkclient/Flink/flink/conf/flink-conf.yaml:80: "security.kerberos.login.keytab: " | org.apache.flink.configuration.GlobalConfiguration (GlobalConfiguration.java:160)
Exception in thread "main" org.apache.flink.configuration.IllegalConfigurationException: Error while parsing YAML configuration file :80: "security.kerberos.login.keytab: "
        at org.apache.flink.configuration.GlobalConfiguration.loadYAMLResource(GlobalConfiguration.java:161)
        at org.apache.flink.configuration.GlobalConfiguration.loadConfiguration(GlobalConfiguration.java:112)
        at org.apache.flink.configuration.GlobalConfiguration.loadConfiguration(GlobalConfiguration.java:79)
        at org.apache.flink.yarn.cli.FlinkYarnSessionCli.main(FlinkYarnSessionCli.java:482)
[root@8-5-131-10 bin]#
```

## 原因分析<a name="zh-cn_topic_0167276112_section19940122851412"></a>

在安全集群环境下，Flink需要进行安全认证。当前客户端未进行相关安全认证设置。

1.  Flink整个系统有三种认证方式：
    -   使用kerberos认证：Flink  yarn client、Yarn Resource  Manager、JobManager、HDFS、TaskManager、Kafka和Zookeeper。
    -   使用YARN内部的认证机制：Yarn  Resource Manager与Application Master（简称AM）。

2.  如果用户安装安全集群需要使用kerberos认证和security cookie认证。根据日志提示，发现配置文件中“security.kerberos.login.keytab :”配置项错误，未进行安全配置。

## 解决办法<a name="zh-cn_topic_0167276112_section359043201"></a>

1.  <a name="zh-cn_topic_0167276112_li1710292815513"></a>从MRS上下载用户keytab，并将keytab放到Flink客户端所在主机的某个文件夹下。
2.  在“flink-conf.yaml”上配置：
    1.  keytab路径。

        ```
        security.kerberos.login.keytab: /home/flinkuser/keytab/abc222.keytab
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >-   “/home/flinkuser/keytab/abc222.keytab”表示的是用户目录，为[1](#zh-cn_topic_0167276112_li1710292815513)中放置目录。  
        >-   请确保客户端用户具备对应目录权限。  


    1.  principal名。

        ```
        security.kerberos.login.principal: abc222
        ```

    1.  对于HA模式，如果配置了ZooKeeper，还需要设置ZK kerberos认证相关的配置。配置如下：

        ```
        zookeeper.sasl.disable: false 
        security.kerberos.login.contexts: Client
        ```

    1.  如果用户对于Kafka client和Kafka broker之间也需要做kerberos认证，配置如下：

        ```
        security.kerberos.login.contexts: Client,KafkaClient
        ```



