# ALM-16001 Hive数据仓库空间使用率超过阈值<a name="ZH-CN_TOPIC_0191883103"></a>

## 告警解释<a name="zh-cn_topic_0191813901_section23562876"></a>

系统每30秒周期性检测Hive数据仓库空间使用率，该指标可在Hive服务监控界面查看，指标名称为“Hive已经使用的HDFS空间占可使用空间的百分比”。Hive数据仓库空间使用率指标默认提供一个阈值范围（85%），当检测到Hive数据仓库空间使用率超过阈值范围时产生该告警。

当Hive数据仓库空间使用率小于或等于阈值时，告警恢复。用户可通过增加仓库容量或释放部分已使用空间的方式降低仓库空间使用率。

## 告警属性<a name="zh-cn_topic_0191813901_section10739296"></a>

<a name="zh-cn_topic_0191813901_table42586845"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813901_row65610739"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813901_p12869603"><a name="zh-cn_topic_0191813901_p12869603"></a><a name="zh-cn_topic_0191813901_p12869603"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813901_p35804895"><a name="zh-cn_topic_0191813901_p35804895"></a><a name="zh-cn_topic_0191813901_p35804895"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813901_p14515408"><a name="zh-cn_topic_0191813901_p14515408"></a><a name="zh-cn_topic_0191813901_p14515408"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813901_row34897438"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813901_p8120240"><a name="zh-cn_topic_0191813901_p8120240"></a><a name="zh-cn_topic_0191813901_p8120240"></a>16001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813901_p53759727"><a name="zh-cn_topic_0191813901_p53759727"></a><a name="zh-cn_topic_0191813901_p53759727"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813901_p59570626"><a name="zh-cn_topic_0191813901_p59570626"></a><a name="zh-cn_topic_0191813901_p59570626"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813901_section29544808"></a>

<a name="zh-cn_topic_0191813901_table60491410"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813901_row20888703"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813901_p14263389"><a name="zh-cn_topic_0191813901_p14263389"></a><a name="zh-cn_topic_0191813901_p14263389"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813901_p14483900"><a name="zh-cn_topic_0191813901_p14483900"></a><a name="zh-cn_topic_0191813901_p14483900"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813901_row32345284"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813901_p2722332"><a name="zh-cn_topic_0191813901_p2722332"></a><a name="zh-cn_topic_0191813901_p2722332"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813901_p19182316"><a name="zh-cn_topic_0191813901_p19182316"></a><a name="zh-cn_topic_0191813901_p19182316"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813901_row38423121"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813901_p25265097"><a name="zh-cn_topic_0191813901_p25265097"></a><a name="zh-cn_topic_0191813901_p25265097"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813901_p33206990"><a name="zh-cn_topic_0191813901_p33206990"></a><a name="zh-cn_topic_0191813901_p33206990"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813901_row30427456"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813901_p48704899"><a name="zh-cn_topic_0191813901_p48704899"></a><a name="zh-cn_topic_0191813901_p48704899"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813901_p52782726"><a name="zh-cn_topic_0191813901_p52782726"></a><a name="zh-cn_topic_0191813901_p52782726"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813901_row5282487"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813901_p25228285"><a name="zh-cn_topic_0191813901_p25228285"></a><a name="zh-cn_topic_0191813901_p25228285"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813901_p30225241"><a name="zh-cn_topic_0191813901_p30225241"></a><a name="zh-cn_topic_0191813901_p30225241"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813901_section64576684"></a>

系统可能无法正常写入数据，导致部分数据丢失。

## 可能原因<a name="zh-cn_topic_0191813901_section44319244"></a>

-   Hive使用HDFS容量上限过小。
-   系统磁盘空间不足。
-   部分数据节点瘫痪。

## 处理步骤<a name="zh-cn_topic_0191813901_section63328883"></a>

1.  扩展系统配置。
    1.  分析集群HDFS使用情况，增加HDFS分配给Hive使用的容量上限。

        登录MRS集群详情页面，单击“组件管理 \> Hive \> 服务配置”，“参数类别”设置为“全部配置”，然后查找“hive.metastore.warehouse.size.percent”，调大该配置项。设配置项的值为A，HDFS总存储空间为B，阈值为C，Hive已经使用HDFS的空间大小为D。调整策略为A x B x C \> D ，HDFS总存储空间可在HDFS监控界面查看，Hive已经使用HDFS的空间大小可在Hive的监控界面查看。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，单击“组件管理 \> Hive \> 服务配置”进行配置。  

    2.  检查该告警是否恢复。
        -   是，操作结束。
        -   否，执行[2.a](#zh-cn_topic_0191813901_s332)

2.  对系统进行扩容。
    1.  <a name="zh-cn_topic_0191813901_s332"></a>添加节点。
    2.  检查该告警是否恢复。
        -   是，操作结束。
        -   否，执行[3.a](#zh-cn_topic_0191813901_li51692872)。

3.  检查数据节点是否正常。
    1.  <a name="zh-cn_topic_0191813901_li51692872"></a>登录MRS集群详情页面，选择“告警管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“告警管理”。  

    2.  查看是否有“ALM-12006 节点故障”、“ALM-12007 进程故障”、“ALM-14002 DataNode磁盘空间使用率超过阈值”告警。
        -   是，执行[3.c](#zh-cn_topic_0191813901_aalm-16001_mmccppss_step5)。
        -   否，执行[4](#zh-cn_topic_0191813901_li572522141314)。

    3.  <a name="zh-cn_topic_0191813901_aalm-16001_mmccppss_step5"></a>分别参考ALM-12006 节点故障、ALM-12007 进程故障、ALM-14002 DataNode磁盘空间使用率超过阈值的处理步骤处理告警。
    4.  查看本告警是否恢复。
        -   是，操作结束。
        -   否，执行[4](#zh-cn_topic_0191813901_li572522141314)。

4.  <a name="zh-cn_topic_0191813901_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813901_section33089041"></a>

无。

