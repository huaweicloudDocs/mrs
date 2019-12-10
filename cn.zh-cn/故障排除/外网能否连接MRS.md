# 外网能否连接MRS<a name="ZH-CN_TOPIC_0169495358"></a>

## 用户问题<a name="zh-cn_topic_0135447915_section18305143583116"></a>

外网能否连接MRS

## 问题现象<a name="zh-cn_topic_0135447915_section117424454313"></a>

集群创建完成后，外网无法访问集群的MRS Manager界面。

## 原因分析<a name="zh-cn_topic_0135447915_section1237061220324"></a>

-   需要对MRS节点绑定弹性IP才可访问
-   需要添加安全组规则，放开9022端口
-   集群的版本号必须是1.8.0及之上版本才支持外网连接

## 处理步骤<a name="zh-cn_topic_0135447915_section520813413313"></a>

1.  登录MRS的console页面，在现有集群列表中找到需要访问的集群，单击集群名称。
2.  在节点信息中单击需要访问的节点名称，选择“弹性公网IP“  \>  “绑定弹性公网IP“。
3.  在“绑定弹性公网“IP页面，“选择网卡“下拉框中选择需要绑定的网卡，“选择弹性公网IP”中选择需要绑定的弹性公网IP，单击“确定“。
4.  弹性IP绑定成功后，需要将安全组规则中9022端口放开。

    选择“安全组”页签，单击“更改安全组”。

    可以选择添加已有的安全组，或者单击“新建安全组“，进入安全组管理界面进行创建，添加用户访问公网IP地址9022端口的安全组规则。具体操作可以参考[配置安全组规则](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0030878383.html)。

5.  添加成功后，可通过_https://弹性ip:9022/mrsmanager/_访问MRS。如果还未能访问，请联系技术支持。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果弹性IP列表中没有可选IP，可以进行购买，操作方法请参见[为弹性云服务器申请和绑定弹性公网IP](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748738.html)。  
    >-   组件端口可以参考[开源组件端口列表](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0504.html)。  


