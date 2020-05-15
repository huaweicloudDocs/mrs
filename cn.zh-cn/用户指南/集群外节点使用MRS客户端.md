# 集群外节点使用MRS客户端<a name="ZH-CN_TOPIC_0173179087"></a>

## 操作场景<a name="section47062638171526"></a>

用户可以在公有云MRS集群以外的节点上使用客户端，在使用客户端前需要安装客户端。

>![](public_sys-resources/icon-note.gif) **说明：**   
>如果集群外的节点已安装客户端且只需要更新客户端，请使用安装客户端的用户例如“root“。  

## 前提条件<a name="section3219221104310"></a>

-   已准备一个弹性云服务器，主机操作系统及版本请参见[表1](#table40818788104630)。

    **表 1**  参考列表

    <a name="table40818788104630"></a>
    <table><thead align="left"><tr id="row38578049104630"><th class="cellrowborder" valign="top" width="19.36%" id="mcps1.2.3.1.1"><p id="p37814246104630"><a name="p37814246104630"></a><a name="p37814246104630"></a>操作系统</p>
    </th>
    <th class="cellrowborder" valign="top" width="80.64%" id="mcps1.2.3.1.2"><p id="p43055100104630"><a name="p43055100104630"></a><a name="p43055100104630"></a>支持的版本号</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row64911082104630"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="p23306329104630"><a name="p23306329104630"></a><a name="p23306329104630"></a>SuSE</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><a name="ul8764529104630"></a><a name="ul8764529104630"></a><ul id="ul8764529104630"><li>推荐：SUSE Linux Enterprise Server 11 SP4（SuSE11.4）</li><li>可用：SUSE Linux Enterprise Server 11 SP3（SuSE11.3）</li><li>可用：SUSE Linux Enterprise Server 11 SP1（SuSE11.1）</li><li>可用：SUSE Linux Enterprise Server 11 SP2（SuSE11.2）</li></ul>
    </td>
    </tr>
    <tr id="row60240262104630"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="p47623054104630"><a name="p47623054104630"></a><a name="p47623054104630"></a>RedHat</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><a name="ul32262179104630"></a><a name="ul32262179104630"></a><ul id="ul32262179104630"><li>推荐：RedHat-6.6-x86_64（RedHat6.6）</li><li>可用：RedHat-6.4-x86_64（RedHat6.4）</li><li>可用：RedHat-6.5-x86_64（RedHat6.5）</li><li>可用：RedHat-6.7-x86_64（RedHat6.7）</li></ul>
    </td>
    </tr>
    <tr id="row30103971104630"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="p22502558104630"><a name="p22502558104630"></a><a name="p22502558104630"></a>CentOS</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><a name="ul10767914104630"></a><a name="ul10767914104630"></a><ul id="ul10767914104630"><li>可用：CentOS–6.4版本（CentOS6.4）</li><li>可用：CentOS–6.5版本（CentOS6.5）</li><li>可用：CentOS–6.6版本（CentOS6.6）</li><li>可用：CentOS–6.7版本（CentOS6.7）</li><li>可用：CentOS–7.2版本（CentOS7.2）</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    例如，用户可以选择镜像“CentOS 7.2 64bit\(40GB\)“为弹性云服务器准备操作。

    同时为弹性云服务分配足够的磁盘空间，例如“40GB“。

-   弹性云服务器的VPC需要与MRS集群在同一个VPC中。
-   弹性云服务器的安全组需要和MRS集群Master节点的安全组相同。

    如果不同，请修改弹性云服务器安全组或配置弹性云服务器安全组的出入规则允许MRS集群所有安全组的访问。

    创建满足以上要求的弹性云服务器，请参见[购买并登录Linux弹性云服务器](https://support.huaweicloud.com/qs-ecs/zh-cn_topic_0092494193.html)。

-   需要允许用户使用密码方式登录Linux弹性云服务器（SSH方式），请参见[SSH密码方式登录](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0017955633.html)。

## 操作步骤<a name="section6090605618256"></a>

1.  根据前提条件，创建一个满足要求的弹性云服务器。
2.  <a name="li1148114223118"></a>登录MRS管理控制台，单击集群名称进入集群详情页，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“点击同步”进行IAM用户同步）。  
    >-   针对MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

3.  单击“下载客户端“。
4.  在“客户端类型“选择“完整客户端“。
5.  在“下载路径“选择“远端主机“。
6.  将“主机IP“设置为ECS的IP地址，设置“主机端口“为“22“，并将“存放路径“设置为“/tmp“。
    -   如果使用SSH登录ECS的默认端口“22“被修改，请将“主机端口“设置为新端口。
    -   “存放路径“最多可以包含256个字符。

7.  针对MRS1.6.2版本（不包含）前的集群，将“登录用户“设置为“linux“。针对MRS1.6.2版本（包含）及以后的集群，“登录用户“设置为“root“。

    如果使用其他用户，请确保该用户对保存目录拥有读取、写入和执行权限。

8.  针对MRS 1.8.2及以后版本，在“登录方式“选择“密码“或“SSH私钥“。

    -   密码：输入创建集群时设置的root用户密码。
    -   SSH私钥：选择并上传创建集群时使用的密钥文件。

    针对MRS 1.8.2之前版本，在“SSH私钥“选择并上传创建B集群时使用的密钥文件。

9.  单击“确定“开始生成客户端文件。

    若界面显示以下提示信息表示客户端包已经成功保存。单击“关闭“。客户端文件请到下载客户端时设置的远端主机的“存放路径“中获取。

    ```
    下载客户端文件到远端主机成功。
    ```

    若界面显示以下提示信息，请检查用户名密码及远端主机的安全组配置，确保用户名密码正确，及远端主机的安全组已增加SSH\(22\)端口的入方向规则。然后从[2](#li1148114223118)执行重新开始下载客户端。

    ```
    连接到服务器失败，请检查网络连接或参数设置。
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >生成客户端会占用大量的磁盘IO，不建议在集群处于安装中、启动中、打补丁中等非稳态场景下载客户端。  

10. 使用VNC方式，登录弹性云服务器。参见[远程登录（VNC方式）](https://support.huaweicloud.com/usermanual-ecs/ecs_03_0136.html)\)。

    所有镜像均支持Cloud-init特性。针对MRS1.6.2版本（不包含）前的集群，Cloud-init预配置的用户名“linux”，密码为“cloud.1234”，如果用户修改了默认密码请使用新密码。针对MRS1.6.2版本（包含）及以后的集群，Cloud-init预配置的用户名“root”，密码为创建集群时设置的密码。首次登录建议修改。

11. 在弹性云服务器，切换到**root**用户，并将安装包复制到目录“/opt“。

    **sudo su - root**

    **cp /tmp/MRS\_Services\_Client.tar /opt**

12. 在“/opt“目录执行以下命令，解压压缩包获取校验文件与客户端配置包。

    **tar -xvf MRS\_Services\_Client.tar**

13. 执行以下命令，校验文件包。

    **sha256sum -c MRS\_Services\_ClientConfig.tar.sha256**

    界面显示如下：

    ```
    MRS_Services_ClientConfig.tar: OK
    ```

14. 执行以下命令，解压“MRS\_Services\_ClientConfig.tar“。

    **tar -xvf MRS\_Services\_ClientConfig.tar**

15. 执行以下命令，安装客户端到新的目录，例如“/opt/client“。安装时自动生成目录。

    **sh /opt/MRS\_Services\_ClientConfig/install.sh /opt/client**

    查看安装输出信息，如有以下结果表示客户端安装成功：

    ```
    Components client installation is complete.
    ```

16. 验证弹性云服务器节点是否与集群Master节点的IP是否连通？

    例如，执行以下命令：**ping** _Master节点IP地址_

    -   是，执行[17](#li6406429718107)。
    -   否，检查VPC、安全组是否正确，是否与MRS集群在相同VPC和安全组，然后执行[17](#li6406429718107)。

17. <a name="li6406429718107"></a>执行以下命令配置环境变量：

    **source /opt/client/bigdata\_env**

18. 如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** **_MRS集群用户_**

    例如,  **kinit admin**.

19. 执行组件的客户端命令。

    例如，执行以下命令查看HDFS目录：

    **hdfs dfs -ls /**


