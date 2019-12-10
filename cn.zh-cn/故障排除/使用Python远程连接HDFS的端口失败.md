# 使用Python远程连接HDFS的端口失败<a name="ZH-CN_TOPIC_0170677991"></a>

## 用户问题<a name="section18305143583116"></a>

使用Python远程连接HDFS的端口失败，如何解决？

## 问题现象<a name="section117424454313"></a>

用户使用Python远程连接HDFS的50070端口失败。

## 原因分析<a name="section1237061220324"></a>

HDFS开源3.0.0以下版本的默认端口为50070，3.0.0及以上的默认端口为9870。用户使用的端口和HDFS版本不匹配导致连接端口失败。

1.  登录集群的主Master节点。
2.  执行**su - omm**命令，切换到omm用户。
3.  执行**/opt/Bigdata/om-0.0.1/sbin/queryVersion.sh**命令，查看集群中的HDFS版本号。

    根据版本号确认开源组件的端口号，查询开源组件的端口号可参考[开源组件端口列表](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0504.html)，获取对应版本的HDFS端口号。

4.  执行**netstat -anp|grep $\{port\}**命令，查看组件的默认端口号是否存在。

    如果不存在，说明用户修改了默认的端口号。请修改为默认端口，再重新连接HDFS。

    如果存在，请联系技术服务。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   $\{ port \}：表示与组件版本相对应的组件默认端口号。  
    >-   如果用户修改了默认端口号，请使用修改后的端口号连接HDFS。不建议修改默认端口号。  


