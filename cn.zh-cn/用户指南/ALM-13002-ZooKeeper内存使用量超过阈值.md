# ALM-13002 ZooKeeper内存使用量超过阈值<a name="alm_13002"></a>

## 告警解释<a name="zh-cn_topic_0191813895_section46652504"></a>

系统每30秒周期性检测ZooKeeper服务内存使用状态，当检测到ZooKeeper实例内存使用量超出阈值（最大内存的百分之八十）时产生该告警。

内存使用率小于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813895_section17219353"></a>

<a name="zh-cn_topic_0191813895_table17618432"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813895_row61813935"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813895_p40872853"><a name="zh-cn_topic_0191813895_p40872853"></a><a name="zh-cn_topic_0191813895_p40872853"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813895_p22366803"><a name="zh-cn_topic_0191813895_p22366803"></a><a name="zh-cn_topic_0191813895_p22366803"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813895_p66880658"><a name="zh-cn_topic_0191813895_p66880658"></a><a name="zh-cn_topic_0191813895_p66880658"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813895_row48624250"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813895_p46250162"><a name="zh-cn_topic_0191813895_p46250162"></a><a name="zh-cn_topic_0191813895_p46250162"></a>13002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813895_p55275618"><a name="zh-cn_topic_0191813895_p55275618"></a><a name="zh-cn_topic_0191813895_p55275618"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813895_p48140083"><a name="zh-cn_topic_0191813895_p48140083"></a><a name="zh-cn_topic_0191813895_p48140083"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813895_section20756449"></a>

<a name="zh-cn_topic_0191813895_table7032652"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813895_row1472067"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813895_p52128573"><a name="zh-cn_topic_0191813895_p52128573"></a><a name="zh-cn_topic_0191813895_p52128573"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813895_p61664867"><a name="zh-cn_topic_0191813895_p61664867"></a><a name="zh-cn_topic_0191813895_p61664867"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813895_row28798367"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813895_p50966358"><a name="zh-cn_topic_0191813895_p50966358"></a><a name="zh-cn_topic_0191813895_p50966358"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813895_p34634354"><a name="zh-cn_topic_0191813895_p34634354"></a><a name="zh-cn_topic_0191813895_p34634354"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813895_row43273738"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813895_p15511864"><a name="zh-cn_topic_0191813895_p15511864"></a><a name="zh-cn_topic_0191813895_p15511864"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813895_p48501438"><a name="zh-cn_topic_0191813895_p48501438"></a><a name="zh-cn_topic_0191813895_p48501438"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813895_row33859762"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813895_p58286192"><a name="zh-cn_topic_0191813895_p58286192"></a><a name="zh-cn_topic_0191813895_p58286192"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813895_p23561115"><a name="zh-cn_topic_0191813895_p23561115"></a><a name="zh-cn_topic_0191813895_p23561115"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813895_row10723444"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813895_p63292653"><a name="zh-cn_topic_0191813895_p63292653"></a><a name="zh-cn_topic_0191813895_p63292653"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813895_p26431238"><a name="zh-cn_topic_0191813895_p26431238"></a><a name="zh-cn_topic_0191813895_p26431238"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813895_section52590313"></a>

ZooKeeper可用内存不足，可能会造成内存溢出导致服务崩溃。

## 可能原因<a name="zh-cn_topic_0191813895_section3550770"></a>

该节点ZooKeeper实例内存使用量过大，或分配的内存不合理，导致使用量超过阈值。

## 处理步骤<a name="zh-cn_topic_0191813895_section31956933"></a>

1.  检查内存使用量。
    1.  在MRS集群详情页面，单击“告警管理 \> 13002连接数不足 \> 定位信息”。查看告警上报的实例的ip。
    2.  在MRS集群详情页面，单击“组件管理 \> ZooKeeper \> 实例 \> quorumpeer（对应上报告警实例ip） \> 定制  \> ZooKeeper堆内存与直接内存资源状况”。查看堆内存使用情况。
    3.  查看ZooKeeper使用的堆内存是否已达到ZooKeeper设定的最大堆内存的百分之80？
        -   是，执行[1.d](#zh-cn_topic_0191813895_cn_58_42_000001_3_mmccppss_stepb2)。
        -   否，执行[1.f](#zh-cn_topic_0191813895_cn_58_42_000001_3_mmccppss_stepb4)。

    4.  <a name="zh-cn_topic_0191813895_cn_58_42_000001_3_mmccppss_stepb2"></a>在MRS Manager首页，单击“服务管理 \> ZooKeeper \> 服务配置 \> 全部配置 \> quorumpeer \> 系统”。将GC\_OPTS参数中-Xmx的值根据实际情况调大。
    5.  观察界面告警是否清除？
        -   是，处理完毕。
        -   否，执行[1.f](#zh-cn_topic_0191813895_cn_58_42_000001_3_mmccppss_stepb4)。

    6.  <a name="zh-cn_topic_0191813895_cn_58_42_000001_3_mmccppss_stepb4"></a>在MRS集群详情页面，单击“组件管理 \> ZooKeeper \> 实例 \> quorumpeer（对应上报告警实例ip） \> 定制 \> ZooKeeper堆内存与直接内存资源情况 ”。查看直接内存的使用情况。
    7.  查看ZooKeeper使用的直接内存是否已达到ZooKeeper设定的最大直接内存的百分之80？
        -   是，执行[1.h](#zh-cn_topic_0191813895_li49457583153150)。
        -   否，执行[2](#zh-cn_topic_0191813895_li572522141314)。

    8.  <a name="zh-cn_topic_0191813895_li49457583153150"></a>在MRS集群详情页面，单击“组件管理 \> ZooKeeper \> 服务配置 \> 全部配置 \> quorumpeer \> 系统”。

        将GC\_OPTS参数中-XX:MaxDirectMemorySize的值根据实际情况调大。

    9.  观察界面告警是否清除？
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813895_li572522141314)。

2.  <a name="zh-cn_topic_0191813895_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813895_section19176948"></a>

无。

