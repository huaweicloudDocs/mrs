# omm用户提权漏洞修复<a name="mrs_01_9040"></a>

## 适用版本<a name="section081584195517"></a>

MRS集群的所有版本。

## 补丁解决的问题<a name="section289122017567"></a>

修复omm用户通过installSudoExecute.sh脚本获取root用户权限的问题。

## 补丁包结构<a name="section175561942175917"></a>

-   install.sh：补丁安装脚本
-   ips.ini：存放集群中所有节点IP地址的文件，请根据集群实际的节点IP修改该文件，每个节点的IP地址一行，IP地址间不能出现空行，文件末尾留一个空行
-   scp-util.exp：scp工具脚本
-   ssh-util.exp：ssh工具脚本
-   Sudo\_Vulnerability\_20210330：存放sudo\_repair.sh脚本的目录，用户复制到各节点上执行脚本的文件夹
-   sudo\_repair.sh：修复漏洞的脚本
-   README.md：补丁工具使用说明

## 安装补丁<a name="section7951233937"></a>

1.  单击集群对应区域的地址下载补丁包。
    -   华北-北京一：[https://mrs-container1-patch-cn-north-1.obs.cn-north-1.myhuaweicloud.com/MRS\_Common\_Script/MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz](https://mrs-container1-patch-cn-north-1.obs.cn-north-1.myhuaweicloud.com/MRS_Common_Script/MRS_All_Sudo_Vulnerability_20210330.tar.gz)
    -   华东-上海二：[https://mrs-container1-patch-cn-east-2.obs.cn-east-2.myhuaweicloud.com/MRS\_Common\_Script/MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz](https://mrs-container1-patch-cn-east-2.obs.cn-east-2.myhuaweicloud.com/MRS_Common_Script/MRS_All_Sudo_Vulnerability_20210330.tar.gz)
    -   华南-广州：[https://mrs-container1-patch-cn-south-1.obs.cn-south-1.myhuaweicloud.com/MRS\_Common\_Script/MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz](https://mrs-container1-patch-cn-south-1.obs.cn-south-1.myhuaweicloud.com/MRS_Common_Script/MRS_All_Sudo_Vulnerability_20210330.tar.gz)
    -   华北-北京四：[https://mrs-container1-patch-cn-north-4.obs.cn-north-4.myhuaweicloud.com/MRS\_Common\_Script/MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz](https://mrs-container1-patch-cn-north-4.obs.cn-north-4.myhuaweicloud.com/MRS_Common_Script/MRS_All_Sudo_Vulnerability_20210330.tar.gz)

2.  以**root**用户登录集群主Master节点。
3.  将补丁包上传到"/root/"目录下。
4.  执行如下命令解压补丁工具\(MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz\)至当前目录\(/root\)。

    **tar -zxf MRS\_All\_Sudo\_Vulnerability\_20210330.tar.gz**

5.  执行如下命令打开ips.ini文件所在目录。

    **cd /root/MRS\_All\_Sudo\_Vulnerability\_20210330/**

6.  在ips.ini文件中配置集群所有节点的IP地址。每个节点的IP地址一行，IP地址间不能出现空行，文件末尾留一个空行。
7.  执行如下脚本安装补丁。

    执行脚本后需要输入root密码，请输入正确无误的密码，若密码有误可能会导致脚本SSH过程中将**root**密码锁定5分钟。

    **cd /root/MRS\_All\_Sudo\_Vulnerability\_20210330/**

    **dos2unix ./\***

    **chmod +x ./\* -R**

    **sh install.sh "install"**


## 卸载补丁<a name="section1227194616316"></a>

执行如下脚本卸载补丁，执行脚本后需要输入root密码，请输入正确无误的密码，若密码有误可能会导致脚本SSH过程中将**root**密码锁定5分钟。

**cd /root/MRS\_All\_Sudo\_Vulnerability\_20210330/**

**sh install.sh "uninstall"**

