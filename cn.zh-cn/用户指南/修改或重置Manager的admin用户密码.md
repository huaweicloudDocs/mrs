# 修改或重置Manager的admin用户密码<a name="admin_guide_000321"></a>

“admin”是Manager的系统管理员帐号，建议用户通过Manager定期修改密码，提高系统安全性。

用户在密码丢失情况可参考[重置admin密码](#section21461134135216)重置密码。

## 修改admin密码<a name="section17146934205215"></a>

开启Kerberos认证的集群和开启弹性公网IP功能未开启Kerberos认证的集群支持通过Manager界面修改admin密码。

1.  登录FusionInsight Manager。

    需使用“admin”登录。

2.  移动鼠标到界面右上角的“Hello, admin“。

    在弹出菜单中单击“修改密码”。

3.  分别输入“旧密码”、“新密码”、“确认新密码”，单击“确定”完成修改。

## 重置admin密码<a name="section21461134135216"></a>

1.  登录Master1节点。
2.  （可选）若想要使用omm用户修改密码，请执行以下命令切换用户。

    **sudo su - omm**

3.  执行以下命令，切换到客户端目录，例如“/opt/Bigdata/client“。

    **cd /opt/Bigdata/client**

4.  执行以下命令，配置环境变量。

    **source bigdata\_env**

5.  执行以下命令，使用kadmin/admin登录控制台。

    **kadmin -p kadmin/admin**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >kadmin/admin的默认密码为“Admin@123”，首次登录后会提示该密码过期，请按照提示修改密码并妥善保存。

6.  执行以下命令，重置admin用户密码。

    **cpw admin**


