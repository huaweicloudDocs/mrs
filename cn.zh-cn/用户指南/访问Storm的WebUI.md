# 访问Storm的WebUI<a name="ZH-CN_TOPIC_0173178131"></a>

## 操作场景<a name="seb49c466f7844f689d9ea577a085ca8b"></a>

用户可以通过Storm的WebUI，在图形化界面使用Storm。仅启用Kerberos认证的流集群支持Storm WebUI功能。

## 前提条件<a name="s5e180c6a1e264422a14ddfca7e340a74"></a>

-   获取用户“admin“帐号密码。“admin“密码在创建MRS集群时由用户指定。
-   使用其他用户访问Storm WebUI，需要用户属于“storm“或“stormadmin“用户组。

## 操作步骤<a name="s7dd270065b604b34a88e5f26b90b06b7"></a>

1.  登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0207903633.png)进行IAM用户同步）。  
    >-   针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“Storm“，在“Storm 概述“的“Storm WebUI“，单击任意一个UI链接，打开Storm的WebUI。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >第一次访问Storm WebUI，需要在浏览器中添加站点信任以继续打开页面。  

    Storm的WebUI支持查看以下信息：

    -   Storm集群汇总信息
    -   Nimbus汇总信息
    -   拓扑汇总信息
    -   Supervisor汇总信息
    -   Nimbus配置信息


## 相关任务<a name="s6d834aa47c5a4b47a4ecc5428612ae71"></a>

**查看拓扑详细信息**

1.  访问Storm WebUI。
2.  在“Topology Summary“单击拓扑的名称，可以查看指定拓扑的详细信息、拓扑状态、Spouts信息、Bolts信息和拓扑配置。

