# 修改LDAP管理员和LDAP用户密码（含OMS LDAP）<a name="admin_guide_000255"></a>

## 操作场景<a name="section32983569"></a>

建议管理员定期修改集群的LDAP管理员用户“cn=root,dc=hadoop,dc=com”和LDAP用户“cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com”的密码，以提升系统运维安全性。

修改上述用户密码将同步修改OMS LDAP管理员或用户密码。

>![](public_sys-resources/icon-note.gif) **说明：** 
>旧版本集群升级到新版本后，LDAP管理员密码将继承旧集群的密码策略，为保证系统安全，建议集群升级后及时修改密码。

## 对系统的影响<a name="section28416672"></a>

-   修改LdapServer服务的用户密码为高危操作，需要重启KrbServer和LdapServer服务。重启KrbServer可能会导致集群中的节点短时间内出现执行**id**命令查询不到用户的现象，请谨慎执行。
-   修改LDAP用户“cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com”的密码后，可能会导致该用户在组件LDAP上被锁定。因此，建议修改密码后对该用户进行解锁，解锁方法请参见[解锁LDAP用户和管理帐户](解锁LDAP用户和管理帐户.md)章节。

## 前提条件<a name="section54423456"></a>

修改LDAP用户“cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com”的密码前需先确认该用户没有被锁定，在集群主管理节点上执行如下命令：

>![](public_sys-resources/icon-note.gif) **说明：** 
>oldap端口查询方法：
>1.  登录FusionInsight Manager，选择“系统  \>  OMS  \>  oldap  \>  修改配置“；
>2.  “Ldap服务监听端口”参数值即为oldap端口。

**ldapsearch -H ldaps://**_OMS浮动__地址:OLdap__端口 _**-LLL -x -D cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com -W -b cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com -e ppolicy**

输入LDAP用户pg\_search\_dn的密码，出现如下提示表示该用户被锁定，则需要解锁用户，具体请参见[解锁LDAP用户和管理帐户](解锁LDAP用户和管理帐户.md)。

```
ldap_bind: Invalid credentials (49); Account locked
```

## 操作步骤<a name="section36081314113519"></a>

1.  登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer”。
2.  选择 “更多 \> 修改数据库密码”，在弹出窗口中输入当前登录的用户密码确认身份，单击“确定”。
3.  在“修改密码”对话框的“用户信息”中选择需要修改密码的用户名。
4.  在“旧密码”输入旧密码，“新密码”和“确认密码”输入新密码。

    默认密码复杂度要求：

    -   密码字符长度为16～32位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\`\~!@\#$%^&\*\(\)-\_=+|\[\{\}\];,<.\>/?中的3种类型字符。
    -   不可和用户名相同或用户名的倒序字符相同。
    -   不可与当前密码相同。

5.  勾选“我已阅读此信息并了解其影响”，单击“确定”确认修改并重启服务。

