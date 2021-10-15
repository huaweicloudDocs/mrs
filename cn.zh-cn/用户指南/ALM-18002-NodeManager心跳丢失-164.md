# ALM-18002 NodeManager心跳丢失<a name="ALM-18002"></a>

## 告警解释<a name="section9054680"></a>

系统每30秒周期性检测丢失的NodeManager节点，并把丢失的节点数和阈值相比较。“丢失的节点数”指标默认提供一个阈值。当检测到“丢失的节点数”的值超出阈值时产生该告警。

用户可通过选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置”，修改yarn.nodemanager.lost.alarm.threshold的值来配置阈值（修改该参数不用重启Yarn，就可以生效）。

阈值默认为零，当丢失节点数超过该值时，触发告警，小于阈值时会自动消除告警。

## 告警属性<a name="section14383261"></a>

<a name="table1491941"></a>
<table><thead align="left"><tr id="row54548545"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p56356030"><a name="p56356030"></a><a name="p56356030"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p1435736"><a name="p1435736"></a><a name="p1435736"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p49185782"><a name="p49185782"></a><a name="p49185782"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row24625409"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p48501088"><a name="p48501088"></a><a name="p48501088"></a>18002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p36274044"><a name="p36274044"></a><a name="p36274044"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p52516412"><a name="p52516412"></a><a name="p52516412"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section62340489"></a>

<a name="table25970952"></a>
<table><thead align="left"><tr id="row54141476"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p23383448"><a name="p23383448"></a><a name="p23383448"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p15011099"><a name="p15011099"></a><a name="p15011099"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row2302832142015"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row7939544"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p14872090"><a name="p14872090"></a><a name="p14872090"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row66739952"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62596758"><a name="p62596758"></a><a name="p62596758"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row26499917"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p54003533"><a name="p54003533"></a><a name="p54003533"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row16269750"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p169162942710"><a name="p169162942710"></a><a name="p169162942710"></a>Lost Host</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p42741538"><a name="p42741538"></a><a name="p42741538"></a>丢失节点的主机列表。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section24193493"></a>

-   丢失的NodeManager节点无法提供Yarn服务。
-   容器减少，集群性能下降。

## 可能原因<a name="section16414850"></a>

-   NodeManager没有经过退服操作，强制被删除。
-   NodeManager所有实例被停止或者进程故障。
-   NodeManager节点所在主机故障。
-   NodeManager和ResourceManager之间的网络断连或者繁忙。

## 处理步骤<a name="section13515930"></a>

**检查NodeManager状态。**

1.  <a name="li61419583194749"></a>在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”，在告警列表中找到当前告警，单击![](figures/zh-cn_image_0263895536.png)获取告警详细信息，在“附加信息”中获取丢失状态的节点。
2.  确认处于丢失状态的节点是否是人为未经过退服操作，直接主动删除的主机。
    -   是，执行[3](#li66611600194749)。
    -   否，执行[5](#li925923194749)。

3.  <a name="li66611600194749"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn”，进入“配置”页面，选择“全部配置”，搜索“yarn.nodemanager.lost.alarm.threshold”，修改值为未退服主动删除的主机个数。设置成功后检查告警是否清除。
    -   是，处理完毕。
    -   否，执行[4](#li62633489194749)。

4.  <a name="li62633489194749"></a>手动清除此告警，后续删除主机前务必进行退服操作。
5.  <a name="li925923194749"></a>在FusionInsight Manager界面，选择“集群 \> 主机”，查看[1](#li61419583194749)中获取的节点是否健康。
    -   是，执行[7](#li1961161194749)。
    -   否，执行[6](#li16448867194749)。

6.  <a name="li16448867194749"></a>参考“ALM-12006 节点故障”的操作步骤进行处理，节点恢复正常后，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li1961161194749)。


**检查进程状态。**

1.  <a name="li1961161194749"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例”，查看是否存在状态为非“良好”的NodeManager。
    -   是，执行[10](#li64163527194749)。
    -   否，执行[8](#li41079788194749)。

2.  <a name="li41079788194749"></a>确认此NodeManager实例是否被删除。
    -   是，执行[9](#li30856451194749)。
    -   否，执行[11](#li41604207194749)。

3.  <a name="li30856451194749"></a>重启ResourceManager的主备实例，然后检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li28939094194749)。


**检查实例状态。**

1.  <a name="li64163527194749"></a>选择处于非“良好”状态的NodeManager实例并重启该实例。检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li41604207194749)。


**检查网络状态。**

1.  <a name="li41604207194749"></a>登录管理节点，**ping**丢失的NodeManager节点的IP地址，检查网络是否断连或繁忙。管理节点的主备状态及对应IP地址可在FusionInsight Manager主机管理界面查看。
    -   是，执行[12](#li25585076194749)。
    -   否，执行[13](#li28939094194749)。

2.  <a name="li25585076194749"></a>修复网络故障，然后查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li28939094194749)。


**收集故障信息。**

1.  <a name="li28939094194749"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section54534508"></a>

无。

