# 通过Windows弹性云服务器访问<a name="ZH-CN_TOPIC_0173264860"></a>

MRS支持通过Windows弹性云服务器访问开源组件Web站点。该方式操作较为复杂，推荐不支持EIP功能的MRS集群使用（MRS 1.8.0之前版本开启Kerberos认证的安全集群）。

1.  在MRS管理控制台，单击“集群列表“。
2.  在  “现有集群“  列表中，单击指定的集群名称。

    记录集群的“可用区“、“虚拟私有云“、“集群控制台地址“、“安全组“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >集群控制台地址获取方式：远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示集群控制台地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到集群控制台地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。  

3.  在ECS管理控制台，创建一个新的弹性云服务器。

    -   弹性云服务器的“可用区“、“虚拟私有云“、“安全组“，需要和待访问集群的配置相同。
    -   选择一个Windows系统的公共镜像。例如，选择一个标准镜像“Windows Server 2012 R2 Standard 64bit\(40GB\)“。
    -   其他配置参数详细信息，请参见[购买弹性云服务器](https://support.huaweicloud.com/qs-ecs/zh-cn_topic_0021831611.html)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果ECS的安全组和MRS集群的“安全组“不同，用户可以选择以下任一种方法修改配置：  
    >-   将ECS的安全组修改为MRS集群的安全组，请参见[更改安全组](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0093492517.html)。  
    >-   在集群Master节点和Core节点的安全组中添加两条安全组规则使ECS可以访问集群，“协议“需选择为“TCP“，“端口“需分别选择“28443“和“20009“。请参见[创建安全组](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748715.html)。  

4.  在VPC管理控制台，申请一个弹性IP地址，并与ECS绑定。

    具体请参见[为弹性云服务器申请和绑定弹性公网IP](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748738.html)。

5.  登录弹性云服务器。

    登录ECS需要Windows系统的帐号、密码，弹性IP地址以及配置安全组规则。具体请参见[Windows云服务器登录方式](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0092494943.html)。

6.  在Windows的远程桌面中，打开浏览器访问Manager。

    例如Windows 2012操作系统可以使用Internet Explorer 11。

    Manager访问地址形式为**https://_集群控制台地址_:28443/web**。访问时需要输入MRS集群的用户名和密码，例如“admin“用户。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   集群控制台地址：远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示集群控制台地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到集群控制台地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。  
    >-   如果使用其他MRS集群用户访问Manager，第一次访问时需要修改密码。新密码需要满足集群当前的用户密码复杂度策略。请咨询管理员。  
    >-   默认情况下，在登录时输入5次错误密码将锁定用户，需等待5分钟自动解锁。  

7.  请参考[开源组件Web站点](开源组件Web站点.md)页面提供的站点地址访问开源组件Web站点。

