# 修改Kerberos管理员密码<a name="ZH-CN_TOPIC_0174499492"></a>

## 操作场景<a name="zh-cn_topic_0040967542_section293727014453"></a>

该任务指导用户定期修改MRS集群Kerberos管理员“kadmin”的密码，以提升系统运维安全性。

## 前提条件<a name="zh-cn_topic_0040967542_section64718576144528"></a>

已在Master1节点准备客户端。

## 操作步骤<a name="zh-cn_topic_0040967542_section65388622144546"></a>

1.  登录Master1节点。
2.  （可选）若想要使用omm用户修改密码，请执行以下命令切换用户。

    **sudo su - omm**

3.  执行以下命令，切换到客户端目录“/opt/client”。

    **cd /opt/client**

4.  执行以下命令，配置环境变量。

    **source bigdata\_env**

5.  执行以下命令，修改**kadmin/admin**密码。此操作对所有服务器生效。

    **kpasswd kadmin/admin**

    MRS 1.6.2及以后集群中，默认的密码复杂度要求：

    -   密码字符长度至少8位。
    -   至少需要包含大写字母、小写字母、数字、空格、特殊字符'\~!@\#$%^&\*\(\)-\_=+\\|\[\{\}\];:'",<.\>/?中的3种类型字符。
    -   不能与用户名或倒序的用户名相同。


