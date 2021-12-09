# 安装客户端修改配置后执行命令错误，提示IllegalConfigurationException: Error while parsing YAML configuration file<a name="mrs_03_0134"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276087_section370710207470"></a>

客户端安装成功，执行客户端命令例如yarn-session.sh命令报错，提示IllegalConfigurationException: Error while parsing YAML configuration file :81: "security.kerberos.login.principal:pippo "

```
[root@8-5-131-10 bin]# yarn-session.sh
2018-10-25 19:27:01,397 | ERROR | [main] | Error while trying to split key and value in configuration file /opt/flinkclient/Flink/flink/conf/flink-conf.yaml:81: "security.kerberos.login.principal:pippo " | org.apache.flink.configuration.GlobalConfiguration (GlobalConfiguration.java:160)
Exception in thread "main" org.apache.flink.configuration.IllegalConfigurationException: Error while parsing YAML configuration file :81: "security.kerberos.login.principal:pippo "
        at org.apache.flink.configuration.GlobalConfiguration.loadYAMLResource(GlobalConfiguration.java:161)
        at org.apache.flink.configuration.GlobalConfiguration.loadConfiguration(GlobalConfiguration.java:112)
        at org.apache.flink.configuration.GlobalConfiguration.loadConfiguration(GlobalConfiguration.java:79)
        at org.apache.flink.yarn.cli.FlinkYarnSessionCli.main(FlinkYarnSessionCli.java:482)
```

## 原因分析<a name="zh-cn_topic_0167276087_section19940122851412"></a>

配置文件flink-conf.yaml中配置项"security.kerberos.login.principal:pippo”错误。

![](figures/zh-cn_image_0264281799.png)

## 解决办法<a name="zh-cn_topic_0167276087_section359043201"></a>

修改flink-conf.yaml中配置。

注意：配置项名称和值之间存在空格。

![](figures/zh-cn_image_0264281646.png)

