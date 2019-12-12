# ALM-38000 Kafka服务不可用<a name="ZH-CN_TOPIC_0191883123"></a>

## 告警解释<a name="zh-cn_topic_0191813970_section19665522175625"></a>

系统按照30秒的周期检测Kafka服务是否可用，当Kafka服务不可用，系统产生此告警。

当Kafka服务恢复正常，告警自动清除。

## 告警属性<a name="zh-cn_topic_0191813970_section42254989175625"></a>

<a name="zh-cn_topic_0191813970_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813970_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813970_p34183898175625"><a name="zh-cn_topic_0191813970_p34183898175625"></a><a name="zh-cn_topic_0191813970_p34183898175625"></a><strong id="zh-cn_topic_0191813970_b39219631175625"><a name="zh-cn_topic_0191813970_b39219631175625"></a><a name="zh-cn_topic_0191813970_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813970_p22673543175625"><a name="zh-cn_topic_0191813970_p22673543175625"></a><a name="zh-cn_topic_0191813970_p22673543175625"></a><strong id="zh-cn_topic_0191813970_b2735300175625"><a name="zh-cn_topic_0191813970_b2735300175625"></a><a name="zh-cn_topic_0191813970_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813970_p20232782175625"><a name="zh-cn_topic_0191813970_p20232782175625"></a><a name="zh-cn_topic_0191813970_p20232782175625"></a><strong id="zh-cn_topic_0191813970_b47877317175625"><a name="zh-cn_topic_0191813970_b47877317175625"></a><a name="zh-cn_topic_0191813970_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813970_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813970_p35937536181151"><a name="zh-cn_topic_0191813970_p35937536181151"></a><a name="zh-cn_topic_0191813970_p35937536181151"></a>38000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813970_p25259281181151"><a name="zh-cn_topic_0191813970_p25259281181151"></a><a name="zh-cn_topic_0191813970_p25259281181151"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813970_p32735912181151"><a name="zh-cn_topic_0191813970_p32735912181151"></a><a name="zh-cn_topic_0191813970_p32735912181151"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813970_section27218191175625"></a>

<a name="zh-cn_topic_0191813970_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813970_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813970_p9726186175625"><a name="zh-cn_topic_0191813970_p9726186175625"></a><a name="zh-cn_topic_0191813970_p9726186175625"></a><strong id="zh-cn_topic_0191813970_b20426813175625"><a name="zh-cn_topic_0191813970_b20426813175625"></a><a name="zh-cn_topic_0191813970_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813970_p43959148175625"><a name="zh-cn_topic_0191813970_p43959148175625"></a><a name="zh-cn_topic_0191813970_p43959148175625"></a><strong id="zh-cn_topic_0191813970_b60088019175625"><a name="zh-cn_topic_0191813970_b60088019175625"></a><a name="zh-cn_topic_0191813970_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813970_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813970_p8637281181159"><a name="zh-cn_topic_0191813970_p8637281181159"></a><a name="zh-cn_topic_0191813970_p8637281181159"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813970_p28531188181159"><a name="zh-cn_topic_0191813970_p28531188181159"></a><a name="zh-cn_topic_0191813970_p28531188181159"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813970_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813970_p62597248181159"><a name="zh-cn_topic_0191813970_p62597248181159"></a><a name="zh-cn_topic_0191813970_p62597248181159"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813970_p37212310181159"><a name="zh-cn_topic_0191813970_p37212310181159"></a><a name="zh-cn_topic_0191813970_p37212310181159"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813970_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813970_p15793618181159"><a name="zh-cn_topic_0191813970_p15793618181159"></a><a name="zh-cn_topic_0191813970_p15793618181159"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813970_p4214711181159"><a name="zh-cn_topic_0191813970_p4214711181159"></a><a name="zh-cn_topic_0191813970_p4214711181159"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813970_section23922301175625"></a>

集群无法对外提供Kafka服务，用户无法执行新的Kafka任务。

## 可能原因<a name="zh-cn_topic_0191813970_section58162349175625"></a>

-   KrbServer组件故障。
-   ZooKeeper组件故障或无响应。
-   Kafka集群中Broker节点异常。

## 处理步骤<a name="zh-cn_topic_0191813970_section51182191175625"></a>

1.  检查KrbServer组件状态。未启用Kerberos认证的集群无需检查Kerberos状态，请直接执行[2](#zh-cn_topic_0191813970_li21507667181241)。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  <a name="zh-cn_topic_0191813970_li1071286918299"></a>查看KrbServer服务的健康状态是否为“良好“。
        -   是，执行[2.a](#zh-cn_topic_0191813970_li22712539182948)。
        -   否，执行[1.c](#zh-cn_topic_0191813970_li50060872182922)。

    3.  <a name="zh-cn_topic_0191813970_li50060872182922"></a>参考ALM-25500 KrbServer服务不可用的处理步骤进行操作。
    4.  再次执行[1.b](#zh-cn_topic_0191813970_li1071286918299)。

2.  <a name="zh-cn_topic_0191813970_li21507667181241"></a>检查ZooKeeper组件状态。
    1.  <a name="zh-cn_topic_0191813970_li22712539182948"></a>查看ZooKeeper服务的健康状态是否为“良好“。
        -   是，执行[3.a](#zh-cn_topic_0191813970_li6551802183028)。
        -   否，执行[2.b](#zh-cn_topic_0191813970_li35295745182948)。

    2.  <a name="zh-cn_topic_0191813970_li35295745182948"></a>如果ZooKeeper服务已停止，则启动ZooKeeper服务，否则参考ALM-13000 ZooKeeper服务不可用的处理步骤进行操作。
    3.  再次执行[2.a](#zh-cn_topic_0191813970_li22712539182948)。

3.  检查Broker状态。
    1.  <a name="zh-cn_topic_0191813970_li6551802183028"></a>选择“组件管理 \> Kafka \> Broker“，进入Kafka实例页面。
    2.  查看“角色“中所有实例是否正常。
        -   是，执行[3.d](#zh-cn_topic_0191813970_li54013684183028)。
        -   否，执行[3.c](#zh-cn_topic_0191813970_li7614495183028)。

    3.  <a name="zh-cn_topic_0191813970_li7614495183028"></a>勾选Broker所有实例，选择“更多 \> 重启实例“，查看是否重启成功。
        -   是，执行[3.d](#zh-cn_topic_0191813970_li54013684183028)。
        -   否，执行[4](#zh-cn_topic_0191813970_li572522141314)。

    4.  <a name="zh-cn_topic_0191813970_li54013684183028"></a>选择“组件管理 \> Kafka“，查看健康状态是否为“良好“。
        -   是，执行[3.e](#zh-cn_topic_0191813970_li11571314183028)。
        -   否，执行[4](#zh-cn_topic_0191813970_li572522141314)。

    5.  <a name="zh-cn_topic_0191813970_li11571314183028"></a>等待30秒，查看告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813970_li572522141314)。

4.  <a name="zh-cn_topic_0191813970_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813970_section20269844175625"></a>

无。

