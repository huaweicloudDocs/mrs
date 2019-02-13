# ALM-26051 Storm服务不可用<a name="ZH-CN_TOPIC_0093195075"></a>

## 告警解释<a name="zh-cn_topic_0053790965_section5795214917567"></a>

系统按照30秒的周期检测Storm服务是否可用，当集群全部的Nimbus实例所在节点异常时，Storm服务不可用，系统产生此告警。

当Storm服务恢复正常，告警自动清除。

## 告警属性<a name="zh-cn_topic_0053790965_section5233852717567"></a>

<a name="zh-cn_topic_0053790965_table1156228317567"></a>
<table><thead align="left"><tr id="zh-cn_topic_0053790965_row4943527217567"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0053790965_p4483413417567"><a name="zh-cn_topic_0053790965_p4483413417567"></a><a name="zh-cn_topic_0053790965_p4483413417567"></a><strong id="zh-cn_topic_0053790965_b85402717567"><a name="zh-cn_topic_0053790965_b85402717567"></a><a name="zh-cn_topic_0053790965_b85402717567"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0053790965_p206737517567"><a name="zh-cn_topic_0053790965_p206737517567"></a><a name="zh-cn_topic_0053790965_p206737517567"></a><strong id="zh-cn_topic_0053790965_b1860637517567"><a name="zh-cn_topic_0053790965_b1860637517567"></a><a name="zh-cn_topic_0053790965_b1860637517567"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0053790965_p3072140217567"><a name="zh-cn_topic_0053790965_p3072140217567"></a><a name="zh-cn_topic_0053790965_p3072140217567"></a><strong id="zh-cn_topic_0053790965_b805716717567"><a name="zh-cn_topic_0053790965_b805716717567"></a><a name="zh-cn_topic_0053790965_b805716717567"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0053790965_row4865078017567"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0053790965_p4839908917567"><a name="zh-cn_topic_0053790965_p4839908917567"></a><a name="zh-cn_topic_0053790965_p4839908917567"></a>26051</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0053790965_p2801215117567"><a name="zh-cn_topic_0053790965_p2801215117567"></a><a name="zh-cn_topic_0053790965_p2801215117567"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0053790965_p5439176517567"><a name="zh-cn_topic_0053790965_p5439176517567"></a><a name="zh-cn_topic_0053790965_p5439176517567"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0053790965_section1976384517567"></a>

<a name="zh-cn_topic_0053790965_table5736764417567"></a>
<table><thead align="left"><tr id="zh-cn_topic_0053790965_row4788438817567"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0053790965_p5343022917567"><a name="zh-cn_topic_0053790965_p5343022917567"></a><a name="zh-cn_topic_0053790965_p5343022917567"></a><strong id="zh-cn_topic_0053790965_b1111001717567"><a name="zh-cn_topic_0053790965_b1111001717567"></a><a name="zh-cn_topic_0053790965_b1111001717567"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0053790965_p2749619817567"><a name="zh-cn_topic_0053790965_p2749619817567"></a><a name="zh-cn_topic_0053790965_p2749619817567"></a><strong id="zh-cn_topic_0053790965_b4613919217567"><a name="zh-cn_topic_0053790965_b4613919217567"></a><a name="zh-cn_topic_0053790965_b4613919217567"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0053790965_row4628709917567"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790965_p5826751817567"><a name="zh-cn_topic_0053790965_p5826751817567"></a><a name="zh-cn_topic_0053790965_p5826751817567"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790965_p2204848917567"><a name="zh-cn_topic_0053790965_p2204848917567"></a><a name="zh-cn_topic_0053790965_p2204848917567"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0053790965_row6421867717567"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790965_p3433038517567"><a name="zh-cn_topic_0053790965_p3433038517567"></a><a name="zh-cn_topic_0053790965_p3433038517567"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790965_p2929776817567"><a name="zh-cn_topic_0053790965_p2929776817567"></a><a name="zh-cn_topic_0053790965_p2929776817567"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0053790965_row6235332617567"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790965_p1745466817567"><a name="zh-cn_topic_0053790965_p1745466817567"></a><a name="zh-cn_topic_0053790965_p1745466817567"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790965_p454197817567"><a name="zh-cn_topic_0053790965_p454197817567"></a><a name="zh-cn_topic_0053790965_p454197817567"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0053790965_section4087780217567"></a>

-   集群无法对外提供Storm服务。
-   用户无法执行新的Storm任务。

## 可能原因<a name="zh-cn_topic_0053790965_section358256717567"></a>

-   Kerberos组件故障
-   ZooKeeper组件故障或假死
-   Storm集群中主备Nimbus状态异常

## 处理步骤<a name="zh-cn_topic_0053790965_section5745431217567"></a>

1.  检查Kerberos组件状态。未启用Kerberos认证的集群无需检查Kerberos状态，请执行[2](#zh-cn_topic_0053790965_li59618494175936)。
    1.  在MRS Manager管理界面，单击“服务管理“。
    2.  <a name="zh-cn_topic_0053790965_li4574896917592"></a>查看Kerberos服务的健康状态是否为“良好“。
        -   是，执行[2.a](#zh-cn_topic_0053790965_li384738318010)。
        -   否，执行[1.c](#zh-cn_topic_0053790965_li22276139175922)。

    3.  <a name="zh-cn_topic_0053790965_li22276139175922"></a>参考ALM-25500 KrbServer服务不可用的相关维护信息进行操作。
    4.  再次执行[1.b](#zh-cn_topic_0053790965_li4574896917592)。

2.  <a name="zh-cn_topic_0053790965_li59618494175936"></a>检查ZooKeeper组件状态。
    1.  <a name="zh-cn_topic_0053790965_li384738318010"></a>查看ZooKeeper服务的健康状态是否为“良好“。
        -   是，执行[3.a](#zh-cn_topic_0053790965_li2005716918338)。
        -   否，执行[2.b](#zh-cn_topic_0053790965_li398384891819)。

    2.  <a name="zh-cn_topic_0053790965_li398384891819"></a>如果ZooKeeper服务停止运行，则启动服务，否则参考ALM-13000 ZooKeeper服务不可用的相关维护信息进行操作。
    3.  再次执行[2.a](#zh-cn_topic_0053790965_li384738318010)。

3.  检查主备Nimbus状态。
    1.  <a name="zh-cn_topic_0053790965_li2005716918338"></a>选择“服务管理  \>  Storm  \>  Nimbus“，进入Nimbus实例页面。
    2.  查看“角色“中是否存在且仅存在一个状态为主的Nimbus节点。
        -   是，执行[4.a](#zh-cn_topic_0053790965_li4718188915959)。
        -   否，执行[3.c](#zh-cn_topic_0053790965_li4603773018356)。

    3.  <a name="zh-cn_topic_0053790965_li4603773018356"></a>勾选两个Nimbus角色实例，选择“更多 \> 重启实例“，查看是否重启成功。
        -   是，执行[3.d](#zh-cn_topic_0053790965_li632054418412)。
        -   否，执行[4.a](#zh-cn_topic_0053790965_li4718188915959)。

    4.  <a name="zh-cn_topic_0053790965_li632054418412"></a>重新登录MRS Manager管理界面，选择“服务管理  \>  Storm  \>  Nimbus“，查看健康状态是否为“良好”。
        -   是，执行[3.e](#zh-cn_topic_0053790965_li5966586218421)。
        -   否，执行[4.a](#zh-cn_topic_0053790965_li4718188915959)。

    5.  <a name="zh-cn_topic_0053790965_li5966586218421"></a>等待30秒，查看告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0053790965_li4718188915959)。


4.  收集故障信息。
    1.  <a name="zh-cn_topic_0053790965_li4718188915959"></a>在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0053790965_section6569928217567"></a>

无。

