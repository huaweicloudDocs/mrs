# 修改DBService数据库omm用户密码<a name="mrs_01_2313"></a>

1.  以**root**用户登录DBService主节点。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**DBService数据库omm**用户密码不支持在DBService备节点修改。只需在DBService主节点执行修改操作，无需在备管理节点操作。

2.  执行以下命令，切换用户。

    **su - omm**

3.  执行以下命令，切换目录。

    **source $DBSERVER\_HOME/.dbservice\_profile**

    **cd  **$\{DBSERVICE\_SOFTWARE\_DIR\}/**sbin/**

4.  执行以下命令，修改**omm**用户密码。

    **sh modifyDBPwd.sh**

5.  输入**omm**的原密码后，再输入两次新密码。

    密码复杂度要求：

    -   密码字符长度为8～32位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!@\#$%^&\*\(\)-+\_=\\|\[\{\}\];",<.\>/?中的3种类型字符。
    -   不可和用户名相同或用户名的倒序字符相同。
    -   不可与前20个历史密码相同。

    显示如下结果，说明修改成功：

    ```
    Successful to modify password.
    ```


