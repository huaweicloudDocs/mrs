# ALM-24005 Flume传输数据异常<a name="ALM-24005"></a>

## 告警解释<a name="section6563861"></a>

告警模块对Flume Channel的容量状态进行监控，当Channel满的时长超过阈值，或Source向Channel放数据失败的次数超过阈值后，系统即时上报告警。

默认阈值为10，用户可通过配置文件properties.properties修改阈值：修改对应channel的“channelfullcount”参数。

当Flume Channel空间被释放，且告警处理完成时，告警恢复。

## 告警属性<a name="section59074751"></a>

<a name="table45065821"></a>
<table><thead align="left"><tr id="row13802373"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p44250398"><a name="p44250398"></a><a name="p44250398"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p27512447"><a name="p27512447"></a><a name="p27512447"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p13915729"><a name="p13915729"></a><a name="p13915729"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row53432251"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p33045094"><a name="p33045094"></a><a name="p33045094"></a>24005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p59406970"><a name="p59406970"></a><a name="p59406970"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p47235229"><a name="p47235229"></a><a name="p47235229"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section61910715"></a>

<a name="table848378"></a>
<table><thead align="left"><tr id="row32681314"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p29940743"><a name="p29940743"></a><a name="p29940743"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p9281096"><a name="p9281096"></a><a name="p9281096"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row25016533157"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row13571343"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p25536961"><a name="p25536961"></a><a name="p25536961"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55227976"><a name="p55227976"></a><a name="p55227976"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row27289743"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p62985584"><a name="p62985584"></a><a name="p62985584"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1558681"><a name="p1558681"></a><a name="p1558681"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row390817108323"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p122238832019"><a name="p122238832019"></a><a name="p122238832019"></a>AgentId</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5908181018320"><a name="p5908181018320"></a><a name="p5908181018320"></a>产生告警的Agent id。</p>
</td>
</tr>
<tr id="row14028137"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1259352420200"><a name="p1259352420200"></a><a name="p1259352420200"></a>部件类型</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32356376"><a name="p32356376"></a><a name="p32356376"></a>产生告警的元素类型。</p>
</td>
</tr>
<tr id="row22771929"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p29641231152015"><a name="p29641231152015"></a><a name="p29641231152015"></a>部件名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22295840"><a name="p22295840"></a><a name="p22295840"></a>产生告警的元素名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section20325531"></a>

Flume Channel的磁盘空间使用量有继续增长的趋势，将会使数据导入到指定目的地的时间增长，当Flume Channel的磁盘空间使用量达到100%时会导致Flume Agent进程暂停工作。

## 可能原因<a name="section48712055"></a>

-   Flume Sink故障，导致数据无法发送。
-   网络故障，导致数据无法发送。

## 处理步骤<a name="section35755311"></a>

**检查Flume Sink是否故障。**

1.  本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“type = hdfs”关键字确认Flume Sink是否是HDFS类型。
    -   是，执行[2](#li893062611148)。
    -   否，执行[3](#li2804053511148)。

2.  <a name="li893062611148"></a>在FusionInsight Manager的告警列表中查看是否有“HDFS服务不可用”告警产生，服务列表中HDFS是否已停止。
    -   是，如果有告警参考“ALM-14000 HDFS服务不可用”的处理步骤处理该故障；如果HDFS已停止，启动HDFS服务，执行[7](#li5165783111148)。
    -   否，执行[7](#li5165783111148)。

3.  <a name="li2804053511148"></a>本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“type = hbase”关键字确认Flume Sink是否是HBase类型。
    -   是，执行[4](#li5423421711148)。
    -   否，执行[5](#li3655261711148)。

4.  <a name="li5423421711148"></a>在FusionInsight Manager的告警列表中，查看是否有“HBase服务不可用”告警产生，服务列表中HBase是否已停止。
    -   是，如果有告警参考“ALM-19000 HBase服务不可用”的处理步骤处理该故障，如果HBase已停止，启动HBase服务。执行[7](#li5165783111148)。
    -   否，执行[7](#li5165783111148)。

5.  <a name="li3655261711148"></a>本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“org.apache.flume.sink.kafka.KafkaSink”关键字确认Flume Sink是否是Kafka类型。
    -   是，执行[6](#li5047900111148)。
    -   否，执行[9](#li3789323111148)。

6.  <a name="li5047900111148"></a>在FusionInsight Manager的告警列表中，查看是否有“Kafka服务不可用”告警产生，服务列表中Kafka是否已停止。
    -   是，如果有告警参考“ALM-38000 Kafka服务不可用”的处理步骤处理该故障；如果Kafka已停止，启动Kafka服务，执行[7](#li5165783111148)。
    -   否，执行[7](#li5165783111148)。

7.  <a name="li5165783111148"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Flume \> 实例”。
8.  单击进入故障节点的Flume实例页面，查看指标“Sink速度指标”，检查其速度是否为0。
    -   是，执行[13](#li2555818811148)。
    -   否，执行步骤[9](#li3789323111148)。


**检查Flume Sink配置的IP所在节点与故障节点的网络状态。**

1.  <a name="li3789323111148"></a>本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“type = avro”关键字确认Flume Sink是否是avro类型。
    -   是，执行[10](#li3657487511148)。
    -   否，执行[13](#li2555818811148)。

2.  <a name="li3657487511148"></a>以**root**用户登录故障节点所在主机，执行**ping **_Flume Sink__配置的IP__地址_命令查看对端主机是否可以ping通，用户密码为安装前用户自定义，请咨询系统管理员。
    -   是，执行[13](#li2555818811148)。
    -   否，执行[11](#li6073842411148)。

3.  <a name="li6073842411148"></a>联系网络管理员恢复网络。
4.  等待一段时间后，在告警列表中，查看告警是否清除。
    -   是，处理完毕。
    -   否， 执行[13](#li2555818811148)。


**收集故障信息。**

1.  <a name="li2555818811148"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Flume”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无。

