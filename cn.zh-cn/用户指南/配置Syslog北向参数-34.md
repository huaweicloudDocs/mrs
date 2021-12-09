# 配置Syslog北向参数<a name="mrs_01_0239"></a>

## 操作场景<a name="zh-cn_topic_0035209606_section2203633518343"></a>

该任务指导用户以Syslog方式将MRS Manager的告警事件上报到指定的监控运维系统中。

>![](public_sys-resources/icon-notice.gif) **须知：** 
>Syslog协议未做加密，传输数据容易被窃取，存在安全风险。

## 前提条件<a name="zh-cn_topic_0035209606_section36395386183434"></a>

对接服务器对应的弹性云服务器需要和MRS集群的Master节点在相同的VPC，且Master节点可以访问对接服务器的IP地址和指定端口。

## 操作步骤<a name="zh-cn_topic_0035209606_section58423188183440"></a>

1.  在MRS Manager，单击“系统设置”。
2.  在“配置”区域“监控和告警配置”下，单击“Syslog配置”。

    “Syslog服务”的开关默认为关闭，单击启用Syslog服务。

3.  设置[表1](#zh-cn_topic_0035209606_table27202707183556)所示的对接参数。

    **表 1**  对接参数

    <a name="zh-cn_topic_0035209606_table27202707183556"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0035209606_row47060330183556"><th class="cellrowborder" valign="top" width="25.06250625062506%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0035209606_p14351306183556"><a name="zh-cn_topic_0035209606_p14351306183556"></a><a name="zh-cn_topic_0035209606_p14351306183556"></a><strong id="zh-cn_topic_0035209606_b20231298183759"><a name="zh-cn_topic_0035209606_b20231298183759"></a><a name="zh-cn_topic_0035209606_b20231298183759"></a>参数区域</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="41.6041604160416%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0035209606_p21605148183556"><a name="zh-cn_topic_0035209606_p21605148183556"></a><a name="zh-cn_topic_0035209606_p21605148183556"></a><strong id="zh-cn_topic_0035209606_b28122452183759"><a name="zh-cn_topic_0035209606_b28122452183759"></a><a name="zh-cn_topic_0035209606_b28122452183759"></a>参数名称</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0035209606_p5186587183556"><a name="zh-cn_topic_0035209606_p5186587183556"></a><a name="zh-cn_topic_0035209606_p5186587183556"></a><strong id="zh-cn_topic_0035209606_b63326163183759"><a name="zh-cn_topic_0035209606_b63326163183759"></a><a name="zh-cn_topic_0035209606_b63326163183759"></a>参数说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0035209606_row46679286183556"><td class="cellrowborder" rowspan="6" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p50057990183715"><a name="zh-cn_topic_0035209606_p50057990183715"></a><a name="zh-cn_topic_0035209606_p50057990183715"></a>Syslog协议</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.6041604160416%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p725082518366"><a name="zh-cn_topic_0035209606_p725082518366"></a><a name="zh-cn_topic_0035209606_p725082518366"></a>服务IP</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0035209606_p5044598018366"><a name="zh-cn_topic_0035209606_p5044598018366"></a><a name="zh-cn_topic_0035209606_p5044598018366"></a>设置对接服务器IP地址。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row29064819183556"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p6657098418366"><a name="zh-cn_topic_0035209606_p6657098418366"></a><a name="zh-cn_topic_0035209606_p6657098418366"></a>服务端口</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p2354060618366"><a name="zh-cn_topic_0035209606_p2354060618366"></a><a name="zh-cn_topic_0035209606_p2354060618366"></a>设置对接端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row49691024183556"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p7949112183556"><a name="zh-cn_topic_0035209606_p7949112183556"></a><a name="zh-cn_topic_0035209606_p7949112183556"></a>协议</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p39898345183556"><a name="zh-cn_topic_0035209606_p39898345183556"></a><a name="zh-cn_topic_0035209606_p39898345183556"></a>设置协议类型，取值范围：</p>
    <a name="zh-cn_topic_0035209606_ul34893161183618"></a><a name="zh-cn_topic_0035209606_ul34893161183618"></a><ul id="zh-cn_topic_0035209606_ul34893161183618"><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue29139435153342"><a name="zh-cn_topic_0035209606_parmvalue29139435153342"></a><a name="zh-cn_topic_0035209606_parmvalue29139435153342"></a>“TCP”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue35394249153344"><a name="zh-cn_topic_0035209606_parmvalue35394249153344"></a><a name="zh-cn_topic_0035209606_parmvalue35394249153344"></a>“UDP”</span></li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row23540789183556"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p33624883183556"><a name="zh-cn_topic_0035209606_p33624883183556"></a><a name="zh-cn_topic_0035209606_p33624883183556"></a>安全级别</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p12333865183623"><a name="zh-cn_topic_0035209606_p12333865183623"></a><a name="zh-cn_topic_0035209606_p12333865183623"></a>设置上报消息的严重程度，取值范围：</p>
    <a name="zh-cn_topic_0035209606_ul31709965183626"></a><a name="zh-cn_topic_0035209606_ul31709965183626"></a><ul id="zh-cn_topic_0035209606_ul31709965183626"><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue56757637153346"><a name="zh-cn_topic_0035209606_parmvalue56757637153346"></a><a name="zh-cn_topic_0035209606_parmvalue56757637153346"></a>“Informational”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue56740577153347"><a name="zh-cn_topic_0035209606_parmvalue56740577153347"></a><a name="zh-cn_topic_0035209606_parmvalue56740577153347"></a>“Emergency”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue45090428153349"><a name="zh-cn_topic_0035209606_parmvalue45090428153349"></a><a name="zh-cn_topic_0035209606_parmvalue45090428153349"></a>“Alert”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue302693153352"><a name="zh-cn_topic_0035209606_parmvalue302693153352"></a><a name="zh-cn_topic_0035209606_parmvalue302693153352"></a>“Critical”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue23215426153359"><a name="zh-cn_topic_0035209606_parmvalue23215426153359"></a><a name="zh-cn_topic_0035209606_parmvalue23215426153359"></a>“Error”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue4727945015341"><a name="zh-cn_topic_0035209606_parmvalue4727945015341"></a><a name="zh-cn_topic_0035209606_parmvalue4727945015341"></a>“Warning”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue5878855515343"><a name="zh-cn_topic_0035209606_parmvalue5878855515343"></a><a name="zh-cn_topic_0035209606_parmvalue5878855515343"></a>“Notice”</span></li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue1493165215345"><a name="zh-cn_topic_0035209606_parmvalue1493165215345"></a><a name="zh-cn_topic_0035209606_parmvalue1493165215345"></a>“Debug”</span></li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row17804690183556"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p18796795183644"><a name="zh-cn_topic_0035209606_p18796795183644"></a><a name="zh-cn_topic_0035209606_p18796795183644"></a>Facility</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p46145461183644"><a name="zh-cn_topic_0035209606_p46145461183644"></a><a name="zh-cn_topic_0035209606_p46145461183644"></a>设置产生日志的模块。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row19573745183642"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p18500810183644"><a name="zh-cn_topic_0035209606_p18500810183644"></a><a name="zh-cn_topic_0035209606_p18500810183644"></a>标识符</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p22170612183644"><a name="zh-cn_topic_0035209606_p22170612183644"></a><a name="zh-cn_topic_0035209606_p22170612183644"></a>设置产品标识，默认为“MRS Manager”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row23164398183655"><td class="cellrowborder" rowspan="3" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p60367007183655"><a name="zh-cn_topic_0035209606_p60367007183655"></a><a name="zh-cn_topic_0035209606_p60367007183655"></a>报告信息</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.6041604160416%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p57889435183655"><a name="zh-cn_topic_0035209606_p57889435183655"></a><a name="zh-cn_topic_0035209606_p57889435183655"></a>报文格式</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0035209606_p58532626183655"><a name="zh-cn_topic_0035209606_p58532626183655"></a><a name="zh-cn_topic_0035209606_p58532626183655"></a>设置告警报告的消息格式，具体要求请参考界面帮助。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row24943443183655"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p56156262183655"><a name="zh-cn_topic_0035209606_p56156262183655"></a><a name="zh-cn_topic_0035209606_p56156262183655"></a>报告告警类型</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p52363348183655"><a name="zh-cn_topic_0035209606_p52363348183655"></a><a name="zh-cn_topic_0035209606_p52363348183655"></a>设置需要上报的告警类型。</p>
    <a name="zh-cn_topic_0035209606_ul5247844153723"></a><a name="zh-cn_topic_0035209606_ul5247844153723"></a><ul id="zh-cn_topic_0035209606_ul5247844153723"><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue22422197153723"><a name="zh-cn_topic_0035209606_parmvalue22422197153723"></a><a name="zh-cn_topic_0035209606_parmvalue22422197153723"></a>“故障”</span>表示Manager产生告警时会上报Syslog告警消息。</li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue4258700153723"><a name="zh-cn_topic_0035209606_parmvalue4258700153723"></a><a name="zh-cn_topic_0035209606_parmvalue4258700153723"></a>“清除”</span>表示清除Manager告警时会上报Syslog告警消息。</li><li><span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue9410382153723"><a name="zh-cn_topic_0035209606_parmvalue9410382153723"></a><a name="zh-cn_topic_0035209606_parmvalue9410382153723"></a>“事件”</span>表示Manager产生事件时会上报Syslog告警消息。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row17684574183655"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p55045998183655"><a name="zh-cn_topic_0035209606_p55045998183655"></a><a name="zh-cn_topic_0035209606_p55045998183655"></a>报告告警级别</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p29540844183655"><a name="zh-cn_topic_0035209606_p29540844183655"></a><a name="zh-cn_topic_0035209606_p29540844183655"></a>设置需要上报的告警级别。支持<span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue865160416104"><a name="zh-cn_topic_0035209606_parmvalue865160416104"></a><a name="zh-cn_topic_0035209606_parmvalue865160416104"></a>“提示”</span>、<span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue2969128516104"><a name="zh-cn_topic_0035209606_parmvalue2969128516104"></a><a name="zh-cn_topic_0035209606_parmvalue2969128516104"></a>“一般”</span>、<span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue5618387916104"><a name="zh-cn_topic_0035209606_parmvalue5618387916104"></a><a name="zh-cn_topic_0035209606_parmvalue5618387916104"></a>“严重”</span>和&nbsp;<span class="parmvalue" id="zh-cn_topic_0035209606_parmvalue5460033716104"><a name="zh-cn_topic_0035209606_parmvalue5460033716104"></a><a name="zh-cn_topic_0035209606_parmvalue5460033716104"></a>“致命”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row2785453918375"><td class="cellrowborder" rowspan="2" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p594299018375"><a name="zh-cn_topic_0035209606_p594299018375"></a><a name="zh-cn_topic_0035209606_p594299018375"></a>未恢复告警上报设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.6041604160416%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p1162016618375"><a name="zh-cn_topic_0035209606_p1162016618375"></a><a name="zh-cn_topic_0035209606_p1162016618375"></a>周期上报未恢复告警</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0035209606_p170936618375"><a name="zh-cn_topic_0035209606_p170936618375"></a><a name="zh-cn_topic_0035209606_p170936618375"></a>设置是否按指定周期上报未清除的告警。“周期上报未恢复告警”的开关默认为关闭，单击启用此功能。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row309494818375"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p3816870718375"><a name="zh-cn_topic_0035209606_p3816870718375"></a><a name="zh-cn_topic_0035209606_p3816870718375"></a>间隔时间（分钟）</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p465757618375"><a name="zh-cn_topic_0035209606_p465757618375"></a><a name="zh-cn_topic_0035209606_p465757618375"></a>设置周期上报未恢复告警到远程Syslog服务的时间间隔，当“周期上报未恢复告警”开关打开时启用。单位为分钟，默认值为“15”，取值范围为5分钟到一天（1440分钟）。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row57559907103132"><td class="cellrowborder" rowspan="3" valign="top" width="25.06250625062506%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p43130437103143"><a name="zh-cn_topic_0035209606_p43130437103143"></a><a name="zh-cn_topic_0035209606_p43130437103143"></a>心跳设置</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.6041604160416%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p28973752103132"><a name="zh-cn_topic_0035209606_p28973752103132"></a><a name="zh-cn_topic_0035209606_p28973752103132"></a>上报心跳</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0035209606_p65172541103132"><a name="zh-cn_topic_0035209606_p65172541103132"></a><a name="zh-cn_topic_0035209606_p65172541103132"></a>设置是否开启周期上报Syslog心跳消息。“周期上报未恢复告警”的开关默认为关闭，单击启用此功能。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row11696325103136"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p34159861103136"><a name="zh-cn_topic_0035209606_p34159861103136"></a><a name="zh-cn_topic_0035209606_p34159861103136"></a>心跳周期（分钟）</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p15485339103136"><a name="zh-cn_topic_0035209606_p15485339103136"></a><a name="zh-cn_topic_0035209606_p15485339103136"></a>设置周期上报心跳的时间间隔，当“上报心跳”开关打开时启用。单位为分钟，默认值为“15”，取值范围为1-60。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0035209606_row7390342103140"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035209606_p35436937103140"><a name="zh-cn_topic_0035209606_p35436937103140"></a><a name="zh-cn_topic_0035209606_p35436937103140"></a>心跳报文</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0035209606_p51819629103140"><a name="zh-cn_topic_0035209606_p51819629103140"></a><a name="zh-cn_topic_0035209606_p51819629103140"></a>设置心跳上报的内容，当“上报心跳”开关打开时启用，不能为空。支持数字、字母、下划线、竖线、冒号、空格、英文逗号和句号等字符，长度小于等于256。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >设置周期上报心跳报文后，在某些集群容错自动恢复的场景下（例如主备管理节点倒换）可能会出现报文上报中断的现象，此时等待自动恢复即可。

4.  单击“确定”，设置完成。

