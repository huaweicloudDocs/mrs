# 普通集群在Core节点安装hdfs客户端，使用时报错<a name="ZH-CN_TOPIC_0232157194"></a>

## 用户问题<a name="section18305143583116"></a>

普通集群在Core节点新建用户安装使用客户端报有误导的报错。

## 问题现象<a name="section117424454313"></a>

普通集群在Core节点新建用户安装使用客户端报错如下：

```
2020-03-14 19:16:17,166 WARN shortcircuit.DomainSocketFactory: error creating DomainSocket
java.net.ConnectException: connect(2) error: Permission denied when trying to connect to '/var/run/MRS-HDFS/dn_socket'
at org.apache.hadoop.net.unix.DomainSocket.connect0(Native Method)
at org.apache.hadoop.net.unix.DomainSocket.connect(DomainSocket.java:256)
at org.apache.hadoop.hdfs.shortcircuit.DomainSocketFactory.createSocket(DomainSocketFactory.java:168)
at org.apache.hadoop.hdfs.client.impl.BlockReaderFactory.nextDomainPeer(BlockReaderFactory.java:799)
...
```

## 原因分析<a name="section1237061220324"></a>

用户使用  **useradd**  命令来创建用户，此用户默认用户组不包含“ficommmon“用户组，导致在使用hdfs的get命令的时候出现上述报错。

## 处理步骤<a name="section520813413313"></a>

使用命令**usermod -a -G ficommon username**  为用户添加用户组“ficommon“。

