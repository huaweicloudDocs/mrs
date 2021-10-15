# ALM-14008 HDFS DataNode内存使用率超过阈值<a name="alm_14008"></a>

## 告警解释<a name="zh-cn_topic_0191813907_section27139175"></a>

系统每30秒周期性检测HDFS DataNode内存使用率，并把实际的HDFS DataNode内存使用率和阈值相比较。HDFS DataNode内存使用率指标默认提供一个阈值范围。当HDFS DataNode内存使用率超出阈值范围时，产生该告警。

当HDFS DataNode内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813907_section42925989"></a>

<a name="zh-cn_topic_0191813907_table54967495"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813907_row29231803"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813907_p18965813"><a name="zh-cn_topic_0191813907_p18965813"></a><a name="zh-cn_topic_0191813907_p18965813"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813907_p59835867"><a name="zh-cn_topic_0191813907_p59835867"></a><a name="zh-cn_topic_0191813907_p59835867"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813907_p14867095"><a name="zh-cn_topic_0191813907_p14867095"></a><a name="zh-cn_topic_0191813907_p14867095"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813907_row63384014"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813907_p33831530"><a name="zh-cn_topic_0191813907_p33831530"></a><a name="zh-cn_topic_0191813907_p33831530"></a>14007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813907_p55999443"><a name="zh-cn_topic_0191813907_p55999443"></a><a name="zh-cn_topic_0191813907_p55999443"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813907_p39661040"><a name="zh-cn_topic_0191813907_p39661040"></a><a name="zh-cn_topic_0191813907_p39661040"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813907_section50789581"></a>

<a name="zh-cn_topic_0191813907_table58427690"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813907_row29990828"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813907_p13338021"><a name="zh-cn_topic_0191813907_p13338021"></a><a name="zh-cn_topic_0191813907_p13338021"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813907_p6637886"><a name="zh-cn_topic_0191813907_p6637886"></a><a name="zh-cn_topic_0191813907_p6637886"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813907_row797855"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813907_p64626289"><a name="zh-cn_topic_0191813907_p64626289"></a><a name="zh-cn_topic_0191813907_p64626289"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813907_p238043"><a name="zh-cn_topic_0191813907_p238043"></a><a name="zh-cn_topic_0191813907_p238043"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813907_row2142393"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813907_p39316155"><a name="zh-cn_topic_0191813907_p39316155"></a><a name="zh-cn_topic_0191813907_p39316155"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813907_p30492010"><a name="zh-cn_topic_0191813907_p30492010"></a><a name="zh-cn_topic_0191813907_p30492010"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813907_row5992637"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813907_p15641626"><a name="zh-cn_topic_0191813907_p15641626"></a><a name="zh-cn_topic_0191813907_p15641626"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813907_p59012183"><a name="zh-cn_topic_0191813907_p59012183"></a><a name="zh-cn_topic_0191813907_p59012183"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813907_row61347601"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813907_p3099778"><a name="zh-cn_topic_0191813907_p3099778"></a><a name="zh-cn_topic_0191813907_p3099778"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813907_p49755431"><a name="zh-cn_topic_0191813907_p49755431"></a><a name="zh-cn_topic_0191813907_p49755431"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813907_section54453050"></a>

HDFS DataNode内存使用率过高，会影响到HDFS的数据读写性能。

## 可能原因<a name="zh-cn_topic_0191813907_section20315403"></a>

HDFS DataNode配置的内存不足。

## 处理步骤<a name="zh-cn_topic_0191813907_section48620907"></a>

1.  清除无用文件。
    1.  在集群节点使用客户端，执行**hdfs dfs -rm -r** _文件或目录路径_命令，确认删除无用的文件。
    2.  等待5分钟后，检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813907_li572522141314)。

2.  <a name="zh-cn_topic_0191813907_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813907_section34934986"></a>

无。

