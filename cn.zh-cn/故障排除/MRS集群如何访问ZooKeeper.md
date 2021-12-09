# MRS集群如何访问ZooKeeper<a name="mrs_03_0211"></a>

## 用户问题<a name="section18305143583116"></a>

MRS集群如何访问ZooKeeper？

## 问题现象<a name="section117424454313"></a>

客户在MRS的Master节点使用zkcli.sh访问ZooKeeper但是存在报错。

## 原因分析<a name="section1237061220324"></a>

客户使用命令有问题，造成报错的发生。

## 处理步骤<a name="section11365635122812"></a>

1.  <a name="li84321112520"></a>获取ZooKeeper的IP地址，具体请参考[如何获取ZooKeeper地址？](https://support.huaweicloud.com/mrs_faq/mrs_03_1071.html)。
2.  以root用户登录Master节点。
3.  初始化环境变量。

    **source /opt/client/bigdata\_env**

4.  执行**zkCli.sh -server **_ZooKeeper所在节点的IP_:**2181**即可连接上MRS的ZooKeeper。

    zk所在节点的IP即为[1](#li84321112520)中查到的结果，多个IP之间以逗号间隔。

5.  使用**ls /**等常用的命令查看ZooKeeper上的信息。

