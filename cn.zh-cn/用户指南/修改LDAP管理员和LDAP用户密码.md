# 修改LDAP管理员和LDAP用户密码<a name="ZH-CN_TOPIC_0173397679"></a>

## 操作场景<a name="section446724189518"></a>

该任务指导用户定期修改MRS集群的LDAP管理员用户“rootdn:cn=root,dc=hadoop,dc=com“和LDAP用户“pg\_search\_dn:cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com“的密码，以提升系统运维安全性。

## 对系统的影响<a name="section2536914895153"></a>

修改密码需要重启全部服务，服务在重启时无法访问。

## 操作步骤<a name="section1075407895245"></a>

1.  在集群详情页，单击“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 1.8.10及之前版本，具体请参见[修改LDAP管理员和LDAP用户密码](修改LDAP管理员和LDAP用户密码-170.md)。  

2.  选择“LdapServer \> 更多 \> 修改密码”。
3.  在“修改密码”对话框的“用户信息”选择要修改的用户。
4.  在“修改密码”对话框的“旧密码”输入旧密码，“新密码”和“确认密码”输入新密码。

    默认密码复杂度要求：

    -   密码字符长度为16～32位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\`\~!@\#$%^&\*\(\)-\_=+\\|\[\{\}\];:",<.\>/?中的3种类型字符。
    -   不能与用户名或倒序用户名相同。
    -   不可与当前密码相同。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >LDAP管理员用户“rootdn:cn=root,dc=hadoop,dc=com“的默认密码为“LdapChangeMe@123“，LDAP用户“pg\_search\_dn:cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com“的默认密码为“pg\_search\_dn@123“，请定期修改密码并妥善保存。  

5.  勾选“我已阅读此信息并了解其影响。”，单击“确定”确认修改并重启服务。

