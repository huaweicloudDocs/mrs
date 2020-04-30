# DaYu调度spark作业失败<a name="ZH-CN_TOPIC_0239258650"></a>

## 用户问题<a name="section18305143583116"></a>

DaYu作业调度失败，显示读取/thriftserver/active\_thriftserver路径下的数据失败

## 问题现象<a name="section117424454313"></a>

DaYu作业调度失败，显示读取/thriftserver/active\_thriftserver路径下的数据失败，

报错信息为：Can not get JDBC Connection, due to KeeperErrorCode = NoNode for /thriftserver/active\_thriftserver

## 原因分析<a name="section1237061220324"></a>

DaYu提交spark作业时调用spark的JDBC方式，而Spark会启动一个名为thriftserver的进程以供客户端提供JDBC连接，JDBCServer在启动时会在zk的/thriftserver目录下创建子目录active\_thriftserver，并且注册相关连接信息。如果读不到该连接信息就会JDBC连接异常。

## 处理步骤<a name="section14131043103916"></a>

检查zookeeper下面是否有目标目录和注册的信息

1.  以root用户登录任意一个Master节点并初始化环境变量。

    **source /opt/client/bigdata\_env**

2.  执行**zkCli.sh -server 'ZookeeperIp:2181'**命令登录zk。
3.  执行**ls /thriftserver**查看是否有active\_thriftserver目录。
    -   如果有active\_thriftserver目录，执行**get /thriftserver/active\_thriftserver**查看该目录下是否有注册的配置信息。
        -   如果有注册的配置信息，联系华为云支持人员处理。
        -   如果没有注册的配置信息，执行[4](#li1936217343284)

    -   如果没有active\_thriftserver目录，执行[4](#li1936217343284)。

4.  <a name="li1936217343284"></a>登录[MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)，查看Spark的JDBCServer实例的主备状态是否未知。
    -   是，执行[5](#li6928171252710)。
    -   否，联系华为云支持人员处理。

5.  <a name="li6928171252710"></a>重启两个JDBCServer实例，查看主备实例状态恢复正常且zk下面有了目标目录和数据，作业即可恢复正常。若实例状态没有恢复请联系华为云支持人员处理。

## 建议与总结<a name="section8898183420"></a>

无

## 参考信息<a name="section18208334123312"></a>

无

