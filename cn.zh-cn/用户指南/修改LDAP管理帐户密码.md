# 修改LDAP管理帐户密码<a name="admin_guide_000256"></a>

## 操作场景<a name="zh-cn_topic_0263899625_section14368423113735"></a>

建议管理员定期修改集群LDAP管理帐户“cn=krbkdc,ou=Users,dc=hadoop,dc=com”和“cn=krbadmin,ou=Users,dc=hadoop,dc=com”的密码，以提升系统运维安全性。

## 对系统的影响<a name="zh-cn_topic_0263899625_section36437228113742"></a>

-   修改密码后需要重启KrbServer服务。
-   修改密码后需要确认LDAP管理帐户“cn=krbkdc,ou=Users,dc=hadoop,dc=com”和“cn=krbadmin,ou=Users,dc=hadoop,dc=com”是否被锁定，在集群主管理节点上执行如果下命令查看krbkdc是否被锁定（krbadmin用户方法类似）：

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >oldap端口查询方法：
    >1.  登录FusionInsight Manager，选择“系统  \>  OMS  \>  oldap  \>  修改配置“；
    >2.  “Ldap服务监听端口”参数值即为oldap端口。

    **ldapsearch -H ldaps://**_OMS\_FLOAT\_ IP地址:OLdap端口_ **-LLL -x -D** **cn=krbkdc,ou=Users,dc=hadoop,dc=com -W -b cn=krbkdc,ou=Users,dc=hadoop,dc=com -e ppolicy**

    输入LDAP管理帐户krbkdc的密码，出现如下提示表示该用户被锁定，则需要解锁用户，具体请参见[解锁LDAP用户和管理帐户](解锁LDAP用户和管理帐户.md#admin_guide_000245)。

    ```
    ldap_bind: Invalid credentials (49); Account locked
    ```


## 前提条件<a name="zh-cn_topic_0263899625_section316609511390"></a>

已确认主管理节点IP地址。

## 操作步骤<a name="zh-cn_topic_0263899625_section6358335125513"></a>

1.  以**omm**用户通过管理节点IP登录主管理节点。
2.  执行以下命令，切换到目录。

    **cd $\{BIGDATA\_HOME\}/om-server/om/meta-0.0.1-SNAPSHOT/kerberos/scripts**

3.  执行以下命令，修改LDAP管理帐户密码。

    **./okerberos\_modpwd.sh**

    输入旧密码后，再输入两次新密码。

    密码复杂度要求：

    -   密码字符长度为16～32位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\`\~!@\#$%^&\*\(\)-\_=+|\[\{\}\];,<.\>/?中的3种类型字符。
    -   不可与当前密码相同。

    显示如下结果，说明修改成功：

    ```
    Modify kerberos server password successfully.
    ```

4.  登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> KrbServer \> 更多 \> 重启服务”。

    验证用户身份后不勾选“同时重启上层服务”，单击“确定”重启KrbServer服务。


