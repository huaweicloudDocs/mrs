# 安全集群外节点安装客户端访问HBase很慢<a name="mrs_03_0271"></a>

## 用户问题<a name="section18305143583116"></a>

安全集群外节点安装了集群的客户端，并使用客户端命令hbase shell访问hbase，发现访问hbase非常慢。

## 问题现象<a name="section117424454313"></a>

客户创建了安全集群，在集群外节点安装了集群的客户端，并使用客户端命令hbase shell访问hbase，发现访问hbase非常慢。

## 原因分析<a name="section1237061220324"></a>

安全集群需要进行Kerberos认证，需要在客户端节点的hosts中配置信息，访问速度才不会收到影响。

```
1.1.1.1 hadoop.782670e3_1364_47e2_8c70_1b61bb80479c.com
1.1.1.1 hadoop.hadoop.com
1.1.1.1 hacluster
1.1.1.1 haclusterX
1.1.1.1 haclusterX1
1.1.1.1 haclusterX2
1.1.1.1 haclusterX3
1.1.1.1 haclusterX4
1.1.1.1 ClusterX
1.1.1.1 manager
ip1 hostname1
ip2 hostname2
ip3 hostname3
ip4 hostname4
```

## 处理步骤<a name="section44423482543"></a>

将集群的节点上的hosts文件拷贝到安装客户端的节点中。

