# 修改OMS数据库访问用户密码<a name="admin_guide_000260"></a>

## 操作场景<a name="section1834132911473"></a>

建议管理员定期修改OMS数据库访问用户的密码，以提升系统运维安全性。

## 对系统的影响<a name="section1616558911473"></a>

修改密码需要重启OMS服务，服务在重启时系统无法访问。

## 操作步骤<a name="section178102217357"></a>

1.  在FusionInsight Manager选择“系统  \>  OMS  \>  gaussDB  \>  修改密码“。
2.  在omm用户所在行，单击“操作”列下的“修改密码“。
3.  在弹出窗口中输入当前登录的用户密码确认身份，单击“确定”。
4.  根据界面信息，输入新旧密码。

    密码复杂度要求：

    -   密码字符长度为8～32位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!@\#$%^&\*\(\)-+\_=\\|\[\{\}\];",<.\>/?中的3种类型字符。
    -   不可和用户名相同或用户名的倒序字符相同。
    -   不可与前20个历史密码相同。

5.  单击“确定”，等待界面提示操作成功。
6.  在**omm**用户所在行，单击“操作”列下的“重启OMS服务“。
7.  在弹出窗口中输入当前登录的用户密码确认身份，单击“确定”。
8.  在确定重启的对话框中，单击“确定”，重新启动OMS服务。

