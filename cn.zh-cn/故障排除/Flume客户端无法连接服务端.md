# Flume客户端无法连接服务端<a name="mrs_03_0054"></a>

## 问题现象<a name="zh-cn_topic_0167275231_sd64242caa665405798481482f49ab0ee"></a>

安装Flume客户端并设置avro sink与服务端通信，发现无法连接Flume服务端。

## 原因分析<a name="zh-cn_topic_0167275231_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

1.  服务端配置错误，监听端口启动失败，例如服务端avro source配置了错误的IP，或者已经被占用了的端口。查看Flume运行日志：

    ```
    2016-08-31 17:28:42,092 | ERROR | [lifecycleSupervisor-1-9] |  Unable to start EventDrivenSourceRunner: { source:Avro source avro_source: { bindAddress: 10.120.205.7, port: 21154 } } - Exception follows.  | org.apache.flume.lifecycle.LifecycleSupervisor$MonitorRunnable.run(LifecycleSupervisor.java:253)
    java.lang.RuntimeException: org.jboss.netty.channel.ChannelException: Failed to bind to: /192.168.205.7:21154
    ```

2.  若采用了加密传输，证书或密码错误。

    ```
    2016-08-31 17:15:59,593 | ERROR | [conf-file-poller-0] |  Source avro_source has been removed due to an error during configuration  | org.apache.flume.node.AbstractConfigurationProvider.loadSources(AbstractConfigurationProvider.java:388)
    org.apache.flume.FlumeException: Avro source configured with invalid keystore: /opt/Bigdata/MRS_XXX/install/FusionInsight-Flume-1.9.0/flume/conf/flume_sChat.jks
    ```

3.  客户端与服务端通信异常。

    ```
    PING 192.168.85.55 (10.120.85.55) 56(84) bytes of data.
    From 192.168.85.50 icmp_seq=1 Destination Host Unreachable
    From 192.168.85.50 icmp_seq=2 Destination Host Unreachable
    From 192.168.85.50 icmp_seq=3 Destination Host Unreachable
    From 192.168.85.50 icmp_seq=4 Destination Host Unreachable
    ```


## 解决办法<a name="zh-cn_topic_0167275231_section4599086017025"></a>

1.  设置为正确的IP，必须为本机的IP，如果端口被占用，重新配置一个空闲的端口。
2.  配置正确的证书路径。
3.  联系网络管理员，恢复网络。

