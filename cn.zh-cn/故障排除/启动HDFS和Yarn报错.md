# 启动HDFS和Yarn报错<a name="ZH-CN_TOPIC_0171383715"></a>

## 用户问题<a name="section18305143583116"></a>

启动HDFS和Yarn时报错

## 问题现象<a name="section117424454313"></a>

无法启动HDFS、Yarn服务组件，报错内容：/dev/null Permission denied

![](figures/zh-cn_image_0171384043.png)

## 原因分析<a name="section1237061220324"></a>

客户修改了虚机系统的/dev/null的权限值为775。

![](figures/zh-cn_image_0171384045.png)

## 处理步骤<a name="section43069141981"></a>

1.  以root用户登录集群的任意一个Master节点。
2.  登录成功后，执行**chmod 666 /dev/null**命令，修改/dev/null的权限值为666。
3.  执行**ls -al /dev/null**命令，查看修改的/dev/null权限值是否为666，如果不是，需要修改为666。
4.  修改成功后，重新启动HDFS和Yarn组件。

