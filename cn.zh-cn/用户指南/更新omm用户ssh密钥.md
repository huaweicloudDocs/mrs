# 更新omm用户ssh密钥<a name="admin_guide_000285"></a>

## 操作场景<a name="zh-cn_topic_0263899573_sf62891bac17a4dd785446d1aef7f7476"></a>

在安装集群时，系统将自动为**omm**用户生成ssh认证私钥和公钥，用来建立节点间的互信。在集群安装成功后，如果原始私钥不慎意外泄露或者需要使用新的密钥时，系统管理员可以通过以下操作手动更改密钥值。

## 前提条件<a name="zh-cn_topic_0263899573_scf3c6e2c94eb46c6a60fdc315ec05d94"></a>

-   已停止集群。
-   修改时禁止同时进行其他管理类操作。

## 操作步骤<a name="zh-cn_topic_0263899573_s9df9c34615cb4efe868908100ab20071"></a>

1.  以**omm**用户登录到需要替换ssh密钥的节点。

    如果该节点是Manager管理节点，务必在主管理节点上执行相关操作。

2.  执行以下命令，防止超时退出。

    **TMOUT=0**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >执行完本章节操作后，请及时恢复超时退出时间，执行命令**TMOUT=**_超时退出时间_。例如：**TMOUT=600**，表示用户无操作600秒后超时退出。

3.  执行以下命令，为节点生成新的密钥：

    -   如果当前节点是Manager管理节点，执行以下命令：

        **sh $\{CONTROLLER\_HOME\}/sbin/update-ssh-key.sh**

    -   如果当前节点是非管理节点，执行以下命令：

        **sh $\{NODE\_AGENT\_HOME\}/bin/update-ssh-key.sh**

    执行上述命令时界面提示“Succeed to update ssh private key.”信息，表示ssh密钥生成成功。


1.  执行以下命令将该节点的公钥拷贝到主管理节点：

    **scp $\{HOME\}/.ssh/id\_rsa.pub **_oms\_ip_**:$\{HOME\}/.ssh/id\_rsa.pub\_bak**

    oms\_ip：表示主管理节点IP。

    根据提示输入**omm**用户密码完成文件拷贝。

2.  以**omm**用户登录到主管理节点。
3.  执行以下命令，防止超时退出：

    **TMOUT=0**

4.  执行以下命令，切换目录：

    **cd $\{HOME\}/.ssh**

5.  执行以下命令删除主管理节点authorized\_keys文件中废弃的公钥：

    **sed -i "/$\(cat id\_rsa.pub\_bak | awk '\{print $3\}'\)$/d" authorized\_keys**

6.  执行以下命令添加新的公钥信息：

    **cat id\_rsa.pub\_bak \>\> authorized\_keys**

7.  执行以下命令移动临时公钥文件到其他目录，例如，移动到“/tmp”目录。

    **mv -rf id\_rsa.pub\_bak** **/tmp**

8.  拷贝主管理节点的authorized\_keys文件到集群内其他节点：

    **scp authorized\_keys **_node\_ip_**:/$\{HOME\}/.ssh/authorized\_keys**

    node\_ip：集群内其他节点IP，不支持多个IP。

9.  执行以下命令无需输入密码确认私钥替换完成：

    **ssh **_node\_ip_

    node\_ip：集群内其他节点IP，不支持多个IP。

10. 登录FusionInsight Manager，在“主页”中单击待操作集群名称后的“![](figures/zh-cn_image_0263899299.png)  \> 启动”，启动集群。

