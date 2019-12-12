# ALM-14012 HDFS Journalnode数据不同步<a name="ZH-CN_TOPIC_0191883101"></a>

## 告警解释<a name="zh-cn_topic_0191813911_section18191719"></a>

在主NameNode节点上，系统每5分钟检测一次集群中所有JournalNode节点的数据同步性。如果有JournalNode节点的数据不同步，系统产生该告警。

当Journalnode数据同步5分钟后，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813911_section29507743"></a>

<a name="zh-cn_topic_0191813911_table56187107"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813911_row43395070"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813911_p25339754"><a name="zh-cn_topic_0191813911_p25339754"></a><a name="zh-cn_topic_0191813911_p25339754"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813911_p39254219"><a name="zh-cn_topic_0191813911_p39254219"></a><a name="zh-cn_topic_0191813911_p39254219"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813911_p25475209"><a name="zh-cn_topic_0191813911_p25475209"></a><a name="zh-cn_topic_0191813911_p25475209"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813911_row50226059"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813911_p41779002"><a name="zh-cn_topic_0191813911_p41779002"></a><a name="zh-cn_topic_0191813911_p41779002"></a>14012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813911_p28655997"><a name="zh-cn_topic_0191813911_p28655997"></a><a name="zh-cn_topic_0191813911_p28655997"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813911_p39434429"><a name="zh-cn_topic_0191813911_p39434429"></a><a name="zh-cn_topic_0191813911_p39434429"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813911_section64243102"></a>

<a name="zh-cn_topic_0191813911_table40072161"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813911_row29623216"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813911_p50670335"><a name="zh-cn_topic_0191813911_p50670335"></a><a name="zh-cn_topic_0191813911_p50670335"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813911_p10656503"><a name="zh-cn_topic_0191813911_p10656503"></a><a name="zh-cn_topic_0191813911_p10656503"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813911_row57870399"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813911_p56990719"><a name="zh-cn_topic_0191813911_p56990719"></a><a name="zh-cn_topic_0191813911_p56990719"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813911_p52845536"><a name="zh-cn_topic_0191813911_p52845536"></a><a name="zh-cn_topic_0191813911_p52845536"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813911_row5847780"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813911_p3908185"><a name="zh-cn_topic_0191813911_p3908185"></a><a name="zh-cn_topic_0191813911_p3908185"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813911_p48127554"><a name="zh-cn_topic_0191813911_p48127554"></a><a name="zh-cn_topic_0191813911_p48127554"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813911_row30494806"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813911_p54160201"><a name="zh-cn_topic_0191813911_p54160201"></a><a name="zh-cn_topic_0191813911_p54160201"></a>IP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813911_p24900132"><a name="zh-cn_topic_0191813911_p24900132"></a><a name="zh-cn_topic_0191813911_p24900132"></a>产生告警的JournalNode实例的业务IP地址。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813911_section41317012"></a>

当一个JournalNode节点工作状态异常时，其数据就会与其他JournalNode节点的数据不同步。如果超过一半的JournalNode节点的数据不同步时，NameNode将无法工作，导致HDFS服务不可用。

## 可能原因<a name="zh-cn_topic_0191813911_section36308794"></a>

-   JournalNode实例未启动或已停止。
-   JournalNode实例运行状态异常。
-   JournalNode节点的网络不可达。

## 处理步骤<a name="zh-cn_topic_0191813911_section58343698"></a>

1.  查看JournalNode实例是否启动。
    1.  登录MRS集群详情页面，单击“告警管理”，在告警列表中单击此告警。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请打开MRS Manager页面操作。  

    2.  在“告警详情”区域，查看“定位信息”，获取告警产生的JournalNode节点IP地址。
    3.  单击“组件管理 \> HDFS \> 实例”，在实例列表中单击告警节点上的JournalNode实例，查看其“操作状态”是否为“已启动”。
        -   是，执行[2.a](#zh-cn_topic_0191813911_alm14012_mmccppss_s6)。
        -   否，执行[1.d](#zh-cn_topic_0191813911_alm14012_mmccppss_s4)。

    4.  <a name="zh-cn_topic_0191813911_alm14012_mmccppss_s4"></a>勾选该JournalNode实例，单击“更多 \> 启动实例”，等待启动完成。
    5.  等待5分钟后，查看告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813911_li572522141314)。

2.  查看JournalNode实例运行状态是否正常。
    1.  <a name="zh-cn_topic_0191813911_alm14012_mmccppss_s6"></a>查看该JournalNode实例的“健康状态”是否为“良好”。
        -   是，执行[3.a](#zh-cn_topic_0191813911_alm14012_mmccppss_s10)。
        -   否，执行[2.b](#zh-cn_topic_0191813911_s7)。

    2.  <a name="zh-cn_topic_0191813911_s7"></a>勾选该JournalNode实例，单击“更多 \> 重启实例”，等待启动完成。
    3.  等待5分钟后，查看告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813911_li572522141314)。

3.  查看JournalNode节点网络是否可达。
    1.  <a name="zh-cn_topic_0191813911_alm14012_mmccppss_s10"></a>在MRS集群详情页面，单击“组件管理 \> HDFS \> 实例”，查看主NameNode节点的业务IP地址。
    2.  登录主NameNode节点。
    3.  使用**ping**命令检查主NameNode与该JournalNode之间的网络状况，是否有超时或者网络不可达的情况。

        **ping** _JournalNode__的业务IP__地址_

        -   是，执行[3.d](#zh-cn_topic_0191813911_alm14012_mmccppss_s13)。
        -   否，执行[4](#zh-cn_topic_0191813911_li572522141314)。

    4.  <a name="zh-cn_topic_0191813911_alm14012_mmccppss_s13"></a>联系运维人员处理网络故障，故障恢复后等待5分钟，查看告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813911_li572522141314)。

4.  <a name="zh-cn_topic_0191813911_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813911_section55331235"></a>

无。

