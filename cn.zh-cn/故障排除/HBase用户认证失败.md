# HBase用户认证失败<a name="ZH-CN_TOPIC_0168547217"></a>

## 用户问题<a name="section18305143583116"></a>

HBase用户认证失败

## 问题现象<a name="section117424454313"></a>

客户侧HBase用户认证失败，报错信息如下：

```
2019-05-13 10:53:09,975 ERROR [localhost-startStop-1] huaweiConfig.LoginUtil: login failed with hbaseuser and /usr/local/linoseyc/hbase-tomcat/webapps/bigdata_hbase/WEB-INF/classes/user.keytab.
2019-05-13 10:53:09,975 ERROR [localhost-startStop-1] huaweiConfig.LoginUtil: perhaps cause 1 is (wrong password) keytab file and user not match, you can kinit -k -t keytab user in client server to check.
2019-05-13 10:53:09,975 ERROR [localhost-startStop-1] huaweiConfig.LoginUtil: perhaps cause 2 is (clock skew) time of local server and remote server not match, please check ntp to remote server.
2019-05-13 10:53:09,975 ERROR [localhost-startStop-1] huaweiConfig.LoginUtil: perhaps cause 3 is (aes256 not support) aes256 not support by default jdk/jre, need copy local_policy.jar and US_export_policy.jar from remote server in path /opt/huawei/Bigdata/jdk/jre/lib/security.
2019-05-13 10:53:09,975 ERROR [localhost-startStop-1] huaweiConfig.LoginUtil:
```

## 原因分析<a name="section1237061220324"></a>

客户使用的JDK中的jar包与MRS服务认证的jar包版本不一致。

## 处理步骤<a name="section1197815121946"></a>

1.  以root登录集群Master1节点。
2.  执行如下命令，查看MRS服务认证的jar包。

    **/opt/share/local\_policy/local\_policy.jar**

    **/opt/Bigdata/jdk1.8.0\_172/jre/lib/security/local\_policy.jar**

3.  执行**wget** **-P $path**命令，将步骤2中的jar包下载到本地。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >$path为需要下载的本地路径。例如，/opt/share/local\_policy/local\_policy.jar  

4.  将下载的jar包替换到本地JDK目录/opt/huawei/Bigdata/jdk/jre/lib/security。
5.  执行**cd /opt/client/HBase/hbase/bin**  命令，进入到HBase的bin目录。
6.  执行**sh  start-hbase.sh**命令，重启HBase组件。

