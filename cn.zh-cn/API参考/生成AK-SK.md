# 生成AK/SK<a name="ZH-CN_TOPIC_0109962573"></a>

通过API网关向下层服务发送请求时，必须使用AK（Access Key ID）、SK（Secret Access Key）对请求进行签名。

>![](public_sys-resources/icon-note.gif) **说明：**   
>AK（Access Key ID）：访问密钥ID。与私有访问密钥关联的唯一标识符；访问密钥ID和私有访问密钥一起使用，对请求进行加密签名。  
>SK（Secret Access Key）：与访问密钥ID结合使用的密钥，对请求进行加密签名，可标识发送方，并防止请求被修改。  

## 操作步骤<a name="s15d4acfc9ac74324a26031f31df4fc2a"></a>

1.  登录MapReduce服务管理控制台。
2.  单击用户名，在下拉列表中选择“我的凭证“。
3.  选择“管理访问秘钥“页签。
4.  单击“新增访问密钥“，进入“新增访问密钥”页面。
5.  输入当前用户的登录密码。
6.  通过手机进行验证，输入对应的验证码。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   在统一身份服务中创建的用户，如果创建时未填写邮箱或者手机号，则只需校验登录密码。  
    >-   MyWorkplace的用户不需校验登录密码。如果没有邮箱或者手机信息，则不需要验证码就可以创建新的访问密钥。  

7.  在弹出的对话框中，单击“确定”，完成证书下载。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >为防止访问密钥泄漏，请妥善保管。  


