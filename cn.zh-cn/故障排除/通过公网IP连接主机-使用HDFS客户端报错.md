# 通过公网IP连接主机，使用HDFS客户端报错<a name="mrs_03_0039"></a>

## 用户问题<a name="section18305143583116"></a>

通过公网IP连接主机，不能使用HDFS客户端，运行HDFS提示**-bash: hdfs: command not found。**

## 问题现象<a name="section117424454313"></a>

通过公网IP连接主机，不能使用HDFS客户端，运行HDFS提示**-bash: hdfs: command not found**。

## 原因分析<a name="section1237061220324"></a>

用户登录Master节点执行命令之前，未设置环境变量。

## 处理步骤<a name="section3677104210412"></a>

1.  以**root**用户登录任意一个Master节点。
2.  执行**source /opt/client/bigdata\_env**命令，设置环境变量。
3.  执行**hdfs**命令即可成功使用HDFS客户端。

