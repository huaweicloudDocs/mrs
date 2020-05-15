# ALM-14002 DataNode磁盘空间使用率超过阈值<a name="ZH-CN_TOPIC_0191883092"></a>

## 告警解释<a name="zh-cn_topic_0191813920_section20869327"></a>

系统每30秒周期性检测DataNode磁盘空间使用率，并把实际磁盘使用率和阈值相比较。DataNode容量百分比指标默认提供一个阈值范围。当检测到DataNode容量百分比指标超出阈值范围时产生该告警。

当DataNode容量百分比指标的值小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813920_section53606218"></a>

<a name="zh-cn_topic_0191813920_table11766267"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813920_row7304143"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813920_p54764719"><a name="zh-cn_topic_0191813920_p54764719"></a><a name="zh-cn_topic_0191813920_p54764719"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813920_p6757235"><a name="zh-cn_topic_0191813920_p6757235"></a><a name="zh-cn_topic_0191813920_p6757235"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813920_p10465156"><a name="zh-cn_topic_0191813920_p10465156"></a><a name="zh-cn_topic_0191813920_p10465156"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813920_row42371273"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813920_p9521066"><a name="zh-cn_topic_0191813920_p9521066"></a><a name="zh-cn_topic_0191813920_p9521066"></a>14002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813920_p33008913"><a name="zh-cn_topic_0191813920_p33008913"></a><a name="zh-cn_topic_0191813920_p33008913"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813920_p56476259"><a name="zh-cn_topic_0191813920_p56476259"></a><a name="zh-cn_topic_0191813920_p56476259"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813920_section12693918"></a>

<a name="zh-cn_topic_0191813920_table11174282"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813920_row15876907"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813920_p10961125"><a name="zh-cn_topic_0191813920_p10961125"></a><a name="zh-cn_topic_0191813920_p10961125"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813920_p15435960"><a name="zh-cn_topic_0191813920_p15435960"></a><a name="zh-cn_topic_0191813920_p15435960"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813920_row42353227"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813920_p8059334"><a name="zh-cn_topic_0191813920_p8059334"></a><a name="zh-cn_topic_0191813920_p8059334"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813920_p48826322"><a name="zh-cn_topic_0191813920_p48826322"></a><a name="zh-cn_topic_0191813920_p48826322"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813920_row36783718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813920_p26691149"><a name="zh-cn_topic_0191813920_p26691149"></a><a name="zh-cn_topic_0191813920_p26691149"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813920_p14499481"><a name="zh-cn_topic_0191813920_p14499481"></a><a name="zh-cn_topic_0191813920_p14499481"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813920_row63386473"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813920_p34030663"><a name="zh-cn_topic_0191813920_p34030663"></a><a name="zh-cn_topic_0191813920_p34030663"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813920_p5020285"><a name="zh-cn_topic_0191813920_p5020285"></a><a name="zh-cn_topic_0191813920_p5020285"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813920_row45182569"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813920_p35909463"><a name="zh-cn_topic_0191813920_p35909463"></a><a name="zh-cn_topic_0191813920_p35909463"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813920_p22985394"><a name="zh-cn_topic_0191813920_p22985394"></a><a name="zh-cn_topic_0191813920_p22985394"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813920_section47136405"></a>

DataNode容量不足，会影响到HDFS的数据写入。

## 可能原因<a name="zh-cn_topic_0191813920_section21574462"></a>

-   集群磁盘容量已满。
-   DataNode节点间数据倾斜。

## 处理步骤<a name="zh-cn_topic_0191813920_section59952436"></a>

1.  检查集群磁盘容量是否已满。
    1.  登录MRS集群详情页面，在“告警管理”页面查看是否存在“ALM-14001 HDFS磁盘空间使用率超过阈值”告警。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请登录MRS Manager页面查看告警信息。  

        -   是，执行[1.b](#zh-cn_topic_0191813920_yt2)。
        -   否，执行[2.a](#zh-cn_topic_0191813920_li64268160)。

    2.  <a name="zh-cn_topic_0191813920_yt2"></a>参考ALM-14001 HDFS磁盘空间使用率超过阈值进行处理，查看对应告警是否清除。
        -   是，执行[1.c](#zh-cn_topic_0191813920_yt3)。
        -   否，执行[3](#zh-cn_topic_0191813920_li572522141314)。

    3.  <a name="zh-cn_topic_0191813920_yt3"></a>等待5分钟后，在“告警管理”页面查看本告警是否清除。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813920_li64268160)。

2.  检查DataNode节点平衡状态。
    1.  <a name="zh-cn_topic_0191813920_li64268160"></a>在集群节点使用客户端，执行**hdfs dfsadmin -report**命令，查看出现告警的DataNode的DFS Used%显示项的值和其他的DataNodes的DFS Used%显示项的值比较。查看是否有差值大于10。
        -   是，执行[2.b](#zh-cn_topic_0191813920_step17)。
        -   否，执行[3](#zh-cn_topic_0191813920_li572522141314)。

    2.  <a name="zh-cn_topic_0191813920_step17"></a>数据倾斜，在集群节点使用客户端，执行**hdfs balancer -threshold 10**。
    3.  等待5分钟，检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813920_li572522141314)。

3.  <a name="zh-cn_topic_0191813920_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813920_section2701015"></a>

无。

