# ALM-27003 DBService主备节点间心跳中断<a name="ZH-CN_TOPIC_0174499373"></a>

## 告警解释<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section48623408"></a>

DBService主节点或备节点未收到对端的心跳消息后，系统产生告警。

当心跳恢复后，该告警恢复。

## 告警属性<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section34957489"></a>

<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_table18176840"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row123050"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9967070"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9967070"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9967070"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p2026335"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p2026335"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p2026335"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p29915412"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p29915412"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p29915412"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row7229285"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p48701244"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p48701244"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p48701244"></a>27003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p52486654"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p52486654"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p52486654"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p23560597"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p23560597"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p23560597"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section46181951"></a>

<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_table29360233"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row2035480"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p30656219"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p30656219"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p30656219"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p125790"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p125790"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p125790"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row10189001"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p20002757"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p20002757"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p20002757"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9610617"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9610617"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p9610617"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row19386696"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p26818564"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p26818564"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p26818564"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p24820109"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p24820109"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p24820109"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row22054394"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p41575456"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p41575456"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p41575456"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12168775"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12168775"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12168775"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row42410114"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12667213"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12667213"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p12667213"></a>Local DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p19411308"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p19411308"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p19411308"></a>本地DBService HA名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_row40484047"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p57982344"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p57982344"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p57982344"></a>Peer DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p66058249"><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p66058249"></a><a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_p66058249"></a>对端DBService HA名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section12984378"></a>

DBService主备间心跳中断时只有一个节点提供服务，一旦该节点故障，再无法切换到备节点，就会服务不可用。

## 可能原因<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section49750539"></a>

主备DBService节点间链路异常。

## 处理步骤<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section45101667"></a>

1.  检查主备DBService服务器间的网络是否正常。
    1.  打开MRS Manager页面，在告警列表中，单击此告警所在行，在告警详情中，查看该告警的DBService备服务器地址。
    2.  登录主DBService服务器。
    3.  执行**ping** _备DBService__心跳IP__地址_命令检查备DBService服务器是否可达。
        -   是，执行[2](#zh-cn_topic_0093195072_zh-cn_topic_0035998746_li2633232915350)。
        -   否，执行[1.d](#zh-cn_topic_0093195072_zh-cn_topic_0035998746_alm-27002_2_mmccppss_step2)。

    4.  <a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_alm-27002_2_mmccppss_step2"></a>联系网络管理员查看是否为网络故障。
        -   是，执行[1.e](#zh-cn_topic_0093195072_zh-cn_topic_0035998746_alm-27002_2_mmccppss_s4)。
        -   否，执行[2](#zh-cn_topic_0093195072_zh-cn_topic_0035998746_li2633232915350)。

    5.  <a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_alm-27002_2_mmccppss_s4"></a>修复网络故障，查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0093195072_zh-cn_topic_0035998746_li2633232915350)。

2.  <a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_li2633232915350"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195072_zh-cn_topic_0035998746_section3261819"></a>

无。

