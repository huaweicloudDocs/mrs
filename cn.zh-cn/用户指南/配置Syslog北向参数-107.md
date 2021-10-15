# 配置Syslog北向参数<a name="admin_guide_000155"></a>

## 操作场景<a name="zh-cn_topic_0263899650_s42593dcae9e5421d931e12108cb5b0b2"></a>

如果用户需要在统一的告警平台查看集群的告警和事件，管理员可以在FusionInsight Manager使用Syslog协议将相关数据上报到告警平台。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>Syslog协议未做加密，传输数据容易被窃取，存在安全风险。

## 操作步骤<a name="zh-cn_topic_0263899650_section12167315152819"></a>

1.  登录FusionInsight Manager。
2.  选择“系统  \>  对接  \>  Syslog“。
3.  单击“Syslog服务”右侧的开关。

    “Syslog服务”默认为不启用，开关显示为![](figures/zh-cn_image_0263899496.png)表示启用。

4.  根据[表1](#zh-cn_topic_0263899650_tba2589a9e61145faacec7d81c6eb3235)所示的说明填写北向参数。

    **表 1**  Syslog对接参数

    <a name="zh-cn_topic_0263899650_tba2589a9e61145faacec7d81c6eb3235"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0263899650_r550ac50acd6c4a1d967a603266e5b8f2"><th class="cellrowborder" valign="top" width="13.86%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0263899650_a2a00056ccfce4f70b0c752b17f58f449"><a name="zh-cn_topic_0263899650_a2a00056ccfce4f70b0c752b17f58f449"></a><a name="zh-cn_topic_0263899650_a2a00056ccfce4f70b0c752b17f58f449"></a>参数区域</p>
    </th>
    <th class="cellrowborder" valign="top" width="15.840000000000002%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0263899650_aa2498f46cfa644d1bd4b9f9390e2b185"><a name="zh-cn_topic_0263899650_aa2498f46cfa644d1bd4b9f9390e2b185"></a><a name="zh-cn_topic_0263899650_aa2498f46cfa644d1bd4b9f9390e2b185"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="70.3%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0263899650_a3d62c772501644648997081ecda88601"><a name="zh-cn_topic_0263899650_a3d62c772501644648997081ecda88601"></a><a name="zh-cn_topic_0263899650_a3d62c772501644648997081ecda88601"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0263899650_row173214818311"><td class="cellrowborder" rowspan="7" valign="top" width="13.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_abce0940bd0314a6fa10cdb62cafc3560"><a name="zh-cn_topic_0263899650_abce0940bd0314a6fa10cdb62cafc3560"></a><a name="zh-cn_topic_0263899650_abce0940bd0314a6fa10cdb62cafc3560"></a>Syslog协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_p173234813311"><a name="zh-cn_topic_0263899650_p173234813311"></a><a name="zh-cn_topic_0263899650_p173234813311"></a>服务IP模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="70.3%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_p13224810318"><a name="zh-cn_topic_0263899650_p13224810318"></a><a name="zh-cn_topic_0263899650_p13224810318"></a>设置对接服务器IP地址模式，可选择<span class="parmvalue" id="zh-cn_topic_0263899650_parmvalue68378551215"><a name="zh-cn_topic_0263899650_parmvalue68378551215"></a><a name="zh-cn_topic_0263899650_parmvalue68378551215"></a>“IPV4”</span>或者<span class="parmvalue" id="zh-cn_topic_0263899650_parmvalue2342105816210"><a name="zh-cn_topic_0263899650_parmvalue2342105816210"></a><a name="zh-cn_topic_0263899650_parmvalue2342105816210"></a>“IPV6”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r34bc846dbe0d4fcd9aa499582b529739"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_abe92325a1b4d4e6aacd52933b0ee3a1d"><a name="zh-cn_topic_0263899650_abe92325a1b4d4e6aacd52933b0ee3a1d"></a><a name="zh-cn_topic_0263899650_abe92325a1b4d4e6aacd52933b0ee3a1d"></a>服务IP</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a2bb89087076f43469de05f314fcb9c0f"><a name="zh-cn_topic_0263899650_a2bb89087076f43469de05f314fcb9c0f"></a><a name="zh-cn_topic_0263899650_a2bb89087076f43469de05f314fcb9c0f"></a>设置对接服务器IP地址。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_rd0a4686534ea41d68c2ca40566709e01"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a93e3c03160ea4379aa4fc2d4d54b723a"><a name="zh-cn_topic_0263899650_a93e3c03160ea4379aa4fc2d4d54b723a"></a><a name="zh-cn_topic_0263899650_a93e3c03160ea4379aa4fc2d4d54b723a"></a>服务端口</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a647e3cf7c7ae4a32ba279e7f5e3b9311"><a name="zh-cn_topic_0263899650_a647e3cf7c7ae4a32ba279e7f5e3b9311"></a><a name="zh-cn_topic_0263899650_a647e3cf7c7ae4a32ba279e7f5e3b9311"></a>设置对接端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r6f6bc1e357cf43388667a5fc77aef65b"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a1efd80b963dd4193ac3a6a4224063e4c"><a name="zh-cn_topic_0263899650_a1efd80b963dd4193ac3a6a4224063e4c"></a><a name="zh-cn_topic_0263899650_a1efd80b963dd4193ac3a6a4224063e4c"></a>协议</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_ac85a52099b1a4880ac680436f22a852b"><a name="zh-cn_topic_0263899650_ac85a52099b1a4880ac680436f22a852b"></a><a name="zh-cn_topic_0263899650_ac85a52099b1a4880ac680436f22a852b"></a>设置协议类型，可选值：</p>
    <a name="zh-cn_topic_0263899650_u51c521fec20a44edb0ff6b9fbfe18868"></a><a name="zh-cn_topic_0263899650_u51c521fec20a44edb0ff6b9fbfe18868"></a><ul id="zh-cn_topic_0263899650_u51c521fec20a44edb0ff6b9fbfe18868"><li>TCP</li><li>UDP</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r28459ca392f9415981b3f518274477a7"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a96c7b335d98e457cb44a42b25476d4c3"><a name="zh-cn_topic_0263899650_a96c7b335d98e457cb44a42b25476d4c3"></a><a name="zh-cn_topic_0263899650_a96c7b335d98e457cb44a42b25476d4c3"></a>安全级别</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_aa2a31570628c4e13a176e42dbec439dd"><a name="zh-cn_topic_0263899650_aa2a31570628c4e13a176e42dbec439dd"></a><a name="zh-cn_topic_0263899650_aa2a31570628c4e13a176e42dbec439dd"></a>设置上报消息的严重程度，取值范围：</p>
    <a name="zh-cn_topic_0263899650_u5826029a85e843508c5b027b850bd5d0"></a><a name="zh-cn_topic_0263899650_u5826029a85e843508c5b027b850bd5d0"></a><ul id="zh-cn_topic_0263899650_u5826029a85e843508c5b027b850bd5d0"><li>Emergency</li><li>Alert</li><li>Critical</li><li>Error</li><li>Warning</li><li>Notice</li><li>Informational（默认值）</li><li>Debug<div class="note" id="zh-cn_topic_0263899650_nce6f8aea10e44ed58560885c2f0ec97a"><a name="zh-cn_topic_0263899650_nce6f8aea10e44ed58560885c2f0ec97a"></a><a name="zh-cn_topic_0263899650_nce6f8aea10e44ed58560885c2f0ec97a"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0263899650_a6f45328b5c7741aa80d2784e1b50d4b0"><a name="zh-cn_topic_0263899650_a6f45328b5c7741aa80d2784e1b50d4b0"></a><a name="zh-cn_topic_0263899650_a6f45328b5c7741aa80d2784e1b50d4b0"></a><span class="parmname" id="zh-cn_topic_0263899650_pac2e1cfa4b194cb99d84f79ad72f7583"><a name="zh-cn_topic_0263899650_pac2e1cfa4b194cb99d84f79ad72f7583"></a><a name="zh-cn_topic_0263899650_pac2e1cfa4b194cb99d84f79ad72f7583"></a>“安全级别”</span>和<span class="parmname" id="zh-cn_topic_0263899650_p7174d8ea511f49ed80ff1dd5723a148f"><a name="zh-cn_topic_0263899650_p7174d8ea511f49ed80ff1dd5723a148f"></a><a name="zh-cn_topic_0263899650_p7174d8ea511f49ed80ff1dd5723a148f"></a>“Facility”</span>共同组成发出消息的优先级（<strong id="zh-cn_topic_0263899650_a03369fd3f09945d78452af441d9c642b"><a name="zh-cn_topic_0263899650_a03369fd3f09945d78452af441d9c642b"></a><a name="zh-cn_topic_0263899650_a03369fd3f09945d78452af441d9c642b"></a>Priority</strong>）。</p>
    <p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p135195994413"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p135195994413"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p135195994413"></a>优先级（<strong id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_b730620714457"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_b730620714457"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_b730620714457"></a>Priority</strong>）=&nbsp;<span class="parmname" id="zh-cn_topic_0263899650_pef38794bb484422c809146f82b35b3a4"><a name="zh-cn_topic_0263899650_pef38794bb484422c809146f82b35b3a4"></a><a name="zh-cn_topic_0263899650_pef38794bb484422c809146f82b35b3a4"></a>“Facility”</span>&nbsp;× 8 +<span class="parmname" id="zh-cn_topic_0263899650_p834680929ac244d98dc6eeb1add8445c"><a name="zh-cn_topic_0263899650_p834680929ac244d98dc6eeb1add8445c"></a><a name="zh-cn_topic_0263899650_p834680929ac244d98dc6eeb1add8445c"></a>“安全级别”</span></p>
    <p id="zh-cn_topic_0263899650_a1e8a9fbf210345b48a20dbfff6246cbd"><a name="zh-cn_topic_0263899650_a1e8a9fbf210345b48a20dbfff6246cbd"></a><a name="zh-cn_topic_0263899650_a1e8a9fbf210345b48a20dbfff6246cbd"></a><span class="parmname" id="zh-cn_topic_0263899650_p6c858bbead9b46c0ae717f91cfc77494"><a name="zh-cn_topic_0263899650_p6c858bbead9b46c0ae717f91cfc77494"></a><a name="zh-cn_topic_0263899650_p6c858bbead9b46c0ae717f91cfc77494"></a>“安全级别”</span>和<span class="parmname" id="zh-cn_topic_0263899650_p6983349338224dc18b4c65076091564e"><a name="zh-cn_topic_0263899650_p6983349338224dc18b4c65076091564e"></a><a name="zh-cn_topic_0263899650_p6983349338224dc18b4c65076091564e"></a>“Facility”</span>各项对应的数值请参考<a href="#zh-cn_topic_0263899650_t05bc8524f4804c44982ceceae14e8388">表2</a>。</p>
    </div></div>
    </li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r27497403735e49b6a15af2bdde329152"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a73b6e2dd41bf44f2a5fcbb87082a34c0"><a name="zh-cn_topic_0263899650_a73b6e2dd41bf44f2a5fcbb87082a34c0"></a><a name="zh-cn_topic_0263899650_a73b6e2dd41bf44f2a5fcbb87082a34c0"></a>Facility</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_acce3c9ab233c4b8fa0f7ef939138dc91"><a name="zh-cn_topic_0263899650_acce3c9ab233c4b8fa0f7ef939138dc91"></a><a name="zh-cn_topic_0263899650_acce3c9ab233c4b8fa0f7ef939138dc91"></a>设置产生日志的模块。可选项参考<a href="#zh-cn_topic_0263899650_t05bc8524f4804c44982ceceae14e8388">表2</a>，推荐使用默认值<span class="parmvalue" id="zh-cn_topic_0263899650_p39f11138c3534beeac97564d0285ba45"><a name="zh-cn_topic_0263899650_p39f11138c3534beeac97564d0285ba45"></a><a name="zh-cn_topic_0263899650_p39f11138c3534beeac97564d0285ba45"></a>“local use 0 (local0)”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r3917aacdeef749039d83834681b8bbd9"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a279f49c9aa56497e935502ad49339550"><a name="zh-cn_topic_0263899650_a279f49c9aa56497e935502ad49339550"></a><a name="zh-cn_topic_0263899650_a279f49c9aa56497e935502ad49339550"></a>标识符</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a56fc6fd236c6440f8e0853aa655ade43"><a name="zh-cn_topic_0263899650_a56fc6fd236c6440f8e0853aa655ade43"></a><a name="zh-cn_topic_0263899650_a56fc6fd236c6440f8e0853aa655ade43"></a>设置产品标识，默认为“FusionInsight Manager”。</p>
    <p id="zh-cn_topic_0263899650_a993f3a7bca0f47ccbc86769b3625821b"><a name="zh-cn_topic_0263899650_a993f3a7bca0f47ccbc86769b3625821b"></a><a name="zh-cn_topic_0263899650_a993f3a7bca0f47ccbc86769b3625821b"></a>标识符可以包含字母、数字、下划线、 空格、|、 $、 {、 }、 点、中划线，并且不能超过256个字符。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r7ee8cd8d971e46219629001590136c2d"><td class="cellrowborder" rowspan="3" valign="top" width="13.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_ad86235be3b8e4c7e9768438f9dcf9324"><a name="zh-cn_topic_0263899650_ad86235be3b8e4c7e9768438f9dcf9324"></a><a name="zh-cn_topic_0263899650_ad86235be3b8e4c7e9768438f9dcf9324"></a>报告信息</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a241eda6390b24c44aabed7d08cf6c0d2"><a name="zh-cn_topic_0263899650_a241eda6390b24c44aabed7d08cf6c0d2"></a><a name="zh-cn_topic_0263899650_a241eda6390b24c44aabed7d08cf6c0d2"></a>报文格式</p>
    </td>
    <td class="cellrowborder" valign="top" width="70.3%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a91805214d12f421887d3cc165dfa48a6"><a name="zh-cn_topic_0263899650_a91805214d12f421887d3cc165dfa48a6"></a><a name="zh-cn_topic_0263899650_a91805214d12f421887d3cc165dfa48a6"></a>设置告警报告的消息格式，具体要求请参考界面帮助。</p>
    <p id="zh-cn_topic_0263899650_a3e032fae4fd14801bd0a75362f1d50c5"><a name="zh-cn_topic_0263899650_a3e032fae4fd14801bd0a75362f1d50c5"></a><a name="zh-cn_topic_0263899650_a3e032fae4fd14801bd0a75362f1d50c5"></a>报文格式可以包含字母、数字、下划线、 空格、|、 $、 {、 }、 点、中划线，并且不能超过1024个字符。</p>
    <div class="note" id="zh-cn_topic_0263899650_nbe2dd3c5868f4e97a2834f25f7e11d0b"><a name="zh-cn_topic_0263899650_nbe2dd3c5868f4e97a2834f25f7e11d0b"></a><a name="zh-cn_topic_0263899650_nbe2dd3c5868f4e97a2834f25f7e11d0b"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0263899650_aa27c946c96e34d36922c8dbb1e1a8a94"><a name="zh-cn_topic_0263899650_aa27c946c96e34d36922c8dbb1e1a8a94"></a><a name="zh-cn_topic_0263899650_aa27c946c96e34d36922c8dbb1e1a8a94"></a>报文格式中信息域的说明请参考<a href="#zh-cn_topic_0263899650_t614aa61f080f47f0ba68c57aa68e7dc1">表3</a>。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_rb8fdd0e814d94e6ebcb815c55d878101"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a6ed44584e76d447bbc4b98661f86e264"><a name="zh-cn_topic_0263899650_a6ed44584e76d447bbc4b98661f86e264"></a><a name="zh-cn_topic_0263899650_a6ed44584e76d447bbc4b98661f86e264"></a>报告信息类型</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a0e513e37b06c4eba834b1ce3b78d53c1"><a name="zh-cn_topic_0263899650_a0e513e37b06c4eba834b1ce3b78d53c1"></a><a name="zh-cn_topic_0263899650_a0e513e37b06c4eba834b1ce3b78d53c1"></a>设置需要上报的告警类型。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_rd649f98bec494f488d1c71f0cca2cb8d"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a4fc7caad9c6b4d218f8ed12d29120f98"><a name="zh-cn_topic_0263899650_a4fc7caad9c6b4d218f8ed12d29120f98"></a><a name="zh-cn_topic_0263899650_a4fc7caad9c6b4d218f8ed12d29120f98"></a>上报消息级别</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a54139a3877644ee0aa95546c198acf85"><a name="zh-cn_topic_0263899650_a54139a3877644ee0aa95546c198acf85"></a><a name="zh-cn_topic_0263899650_a54139a3877644ee0aa95546c198acf85"></a>设置需要上报的告警级别。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r9c5926ec0fbc450cb13377d4632880dc"><td class="cellrowborder" rowspan="2" valign="top" width="13.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a73c2ee8dee5841409dfe13ea281b3075"><a name="zh-cn_topic_0263899650_a73c2ee8dee5841409dfe13ea281b3075"></a><a name="zh-cn_topic_0263899650_a73c2ee8dee5841409dfe13ea281b3075"></a>未恢复告警上报设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a2b0728524fd348098070cd5c8bd889fb"><a name="zh-cn_topic_0263899650_a2b0728524fd348098070cd5c8bd889fb"></a><a name="zh-cn_topic_0263899650_a2b0728524fd348098070cd5c8bd889fb"></a>周期上报未恢复告警</p>
    </td>
    <td class="cellrowborder" valign="top" width="70.3%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a7efe26b1b59a4471b257f0abe3dd8df0"><a name="zh-cn_topic_0263899650_a7efe26b1b59a4471b257f0abe3dd8df0"></a><a name="zh-cn_topic_0263899650_a7efe26b1b59a4471b257f0abe3dd8df0"></a>设置是否按指定周期上报未清除的告警。打开开关表示启用此功能，关闭开关表示不启用。开关默认为关闭。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_r63c442d8eb51430581263e12dfcbfd51"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_abe7b6b2a0c1542c8a64a6cabc6f2b69b"><a name="zh-cn_topic_0263899650_abe7b6b2a0c1542c8a64a6cabc6f2b69b"></a><a name="zh-cn_topic_0263899650_abe7b6b2a0c1542c8a64a6cabc6f2b69b"></a>间隔时间（分钟）</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a0be11c463ceb4b83a6af2318d3849877"><a name="zh-cn_topic_0263899650_a0be11c463ceb4b83a6af2318d3849877"></a><a name="zh-cn_topic_0263899650_a0be11c463ceb4b83a6af2318d3849877"></a>设置周期上报告警的时间间隔，当“周期上报未恢复告警”开关设置为打开时启用。单位为分钟，默认值为“15”，支持范围为“5”到“1440”（1天）。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_rc818398b7daa4dbebe4ddbaffcc9b375"><td class="cellrowborder" rowspan="3" valign="top" width="13.86%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a02efb03bf98d438ca6a17f750d6c700c"><a name="zh-cn_topic_0263899650_a02efb03bf98d438ca6a17f750d6c700c"></a><a name="zh-cn_topic_0263899650_a02efb03bf98d438ca6a17f750d6c700c"></a>心跳设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_af0fe95a49296427b8ada933b7e1c6621"><a name="zh-cn_topic_0263899650_af0fe95a49296427b8ada933b7e1c6621"></a><a name="zh-cn_topic_0263899650_af0fe95a49296427b8ada933b7e1c6621"></a>上报心跳</p>
    </td>
    <td class="cellrowborder" valign="top" width="70.3%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a54dda0a8be89467993e44f9cc54040fb"><a name="zh-cn_topic_0263899650_a54dda0a8be89467993e44f9cc54040fb"></a><a name="zh-cn_topic_0263899650_a54dda0a8be89467993e44f9cc54040fb"></a>设置是否开启周期上报Syslog心跳消息。打开开关表示开启此功能，关闭开关表示不启用。开关默认为关闭。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_raef3e745f38f48e19aeffeae0bad5fc4"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_ae396007232154196b857b37570a681a7"><a name="zh-cn_topic_0263899650_ae396007232154196b857b37570a681a7"></a><a name="zh-cn_topic_0263899650_ae396007232154196b857b37570a681a7"></a>心跳周期（分钟）</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a68e8034d8a9c400ba789c673463e8437"><a name="zh-cn_topic_0263899650_a68e8034d8a9c400ba789c673463e8437"></a><a name="zh-cn_topic_0263899650_a68e8034d8a9c400ba789c673463e8437"></a>设置周期上报心跳的时间间隔，当“上报心跳”开关设置为打开时启用。单位为分钟，默认值为“15”，支持范围为“1”到“60”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899650_rac5db9042854496bbc8ebed074f33b20"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_abacc594f309a4ffba20e2246ff6ff539"><a name="zh-cn_topic_0263899650_abacc594f309a4ffba20e2246ff6ff539"></a><a name="zh-cn_topic_0263899650_abacc594f309a4ffba20e2246ff6ff539"></a>心跳报文</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a69d21acbf8a34146922c385820a3c5a5"><a name="zh-cn_topic_0263899650_a69d21acbf8a34146922c385820a3c5a5"></a><a name="zh-cn_topic_0263899650_a69d21acbf8a34146922c385820a3c5a5"></a>设置心跳上报的内容，当“上报心跳”开关设置为打开时启用，不能为空。支持数字、字母、下划线、竖线、冒号、空格、英文逗号和句号字符，长度小于等于256。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >设置周期上报心跳报文后，在某些集群容错自动恢复的场景下（例如主备OMS倒换）可能会出现报文上报中断的现象，此时等待自动恢复即可。

5.  单击“确定”，设置完成。

## 参考信息<a name="zh-cn_topic_0263899650_sc27fff8256d7482092b1fe6dfb4391cb"></a>

**表 2** “安全级别“和“Facility“**字段数值编码**

<a name="zh-cn_topic_0263899650_t05bc8524f4804c44982ceceae14e8388"></a>
<table><thead align="left"><tr id="zh-cn_topic_0263899650_r4e18a9ed85504b0eb644fc46387a51ff"><th class="cellrowborder" valign="top" width="28.28282828282828%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0263899650_a11292efe65924cf29b53f8bcdb494815"><a name="zh-cn_topic_0263899650_a11292efe65924cf29b53f8bcdb494815"></a><a name="zh-cn_topic_0263899650_a11292efe65924cf29b53f8bcdb494815"></a>安全级别</p>
</th>
<th class="cellrowborder" valign="top" width="43.43434343434344%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p983413232477"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p983413232477"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p983413232477"></a>Facility</p>
</th>
<th class="cellrowborder" valign="top" width="28.28282828282828%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p384361355420"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p384361355420"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p384361355420"></a>数值编码</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0263899650_re42ef90b20f24e67b56dd7d204442dd2"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_ac18556c51ffc4fd3a5d8ed73ab54f501"><a name="zh-cn_topic_0263899650_ac18556c51ffc4fd3a5d8ed73ab54f501"></a><a name="zh-cn_topic_0263899650_ac18556c51ffc4fd3a5d8ed73ab54f501"></a>Emergency</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_ab414d2707a36484b9cf801adefcb92a9"><a name="zh-cn_topic_0263899650_ab414d2707a36484b9cf801adefcb92a9"></a><a name="zh-cn_topic_0263899650_ab414d2707a36484b9cf801adefcb92a9"></a>kernel messages</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p10301795543"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p10301795543"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p10301795543"></a>0</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r402c32fa294043f4bd91142aeba08a66"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a1d2421e1f58a42c9a54b1954e70fab4d"><a name="zh-cn_topic_0263899650_a1d2421e1f58a42c9a54b1954e70fab4d"></a><a name="zh-cn_topic_0263899650_a1d2421e1f58a42c9a54b1954e70fab4d"></a>Alert</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a0f4ab8bc08a549d7b7421d72c30e5e4f"><a name="zh-cn_topic_0263899650_a0f4ab8bc08a549d7b7421d72c30e5e4f"></a><a name="zh-cn_topic_0263899650_a0f4ab8bc08a549d7b7421d72c30e5e4f"></a>user-level messages</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p113016910541"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p113016910541"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p113016910541"></a>1</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_rd47aea7e6a9c4d73b9a3affab735ec32"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a50d8226619264676b8634c504eda4ea8"><a name="zh-cn_topic_0263899650_a50d8226619264676b8634c504eda4ea8"></a><a name="zh-cn_topic_0263899650_a50d8226619264676b8634c504eda4ea8"></a>Critical</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a63635b34fa8e41d0ac8682668359a3a6"><a name="zh-cn_topic_0263899650_a63635b34fa8e41d0ac8682668359a3a6"></a><a name="zh-cn_topic_0263899650_a63635b34fa8e41d0ac8682668359a3a6"></a>mail system</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17301391548"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17301391548"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17301391548"></a>2</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r8a097018d9ac4b9c9df7ab9f4bce8cf9"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p037115785019"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p037115785019"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p037115785019"></a>Error</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a77016add88fd4f2cb7881a013715b9c4"><a name="zh-cn_topic_0263899650_a77016add88fd4f2cb7881a013715b9c4"></a><a name="zh-cn_topic_0263899650_a77016add88fd4f2cb7881a013715b9c4"></a>system daemons</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p11301996541"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p11301996541"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p11301996541"></a>3</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r6e5dbd43673e49068ede2cb840383d74"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p83723573502"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p83723573502"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p83723573502"></a>Warning</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p568116152492"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p568116152492"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p568116152492"></a>security/authorization messages (note 1)</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133022995415"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133022995415"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133022995415"></a>4</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r8b050ff8d8754fbe83c86e4f641ee627"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a31278d5838b045aaadc74a96b4462efd"><a name="zh-cn_topic_0263899650_a31278d5838b045aaadc74a96b4462efd"></a><a name="zh-cn_topic_0263899650_a31278d5838b045aaadc74a96b4462efd"></a>Notice</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a4082162cbe644c3f92c760927717fade"><a name="zh-cn_topic_0263899650_a4082162cbe644c3f92c760927717fade"></a><a name="zh-cn_topic_0263899650_a4082162cbe644c3f92c760927717fade"></a>messages generated internally by syslogd</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p3302290547"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p3302290547"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p3302290547"></a>5</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r1aa52136ba4a46d5888d8438f75e3f57"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p937219579505"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p937219579505"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p937219579505"></a>Informational</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a22a1f9408ad4420d937f8449bff7c656"><a name="zh-cn_topic_0263899650_a22a1f9408ad4420d937f8449bff7c656"></a><a name="zh-cn_topic_0263899650_a22a1f9408ad4420d937f8449bff7c656"></a>line printer subsystem</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17302693540"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17302693540"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p17302693540"></a>6</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r0621a25bb4fa40eab9700efc4673d307"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_af3080cfa3a4e413fa0035ac29a3bbd21"><a name="zh-cn_topic_0263899650_af3080cfa3a4e413fa0035ac29a3bbd21"></a><a name="zh-cn_topic_0263899650_af3080cfa3a4e413fa0035ac29a3bbd21"></a>Debug</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_ac680d6076444490b80a29d1a980e1ca4"><a name="zh-cn_topic_0263899650_ac680d6076444490b80a29d1a980e1ca4"></a><a name="zh-cn_topic_0263899650_ac680d6076444490b80a29d1a980e1ca4"></a>network news subsystem</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p030219175419"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p030219175419"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p030219175419"></a>7</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r12b8ab626b7b43d087acb37d500550cd"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p172859417495"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p172859417495"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p172859417495"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p368251516498"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p368251516498"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p368251516498"></a>UUCP subsystem</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a9e6be324183a429bb25b04c358e50d83"><a name="zh-cn_topic_0263899650_a9e6be324183a429bb25b04c358e50d83"></a><a name="zh-cn_topic_0263899650_a9e6be324183a429bb25b04c358e50d83"></a>8</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r0bbc6466013d41b4954a2288739ff501"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p128504144911"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p128504144911"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p128504144911"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a72ce4bfc550e4904827a1d983425a8e0"><a name="zh-cn_topic_0263899650_a72ce4bfc550e4904827a1d983425a8e0"></a><a name="zh-cn_topic_0263899650_a72ce4bfc550e4904827a1d983425a8e0"></a>clock daemon (note 2)</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p830219919544"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p830219919544"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p830219919544"></a>9</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_row6989439497"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a407716d1d5c04ef89435192192f15379"><a name="zh-cn_topic_0263899650_a407716d1d5c04ef89435192192f15379"></a><a name="zh-cn_topic_0263899650_a407716d1d5c04ef89435192192f15379"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_ad24f458a018d4ab69a736a4ff23a6db6"><a name="zh-cn_topic_0263899650_ad24f458a018d4ab69a736a4ff23a6db6"></a><a name="zh-cn_topic_0263899650_ad24f458a018d4ab69a736a4ff23a6db6"></a>security/authorization messages</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p33029925410"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p33029925410"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p33029925410"></a>10</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_rb59b3512d34d460b9c05addf4c69e141"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p12866410498"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p12866410498"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p12866410498"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_ab48c846efb15406a86a215a93ec41e4e"><a name="zh-cn_topic_0263899650_ab48c846efb15406a86a215a93ec41e4e"></a><a name="zh-cn_topic_0263899650_ab48c846efb15406a86a215a93ec41e4e"></a>FTP daemon</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_aca2c08580df94ee1acc78453a0fe5b77"><a name="zh-cn_topic_0263899650_aca2c08580df94ee1acc78453a0fe5b77"></a><a name="zh-cn_topic_0263899650_aca2c08580df94ee1acc78453a0fe5b77"></a>11</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r832c409c3b9747e697897a84d9c5f80b"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p228614116496"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p228614116496"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p228614116496"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_aef11fa2a63884cde877f58f3e125e1fb"><a name="zh-cn_topic_0263899650_aef11fa2a63884cde877f58f3e125e1fb"></a><a name="zh-cn_topic_0263899650_aef11fa2a63884cde877f58f3e125e1fb"></a>NTP subsystem</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a68bab5349abf4615b9c6802dc69c54a6"><a name="zh-cn_topic_0263899650_a68bab5349abf4615b9c6802dc69c54a6"></a><a name="zh-cn_topic_0263899650_a68bab5349abf4615b9c6802dc69c54a6"></a>12</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r5430edc71f97432185e9ced557ffed01"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a2a378a596c5948579ce4b561ba6859f0"><a name="zh-cn_topic_0263899650_a2a378a596c5948579ce4b561ba6859f0"></a><a name="zh-cn_topic_0263899650_a2a378a596c5948579ce4b561ba6859f0"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_aa6557ed18d074494831c05b96d6f23a3"><a name="zh-cn_topic_0263899650_aa6557ed18d074494831c05b96d6f23a3"></a><a name="zh-cn_topic_0263899650_aa6557ed18d074494831c05b96d6f23a3"></a>log audit (note 1)</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p8302794546"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p8302794546"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p8302794546"></a>13</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_row711997498"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_ac1fe293e65794fd2b7ada80fffdabcb7"><a name="zh-cn_topic_0263899650_ac1fe293e65794fd2b7ada80fffdabcb7"></a><a name="zh-cn_topic_0263899650_ac1fe293e65794fd2b7ada80fffdabcb7"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_a705689d593cb4a7b964ff2010a9322ad"><a name="zh-cn_topic_0263899650_a705689d593cb4a7b964ff2010a9322ad"></a><a name="zh-cn_topic_0263899650_a705689d593cb4a7b964ff2010a9322ad"></a>log alert (note 1)</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_a00b02bcec86247938df2be476495b198"><a name="zh-cn_topic_0263899650_a00b02bcec86247938df2be476495b198"></a><a name="zh-cn_topic_0263899650_a00b02bcec86247938df2be476495b198"></a>14</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_row9112917496"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p42864416496"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p42864416496"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p42864416496"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_af5ba424e876c470b953ad2ec88263ca4"><a name="zh-cn_topic_0263899650_af5ba424e876c470b953ad2ec88263ca4"></a><a name="zh-cn_topic_0263899650_af5ba424e876c470b953ad2ec88263ca4"></a>clock daemon</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133032913548"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133032913548"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p133032913548"></a>15</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r358abc8d0ff84b9cbc38a375e88970bd"><td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899650_a52bfc69eee6a4955b868caf9b20ee64a"><a name="zh-cn_topic_0263899650_a52bfc69eee6a4955b868caf9b20ee64a"></a><a name="zh-cn_topic_0263899650_a52bfc69eee6a4955b868caf9b20ee64a"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="43.43434343434344%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p156830157495"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p156830157495"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p156830157495"></a>local use 0~7 (local0 ~ local7)</p>
</td>
<td class="cellrowborder" valign="top" width="28.28282828282828%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p730319995410"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p730319995410"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p730319995410"></a>16~23</p>
</td>
</tr>
</tbody>
</table>

**表 3**  报文格式信息域表

<a name="zh-cn_topic_0263899650_t614aa61f080f47f0ba68c57aa68e7dc1"></a>
<table><thead align="left"><tr id="zh-cn_topic_0263899650_r1726b4691d524ddbafe1898840b49ebf"><th class="cellrowborder" valign="top" width="30.64%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0263899650_a63e6beb0539445ea9cb2a32c33131014"><a name="zh-cn_topic_0263899650_a63e6beb0539445ea9cb2a32c33131014"></a><a name="zh-cn_topic_0263899650_a63e6beb0539445ea9cb2a32c33131014"></a>信息域</p>
</th>
<th class="cellrowborder" valign="top" width="69.36%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0263899650_af3c2ce477d8e4032ae00fc71d7ccb7f8"><a name="zh-cn_topic_0263899650_af3c2ce477d8e4032ae00fc71d7ccb7f8"></a><a name="zh-cn_topic_0263899650_af3c2ce477d8e4032ae00fc71d7ccb7f8"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0263899650_r7d08cb436693487abc36bd2a3a4e283c"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a00bfaf164b2c41e0a825b60805c5d33a"><a name="zh-cn_topic_0263899650_a00bfaf164b2c41e0a825b60805c5d33a"></a><a name="zh-cn_topic_0263899650_a00bfaf164b2c41e0a825b60805c5d33a"></a>dn</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_afa7464bca1ec4dd284eae63c6ca5f833"><a name="zh-cn_topic_0263899650_afa7464bca1ec4dd284eae63c6ca5f833"></a><a name="zh-cn_topic_0263899650_afa7464bca1ec4dd284eae63c6ca5f833"></a>集群名称</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r763fcfea21b34418810af8a60a369dfb"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a12bef7e1b78143fd83ee7c61c719289f"><a name="zh-cn_topic_0263899650_a12bef7e1b78143fd83ee7c61c719289f"></a><a name="zh-cn_topic_0263899650_a12bef7e1b78143fd83ee7c61c719289f"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a971935f3a0e64b44a0002a44f4adcc4b"><a name="zh-cn_topic_0263899650_a971935f3a0e64b44a0002a44f4adcc4b"></a><a name="zh-cn_topic_0263899650_a971935f3a0e64b44a0002a44f4adcc4b"></a>告警ID</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_redd61f6effbe4e1e895086dd61e515f3"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_ac11a6059485446bb980402c4fa54390a"><a name="zh-cn_topic_0263899650_ac11a6059485446bb980402c4fa54390a"></a><a name="zh-cn_topic_0263899650_ac11a6059485446bb980402c4fa54390a"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a1b3390ee33cd46f59efa40db2cb60ce2"><a name="zh-cn_topic_0263899650_a1b3390ee33cd46f59efa40db2cb60ce2"></a><a name="zh-cn_topic_0263899650_a1b3390ee33cd46f59efa40db2cb60ce2"></a>告警名称</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_rb0281a0085cd40549c5a3c6d9efedde6"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a4cb1709cebf14c8bbba71424e7e1d070"><a name="zh-cn_topic_0263899650_a4cb1709cebf14c8bbba71424e7e1d070"></a><a name="zh-cn_topic_0263899650_a4cb1709cebf14c8bbba71424e7e1d070"></a>serialNo</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a4f9316df5044418c977816ad966dd207"><a name="zh-cn_topic_0263899650_a4f9316df5044418c977816ad966dd207"></a><a name="zh-cn_topic_0263899650_a4f9316df5044418c977816ad966dd207"></a>告警序列号</p>
<div class="note" id="zh-cn_topic_0263899650_n9a8ceec78151449f8c7389749e101d98"><a name="zh-cn_topic_0263899650_n9a8ceec78151449f8c7389749e101d98"></a><a name="zh-cn_topic_0263899650_n9a8ceec78151449f8c7389749e101d98"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0263899650_a0944dd743e204961973976397a62e6fc"><a name="zh-cn_topic_0263899650_a0944dd743e204961973976397a62e6fc"></a><a name="zh-cn_topic_0263899650_a0944dd743e204961973976397a62e6fc"></a>故障告警及其对应的恢复告警的告警序列号相同。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r10ff9624a945445d81d28b73f1192603"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_ae0988127cf7343d4863e992a7d85a621"><a name="zh-cn_topic_0263899650_ae0988127cf7343d4863e992a7d85a621"></a><a name="zh-cn_topic_0263899650_ae0988127cf7343d4863e992a7d85a621"></a>category</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a0cefe7ffb3f44b37a2788709b1385c39"><a name="zh-cn_topic_0263899650_a0cefe7ffb3f44b37a2788709b1385c39"></a><a name="zh-cn_topic_0263899650_a0cefe7ffb3f44b37a2788709b1385c39"></a>告警类型，取值范围：</p>
<a name="zh-cn_topic_0263899650_uff7b44cba906447fa8b87ce6a870d248"></a><a name="zh-cn_topic_0263899650_uff7b44cba906447fa8b87ce6a870d248"></a><ul id="zh-cn_topic_0263899650_uff7b44cba906447fa8b87ce6a870d248"><li>0：故障告警</li><li>1：恢复告警</li><li>2：事件</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_rbf10acabfb3f4e2a8e284ef3b9d3ad8c"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a95273a208a0c4fb9bf198b9243946bd8"><a name="zh-cn_topic_0263899650_a95273a208a0c4fb9bf198b9243946bd8"></a><a name="zh-cn_topic_0263899650_a95273a208a0c4fb9bf198b9243946bd8"></a>occurTime</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a9dd5f61248544b718c2302a474c9d69e"><a name="zh-cn_topic_0263899650_a9dd5f61248544b718c2302a474c9d69e"></a><a name="zh-cn_topic_0263899650_a9dd5f61248544b718c2302a474c9d69e"></a>告警产生时间</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_ra9adea2cbf1848bb8b8f18952ac2b7c2"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_aa9d0f77a10f2448dbaddd93b52ce3a58"><a name="zh-cn_topic_0263899650_aa9d0f77a10f2448dbaddd93b52ce3a58"></a><a name="zh-cn_topic_0263899650_aa9d0f77a10f2448dbaddd93b52ce3a58"></a>clearTime</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a59e070afa1af4b20b01e15ee234a7fab"><a name="zh-cn_topic_0263899650_a59e070afa1af4b20b01e15ee234a7fab"></a><a name="zh-cn_topic_0263899650_a59e070afa1af4b20b01e15ee234a7fab"></a>告警清除时间</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r84934c3091064a8596e6ec52adc951f3"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_ab18421d7c3ac412aa63592899dead338"><a name="zh-cn_topic_0263899650_ab18421d7c3ac412aa63592899dead338"></a><a name="zh-cn_topic_0263899650_ab18421d7c3ac412aa63592899dead338"></a>isAutoClear</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_aaf547a0ded424024b643403806fff4a7"><a name="zh-cn_topic_0263899650_aaf547a0ded424024b643403806fff4a7"></a><a name="zh-cn_topic_0263899650_aaf547a0ded424024b643403806fff4a7"></a>告警是否自动清除，取值范围：</p>
<a name="zh-cn_topic_0263899650_ucad47d79a8f84cc7b1ea28d5fab87d84"></a><a name="zh-cn_topic_0263899650_ucad47d79a8f84cc7b1ea28d5fab87d84"></a><ul id="zh-cn_topic_0263899650_ucad47d79a8f84cc7b1ea28d5fab87d84"><li>1：是</li><li>0：否</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_rcc98d9353f6b4527838e0f345815782a"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a0a30dad484da4f2b81e2a776b17abf9e"><a name="zh-cn_topic_0263899650_a0a30dad484da4f2b81e2a776b17abf9e"></a><a name="zh-cn_topic_0263899650_a0a30dad484da4f2b81e2a776b17abf9e"></a>locationInfo</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a51e425726d9046e689173ef6bcbd9a69"><a name="zh-cn_topic_0263899650_a51e425726d9046e689173ef6bcbd9a69"></a><a name="zh-cn_topic_0263899650_a51e425726d9046e689173ef6bcbd9a69"></a>告警位置信息</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r8c40568fa19141a2b2622a48991ff4e3"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a61f30541a0914f93a381c2a8fe736cb2"><a name="zh-cn_topic_0263899650_a61f30541a0914f93a381c2a8fe736cb2"></a><a name="zh-cn_topic_0263899650_a61f30541a0914f93a381c2a8fe736cb2"></a>clearType</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_a1145921c29764ac18820342b90c52558"><a name="zh-cn_topic_0263899650_a1145921c29764ac18820342b90c52558"></a><a name="zh-cn_topic_0263899650_a1145921c29764ac18820342b90c52558"></a>告警清除类型，取值范围：</p>
<a name="zh-cn_topic_0263899650_uc6be1ff2fab345fb9ac68d66ae295a14"></a><a name="zh-cn_topic_0263899650_uc6be1ff2fab345fb9ac68d66ae295a14"></a><ul id="zh-cn_topic_0263899650_uc6be1ff2fab345fb9ac68d66ae295a14"><li>-1：未清除</li><li>0：自动清除</li><li>2：手动清除</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r2f53d44655f04ea7b7ca8a2c16c1b7dc"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_addcf9ae5200448849465d53aeeb08217"><a name="zh-cn_topic_0263899650_addcf9ae5200448849465d53aeeb08217"></a><a name="zh-cn_topic_0263899650_addcf9ae5200448849465d53aeeb08217"></a>level</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p615625918635"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p615625918635"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p615625918635"></a>告警级别，取值范围：</p>
<a name="zh-cn_topic_0263899650_u5832daf20c65432cac8a24ec11a15e45"></a><a name="zh-cn_topic_0263899650_u5832daf20c65432cac8a24ec11a15e45"></a><ul id="zh-cn_topic_0263899650_u5832daf20c65432cac8a24ec11a15e45"><li>1：紧急告警</li><li>2：重要告警</li><li>3：次要告警</li><li>4：提示告警</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r0345c4fd58c04a318e8ac9a508f004e5"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_aee151c0837334ad4ba90b318720696ce"><a name="zh-cn_topic_0263899650_aee151c0837334ad4ba90b318720696ce"></a><a name="zh-cn_topic_0263899650_aee151c0837334ad4ba90b318720696ce"></a>cause</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p951052018015"><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p951052018015"></a><a name="zh-cn_topic_0263899650_zh-cn_topic_0085617816_p951052018015"></a>告警原因</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_r58424598c1aa4f4ca8261d3ffcd88790"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_a9865848a128247b4a1142e796f20e9c1"><a name="zh-cn_topic_0263899650_a9865848a128247b4a1142e796f20e9c1"></a><a name="zh-cn_topic_0263899650_a9865848a128247b4a1142e796f20e9c1"></a>additionalInfo</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_aceafcfe951ef41829270e533c8f5a272"><a name="zh-cn_topic_0263899650_aceafcfe951ef41829270e533c8f5a272"></a><a name="zh-cn_topic_0263899650_aceafcfe951ef41829270e533c8f5a272"></a>附加信息</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899650_row6742113914322"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899650_p19742939103214"><a name="zh-cn_topic_0263899650_p19742939103214"></a><a name="zh-cn_topic_0263899650_p19742939103214"></a>object</p>
</td>
<td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899650_p2074243913218"><a name="zh-cn_topic_0263899650_p2074243913218"></a><a name="zh-cn_topic_0263899650_p2074243913218"></a>告警对象</p>
</td>
</tr>
</tbody>
</table>

