# 修改OMS Kerberos管理员密码<a name="admin_guide_000254"></a>

## 操作场景<a name="section43716072113549"></a>

管理员应定期修改OMS Kerberos管理员“kadmin”的密码，以提升系统运维安全性。

修改此用户密码将同步修改Kerberos管理员密码。

## 操作步骤<a name="section346215718347"></a>

1.  以**omm**用户登录任意管理节点。
2.  执行以下命令，切换到目录。

    **cd $\{BIGDATA\_HOME\}/om-server/om/meta-0.0.1-SNAPSHOT/kerberos/scripts**

3.  执行以下命令，配置环境变量。

    **source component\_env**

4.  执行以下命令，修改kadmin/admin密码。此操作对所有服务器生效。

    **kpasswd kadmin/admin**

    默认密码复杂度要求：

    -   密码字符长度最小为8位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!?,.;-\_'\(\)\{\}\[\]/<\>@\#$%^&\*+|\\=中的4种类型字符。
    -   不可和用户名相同或用户名的倒序字符相同。
    -   不可以为常见的易破解密码，例如Admin@12345。
    -   不可与最近N次使用过的密码相同，N为[密码策略配置](配置密码策略.md)中“重复使用规则”的值。


