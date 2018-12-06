# 访问Storm的WebUI<a name="ZH-CN_TOPIC_0057181203"></a>

## 操作场景<a name="zh-cn_topic_0053993335_section946489710657"></a>

用户可以通过Storm的WebUI，在图形化界面使用Storm。仅启用Kerberos认证的流集群支持Storm WebUI功能。

## 前提条件<a name="zh-cn_topic_0053993335_section66680320101755"></a>

-   获取用户“admin“帐号密码。“admin“密码在创建MRS集群时由用户指定。
-   使用其他用户访问Storm WebUI，需要用户属于“storm“或“stormadmin“用户组。

## 操作步骤<a name="zh-cn_topic_0053993335_section5792367715546"></a>

1.  访问MRS Manager。
2.  在Manager选择“服务管理  \>  Storm“，在“Storm 概述“的“Storm WebUI“，单击任意一个UI链接，打开Storm的WebUI。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >第一次访问Storm WebUI，需要在浏览器中添加站点信任以继续打开页面。  

    Storm的WebUI支持查看以下信息：

    -   Storm集群汇总信息
    -   Nimbus汇总信息
    -   拓扑汇总信息
    -   Supervisor汇总信息
    -   Nimbus配置信息


## 相关任务<a name="zh-cn_topic_0053993335_section49999596115616"></a>

**查看拓扑详细信息**

1.  访问Storm WebUI。
2.  在“Topology Summary“单击拓扑的名称，可以查看指定拓扑的详细信息、拓扑状态、Spouts信息、Bolts信息和拓扑配置。

