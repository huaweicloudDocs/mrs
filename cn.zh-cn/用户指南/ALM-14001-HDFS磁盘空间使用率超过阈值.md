# ALM-14001 HDFS磁盘空间使用率超过阈值<a name="ZH-CN_TOPIC_0191883091"></a>

## 告警解释<a name="zh-cn_topic_0191813969_section6883221"></a>

系统每30秒周期性检测HDFS集群磁盘空间使用率，并把实际的HDFS集群磁盘空间使用率和阈值相比较。HDFS集群磁盘使用率指标默认提供一个阈值范围。当HDFS集群磁盘空间使用率超出阈值范围时，产生该告警。

当HDFS磁盘使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813969_section61948991"></a>

<a name="zh-cn_topic_0191813969_table48889850"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813969_row1927776"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813969_p21932166"><a name="zh-cn_topic_0191813969_p21932166"></a><a name="zh-cn_topic_0191813969_p21932166"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813969_p31674992"><a name="zh-cn_topic_0191813969_p31674992"></a><a name="zh-cn_topic_0191813969_p31674992"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813969_p15537542"><a name="zh-cn_topic_0191813969_p15537542"></a><a name="zh-cn_topic_0191813969_p15537542"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813969_row50581426"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813969_p3454809"><a name="zh-cn_topic_0191813969_p3454809"></a><a name="zh-cn_topic_0191813969_p3454809"></a>14001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813969_p11404133"><a name="zh-cn_topic_0191813969_p11404133"></a><a name="zh-cn_topic_0191813969_p11404133"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813969_p51319614"><a name="zh-cn_topic_0191813969_p51319614"></a><a name="zh-cn_topic_0191813969_p51319614"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813969_section20670010"></a>

<a name="zh-cn_topic_0191813969_table63248075"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813969_row60232767"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813969_p47015983"><a name="zh-cn_topic_0191813969_p47015983"></a><a name="zh-cn_topic_0191813969_p47015983"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813969_p50198296"><a name="zh-cn_topic_0191813969_p50198296"></a><a name="zh-cn_topic_0191813969_p50198296"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813969_row39530145"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813969_p47825138"><a name="zh-cn_topic_0191813969_p47825138"></a><a name="zh-cn_topic_0191813969_p47825138"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813969_p48630964"><a name="zh-cn_topic_0191813969_p48630964"></a><a name="zh-cn_topic_0191813969_p48630964"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813969_row35025494"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813969_p18492804"><a name="zh-cn_topic_0191813969_p18492804"></a><a name="zh-cn_topic_0191813969_p18492804"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813969_p21522166"><a name="zh-cn_topic_0191813969_p21522166"></a><a name="zh-cn_topic_0191813969_p21522166"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813969_row59481773"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813969_p53294272"><a name="zh-cn_topic_0191813969_p53294272"></a><a name="zh-cn_topic_0191813969_p53294272"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813969_p21868813"><a name="zh-cn_topic_0191813969_p21868813"></a><a name="zh-cn_topic_0191813969_p21868813"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813969_row62601592"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813969_p37564172"><a name="zh-cn_topic_0191813969_p37564172"></a><a name="zh-cn_topic_0191813969_p37564172"></a>NSName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813969_p22799085"><a name="zh-cn_topic_0191813969_p22799085"></a><a name="zh-cn_topic_0191813969_p22799085"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813969_row3865173"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813969_p44643603"><a name="zh-cn_topic_0191813969_p44643603"></a><a name="zh-cn_topic_0191813969_p44643603"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813969_p59362130"><a name="zh-cn_topic_0191813969_p59362130"></a><a name="zh-cn_topic_0191813969_p59362130"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813969_section51812368"></a>

HDFS集群磁盘容量不足，会影响到HDFS的数据写入。

## 可能原因<a name="zh-cn_topic_0191813969_section63658128"></a>

HDFS集群配置的磁盘空间不足。

## 处理步骤<a name="zh-cn_topic_0191813969_section36052245"></a>

1.  查看磁盘容量，清除无用文件。
    1.  在MRS集群详情页面，单击“组件管理 \> HDFS”，弹出“服务状态”页面。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面，单击“服务管理 \> HDFS”。  

    2.  在“图表”区域中，通过监控项“Percentage of HDFS Capacity”查看HDFS磁盘使用率是否超过阈值（默认为80%）。
        -   是，执行[1.c](#zh-cn_topic_0191813969_cn_58_42_000001_5_mmccppss_step5)。
        -   否，执行[3](#zh-cn_topic_0191813969_li572522141314)。

    3.  <a name="zh-cn_topic_0191813969_cn_58_42_000001_5_mmccppss_step5"></a>在集群节点使用客户端，执行hdfs dfsadmin -report命令，查看汇总部分的DFS Used%显示项的值是否小于100%减去阈值的差。
        -   是，执行[1.e](#zh-cn_topic_0191813969_li39567352)
        -   否，执行[3](#zh-cn_topic_0191813969_li572522141314)。

    4.  在集群节点使用客户端，执行**hdfs dfs -rm -r** _文件或目录路径_命令，确认删除无用的文件。
    5.  <a name="zh-cn_topic_0191813969_li39567352"></a>等待5分钟后，检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813969_cn_58_42_000001_5_mmccppss_step13)。

2.  对系统进行扩容。
    1.  <a name="zh-cn_topic_0191813969_cn_58_42_000001_5_mmccppss_step13"></a>对磁盘进行扩容。
    2.  等待5分钟后，检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813969_li572522141314)。

3.  <a name="zh-cn_topic_0191813969_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813969_section56034750"></a>

无。

