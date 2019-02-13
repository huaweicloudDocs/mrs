# 访问Hue的WebUI<a name="ZH-CN_TOPIC_0050661078"></a>

## 操作场景<a name="zh-cn_topic_0049949144_section946489710657"></a>

-   针对MRS 1.8.1之前的集群，MRS集群启用Kerberos认证且安装Hue组件后，用户可以通过Hue的WebUI，在图形化界面使用Hadoop与Hive。
-   针对MRS 1.8.1及之后的集群，MRS集群安装Hue组件后，用户可以通过Hue的WebUI，在图形化界面使用Hadoop与Hive。

该任务指导用户在MRS集群中打开Hue的WebUI。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   Internet Explorer浏览器可能存在兼容性问题，建议更换兼容的浏览器访问Hue WebUI，例如Google Chrome浏览器50版本。  
>-   MRS 1.8.1之前且未启用Kerberos认证的集群，访问Hue的WebUI请参考[访问开源组件UI界面](访问开源组件UI界面.md)。  

## 对系统的影响<a name="zh-cn_topic_0049949144_section61564112104752"></a>

第一次访问MRS Manager和Hue WebUI，需要在浏览器中添加站点信任以继续打开Hue WebUI。

## 前提条件<a name="zh-cn_topic_0049949144_section66680320101755"></a>

启用Kerberos认证时，MRS集群管理员已分配用户使用Hive的权限。具体请参见[创建用户](创建用户-安全.md)。例如创建一个人机用户“hueuser“，并加入“hive“组和“System\_administrator“角色。

## 操作步骤<a name="zh-cn_topic_0049949144_section5792367715546"></a>

1.  访问MRS Manager。

    具体请参见[访问MRS Manager](访问MRS-Manager.md)或[访问支持Kerberos认证的Manager](访问支持Kerberos认证的Manager.md)。

2.  在Manager选择“服务管理  \>  Hue“，在“Hue概述“的“Hue WebUI“，单击“Hue \(主\)“，打开Hue的WebUI。

    Hue的WebUI支持以下功能：

    -   使用“Query Editors“执行Hive的查询语句。需要MRS集群已安装Hive。
    -   使用“Data Browsers“管理Hive中的表。需要MRS集群已安装Hive。
    -   使用“文件浏览器“查看HDFS中的目录和文件。需要MRS集群已安装HDFS。
    -   使用“Job Browser“查看MRS集群中所有作业。需要MRS集群已安装YARN。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   用户获取Hue WebUI的访问地址后，可以给其他无法访问Manager的用户用于访问Hue WebUI。  
    >-   在Hue的WebUI操作但不操作MRS Manager页面，重新访问Manager时需要输入已登录的帐号密码。  


