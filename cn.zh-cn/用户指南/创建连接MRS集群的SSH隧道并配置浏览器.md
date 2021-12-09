# 创建连接MRS集群的SSH隧道并配置浏览器<a name="mrs_01_0363"></a>

## 操作场景<a name="s4a7e0d6307154cbf9d34b23018da2c34"></a>

用户和MRS集群处于不同的网络中，需要创建一个SSH隧道连接，使用户访问站点的数据请求，可以发送到MRS集群并动态转发到对应的站点。

MAC系统暂不支持该功能访问MRS，请参考[通过弹性公网IP访问](通过弹性公网IP访问.md)内容访问MRS。

## 前提条件<a name="s843ccc0a68604f93818fce6344af36fc"></a>

-   准备一个SSH客户端用于创建SSH隧道，例如使用开源SSH客户端Git。请下载并安装。
-   已创建好集群，并准备pem格式的密钥文件或创建集群时的密码。
-   用户本地环境可以访问互联网。

## 操作步骤<a name="seb617a071f984232a97e461b5bfffe08"></a>

1.  登录MRS管理控制台，选择“集群列表  \>  现有集群“。
2.  单击指定名称的MRS集群。

    记录集群的“安全组” 。

3.  为集群Master节点的安全组添加一条需要访问MRS集群的IP地址的入规则，允许指定来源的数据访问端口“22“。

    具体请参见[创建安全组](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748715.html)。

4.  查询集群的主管理节点，具体请参考[如何确认Manager的主备管理节点](如何确认Manager的主备管理节点.md)。
5.  为集群的主管理节点绑定一个弹性IP地址。

    具体请参见[为弹性云服务器申请和绑定弹性公网IP](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748738.html)。

6.  在本地启动Git Bash，执行以下命令登录集群的主管理节点：**ssh root@_弹性IP地址_**或者**ssh -i** _**密钥文件路径**_ **root@**_**弹性IP地址**_
7.  执行以下命令查看数据转发配置：

    **cat /etc/sysctl.conf | grep net.ipv4.ip\_forward**

    -   系统查询到“net.ipv4.ip\_forward=1“表示已配置转发，则请执行[9](#l443dc566475c459399c4e15787485276)。
    -   系统查询到“net.ipv4.ip\_forward=0“表示未配置转发，则请执行[8](#l116ba5c37fe940bc8218c6e3989bfa2a)。
    -   系统查询不到“net.ipv4.ip\_forward“参数表示该参数未配置，则请执行以下命令后再执行[9](#l443dc566475c459399c4e15787485276)。

        echo "net.ipv4.ip\_forward = 1" \>\> /etc/sysctl.conf

8.  <a name="l116ba5c37fe940bc8218c6e3989bfa2a"></a>修改节点转发配置：
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

9.  <a name="l443dc566475c459399c4e15787485276"></a>执行以下命令查看浮动IP地址：

    **ifconfig**

    系统显示的“eth0:FI\_HUE“表示为Hue的浮动IP地址，“eth0:wsom“表示Manager浮动IP地址，请记录“inet“的实际参数值。

    然后退出登录：**exit**

10. <a name="lcf3e5d4b24e645bdbb9a0100a0dca09d"></a>在本地机器执行以下命令创建支持动态端口转发的SSH隧道：

    使用命令**ssh -i** **_密钥文件路径_  -v -ND** _**本地端口地址**_ **root@_弹性IP地址_**或者**_ssh -v -ND 本地端口地址 root@弹性IP地址_**，然后输入创建集群时的密码。

    其中，“本地端口地址“需要指定一个用户本地环境未被使用的端口，建议选择8157。

    创建后的SSH隧道，通过“-D“启用动态端口转发功能。默认情况下，动态端口转发功能将启动一个SOCKS代理进程并侦听用户本地端口，端口的数据将由SSH隧道转发到集群的主管理节点。

11. 执行如下命令配置浏览器代理。
    1.  进入本地Google Chrome浏览器客户端安装目录。
    2.  <a name="l2d621fbf73a04b28a135923e3a74a4f3"></a>按住“shift+鼠标右键”，选择“在此处打开命令窗口”，打开CMD窗口后输入如下命令：

        **chrome --proxy-server="socks5://localhost:8157" --host-resolver-rules="MAP \* 0.0.0.0 , EXCLUDE localhost" --user-data-dir=c:/tmppath --proxy-bypass-list="\*google\*com,\*gstatic.com,\*gvt\*.com,\*:80"**

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   8157为[10](#lcf3e5d4b24e645bdbb9a0100a0dca09d)中配置的本地代理端口。
        >-   若本地操作系统为Windows 10，请打开Windows操作系统“开始”菜单，输入**cmd**命令，打开一个命令行窗口执行[11.b](#l2d621fbf73a04b28a135923e3a74a4f3)中的命令。若该方式不能成功，请打开Windows操作系统“开始”菜单后，在搜索框中输入并执行[11.b](#l2d621fbf73a04b28a135923e3a74a4f3)中的命令。


12. 在新弹出的浏览器地址栏，输入Manager的访问地址。

    Manager访问地址形式为**https://_Manager浮动__IP地址_:28443/web。**

    访问启用Kerberos认证的集群时，需要输入MRS集群的用户名和密码，例如“admin”用户。未启用Kerberos认证的集群则不需要。

    第一次访问时，请根据浏览器提示，添加站点信任以继续打开页面。

13. 准备站点的访问地址。
    1.  参考[Web站点一览](开源组件Web站点.md#sd893f53bb0b2400a8fe79f43dd2b7cf8)，获取Web站点的地址格式及对应的角色实例。
    2.  单击“服务管理“。
    3.  单击指定的服务名称，例如HDFS。
    4.  单击“实例“，查看NameNode的主角色实例“NameNode\(主\)“的“业务IP“。

14. 在浏览器输入访问Web站点真实地址并访问。
15. 退出访问Web站点时，请终止并关闭SSH隧道。

