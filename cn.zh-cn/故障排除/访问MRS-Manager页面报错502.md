# 访问MRS Manager页面报错502<a name="mrs_03_0255"></a>

## 用户问题<a name="section18305143583116"></a>

访问“集群管理页面”地址打开显示502错误，如何修复？

## 问题现象<a name="section117424454313"></a>

MRS 1.7.2未开启Kerberos认证的普通集群，访问MRS Manager页面报错如下图：

**图 1**  访问MRS Manager<a name="fig95331633111015"></a>  
![](figures/访问MRS-Manager.png "访问MRS-Manager")

**图 2**  MRS Manager页面报错<a name="fig1423646191012"></a>  
![](figures/MRS-Manager页面报错.png "MRS-Manager页面报错")

## 原因分析<a name="section1237061220324"></a>

由于MRS的域名由console-emr变更为mrs 导致MRS 1.8.0之前的普通集群访问MRS Manager的链接有误。

## 处理步骤<a name="section7778103963815"></a>

1.  以root用户登录到所有Master节点。
2.  进入**/opt/knox/conf/**目录，找到ext.properties文件。

    ![](figures/zh-cn_image_0267924161.png)

3.  修改所有Master节点中的ext.properties配置中的“console-emr”为 “mrs”。

    ![](figures/zh-cn_image_0267923197.png)

4.  进入**/opt/knox/bin/**  目录，并执行**su - omm**命令切换到 omm 用户。
5.  执行脚本**restart-knox.sh**  重启knox 服务。
6.  再次访问MRS Manager页面即可正常跳转。

