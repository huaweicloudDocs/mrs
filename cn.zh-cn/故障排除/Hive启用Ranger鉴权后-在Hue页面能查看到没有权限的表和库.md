# Hive启用Ranger鉴权后，在Hue页面能查看到没有权限的表和库<a name="mrs_03_0300"></a>

## 用户问题<a name="zh-cn_topic_0135447912_section18305143583116"></a>

Hive启用Ranger鉴权后，在Hue页面能查看到没有权限的表和库

## 问题现象<a name="zh-cn_topic_0135447912_section117424454313"></a>

普通集群（未开启Kerberos认证）中，Hive启用Ranger鉴权后，在Hue页面能查看到没有权限的表和库。

## 原因分析<a name="zh-cn_topic_0135447912_section1237061220324"></a>

Hive启用Ranger鉴权后，默认的Hive策略中有2个关于database的public组策略， 所有用户都属于public组，默认给public组配有default数据库的创表和所有其他数据库的**create**权限，因此默认所有的用户都有**show databases**和**show tables**的权限，如果不想让某些用户有**show databases**和**show tables**权限，可在Ranger WEBUI中删除该默认public组策略，并赋予需要查看的用户权限，具体请参考处理步骤。

## 处理步骤<a name="section1215965619169"></a>

1.  登录Ranger WebUI界面。
2.  在“Service Manager”区域内，单击Hive组件名称，进入Hive组件安全访问策略列表页面。
3.  分别单击“all - database”和“default database tables columns”策略所在行的![](figures/zh-cn_image_0000001181379571.png)按钮。
4.  删除“public”组策略。

    **图 1**  all - database策略<a name="fig97472055874"></a>  
    ![](figures/all---database策略.png "all---database策略")

    **图 2**  default database tables columns策略<a name="fig02264683"></a>  
    ![](figures/default-database-tables-columns策略.png "default-database-tables-columns策略")

5.  在Hive组件安全访问策略列表页面，单击“Add New Policy”为相关用户或者用户组添加资源访问策略，具体请参考[配置组件权限策略](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_1851.html)。

