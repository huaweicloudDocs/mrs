# 修改集群HDFS服务的NameNode RPC端口后，NameNode都变为备状态<a name="ZH-CN_TOPIC_0181149863"></a>

## 用户问题<a name="section18305143583116"></a>

通过页面更改NameNode的RPC端口，随后重启HDFS服务，出现所有NameNode一直是备状态，导致集群异常。

## 问题现象<a name="section117424454313"></a>

所有NameNode都是备状态，导致集群异常。

## 原因分析<a name="section1237061220324"></a>

集群安装启动后，如果修改NameNode的RPC端口，则需要重新格式化Zkfc服务来更新zookeeper上的节点信息。

## 处理步骤<a name="section1910962617165"></a>

1.  登录MRS集群页面，在“现有集群“中，单击对应的集群名称，进入集群详情页面。
2.  单击“集群管理页面“后的“点击查看“，登录到MRS Manager页面。
3.  在MRS Manager页面，选择“服务管理“\>“HDFS“，单击“停止“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >在停止HDFS时，建议不要停止相关服务。  

4.  停止成功后，登录到被修改了RPC端口的Master节点。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果两个Master节点都被修改了RPC端口，则只需登录其中一个修改即可。  

5.  执行**su -omm**命令切换到omm用户。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果是安全集群，需要执行**kinit hdfs**命令进行认证。  

6.  执行如下命令，将环境变量脚本加载到环境中。

    **cd $\{BIGDATA\_HOME\}/MRS\_X.X.X/1\_8\_Zkfc/etc**

    **source $\{BIGDATA\_HOME\}/MRS\_X.X.X/install/FusionInsight-Hadoop-3.1.1/hadoop/sbin/exportENV\_VARS.sh**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >命令中的“MRS\_X.X.X”和“1\_8”根据实际版本而定。  

7.  加载完成后，执行如下命令，格式化Zkfc。

    **cd $\{HADOOP\_HOME\}/bin**

    **./hdfs zkfc -formatZK**

8.  格式化成功后，在MRS Manager页面“重启“HDFS服务。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果更改了NameNode的RPC端口，则之前安装的所有客户端都需要刷新配置文件。  


