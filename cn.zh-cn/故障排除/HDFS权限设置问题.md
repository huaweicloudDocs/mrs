# HDFS权限设置问题<a name="mrs_03_0049"></a>

## 用户问题<a name="section18305143583116"></a>

在使用MRS服务的时候，某个用户可以在其他用户的HDFS目录下面删除或者创建文件。

## 问题现象<a name="section117424454313"></a>

在使用MRS服务时，某个用户可以在其他用户的HDFS目录下面删除或者创建文件。

## 原因分析<a name="section1237061220324"></a>

客户配置的用户具有ficommon组的权限，即为超级用户组，所以可以对HDFS任意操作。需要移除用户的ficommon组权限。

## 处理步骤<a name="section716005111116"></a>

1.  以root用户登录集群的Master节点。
2.  执行**id $\{用户名\}**命令，显示用户组信息，确认是否有ficommon组权限。

    如果存在ficommon组权限，请执行[3](#li6934412122819)。如果不存在，请联系技术服务。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**$\{用户名\}**：出现HDFS权限设置问题的用户名。

3.  <a name="li6934412122819"></a>执行**gpasswd -d $\{用户名\} ficommon**命令，删除该用户的ficommon组权限。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**$\{用户名\}**：出现HDFS权限设置问题的用户名。

4.  执行成功后，登录Manager修改参数。

    MRS Manager界面操作（适用MRS 3.x之前版本）：

    1.  登录MRS Manager，在MRS Manager页面，选择“服务管理 \> HDFS \> 服务配置”。
    2.  “参数类别“选择“全部配置“，在搜索框中输入“dfs.permissions.enabled“，修改为“true“。
    3.  修改完成后，单击“保存配置“，并重启HDFS服务。

    FusionInsight Manager界面操作（适用MRS 3.x之前版本）：

    1.  登录FusionInsight Manager。选择“集群 \> 服务 \> HDFS \> 配置 \> 全部配置”。
    2.  在搜索框中输入“dfs.permissions.enabled“，修改为“true“。
    3.  修改完成后，单击“保存“，并重启HDFS服务。

    MRS集群详情页操作（适用MRS 1.9.2及之后版本）：

    1.  登录MRS控制台，选择“组件管理 \> HDFS \> 服务配置”。
    2.  “参数类别“选择“全部配置“，在搜索框中输入“dfs.permissions.enabled“，修改为“true“。
    3.  修改完成后，单击“保存配置“，并重启HDFS服务。


