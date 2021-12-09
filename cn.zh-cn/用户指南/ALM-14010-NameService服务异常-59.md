# ALM-14010 NameService服务异常<a name="alm_14010"></a>

## 告警解释<a name="zh-cn_topic_0191813899_section48163256"></a>

系统每180秒周期性检测NameService服务状态，当检测到NameService服务不可用时产生该告警。

NameService服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0191813899_section30816121"></a>

<a name="zh-cn_topic_0191813899_table56165728"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813899_row23522831"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813899_p26301173"><a name="zh-cn_topic_0191813899_p26301173"></a><a name="zh-cn_topic_0191813899_p26301173"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813899_p50020275"><a name="zh-cn_topic_0191813899_p50020275"></a><a name="zh-cn_topic_0191813899_p50020275"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813899_p25110514"><a name="zh-cn_topic_0191813899_p25110514"></a><a name="zh-cn_topic_0191813899_p25110514"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813899_row20685786"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813899_p64935954"><a name="zh-cn_topic_0191813899_p64935954"></a><a name="zh-cn_topic_0191813899_p64935954"></a>14010</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813899_p25320898"><a name="zh-cn_topic_0191813899_p25320898"></a><a name="zh-cn_topic_0191813899_p25320898"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813899_p37726867"><a name="zh-cn_topic_0191813899_p37726867"></a><a name="zh-cn_topic_0191813899_p37726867"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813899_section8909633"></a>

<a name="zh-cn_topic_0191813899_table35977388"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813899_row30639779"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813899_p65903005"><a name="zh-cn_topic_0191813899_p65903005"></a><a name="zh-cn_topic_0191813899_p65903005"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813899_p36543171"><a name="zh-cn_topic_0191813899_p36543171"></a><a name="zh-cn_topic_0191813899_p36543171"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813899_row7206911"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813899_p46888886"><a name="zh-cn_topic_0191813899_p46888886"></a><a name="zh-cn_topic_0191813899_p46888886"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813899_p39903442"><a name="zh-cn_topic_0191813899_p39903442"></a><a name="zh-cn_topic_0191813899_p39903442"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813899_row23586666"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813899_p31471768"><a name="zh-cn_topic_0191813899_p31471768"></a><a name="zh-cn_topic_0191813899_p31471768"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813899_p66185246"><a name="zh-cn_topic_0191813899_p66185246"></a><a name="zh-cn_topic_0191813899_p66185246"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813899_row58796306"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813899_p64880336"><a name="zh-cn_topic_0191813899_p64880336"></a><a name="zh-cn_topic_0191813899_p64880336"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813899_p20815867"><a name="zh-cn_topic_0191813899_p20815867"></a><a name="zh-cn_topic_0191813899_p20815867"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813899_row53125076"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813899_p8163917"><a name="zh-cn_topic_0191813899_p8163917"></a><a name="zh-cn_topic_0191813899_p8163917"></a>NSName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813899_p57297510"><a name="zh-cn_topic_0191813899_p57297510"></a><a name="zh-cn_topic_0191813899_p57297510"></a>产生告警的NameService名称</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813899_section13077833"></a>

无法为基于该NameService服务的HBase和MapReduce等上层部件提供服务。用户无法读写文件。

## 可能原因<a name="zh-cn_topic_0191813899_section50591634"></a>

-   JournalNode节点故障。
-   DataNode节点故障。
-   磁盘容量不足。
-   NameNode节点进入安全模式。

## 处理步骤<a name="zh-cn_topic_0191813899_section52671525"></a>

1.  检查JournalNode实例状态。
    1.  在MRS Manager首页，单击“组件管理”。
    2.  单击“HDFS”。
    3.  单击“实例”。
    4.  在页面中，查看JournalNode的“健康状态”是否为“良好”。
        -   是，执行[2.a](#zh-cn_topic_0191813899_alm14010_mmccppss_step11)。
        -   否，执行[1.e](#zh-cn_topic_0191813899_alm14010_mmccppss_step12)。

    5.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step12"></a>选择故障的JournalNode，单击“更多 \> 重启实例”。查看JournalNode能否成功启动。
        -   是，执行[1.f](#zh-cn_topic_0191813899_alm14010_mmccppss_step10)。
        -   否，执行[5](#zh-cn_topic_0191813899_li572522141314)。

    6.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step10"></a>等待5分钟后，在“告警管理”页签，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813899_alm14010_mmccppss_step11)。

2.  检查DataNode实例状态。
    1.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step11"></a>在MRS集群详情页面，单击“组件管理”。
    2.  单击“HDFS”。
    3.  在“操作状态和健康状态”中，查看所有DataNode节点的“健康状态”是否为“良好”。
        -   是，执行[3.a](#zh-cn_topic_0191813899_alm14010_mmccppss_step24)。
        -   否，执行[2.d](#zh-cn_topic_0191813899_alm14010_mmccppss_step14)。

    4.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step14"></a>单击“实例”。在DataNode管理页面，选择故障DataNode，单击“更多 \> 重启实例”。查看DataNode能否成功启动。
        -   是，执行[2.e](#zh-cn_topic_0191813899_alm14010_mmccppss_step15)。
        -   否，执行[3.a](#zh-cn_topic_0191813899_alm14010_mmccppss_step24)。

    5.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step15"></a>等待5分钟后，在“告警管理”页签，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0191813899_step28)。

3.  检查磁盘状态。
    1.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step24"></a>在MRS集群详情页面，单击“节点管理”并展开节点组信息。
    2.  在“磁盘使用率”列，检查磁盘空间是否不足。
        -   是，执行[3.c](#zh-cn_topic_0191813899_alm14010_mmccppss_step26)。
        -   否，执行[4.a](#zh-cn_topic_0191813899_step28)。

    3.  <a name="zh-cn_topic_0191813899_alm14010_mmccppss_step26"></a>对磁盘进行扩容。
    4.  等待5分钟后，在“告警管理”页签，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0191813899_step28)。

4.  检查NameNode节点是否进入安全模式。
    1.  <a name="zh-cn_topic_0191813899_step28"></a>在集群节点使用客户端，执行hdfs dfsadmin -safemode get命令：“Safe mode is ON.”。

        “Safe mode is ON.”表示安全模式已打开，后面的提示信息为告警信息，根据实际情况展现。

        -   是，执行[4.b](#zh-cn_topic_0191813899_li66373591)。
        -   否，执行[5](#zh-cn_topic_0191813899_li572522141314)。

    2.  <a name="zh-cn_topic_0191813899_li66373591"></a>在集群节点使用客户端，执行**hdfs dfsadmin -safemode leave**。
    3.  等待5分钟后，在“告警管理”页签，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[5](#zh-cn_topic_0191813899_li572522141314)。

5.  <a name="zh-cn_topic_0191813899_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813899_section4281684"></a>

无。

