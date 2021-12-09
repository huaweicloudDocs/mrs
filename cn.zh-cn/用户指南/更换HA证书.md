# 更换HA证书<a name="admin_guide_000265"></a>

## 操作场景<a name="s8f601638a33c45919d0fdf21a734985f"></a>

HA证书用于主备进程与高可用进程的通信过程中加密数据，实现安全通信。该任务指导系统管理员FusionInsight Manager完成主备管理节点的HA证书替换工作，以确保产品安全使用。适用于以下场景：

-   首次安装好集群以后，需要更换企业证书。
-   企业证书有效时间已过期或安全性加强，需要更换为新的证书。

>![](public_sys-resources/icon-note.gif) **说明：** 
>不适用于未安装主备管理节点的场景。

证书文件和密钥文件可向企业证书管理员申请或由系统管理员生成。

## 对系统的影响<a name="seb851e3bd0f340ce8487fca0572432fb"></a>

更换过程中FusionInsight Manager需要重启，此时系统无法访问且无法提供服务。

## 前提条件<a name="sb845120911cb47df836fcb532a1199e8"></a>

-   获取需要更换的HA根证书文件“root-ca.crt”和密钥文件“root-ca.pem”。
-   准备一个访问密钥文件的密码_password_，例如“Userpwd@123”用于访问密钥文件。

    密码复杂度要求如下，如果密码复杂度不满足如下要求，可能存在安全风险：

    -   密码字符长度最小为8位。
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!?,.;-\_'\(\)\{\}\[\]/<\>@\#$%^&\*+|\\=中的4种类型字符

-   向证书管理员申请证书时，请提供访问密钥文件的密码并申请crt、cer、cert和pem格式证书文件，以及key和pem格式密钥文件。申请的证书需要有签发功能。

## 操作步骤<a name="s2122b2542b9f4b3298b87632d324198c"></a>

1.  以**omm**用户通过主管理节点IP登录主管理节点。
2.  选择证书和密钥文件的生成方式：
    -   若由证书管理员生成，请在主备管理节点“$\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert”目录保存申请的证书文件与密钥文件。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若获取的证书文件格式不是“.crt”，密钥文件格式不是“.pem”，执行以下命令修改：
        >**mv **_证书名称.__证书格式 _**root-ca.crt**
        >**mv **_密钥名称.__密钥格式 _**root-ca.pem**
        >例如，将证书文件命名为“root-ca.crt”，密钥文件命名为“root-ca.pem”：
        >**mv server.cer root-ca.crt**
        >**mv server\_key.key root-ca.pem**

    -   若由系统管理员生成，执行以下命令在主管理节点“$\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert”目录生成“root-ca.crt”和“root-ca.pem”：

        **sh $\{OMS\_RUN\_PATH\}/workspace/ha/module/hacom/script/gen-cert.sh --root-ca --country=CN --state=**_state_** --city=**_city_** --company=**_company_** --organize=**_organize_** --common-name=**_commonname_** --email=**_管理员邮箱_

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >生成的证书文件有效期为10年，在系统证书文件即将过期时，系统将产生告警“ALM-12055 证书文件即将过期”。

        例如，执行以下命令：

        **sh $\{OMS\_RUN\_PATH\}/workspace/ha/module/hacom/script/gen-cert.sh --root-ca --country=CN --state=guangdong --city=shenzhen --company=huawei --organize=IT --common-name=HADOOP.COM --email=abc@**_xxx_**.com**

        根据提示信息输入_password_，并按回车键确认。

        ```
        Enter pass phrase for /opt/huawei/Bigdata/om-server/OMS/workspace/ha/local/cert/root-ca.pem:
        ```

        提示以下信息表示命令执行成功：

        ```
        Generate root-ca pair success.
        ```

3.  在主管理节点以**omm**用户执行以下命令，复制“root-ca.crt”和“root-ca.pem”到“$\{BIGDATA\_HOME\}/om-server/om/security/certHA”目录。

    **cp -arp $\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert/root-ca.\* $\{BIGDATA\_HOME\}/om-server/om/security/certHA**

4.  使用**omm**用户将主管理节点生成的“root-ca.crt”和“root-ca.pem”复制到备管理节点“$\{BIGDATA\_HOME\}/om-server/om/security/certHA”目录。

    **scp $\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert/root-ca.\*** **omm@**_备管理节点IP_:**$\{BIGDATA\_HOME\}/om-server/om/security/certHA**

5.  <a name="zh-cn_topic_0046736696_hacert_r"></a>执行以下命令，生成HA用户证书并自动替换。

    **sh $\{BIGDATA\_HOME\}/om-server/om/sbin/replacehaSSLCert.sh**

    根据提示信息输入_password_，并按回车键确认。

    ```
    Please input ha ssl cert password:
    ```

    界面提示以下信息表示HA用户证书替换成功：

    ```
    [INFO] Succeed to replace ha ssl cert.
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果用户需要更新HA密码加密套件，可以带-u参数。

6.  <a name="lde9a7729d1c54aeb8769f4121d44099f"></a>执行以下命令，重启OMS。

    **sh $\{BIGDATA\_HOME\}/om-server/om/sbin/restart-oms.sh**

    界面提示以下信息：

    ```
    start HA successfully.
    ```

7.  以**omm**用户通过备管理节点IP登录备管理节点，重复[5](#zh-cn_topic_0046736696_hacert_r)～[6](#lde9a7729d1c54aeb8769f4121d44099f)。

    执行**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**，查看管理节点的“HAAllResOK”是否为“Normal”，并可以重新登录FusionInsight Manager表示操作成功。


