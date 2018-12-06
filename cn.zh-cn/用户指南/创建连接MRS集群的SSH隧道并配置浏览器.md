# 创建连接MRS集群的SSH隧道并配置浏览器<a name="ZH-CN_TOPIC_0071958189"></a>

## 操作场景<a name="zh-cn_topic_0069869152_section10177076151413"></a>

用户和MRS集群处于不同的网络中，需要创建一个SSH隧道连接，使用户访问站点的数据请求，可以发送到MRS集群并动态转发到对应的站点。

## 前提条件<a name="zh-cn_topic_0069869152_section35119877151559"></a>

-   准备一个SSH客户端用于创建SSH隧道，例如使用开源SSH客户端Git。请下载并安装。
-   已创建好集群，并准备pem格式的密钥文件或创建集群时的密码。
-   用户本地环境可以访问互联网。

## 操作步骤<a name="zh-cn_topic_0069869152_section38467281153156"></a>

1.  登录MRS管理控制台，选择“集群列表  \>  现有集群“。
2.  单击指定名称的MRS集群。

    记录集群Master节点的“默认安全组” 。

3.  为集群的Master节点的安全组添加一条入规则，允许指定来源的数据访问端口“22“。

    具体请参见“虚拟私有云  \>  用户指南  \>  安全性  \>  安全组  \>  为安全组添加安全组规则“。

4.  为集群的Master2节点绑定一个弹性IP地址。

    具体请参见“虚拟私有云  \>  用户指南  \>  网络组件  \>  弹性IP  \>  为弹性云服务器申请和绑定弹性IP“。

5.  在本地启动Git Bash，执行以下命令登录Master2节点：
    -   针对MRS1.6.2版本（不包含）前的集群，登录方式：**ssh -i** _**密钥文件路径**_ **linux@**_**弹性IP地址**_
    -   针对MRS1.6.2版本（包含）及以后的集群，登录方式：**ssh root@_弹性IP地址_**或者**ssh -i** _**密钥文件路径**_ **root@**_**弹性IP地址**_

6.  执行以下命令查看数据转发配置：

    **cat /etc/sysctl.conf | grep net.ipv4.ip\_forward**

    -   系统查询到“net.ipv4.ip\_forward=1“表示已配置转发，则请执行[8](#zh-cn_topic_0069869152_li57701365155627)。
    -   系统查询到“net.ipv4.ip\_forward=0“表示未配置转发，则请执行[7](#zh-cn_topic_0069869152_li6061790213580)。
    -   系统查询不到“net.ipv4.ip\_forward“参数表示该参数未配置，则请执行以下命令后再执行[8](#zh-cn_topic_0069869152_li57701365155627)。

        echo net.ipv4.ip\_forward = 1\>\>/etc/sysctl.conf


7.  <a name="zh-cn_topic_0069869152_li6061790213580"></a>修改节点转发配置：
    1.  执行以下命令切换**root**用户：

        **sudo su - root**

    2.  执行以下命令，修改转发配置：

        **echo 1 \> /proc/sys/net/ipv4/ip\_forward**

        **sed -i "s/net.ipv4.ip\_forward=0/net.ipv4.ip\_forward = 1/g" /etc/sysctl.conf**

        **sysctl -w net.ipv4.ip\_forward=1**

    3.  执行以下命令，修改sshd配置文件：

        **vi /etc/ssh/sshd\_config**

        按I进入编辑模式，查找“AllowTcpForwarding“和“GatewayPorts“，并删除注释符号，修改内容如下，然后保存并退出：

        ```
        AllowTcpForwarding yes
        GatewayPorts yes
        ```

    4.  执行以下命令，重启sshd服务：

        **service sshd restart**


8.  <a name="zh-cn_topic_0069869152_li57701365155627"></a>执行以下命令查看浮动IP地址：

    **ifconfig**

    系统显示的“eth0:FI\_HUE“表示为Hue的浮动IP地址，“eth0:wsom“表示MRS Manager浮动IP地址，请记录“inet“的实际参数值。

    然后退出登录：**exit**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果在Master2节点无法查询到Hue的浮动IP地址，请切换到Master1节点查询并记录。  

9.  <a name="zh-cn_topic_0069869152_li5952361416647"></a>执行以下命令创建支持动态端口转发的SSH隧道：

    -   针对MRS1.6.2版本（不包含）前的集群，使用命令**ssh -i** **_密钥文件路径_  -v -ND** _**本地端口地址**_ **linux@_弹性IP地址_**
    -   针对MRS1.6.2版本（包含）及以后的集群，使用命令**ssh -i** **_密钥文件路径_  -v -ND** _**本地端口地址**_ **root@_弹性IP地址_**或者**_ssh -v -ND 本地端口地址 root@弹性IP地址_**，然后输入创建集群时的密码。

    其中，“本地端口地址“需要指定一个用户本地环境未被使用的端口，建议选择8157。

    创建后的SSH隧道，通过“-D“启用动态端口转发功能。默认情况下，动态端口转发功能将启动一个SOCKS代理进程并侦听用户本地端口，端口的数据将由SSH隧道转发到Master2节点。

10. 执行如下命令配置浏览器代理。
    1.  进入本地Google Chrome浏览器客户端安装目录。
    2.  按住“shift+鼠标右键”，选择“在此处打开命令窗口”，输入如下命令：

        **chrome --proxy-server="socks5://localhost:8157" --host-resolver-rules="MAP \* 0.0.0.0 , EXCLUDE localhost" --user-data-dir=c:/tmppath --proxy-bypass-list="\*google\*com,\*gstatic.com,\*gvt\*.com,\*:80",**

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >8157为[9](#zh-cn_topic_0069869152_li5952361416647)中配置的本地代理端口。  


11. 在浏览器地址栏，输入MRS Manager的访问地址。

    Manager访问地址形式为**https://_MRS Manager浮动__IP地址_:28443/web。**

    访问启用Kerberos认证的集群时，需要输入MRS集群的用户名和密码，例如“admin”用户。未启用Kerberos认证的集群则不需要。

    第一次访问时，请根据浏览器提示，添加站点信任以继续打开页面。

12. 准备站点的访问地址。
    1.  参考[Web站点一览](开源组件Web站点.md#zh-cn_topic_0069869151_section11481629144654)，获取Web站点的地址格式及对应的角色实例。
    2.  单击“服务管理“。
    3.  单击指定的服务名称，例如HDFS。
    4.  单击“实例“，查看NameNode的主角色实例“NameNode\(主\)“的“业务IP“。

13. 在浏览器输入访问Web站点真实地址并访问。
14. 退出访问Web站点时，请终止并关闭SSH隧道。

