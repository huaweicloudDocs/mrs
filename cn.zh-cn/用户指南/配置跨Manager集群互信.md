# 配置跨Manager集群互信<a name="admin_guide_000177"></a>

## 操作场景<a name="s5a609b053dbc44dfb2ffbaff94d20def"></a>

当不同的两个Manager系统下安全模式的集群需要互相访问对方的资源时，管理员可以设置互信的系统，使外部系统的用户可以在本系统中使用。

每个系统用户安全使用的范围定义为“域”，不同的Manager系统需要定义唯一的域名。跨Manager访问实际上就是用户跨域使用。

>![](public_sys-resources/icon-note.gif) **说明：** 
>最多支持配置500个互信集群。

## 对系统的影响<a name="s40a625688d3b490998c949ed964032b9"></a>

-   配置跨集群互信后，外部系统的用户可以在本系统中使用，请管理员根据企业业务与安全要求，定期检视Manager系统中用户的权限。
-   配置跨集群互信时需要停止所有集群，会造成业务中断。
-   配置跨集群互信后，互信的集群中均会增加Kerberos内部用户“krbtgt/_本集群域名_@_外部集群域名_”、“krbtgt/_外部集群域名_@_本集群域名_”，用户不能删除。请管理员根据企业安全要求，及时且定期修改密码，需同时修改互信系统中4个用户且密码保持一致。具体请参见[修改组件运行用户密码](修改组件运行用户密码.md)。修改密码期间可能影响跨系统业务应用的连接。
-   配置跨集群互信后，各个集群都需要重新下载并安装客户端。
-   配置跨集群互信后，验证配置后是否可以正常工作，且如何使用本系统用户访问对端系统资源，请参见[配置跨集群互信后的用户权限](配置跨集群互信后的用户权限.md)。

## 前提条件<a name="s536f2156a7c14aef9c8e147a43f2322c"></a>

-   管理员已明确业务需求，并规划好不同系统的域名。域名只能包含大写字母、数字、圆点（.）及下划线（\_），且只能以字母或数字开头。例如“DOMAINA.HW”和“DOMAINB.HW”。
-   配置跨集群互信前，两个Manager系统的域名必须不同。MRS创建ECS/BMS集群时会随机生成唯一系统域名，通常无需修改。
-   配置跨集群互信前，两个集群中不能存在有相同的主机名，也不能存在相同的IP地址。
-   配置互信的两个集群系统时间必须一致，且系统上的NTP服务必须使用同一个时间源。
-   配置互信的两个集群系统内所有集群全部组件的运行状态均为“良好”。
-   Manager内所有集群的ZooKeeper服务的“acl.compare.shortName”参数需确保为默认值“true”。否则请修改该参数为“true”后重启ZooKeeper服务。

## 操作步骤<a name="section4462153619571"></a>

1.  登录其中一个FusionInsight Manager。
2.  在主页中停止所有集群。

    单击主页上待操作集群名称后的![](figures/zh-cn_image_0263899345.png)，单击“停止”，输入管理员密码后在弹出的“停止集群”窗口中单击“确定”，等待集群停止成功。

3.  选择“系统 \> 权限 \> 域和互信”。
4.  修改配置参数“互信对端域”。

    **表 1**  相关参数

    <a name="zh-cn_topic_0046737083_table58621757"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0046737083_row57510483"><th class="cellrowborder" valign="top" width="23.11%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0046737083_p27837507"><a name="zh-cn_topic_0046737083_p27837507"></a><a name="zh-cn_topic_0046737083_p27837507"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.89%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0046737083_p40245567"><a name="zh-cn_topic_0046737083_p40245567"></a><a name="zh-cn_topic_0046737083_p40245567"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0046737083_row38665520"><td class="cellrowborder" valign="top" width="23.11%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046737083_p44899454"><a name="zh-cn_topic_0046737083_p44899454"></a><a name="zh-cn_topic_0046737083_p44899454"></a>“realm_name”</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.89%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046737083_p12977168"><a name="zh-cn_topic_0046737083_p12977168"></a><a name="zh-cn_topic_0046737083_p12977168"></a>填写对端系统的域名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0046737083_row49685655"><td class="cellrowborder" valign="top" width="23.11%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046737083_p65115082"><a name="zh-cn_topic_0046737083_p65115082"></a><a name="zh-cn_topic_0046737083_p65115082"></a>“ip_port”</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.89%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046737083_p39830327"><a name="zh-cn_topic_0046737083_p39830327"></a><a name="zh-cn_topic_0046737083_p39830327"></a>填写对端系统的KDC地址。</p>
    <p id="p1697818206272"><a name="p1697818206272"></a><a name="p1697818206272"></a>参数值格式为：<em id="i697812019276"><a name="i697812019276"></a><a name="i697812019276"></a>对端系统内要配置互信集群</em><em id="i6978152052717"><a name="i6978152052717"></a><a name="i6978152052717"></a>的Kerberos</em><em id="i199789207270"><a name="i199789207270"></a><a name="i199789207270"></a>服务部署的节点IP</em><em id="i89788209273"><a name="i89788209273"></a><a name="i89788209273"></a>地址:端口</em>。</p>
    <a name="ul0969192153916"></a><a name="ul0969192153916"></a><ul id="ul0969192153916"><li>如果是双平面组网，需填写业务平面IP地址。</li><li>采用IPv6地址时，IP地址应写在中括号“[]”中。</li><li>部署主备Kerberos服务或者对端系统内有多个集群需要与本端建立互信时，多个KDC地址使用逗号分隔。</li><li>端口值可通过查看KrbServer服务的“kdc_ports”参数获取，默认值为“21732”。部署服务的节点IP可通过在KrbServer服务页面选择“实例”页签，查看KerberosServer角色的“业务IP”获取。<p id="zh-cn_topic_0046737083_p18945981"><a name="zh-cn_topic_0046737083_p18945981"></a><a name="zh-cn_topic_0046737083_p18945981"></a>例如，Kerberos服务部署在10.0.0.1和10.0.0.2上，与本端系统建立互信，则对应参数值为“10.0.0.1:21732,10.0.0.2:21732”。</p>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果需要配置与多个Manager系统的互信关系，请单击![](figures/a.png)添加新项目，并填写参数值。最多支持16个系统。删除多余的配置请单击![](figures/b.png)。

5.  单击“确定”。
6.  以**omm**用户登录主管理节点，执行以下命令更新域配置。

    **sh $\{BIGDATA\_HOME\}/om-server/om/sbin/restart-RealmConfig.sh**

    提示以下信息表示命令执行成功。

    ```
    Modify realm successfully. Use the new password to log into FusionInsight again.
    ```

    重启后部分主机与服务可能无法访问并触发告警，执行“restart-RealmConfig.sh”后大约需要1分钟自动恢复。

7.  登录FusionInsight Manager，启动所有集群。

    单击主页上待操作集群名称后的![](figures/zh-cn_image_0263899495.png)，单击“启动”，在“启动集群”窗口单击“确定”，等待集群启动成功。

8.  登录另外一个系统的FusionInsight Manager，重复以上操作。

