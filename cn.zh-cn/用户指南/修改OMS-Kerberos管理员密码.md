# 修改OMS Kerberos管理员密码<a name="ZH-CN_TOPIC_0040967543"></a>

## 操作场景<a name="section10784793144838"></a>

该任务指导用户定期修改MRS集群OMS Kerberos管理员“kadmin”的密码，以提升系统运维安全性。

修改此用户密码将同步修改Kerberos管理员密码。

## 前提条件<a name="section49402977144857"></a>

已在Master1准备客户端。

## 操作步骤<a name="section14433119144919"></a>

1.  登录Master1节点。
2.  执行以下命令切换用户。

    **sudo su - omm**

3.  执行以下命令，切换目录。

    **cd $\{BIGDATA\_HOME\}/om-0.0.1/meta-0.0.1-SNAPSHOT/kerberos/scripts**

4.  执行以下命令，配置环境变量。

    **source component\_env**

5.  执行以下命令，修改kadmin/admin密码。此操作对所有服务器生效。

    **kpasswd kadmin/admin**

    MRS 1.6.2及以后的集群中，默认的密码复杂度要求：

    -   密码字符长度为8～32位。
    -   至少需要包含大写字母、小写字母、数字、空格、特殊字符'\~!@\#$%^&\*\(\)-\_=+\\|\[\{\}\];:'",<.\>/?中的3种类型字符。
    -   不能与用户名或倒序的用户名相同。


