# ALM-12011 Manager主备节点同步数据异常<a name="ZH-CN_TOPIC_0191883071"></a>

## 告警解释<a name="zh-cn_topic_0191813887_section15466919171137"></a>

当备Manager无法与主Manager同步文件时，产生该告警。

当备Manager与主Manager正常同步文件时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813887_section20576287171551"></a>

<a name="zh-cn_topic_0191813887_table4702977812324"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813887_row6694854412324"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813887_p156557912324"><a name="zh-cn_topic_0191813887_p156557912324"></a><a name="zh-cn_topic_0191813887_p156557912324"></a><strong id="zh-cn_topic_0191813887_b5521738312324"><a name="zh-cn_topic_0191813887_b5521738312324"></a><a name="zh-cn_topic_0191813887_b5521738312324"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813887_p4434271512324"><a name="zh-cn_topic_0191813887_p4434271512324"></a><a name="zh-cn_topic_0191813887_p4434271512324"></a><strong id="zh-cn_topic_0191813887_b6386833212324"><a name="zh-cn_topic_0191813887_b6386833212324"></a><a name="zh-cn_topic_0191813887_b6386833212324"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813887_p134881812324"><a name="zh-cn_topic_0191813887_p134881812324"></a><a name="zh-cn_topic_0191813887_p134881812324"></a><strong id="zh-cn_topic_0191813887_b2898932912324"><a name="zh-cn_topic_0191813887_b2898932912324"></a><a name="zh-cn_topic_0191813887_b2898932912324"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813887_row1804793212324"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813887_p3217576012324"><a name="zh-cn_topic_0191813887_p3217576012324"></a><a name="zh-cn_topic_0191813887_p3217576012324"></a>12011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813887_p4819992912324"><a name="zh-cn_topic_0191813887_p4819992912324"></a><a name="zh-cn_topic_0191813887_p4819992912324"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813887_p4546102112324"><a name="zh-cn_topic_0191813887_p4546102112324"></a><a name="zh-cn_topic_0191813887_p4546102112324"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813887_section396560517161"></a>

<a name="zh-cn_topic_0191813887_table2728904712324"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813887_row2832476712324"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813887_p3725626112324"><a name="zh-cn_topic_0191813887_p3725626112324"></a><a name="zh-cn_topic_0191813887_p3725626112324"></a><strong id="zh-cn_topic_0191813887_b1171373012324"><a name="zh-cn_topic_0191813887_b1171373012324"></a><a name="zh-cn_topic_0191813887_b1171373012324"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813887_p3758553612324"><a name="zh-cn_topic_0191813887_p3758553612324"></a><a name="zh-cn_topic_0191813887_p3758553612324"></a><strong id="zh-cn_topic_0191813887_b5155602612324"><a name="zh-cn_topic_0191813887_b5155602612324"></a><a name="zh-cn_topic_0191813887_b5155602612324"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813887_row6426373312324"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813887_p1905095412324"><a name="zh-cn_topic_0191813887_p1905095412324"></a><a name="zh-cn_topic_0191813887_p1905095412324"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813887_p2058307812324"><a name="zh-cn_topic_0191813887_p2058307812324"></a><a name="zh-cn_topic_0191813887_p2058307812324"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813887_row752452412324"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813887_p4092241512324"><a name="zh-cn_topic_0191813887_p4092241512324"></a><a name="zh-cn_topic_0191813887_p4092241512324"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813887_p6425274912324"><a name="zh-cn_topic_0191813887_p6425274912324"></a><a name="zh-cn_topic_0191813887_p6425274912324"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813887_row5706328712324"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813887_p2535053012324"><a name="zh-cn_topic_0191813887_p2535053012324"></a><a name="zh-cn_topic_0191813887_p2535053012324"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813887_p4509295512324"><a name="zh-cn_topic_0191813887_p4509295512324"></a><a name="zh-cn_topic_0191813887_p4509295512324"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813887_row2042965912324"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813887_p644338312324"><a name="zh-cn_topic_0191813887_p644338312324"></a><a name="zh-cn_topic_0191813887_p644338312324"></a>Local Manager HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813887_p4962802312324"><a name="zh-cn_topic_0191813887_p4962802312324"></a><a name="zh-cn_topic_0191813887_p4962802312324"></a>本地Manager HA名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813887_row3230190912324"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813887_p1609535712324"><a name="zh-cn_topic_0191813887_p1609535712324"></a><a name="zh-cn_topic_0191813887_p1609535712324"></a>Peer Manager HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813887_p3290559612324"><a name="zh-cn_topic_0191813887_p3290559612324"></a><a name="zh-cn_topic_0191813887_p3290559612324"></a>对端Manager HA名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813887_section50565448171611"></a>

备Manager的配置文件没有更新。主备倒换之后，一些配置可能会丢失。Manager及部分组件可能无法正常运行。

## 可能原因<a name="zh-cn_topic_0191813887_section42612438171616"></a>

主备Manager节点间链路中断。

## 处理步骤<a name="zh-cn_topic_0191813887_section28407751171620"></a>

1.  检查主备Manager服务器间的网络是否正常。
    1.  打开MRS集群详情页面，在告警管理页签的告警列表中，单击此告警所在行，在告警详情中，查看该告警的备Manager IP地址。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面查看告警信息。  

    2.  登录主管理节点。 执行以下命令检查备Manager服务器是否可达。

        **ping** _备Manager IP地址_

        -   是，执行[2](#zh-cn_topic_0191813887_li572522141314)。
        -   否，执行[1.c](#zh-cn_topic_0191813887_li47267615172220)。

    3.  <a name="zh-cn_topic_0191813887_li47267615172220"></a>联系运维人员查看是否为网络故障。
        -   是，执行[1.d](#zh-cn_topic_0191813887_li37136917172238)。
        -   否，执行[2](#zh-cn_topic_0191813887_li572522141314)。

    4.  <a name="zh-cn_topic_0191813887_li37136917172238"></a>修复网络故障，查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813887_li572522141314)。

2.  <a name="zh-cn_topic_0191813887_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813887_section55635852162510"></a>

无。

