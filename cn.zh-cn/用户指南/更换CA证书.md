# 更换CA证书<a name="admin_guide_000264"></a>

## 操作场景<a name="zh-cn_topic_0193214001_s378b1d2405dd42c79682636f38b2bd7b"></a>

MRS CA证书用于组件客户端与服务端在通信过程中加密数据，实现安全通信。该任务指导系统管理员通过FusionInsight Manager完成CA证书替换工作，以确保产品安全使用。适用于以下场景：

-   首次安装好集群以后，需要更换企业证书。
-   企业证书有效时间已过期或安全性加强，需要更换为新的证书。

更换CA证书以后，MRS中HDFS、Yarn、MapReduce、HBase、Loader、Hue、FTP-Server、Metadata、Oozie、Hive、Tomcat、CAS、httpd和LDAP使用的证书将自动更新。

证书文件和密钥文件可向企业证书管理员申请或由系统管理员生成。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   当前FusionInsight仅支持x.509格式证书导入，且必须是具有签发能力的CA证书。
>-   当前FusionInsight要求OS的编码格式必须为“en\_US.UTF-8”或“POSIX”，否则会造成证书功能异常。

## 对系统的影响<a name="zh-cn_topic_0193214001_sc979fad9291b44e391907c630189322e"></a>

更换过程中MRS系统需要重启，此时系统无法访问且无法提供服务。

## 前提条件<a name="zh-cn_topic_0193214001_sc082ef80bd3845ada4c15bba24491856"></a>

-   获取需要导入到MRS集群的CA证书文件（\*.crt）、密钥文件（\*.key）以及保存访问密钥文件密码的文件（password.property）。证书名称和密钥名称支持大小写字母和数字。
-   准备一个访问密钥文件的密码例如“Userpwd@123”用于访问密钥文件。

    密码复杂度要求如下，如果密码复杂度不满足如下要求，可能存在安全风险：

    -   密码字符长度最小为8位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!?,.;-\_'\(\)\{\}\[\]/<\>@\#$%^&\*+|\\=中的4种类型字符。

-   向证书管理员申请证书时，请提供访问密钥文件的密码并申请crt、cer、cert和pem格式证书文件，以及key和pem格式密钥文件。申请的证书需要有签发功能。

## 操作步骤<a name="zh-cn_topic_0193214001_sb25a640e8fde4b8492a7260215e65641"></a>

1.  以**omm**用户登录集群任意管理节点。
2.  选择证书和密钥文件的生成方式：
    -   若由证书管理员生成，请在管理节点**omm**用户目录保存申请的证书文件与密钥文件。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若获取的证书文件格式不是“.crt”，密钥文件格式不是“.key”，执行以下命令修改：
        >**mv **_证书名称.__证书格式 __证书名称_**.crt**
        >**mv **_密钥名称.__密钥格式 __密钥名称_**.key**
        >例如，将证书文件命名为“ca.crt”，密钥文件命名为“ca.key”：
        >**mv server.cer ca.crt**
        >**mv server\_key.pem ca.key**

    -   若由系统管理员生成，执行以下命令在管理节点**omm**用户目录生成证书文件和密钥文件：
        1.  生成密钥文件：

            **openssl genrsa -out **_密钥名称_**.key -aes256 2048 -sha256**

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >对于SUSE 15和EulerOS 2.8系统，需使用如下命令生成密钥文件：
            >**openssl genrsa -out **_密钥名称_**.key -aes256 2048**

            例如，生成密钥文件“ca.key”：

            **openssl genrsa -out ca.key -aes256 2048 -sha256**

            根据提示信息连续输入两次_password_，并按回车键确认。__

            ```
            Enter pass phrase for ca.key:
            Verifying - Enter pass phrase for ca.key:
            ```

        2.  生成证书文件：

            **openssl req -new -x509 -days 1825 -key **_密钥名称_**.key -out **_证书名称_**.crt -subj "/C=cn/ST=guangdong/L=shenzhen/O=huawei/OU=huawei/CN=huawei" -sha256**

            例如，生成证书文件“ca.crt”：

            **openssl req -new -x509 -days 1825 -key ca.key -out ca.crt -subj "/C=cn/ST=guangdong/L=shenzhen/O=huawei/OU=huawei/CN=huawei" -sha256**

            根据提示信息输入密钥文件的密码_password_，并按回车键确认。

            ```
            Enter pass phrase for ca.key:
            ```


3.  执行以下命令在管理节点**omm**用户目录保存访问密钥文件的密码。

    **sh $\{BIGDATA\_HOME\}/om-server/om/sbin/genPwFile.sh**

    根据提示信息连续输入两次_password_，并按回车键确认。_password_加密后保存在“password.property”。

    ```
    Please input key password: 
    Please Confirm password:
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在登录节点生成的“password.property”文件只适用于当前节点所属的集群，不能用于其他集群。

4.  执行以下命令打包三个文件为tar压缩包，并保存在本地。

    **tar -cvf **_压缩包名 __证书名称_**.crt **_密钥名称_**.key password.property**

    例如，**tar -cvf test.tar ca.crt ca.key password.property**

5.  登录FusionInsight Manager系统，选择“系统 \> 证书”。
6.  在“上传证书”区域单击文件选择按钮，在文件窗口中浏览已获取的证书文件tar压缩包并打开压缩包文件，单击“上传文件“，系统将自动完成导入。
7.  导入完成后提示同步集群配置并重启WEB服务使新证书生效，单击“确定”。
8.  在弹出的管理员确认窗口输入密码，单击“确定”自动同步集群配置并重启WEB服务。
9.  重启完成后在浏览器地址栏中，输入并访问FusionInsight Manager的网络地址，验证能否正常打开页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >企业证书有效时间已过期或安全性加强，MRS更换为新的证书后，请同步更换本地证书。

10. 在“集群”下拉列表中单击需要操作的集群名称。
11. 选择“更多 \> 重启”，在弹出窗口中输入当前登录的用户密码确认身份，然后单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >更换CA证书后，需离线重启集群使证书生效，不支持滚动重启。

12. 在确认重启集群的对话框中单击“确定”。

