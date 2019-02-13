# 更换HA证书<a name="ZH-CN_TOPIC_0042008035"></a>

## 操作场景<a name="section27934550113125"></a>

HA证书用于主备进程与高可用进程的通信过程中加密数据，实现安全通信。该任务指导用户为MRS Manager完成主备管理节点的HA证书替换工作，以确保产品安全使用。

证书文件和密钥文件可由用户生成。

## 对系统的影响<a name="section35503302113216"></a>

更换过程中MRS Manager需要重启，此时系统无法访问且无法提供服务。

## 前提条件<a name="section47013901113220"></a>

-   获取需要更换的HA根证书文件“root-ca.crt”和密钥文件“root-ca.pem”。
-   准备一个访问密钥文件的密码password，例如“Userpwd@123”用于访问密钥文件。

    密码复杂度要求如下，如果密码复杂度不满足如下要求，可能存在安全风险：

    -   密码字符长度至少为8个字符
    -   至少需要包含大写字母、小写字母、数字、特殊字符\~\`!?,.:;-\_'\(\)\{\}\[\]/<\>@\#$%^&\*+|\\=中的4种类型字符


## 操作步骤<a name="section66354921113232"></a>

1.  登录主管理节点。
2.  执行以下命令切换用户：

    **sudo su - root**

    **su - omm**

3.  执行以下命令在主管理节点“$\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert”目录生成“root-ca.crt”和“root-ca.pem”：

    **sh $\{OMS\_RUN\_PATH\}/workspace/ha/module/hacom/script/gen-cert.sh --root-ca --country=**_country_ **--state=**_state_ **--city=**_city_ **--company=**_company_ **--organize=**_organize_ **--common-name=**_commonname_ **--email=**_管理员邮箱_ **--password=**_password_

    例如，执行以下命令：**sh $\{OMS\_RUN\_PATH\}/workspace/ha/module/hacom/script/gen-cert.sh --root-ca --country=CN --state=gd --city=sz --company=hw --organize=IT --common-name=HADOOP.COM --email=abc@hw.com --password=Userpwd@123**

    提示以下信息表示命令执行成功：

    ```
    Generate root-ca pair success.
    ```

4.  在主管理节点以“omm”用户执行以下命令，复制“root-ca.crt”和“root-ca.pem”到“$\{BIGDATA\_HOME\}/om-0.0.1/security/certHA”目录。

    **cp -arp $\{OMS\_RUN\_PATH\}/workspace0/ha/local/cert/root-ca.\* $\{BIGDATA\_HOME\}/om-0.0.1/security/certHA**

5.  使用“omm”用户将主管理节点生成的“root-ca.crt”和“root-ca.pem”复制到备管理节点“$\{BIGDATA\_HOME\}/om-0.0.1/security/certHA”目录。
6.  <a name="li61539631113353"></a>执行以下命令，生成HA用户证书并自动替换。

    **sh $\{BIGDATA\_HOME\}/om-0.0.1/sbin/replacehaSSLCert.sh**

    根据提示信息输入password，并按回车键确认。

    ```
    Please input ha ssl cert password:
    ```

    界面提示以下信息表示HA用户证书替换成功：

    ```
    [INFO] Succeed to replace ha ssl cert.
    ```

7.  <a name="li61839614113353"></a>执行以下命令，重启OMS。

    **sh $\{BIGDATA\_HOME\}/om-0.0.1/sbin/restart-oms.sh**

    界面提示以下信息：

    ```
    start HA successfully.
    ```

8.  登录备管理节点并切换到**omm**用户，重复[6](#li61539631113353)～[7](#li61839614113353)。

    执行**sh $\{BIGDATA\_HOME\}/om-0.0.1/sbin/status-oms.sh**，查看管理节点的“HAAllResOK”是否为“Normal”，并可以重新访问MRS Manager表示操作成功。


