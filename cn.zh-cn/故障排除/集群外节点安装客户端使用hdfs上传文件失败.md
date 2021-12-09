# 集群外节点安装客户端使用hdfs上传文件失败<a name="mrs_03_0259"></a>

## 用户问题<a name="zh-cn_topic_0135447914_section18305143583116"></a>

集群外节点安装客户端使用hdfs上传文件失败

## 问题现象<a name="zh-cn_topic_0135447914_section117424454313"></a>

在集群节点上安装客户端，在该客户端使用hdfs命令上传一个文件，报如下错误：

**图 1**  上传文件报错<a name="fig1896162611238"></a>  
![](figures/上传文件报错.png "上传文件报错")

## 原因分析<a name="zh-cn_topic_0135447914_section1237061220324"></a>

从错误截图可以看到报错是no route to host，且报错信息里面有192.168的ip，也即客户端节点到集群的DN节点的内网路由不通，导致上传文件失败。

## 处理步骤<a name="section458618311212"></a>

在客户端节点的客户端目录下，找到HDFS的客户端配置目录hdfs-site.xml文件，在配置文件中增加配置项dfs.client.use.datanode.hostname，并将该配置设置为true。

