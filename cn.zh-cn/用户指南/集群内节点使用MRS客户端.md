# 集群内节点使用MRS客户端<a name="ZH-CN_TOPIC_0173178483"></a>

## 操作场景<a name="section65278330165558"></a>

用户需要在集群的Master节点或者Core节点使用客户端。

## 操作步骤<a name="section51771356165739"></a>

-   在Master节点使用客户端。
    1.  在已安装客户端的主管理节点，即Master节点，执行**sudo su - omm**命令切换用户。执行以下命令切换到客户端目录：

        **cd /opt/client**

    2.  执行以下命令配置环境变量：

        **source bigdata\_env**

    3.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

        **kinit** **_MRS集群用户_**

        例如，**kinit admin**。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >启用Kerberos认证的MRS集群默认创建“admin”用户帐号，用于集群管理员维护集群。  

    4.  直接执行组件的客户端命令。

        例如使用HDFS客户端命令查看HDFS根目录文件，执行**hdfs dfs -ls /**。


-   在Core节点使用客户端。
    1.  <a name="li6130722217153"></a>在主管理节点下载客户端配置文件。
    2.  使用IP地址搜索主管理节点并使用VNC登录主管理节点，具体请参见[登录集群节点](登录集群节点.md)。
    3.  在主管理节点，执行以下命令切换用户。

        **sudo su - omm**

    4.  在MRS管理控制台，查看指定集群“节点管理“页面的“IP“地址。

        记录需使用客户端的Core节点IP地址。

    5.  在主管理节点，执行以下命令，将客户端配置文件压缩包，从主管理节点文件拷贝到当前Core节点：

        **scp -p /tmp/MRS-client/MRS\_Services\_Client.tar** _Core节点的IP地址_**:///opt/client**

    6.  针对MRS1.6.2版本（不包含）前的集群，使用“linux“登录Core节点。针对MRS1.6.2版本（包含）及以后的集群，使用“root“登录Core节点。具体请参见[登录集群节点](登录集群节点.md)。

        针对MRS1.6.2版本（不包含）前的集群，Master节点支持Cloud-Init特性，Cloud-init预配置的用户名“linux“，密码默认为“cloud.1234“，如果用户修改了默认密码请使用新密码。首次登录建议修改。

        针对MRS1.6.2版本（包含）及以后的集群，Master节点支持Cloud-Init特性，Cloud-init预配置的用户名“root“，密码为创建集群时设置的密码。

    7.  执行以下命令切换到客户端目录：

        **cd /opt/client**

    8.  <a name="li7483220165311"></a>执行以下命令，更新客户端配置：

        **sh /opt/client/refreshConfig.sh** _客户端安装目录__ __客户端配置文件压缩包完整路径_

        例如，执行命令：

        **sh refreshConfig.sh /opt/client /opt/client/MRS\_Services\_Client.tar**

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >对于MRS 1.8.5及之后版本集群，步骤[1](#li6130722217153)\~[8](#li7483220165311)的操作也可以参考[更新客户端](更新客户端.md)页面的方法二操作。  

    9.  执行以下命令，切换到客户端目录并配置环境变量：

        **cd /opt/client**

        **source bigdata\_env**

    10. 如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

        **kinit** **_MRS集群用户_**

        例如，**kinit admin**。

    11. 直接执行组件的客户端命令。

        例如使用HDFS客户端命令查看HDFS根目录文件，执行**hdfs dfs -ls /**。



