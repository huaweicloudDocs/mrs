# 安装Flume客户端<a name="ZH-CN_TOPIC_0069282319"></a>

## 操作场景<a name="zh-cn_topic_0066459130_section61077795164654"></a>

使用Flume搜集日志时，需要在日志主机上安装Flume客户端。用户可以创建一个新的ECS并安装Flume客户端。

## 前提条件<a name="zh-cn_topic_0066459130_section46180360164835"></a>

-   已创建包含Flume组件的流集群。
-   日志主机需要与MRS集群在相同的VPC和子网。具体请参见[在虚拟私有云的其他节点使用客户端](在虚拟私有云的其他节点使用客户端.md)。
-   已获取日志主机的登录方式。

## 操作步骤<a name="zh-cn_topic_0066459130_section11276049165016"></a>

1.  根据前提条件，创建一个满足要求的弹性云服务器。
2.  参见[访问开源组件UI界面](访问开源组件UI界面.md#ZH-CN_TOPIC_0071958187)访问MRS Manager，选择“服务管理  \>  Flume\>下载客户端“。
    1.  在“客户端类型“选择“完整客户端“。
    2.  在“下载路径“选择“远端主机“。
    3.  将“主机IP“设置为ECS的IP地址，设置“主机端口“为“22“，并将“存放路径“设置为“/home/linux“。
        -   如果使用SSH登录ECS的默认端口“22“被修改，请将“主机端口“设置为新端口。
        -   “存放路径“最多可以包含256个字符。

    4.  针对MRS1.6.2版本（不包含）前的集群，将“登录用户“设置为“linux“。针对MRS1.6.2版本（包含）及以后的集群，“登录用户“设置为“root“。

        如果使用其他用户，请确保该用户对保存目录拥有读取、写入和执行权限。

    5.  在“SSH私钥“选择并上传创建ECS时使用的密钥文件。
    6.  单击“确定“开始生成客户端文件。

        界面显示以下提示信息表示客户端包已经成功保存。

        ```
        下载客户端文件到远端主机成功。
        ```


3.  单击“实例“，查看任意一个Flume实例和两个MonitorServer实例的“业务IP“。
4.  使用VNC方式，登录弹性云服务器。参见[远程登录（VNC方式）](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0093263548.html)\)。

    所有镜像均支持Cloud-init特性。针对MRS1.6.2版本（不包含）前的集群，Cloud-init预配置的用户名“linux”，密码为“cloud.1234”，如果用户修改了默认密码请使用新密码。针对MRS1.6.2版本（包含）及以后的集群，Cloud-init预配置的用户名“root”，密码为创建集群时设置的密码。参见弹性云服务器《常见问题》的**全面支持Cloud-init特性后，弹性云服务器的登录方法**章节。首次登录建议修改。

5.  在弹性云服务器，切换到**root**用户，并将安装包复制到目录“/opt“。

    **sudo su - root**

    **cp /home/linux/MRS\_Flume\_Client.tar /opt**

6.  在“/opt“目录执行以下命令，解压压缩包获取校验文件与客户端配置包。

    **tar -xvf MRS\_Flume\_Client.tar**

7.  执行以下命令，校验文件包。

    **sha256sum -c MRS\_Flume\_ClientConfig.tar.sha256**

    界面显示如下信息，表明文件包校验成功：

    ```
    MRS_Flume_ClientConfig.tar: OK
    ```

8.  执行以下命令，解压“MRS\_Flume\_ClientConfig.tar“。

    **tar -xvf MRS\_Flume\_ClientConfig.tar**

9.  执行以下命令，安装客户端运行环境到新的目录，例如“/opt/Flumeenv“。安装时自动生成目录。

    **sh /opt/MRS\_Flume\_ClientConfig/install.sh /opt/Flumeenv**

    查看安装输出信息，如有以下结果表示客户端运行环境安装成功：

    ```
    Components client installation is complete.
    ```

10. 执行以下命令，配置环境变量。

    **source /opt/Flumeenv/bigdata\_env**

11. 执行以下命令，解压Flume客户端。

    **cd /opt/MRS\_Flume\_ClientConfig/Flume**

    **tar -xvf FusionInsight-Flume-1.6.0.tar.gz**

12. 执行以下命令，查看当前用户密码是否过期。

    **chage -l root**

    “Password expires“时间早于当前则表示过期。此时需要修改密码，或执行**chage -M -1 root**设置密码为未过期状态。

13. 执行以下命令，安装Flume客户端到新目录，例如“/opt/FlumeClient“。安装时自动生成目录。

    **sh /opt/MRS\_Flume\_ClientConfig/Flume/install.sh -d /opt/FlumeClient -f  _MonitorServer实例__的业务IP地址_  -c Flume配置文件路径 -l /var/log/ -e  _Flume__的业务IP地址_** **-n  _Flume__客户端名称_**

    各参数说明如下：

    -   “-d”：表示Flume客户端安装路径。
    -   “-f”：可选参数，表示两个MonitorServer角色的业务IP地址，中间用英文逗号分隔，若不设置则Flume客户端将不向MonitorServer发送告警信息，同时在MRS Manager界面上看不到该客户端的相关信息。
    -   “-c”：可选参数，表示Flume客户端在安装后默认加载的配置文件“properties.properties“。如不添加参数，默认使用客户端安装目录的“fusioninsight-flume-1.6.0/conf/properties.properties”。客户端中配置文件为空白模板，根据业务需要修改后Flume客户端将自动加载。
    -   “-l”：可选参数，表示日志目录，默认值为“/var/log/Bigdata”。
    -   “-e”：可选参数，表示Flume实例的业务IP地址，主要用于接收客户端上报的监控指标信息。
    -   “-n”：可选参数，表示自定义的Flume客户端的名称。
    -   IBM的JDK不支持“-Xloggc”，需要修改“flume/conf/flume-env.sh”，将“-Xloggc”修改为“-Xverbosegclog”，若JDK为32位，“-Xmx”不能大于3.25GB。
    -   “flume/conf/flume-env.sh”中，“-Xmx”默认为4GB。若客户端机器内存过小，可调整为512M甚至1GB。

    例如执行：**sh install.sh -d /opt/FlumeClient**

    系统显示以下结果表示客户端运行环境安装成功：

    ```
    install flume client successfully.
    ```


