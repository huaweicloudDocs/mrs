# MRS集群节点简介<a name="mrs_01_0081"></a>

介绍远程登录的概念、MRS集群的节点类型和节点功能。

MRS集群节点支持用户远程登录，远程登录包含界面登录和SSH登录两种方式：

-   界面登录：直接通过弹性云服务器管理控制台提供的远程登录功能，登录到集群Master节点的Linux界面。
-   SSH登录：仅适用于Linux弹性云服务器。您可以使用远程登录工具（例如PuTTY），登录弹性云服务器。此时，需要该弹性云服务器绑定弹性IP地址。

    Master节点申请和绑定弹性IP，请参见[为弹性云服务器申请和绑定弹性公网IP](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0013748738.html)。

    可以使用密钥方式也可以使用密码方式登录Linux弹性云服务器。

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >当您使用密钥方式访问集群节点，需要以root用户登录，详细步骤请参见[登录弹性云服务器（SSH密钥方式）](登录集群节点.md#section5513107114)。
    >当您使用密码方式访问集群节点，详细步骤请参见[登录弹性云服务器（SSH密码方式）](登录集群节点.md#section1598312501208)。


MRS集群中每个节点即为一台弹性云服务器，节点类型及节点功能如[表1](#table1615555733016)所示。

**表 1**  集群节点分类

<a name="table1615555733016"></a>
<table><thead align="left"><tr id="row13156205733010"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="p615695717306"><a name="p615695717306"></a><a name="p615695717306"></a>节点类型</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="p315615717306"><a name="p315615717306"></a><a name="p315615717306"></a>功能</p>
</th>
</tr>
</thead>
<tbody><tr id="row101569574309"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p115617571304"><a name="p115617571304"></a><a name="p115617571304"></a>Master节点</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p2258727617341"><a name="p2258727617341"></a><a name="p2258727617341"></a>MRS集群管理节点，负责管理和监控集群。在MRS管理控制台选择“集群列表 &gt; 现有集群”，选中一个运行中的集群并单击集群名，进入集群信息页面。在“节点管理”中查看节点名称，名称中包含“master1”的节点为Master1节点，名称中包含“master2”的节点为Master2节点。</p>
<p id="p6617503518419"><a name="p6617503518419"></a><a name="p6617503518419"></a>Master节点可以通过弹性云服务器界面的VNC方式登录，也可以通过SSH方式登录，并且Master节点可以免密码登录到Core节点。</p>
<p id="p6317347216313"><a name="p6317347216313"></a><a name="p6317347216313"></a>系统自动将Master节点标记为主备管理节点，并支持MRS集群管理的高可用特性。如果主管理节点无法提供服务，则备管理节点会自动切换为主管理节点并继续提供服务。</p>
<p id="p3169034316313"><a name="p3169034316313"></a><a name="p3169034316313"></a>查看Master1节点是否为主管理节点，请参见<a href="如何确认Manager的主备管理节点.md">如何确认Manager的主备管理节点</a>。</p>
</td>
</tr>
<tr id="row10156457193016"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p201563575303"><a name="p201563575303"></a><a name="p201563575303"></a>Core节点</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p9156195714304"><a name="p9156195714304"></a><a name="p9156195714304"></a>MRS集群工作节点，负责处理和分析数据，并存储过程数据。</p>
</td>
</tr>
<tr id="row1589416161134"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p144921454386"><a name="p144921454386"></a><a name="p144921454386"></a>Task节点</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p1513204051211"><a name="p1513204051211"></a><a name="p1513204051211"></a>计算节点，用于弹性伸缩，集群计算资源不足时扩容至集群中。</p>
</td>
</tr>
</tbody>
</table>

