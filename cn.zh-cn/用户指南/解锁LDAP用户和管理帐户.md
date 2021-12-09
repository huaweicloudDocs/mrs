# 解锁LDAP用户和管理帐户<a name="admin_guide_000245"></a>

## 操作场景<a name="section25915775"></a>

管理员在LDAP用户和管理帐户被锁定时，需要在管理节点解锁集群LDAP用户“cn=pg\_search\_dn,ou=Users,dc=hadoop,dc=com”以及LDAP管理帐户“cn=krbkdc,ou=Users,dc=hadoop,dc=com”和“cn=krbadmin,ou=Users,dc=hadoop,dc=com”。

>![](public_sys-resources/icon-note.gif) **说明：** 
>Ldap用户或管理帐户连续使用错误密码操作Ldap次数大于5次时，会造成LDAP用户或管理帐户被锁定。用户被锁定之后，5分钟后会自动解锁。

## 操作步骤<a name="section13187182422311"></a>

1.  以**omm**用户登录主管理节点。
2.  执行以下命令，切换到目录：

    **cd $\{BIGDATA\_HOME\}/om-server/om/ldapserver/ldapserver/local/script**

3.  执行以下命令，解锁LDAP用户或管理帐户：

    **./ldapserver\_unlockUsers.sh **_USER\_NAME_

    其中，_USER\_NAME_表示将要解锁的用户名称。

    例如，解锁LDAP管理帐户“cn=krbkdc,ou=Users,dc=hadoop,dc=com”的方法如下：

    **./ldapserver\_unlockUsers.sh krbkdc**

    运行脚本之后，在ROOT\_DN\_PASSWORD之后输入krbkdc用户密码，显示如下结果，说明解锁成功：

    ```
    Unlock user krbkdc successfully.
    ```


