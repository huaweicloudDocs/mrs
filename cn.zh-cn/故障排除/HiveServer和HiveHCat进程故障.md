# HiveServer和HiveHCat进程故障<a name="ZH-CN_TOPIC_0239258448"></a>

## 用户问题<a name="section18305143583116"></a>

客户集群HiveServer和WebHCat进程状态均为故障

## 问题现象<a name="section117424454313"></a>

客户MRS集群Master2节点上的HiveServer和WebHCat进程状态显示为故障，重启之后仍为故障状态。

## 原因分析<a name="section1237061220324"></a>

在MRS Manager界面单独启动故障的hiveserver进程，登录后台查找hiveserver.out日志中对应时间点的报错，报错信息为：error parsing conf mapred-site.xml  和 Premature end of file。然后重启webhcat也发现同样报错，原因即为解析mapred-site.xml文件错误。

## 处理步骤<a name="section520813413313"></a>

1.  以root用户登录Master2节点。
2.  执行**find / -name 'mapred-site.xml'**命令获取mapred-site.xml文件所在位置。
    -   hiveserver对应路径为/opt/Bigdata/MRS\_2.1.0/1\_13\_HiveServer/etc/mapred-site.xml，
    -   webhcat对应路径为/opt/Bigdata/MRS\_2.1.0/1\_13\_WebHCat/etc/mapred-site.xml。

3.  确认mapred-site.xml文件是否有异常，该案例中该配置文件内容为空导致解析失败。
4.  修复mapred-site.xml文件，将Master1节点上对应目录下的配置文件用scp命令拷贝到Master2节点对应目录替换原文件.
5.  执行**chown omm:wheel mapred-site.xml**命令更改所属组和用户。
6.  在MRS Manager界面重启故障的HiveServer和WebHCat进程，恢复正常。

