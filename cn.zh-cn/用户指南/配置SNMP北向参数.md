# 配置SNMP北向参数<a name="ZH-CN_TOPIC_0174499318"></a>

## 操作场景<a name="zh-cn_topic_0035209607_section44841084183850"></a>

该任务指导用户采用SNMP协议把MRS Manager的告警、监控数据集成到网管平台。

## 前提条件<a name="zh-cn_topic_0035209607_section36395386183434"></a>

对接服务器对应的弹性云服务器需要和MRS集群的Master节点在相同的VPC，且Master节点可以访问对接服务器的IP地址和指定端口。

## 操作步骤<a name="zh-cn_topic_0035209607_section64229460183937"></a>

1.  在MRS Manager，单击“系统设置”。
2.  在“配置”区域“监控和告警配置”下，单击“SNMP配置”。

    “SNMP服务”的开关默认为关闭，单击启用SNMP服务。

3.  设置[表1](#zh-cn_topic_0035209607_table981749184027)所示的对接参数。

    **表 1**  对接参数

    <a name="zh-cn_topic_0035209607_table981749184027"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0035209607_row56396084184027"><th class="cellrowborder" valign="top" width="25.16%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0035209607_p4680074184027"><a name="zh-cn_topic_0035209607_p4680074184027"></a><a name="zh-cn_topic_0035209607_p4680074184027"></a><strong id="zh-cn_topic_0035209607_b55176335184047"><a name="zh-cn_topic_0035209607_b55176335184047"></a><a name="zh-cn_topic_0035209607_b55176335184047"></a>参数名称</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="74.83999999999999%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0035209607_p43541750184027"><a name="zh-cn_topic_0035209607_p43541750184027"></a><a name="zh-cn_topic_0035209607_p43541750184027"></a><strong id="zh-cn_topic_0035209607_b40098116184047"><a name="zh-cn_topic_0035209607_b40098116184047"></a><a name="zh-cn_topic_0035209607_b40098116184047"></a>参数说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0035209607_row37220829184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p62097193184027"><a name="zh-cn_topic_0035209607_p62097193184027"></a><a name="zh-cn_topic_0035209607_p62097193184027"></a>版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p63816770184027"><a name="zh-cn_topic_0035209607_p63816770184027"></a><a name="zh-cn_topic_0035209607_p63816770184027"></a>SNMP协议版本号，取值范围：</p>
    <a name="zh-cn_topic_0035209607_ul37480023184027"></a><a name="zh-cn_topic_0035209607_ul37480023184027"></a><ul id="zh-cn_topic_0035209607_ul37480023184027"><li>v2c：低版本，安全性较低</li><li>v3：高版本，安全性比v2c高</li></ul>
    <p id="zh-cn_topic_0035209607_p9629177184027"><a name="zh-cn_topic_0035209607_p9629177184027"></a><a name="zh-cn_topic_0035209607_p9629177184027"></a>推荐使用v3版本。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row19553732184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p40348451184027"><a name="zh-cn_topic_0035209607_p40348451184027"></a><a name="zh-cn_topic_0035209607_p40348451184027"></a>本地端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p46999123184027"><a name="zh-cn_topic_0035209607_p46999123184027"></a><a name="zh-cn_topic_0035209607_p46999123184027"></a>本地端口，默认值“20000”，取值范围“1025”到“65535”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row20338929184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p36840541184027"><a name="zh-cn_topic_0035209607_p36840541184027"></a><a name="zh-cn_topic_0035209607_p36840541184027"></a>读团体名</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p31293805184027"><a name="zh-cn_topic_0035209607_p31293805184027"></a><a name="zh-cn_topic_0035209607_p31293805184027"></a>该参数仅在设置“版本”为v2c时存在，用于设置只读团体名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row13208790184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p63279064184027"><a name="zh-cn_topic_0035209607_p63279064184027"></a><a name="zh-cn_topic_0035209607_p63279064184027"></a>写团体名</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p25330546184027"><a name="zh-cn_topic_0035209607_p25330546184027"></a><a name="zh-cn_topic_0035209607_p25330546184027"></a>该参数仅在设置“版本”为v2c时存在，用于设置可写团体名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row26648328184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p11030970184027"><a name="zh-cn_topic_0035209607_p11030970184027"></a><a name="zh-cn_topic_0035209607_p11030970184027"></a>安全用户名</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p21093401184027"><a name="zh-cn_topic_0035209607_p21093401184027"></a><a name="zh-cn_topic_0035209607_p21093401184027"></a>该参数仅在设置“版本”为v3时存在，用于设置协议安全用户名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row55622884184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p9159793184027"><a name="zh-cn_topic_0035209607_p9159793184027"></a><a name="zh-cn_topic_0035209607_p9159793184027"></a>认证协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p3745758184027"><a name="zh-cn_topic_0035209607_p3745758184027"></a><a name="zh-cn_topic_0035209607_p3745758184027"></a>该参数仅在设置“版本”为v3时存在，用于设置认证协议，推荐选择SHA。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row33711824184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p46303217184027"><a name="zh-cn_topic_0035209607_p46303217184027"></a><a name="zh-cn_topic_0035209607_p46303217184027"></a>认证密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p59573062184027"><a name="zh-cn_topic_0035209607_p59573062184027"></a><a name="zh-cn_topic_0035209607_p59573062184027"></a>该参数仅在设置“版本”为v3时存在，用于设置认证密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row66395511184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p9327350184027"><a name="zh-cn_topic_0035209607_p9327350184027"></a><a name="zh-cn_topic_0035209607_p9327350184027"></a>确认认证密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p17317918184027"><a name="zh-cn_topic_0035209607_p17317918184027"></a><a name="zh-cn_topic_0035209607_p17317918184027"></a>该参数仅在设置“版本”为v3时存在，用于确认认证密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row21643536184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p8296007184027"><a name="zh-cn_topic_0035209607_p8296007184027"></a><a name="zh-cn_topic_0035209607_p8296007184027"></a>加密协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p887995184027"><a name="zh-cn_topic_0035209607_p887995184027"></a><a name="zh-cn_topic_0035209607_p887995184027"></a>该参数仅在设置“版本”为v3时存在，用于设置加密协议，推荐选择AES256。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row7991959184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p43368944184027"><a name="zh-cn_topic_0035209607_p43368944184027"></a><a name="zh-cn_topic_0035209607_p43368944184027"></a>加密密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p23223610184027"><a name="zh-cn_topic_0035209607_p23223610184027"></a><a name="zh-cn_topic_0035209607_p23223610184027"></a>该参数仅在设置“版本”为v3时存在，用于设置加密密钥。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209607_row7685905184027"><td class="cellrowborder" valign="top" width="25.16%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035209607_p18578567184027"><a name="zh-cn_topic_0035209607_p18578567184027"></a><a name="zh-cn_topic_0035209607_p18578567184027"></a>确认加密密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="74.83999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035209607_p28468929184027"><a name="zh-cn_topic_0035209607_p28468929184027"></a><a name="zh-cn_topic_0035209607_p28468929184027"></a>该参数仅在设置“版本”为v3时存在，用于确认加密密钥。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   “认证密码”和“加密密码”密码长度为8到16位，至少需要包含大写字母、小写字母、数字、特殊字符中的3种类型字符。两个密码不能相同。两个密码不可和安全用户名或安全用户名的逆序字符相同。  
    >-   使用SNMP协议从安全方面考虑，需要定期修改“认证密码”和“加密密码”密码。  
    >-   使用SNMP v3版本时，安全用户在5分钟之内连续鉴权失败5次将被锁定，5分钟后自动解锁。  

4.  单击“Trap目标”下的“添加Trap目标”，在弹出的“添加Trap目标”对话框中填写以下参数：

    -   目标标识：Trap目标标识，一般指接收Trap的网管或主机标识。长度限制1～255字节，一般由字母或数字组成。
    -   目标IP：目标IP。可使用A、B、C类IP地址，要求可与管理节点的管理平面IP地址互通。
    -   目标端口：接收Trap的端口，要求与对端保持一致，取值范围“0”～“65535”。
    -   Trap团体名：该参数仅在设置Version为v2c时存在，用于设置主动上报团体名。

    单击“确定”，设置完成，退出“添加Trap目标”对话框。

5.  单击“确定”，设置完成。

