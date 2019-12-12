# ALM-12010 Manager主备节点间心跳中断<a name="ZH-CN_TOPIC_0191883070"></a>

## 告警解释<a name="zh-cn_topic_0191813932_section3336541317510"></a>

当主Manager节点在7秒内没有收到备Manager节点的心跳信号时，产生该告警。

当主Manager节点收到备Manager节点的心跳信号后，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813932_section6589867417620"></a>

<a name="zh-cn_topic_0191813932_table51335144115950"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813932_row22457334115950"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813932_p31502817115950"><a name="zh-cn_topic_0191813932_p31502817115950"></a><a name="zh-cn_topic_0191813932_p31502817115950"></a><strong id="zh-cn_topic_0191813932_b53744525115950"><a name="zh-cn_topic_0191813932_b53744525115950"></a><a name="zh-cn_topic_0191813932_b53744525115950"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813932_p22174081115950"><a name="zh-cn_topic_0191813932_p22174081115950"></a><a name="zh-cn_topic_0191813932_p22174081115950"></a><strong id="zh-cn_topic_0191813932_b65818178115950"><a name="zh-cn_topic_0191813932_b65818178115950"></a><a name="zh-cn_topic_0191813932_b65818178115950"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813932_p27776904115950"><a name="zh-cn_topic_0191813932_p27776904115950"></a><a name="zh-cn_topic_0191813932_p27776904115950"></a><strong id="zh-cn_topic_0191813932_b5562263115950"><a name="zh-cn_topic_0191813932_b5562263115950"></a><a name="zh-cn_topic_0191813932_b5562263115950"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813932_row1945234115950"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813932_p26013574115950"><a name="zh-cn_topic_0191813932_p26013574115950"></a><a name="zh-cn_topic_0191813932_p26013574115950"></a>12010</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813932_p21947919115950"><a name="zh-cn_topic_0191813932_p21947919115950"></a><a name="zh-cn_topic_0191813932_p21947919115950"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813932_p22246739115950"><a name="zh-cn_topic_0191813932_p22246739115950"></a><a name="zh-cn_topic_0191813932_p22246739115950"></a>是</p>
</td>
</tr>
</tbody>
</table>

## **告警参数**<a name="zh-cn_topic_0191813932_section4656225517628"></a>

<a name="zh-cn_topic_0191813932_table30473597115950"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813932_row3202901115950"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813932_p51699739115950"><a name="zh-cn_topic_0191813932_p51699739115950"></a><a name="zh-cn_topic_0191813932_p51699739115950"></a><strong id="zh-cn_topic_0191813932_b14544104115950"><a name="zh-cn_topic_0191813932_b14544104115950"></a><a name="zh-cn_topic_0191813932_b14544104115950"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813932_p3813318115950"><a name="zh-cn_topic_0191813932_p3813318115950"></a><a name="zh-cn_topic_0191813932_p3813318115950"></a><strong id="zh-cn_topic_0191813932_b58758352115950"><a name="zh-cn_topic_0191813932_b58758352115950"></a><a name="zh-cn_topic_0191813932_b58758352115950"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813932_row63329947115950"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813932_p37698384115950"><a name="zh-cn_topic_0191813932_p37698384115950"></a><a name="zh-cn_topic_0191813932_p37698384115950"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813932_p38746956115950"><a name="zh-cn_topic_0191813932_p38746956115950"></a><a name="zh-cn_topic_0191813932_p38746956115950"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813932_row57870114115950"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813932_p26943429115950"><a name="zh-cn_topic_0191813932_p26943429115950"></a><a name="zh-cn_topic_0191813932_p26943429115950"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813932_p12845059115950"><a name="zh-cn_topic_0191813932_p12845059115950"></a><a name="zh-cn_topic_0191813932_p12845059115950"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813932_row10748285115950"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813932_p62476968115950"><a name="zh-cn_topic_0191813932_p62476968115950"></a><a name="zh-cn_topic_0191813932_p62476968115950"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813932_p31473313115950"><a name="zh-cn_topic_0191813932_p31473313115950"></a><a name="zh-cn_topic_0191813932_p31473313115950"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813932_row50174577115950"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813932_p32369325115950"><a name="zh-cn_topic_0191813932_p32369325115950"></a><a name="zh-cn_topic_0191813932_p32369325115950"></a>Local Manager HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813932_p63610061115950"><a name="zh-cn_topic_0191813932_p63610061115950"></a><a name="zh-cn_topic_0191813932_p63610061115950"></a>本地Manager HA名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813932_row46406907115950"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813932_p33396547115950"><a name="zh-cn_topic_0191813932_p33396547115950"></a><a name="zh-cn_topic_0191813932_p33396547115950"></a>Peer Manager HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813932_p3666786115950"><a name="zh-cn_topic_0191813932_p3666786115950"></a><a name="zh-cn_topic_0191813932_p3666786115950"></a>对端Manager HA名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813932_section6050290517637"></a>

如果主Manager进程异常，主备倒换无法进行，影响业务。

## 可能原因<a name="zh-cn_topic_0191813932_section852502017642"></a>

主备Manager节点间链路异常。

## 处理步骤<a name="zh-cn_topic_0191813932_section2641184617833"></a>

1.  检查主备Manager服务器间的网络是否正常。
    1.  打开MRS集群详情页面，在告警管理页签的告警列表中，单击此告警所在行，在告警详情中，查看该告警的备Manager服务器地址。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请打开MRS Manager页面查看告警信息。  

    2.  登录主管理节点。
    3.  执行以命令，检查备Manager服务器是否可达。

        **ping** _备Manager心跳IP地址_

        -   是，执行[2](#zh-cn_topic_0191813932_li572522141314)。
        -   否，执行[1.d](#zh-cn_topic_0191813932_li233941717940)。

    4.  <a name="zh-cn_topic_0191813932_li233941717940"></a>联系运维人员查看是否为网络故障。
        -   是，执行[1.e](#zh-cn_topic_0191813932_li4279289717106)。
        -   否，执行[2](#zh-cn_topic_0191813932_li572522141314)。

    5.  <a name="zh-cn_topic_0191813932_li4279289717106"></a>修复网络故障，查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813932_li572522141314)。

2.  <a name="zh-cn_topic_0191813932_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813932_section55635852162510"></a>

无。

