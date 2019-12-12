# ALM-14007 HDFS NameNode内存使用率超过阈值<a name="ZH-CN_TOPIC_0191883096"></a>

## 告警解释<a name="zh-cn_topic_0191813906_section439002"></a>

系统每30秒周期性检测HDFS NameNode内存使用率，并把实际的HDFS NameNode内存使用率和阈值相比较。HDFS NameNode内存使用率指标默认提供一个阈值范围。当HDFS NameNode内存使用率超出阈值范围时，产生该告警。

当HDFS NameNode内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813906_section3951024"></a>

<a name="zh-cn_topic_0191813906_table40578897"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813906_row57539933"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813906_p30222983"><a name="zh-cn_topic_0191813906_p30222983"></a><a name="zh-cn_topic_0191813906_p30222983"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813906_p32142578"><a name="zh-cn_topic_0191813906_p32142578"></a><a name="zh-cn_topic_0191813906_p32142578"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813906_p53412038"><a name="zh-cn_topic_0191813906_p53412038"></a><a name="zh-cn_topic_0191813906_p53412038"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813906_row31407785"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813906_p61002694"><a name="zh-cn_topic_0191813906_p61002694"></a><a name="zh-cn_topic_0191813906_p61002694"></a>14007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813906_p42271171"><a name="zh-cn_topic_0191813906_p42271171"></a><a name="zh-cn_topic_0191813906_p42271171"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813906_p1412808"><a name="zh-cn_topic_0191813906_p1412808"></a><a name="zh-cn_topic_0191813906_p1412808"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813906_section35559222"></a>

<a name="zh-cn_topic_0191813906_table47328638"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813906_row27247099"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813906_p59531373"><a name="zh-cn_topic_0191813906_p59531373"></a><a name="zh-cn_topic_0191813906_p59531373"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813906_p57311924"><a name="zh-cn_topic_0191813906_p57311924"></a><a name="zh-cn_topic_0191813906_p57311924"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813906_row11754296"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813906_p12573920"><a name="zh-cn_topic_0191813906_p12573920"></a><a name="zh-cn_topic_0191813906_p12573920"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813906_p11854613"><a name="zh-cn_topic_0191813906_p11854613"></a><a name="zh-cn_topic_0191813906_p11854613"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813906_row39582655"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813906_p52078514"><a name="zh-cn_topic_0191813906_p52078514"></a><a name="zh-cn_topic_0191813906_p52078514"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813906_p57610085"><a name="zh-cn_topic_0191813906_p57610085"></a><a name="zh-cn_topic_0191813906_p57610085"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813906_row48728718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813906_p54712068"><a name="zh-cn_topic_0191813906_p54712068"></a><a name="zh-cn_topic_0191813906_p54712068"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813906_p2492560"><a name="zh-cn_topic_0191813906_p2492560"></a><a name="zh-cn_topic_0191813906_p2492560"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813906_row22433040"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813906_p5136981"><a name="zh-cn_topic_0191813906_p5136981"></a><a name="zh-cn_topic_0191813906_p5136981"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813906_p13442339"><a name="zh-cn_topic_0191813906_p13442339"></a><a name="zh-cn_topic_0191813906_p13442339"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813906_section51597550"></a>

HDFS NameNode内存使用率过高，会影响HDFS的数据读写性能。

## 可能原因<a name="zh-cn_topic_0191813906_section61724767"></a>

HDFS NameNode配置的内存不足。

## 处理步骤<a name="zh-cn_topic_0191813906_section18651996"></a>

1.  清除无用文件。
    1.  在集群节点使用客户端，执行**hdfs dfs -rm -r** _文件或目录路径_命令，确认删除无用的文件。
    2.  等待5分钟后，检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813906_li572522141314)。

2.  <a name="zh-cn_topic_0191813906_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813906_section33650236"></a>

无。

