# 配置SNMP北向参数<a name="admin_guide_000154"></a>

## 操作场景<a name="zh-cn_topic_0263899360_sa61d1e65e5644bdea96e04c39dcfd81d"></a>

如果用户需要在统一的运维网管平台查看集群的告警、监控数据，管理员可以在FusionInsight Manager使用SNMP服务将相关数据上报到网管平台。

## 操作步骤<a name="zh-cn_topic_0263899360_section3469198164614"></a>

1.  登录FusionInsight Manager。
2.  选择“系统  \>  对接  \>  SNMP“。
3.  单击“SNMP服务”右侧的开关。

    “SNMP服务”默认为不启用，开关显示为![](figures/zh-cn_image_0263899496.png)表示启用。

4.  根据[表1](#zh-cn_topic_0263899360_zh-cn_topic_0046736864_tab01)所示的说明填写对接参数。

    **表 1**  对接参数

    <a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_tab01"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row5678417"><th class="cellrowborder" valign="top" width="35.35%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p57298643"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p57298643"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p57298643"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="64.64999999999999%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10678530"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10678530"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10678530"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row59654597"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p184197"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p184197"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p184197"></a>版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14919977"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14919977"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14919977"></a>SNMP协议版本号，取值范围：</p>
    <a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_ul62068"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_ul62068"></a><ul id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_ul62068"><li>V2C：低版本，安全性较低。</li><li>V3：高版本，安全性更高。</li></ul>
    <p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p45248063"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p45248063"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p45248063"></a>推荐使用V3版本。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row4579384"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p35385863"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p35385863"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p35385863"></a>本地端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p47682687"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p47682687"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p47682687"></a>本地端口，默认值“20000”，取值范围“1025”到“65535”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row26491001"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p65396352"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p65396352"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p65396352"></a>读团体名</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p62613188"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p62613188"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p62613188"></a>该参数仅在设置“版本”为v2c时可用，用于设置只读团体名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row26647784"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10986897"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10986897"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p10986897"></a>写团体名</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p17523499"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p17523499"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p17523499"></a>该参数仅在设置“版本”为v2c时可用，用于设置可写团体名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row23493770"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p23947216"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p23947216"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p23947216"></a>安全用户名</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p60676314"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p60676314"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p60676314"></a>该参数仅在设置“版本”为v3时可用，用于设置协议安全用户名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row9215916"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p8291736"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p8291736"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p8291736"></a>认证协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p542012"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p542012"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p542012"></a>该参数仅在设置“版本”为v3时可用，用于设置认证协议，推荐选择SHA。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row4878115"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p59583055"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p59583055"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p59583055"></a>认证密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p61498184"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p61498184"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p61498184"></a>该参数仅在设置“版本”为v3时可用，用于设置认证密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row16612749"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p3455395"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p3455395"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p3455395"></a>确认认证密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p11451578"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p11451578"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p11451578"></a>该参数仅在设置“版本”为v3时可用，用于确认认证密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row35955341"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p26701512"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p26701512"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p26701512"></a>加密协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p15338839"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p15338839"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p15338839"></a>该参数仅在设置“版本”为v3时可用，用于设置加密协议，推荐选择AES256。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row3831826"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41942459"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41942459"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41942459"></a>加密密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41895980"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41895980"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p41895980"></a>该参数仅在设置“版本”为v3时可用，用于设置加密密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_row41519503"><td class="cellrowborder" valign="top" width="35.35%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p7636608"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p7636608"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p7636608"></a>确认加密密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.64999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14585550"><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14585550"></a><a name="zh-cn_topic_0263899360_zh-cn_topic_0046736864_p14585550"></a>该参数仅在设置“版本”为v3时可用，用于确认加密密钥。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   “安全用户名”中禁止出现以64的公因子（1、2、4、8等）为单位长度的重复字符串，例如abab，abcdabcd。
    >-   “认证密码”和“加密密码”密码长度为8到16位，至少需要包含大写字母、小写字母、数字、特殊字符中的3种类型字符。两个密码不能相同。两个密码不可和安全用户名相同或安全用户名的倒序字符相同。
    >-   使用SNMP协议从安全方面考虑，需要定期修改“认证密码”和“加密密码”密码。
    >-   使用SNMP v3版本时，安全用户在5分钟之内连续鉴权失败5次将被锁定，5分钟后自动解锁。

5.  单击“添加Trap目标”，在弹出的“添加Trap目标”对话框中填写以下参数：

    -   目标标识：Trap目标标识，一般指接收Trap的网管或主机标识。长度限制1～255字节，一般由字母或数字组成。
    -   目标IP模式：目标IP的IP地址模式，可选择“IPV4“或者“IPV6“。
    -   目标IP：目标IP，要求可与管理节点的管理平面IP地址互通。
    -   目标端口：接收Trap的端口，要求与对端保持一致，取值范围“0～65535”。
    -   Trap团体名：该参数仅在设置版本为V2C时可用，用于设置主动上报团体名。

    单击“确定”，设置完成，退出“添加Trap目标”对话框。

6.  单击“确定”，设置完成。

