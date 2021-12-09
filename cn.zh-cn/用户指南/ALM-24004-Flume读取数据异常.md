# ALM-24004 Flume读取数据异常<a name="ALM-24004"></a>

## 告警解释<a name="section64226993"></a>

告警模块对Flume Source的状态进行监控，当Source读取不到数据的时长超过阈值时，系统即时上报告警。

默认阈值为0，表示不开启。用户可通过配置文件properties.properties修改阈值：修改对应source的“NoDatatime”参数。

当Source读取到数据，且告警处理完成时，告警恢复。

## 告警属性<a name="section41172029"></a>

<a name="table48972615"></a>
<table><thead align="left"><tr id="row30410955"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p47368280"><a name="p47368280"></a><a name="p47368280"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p11625453"><a name="p11625453"></a><a name="p11625453"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p2137651"><a name="p2137651"></a><a name="p2137651"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row38932049"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p66488304"><a name="p66488304"></a><a name="p66488304"></a>24004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p16843576"><a name="p16843576"></a><a name="p16843576"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p22152400"><a name="p22152400"></a><a name="p22152400"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section35003948"></a>

<a name="table49513952"></a>
<table><thead align="left"><tr id="row17509858"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p9012379"><a name="p9012379"></a><a name="p9012379"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p58914097"><a name="p58914097"></a><a name="p58914097"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row16441185817153"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row7312523"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p55443473"><a name="p55443473"></a><a name="p55443473"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61736365"><a name="p61736365"></a><a name="p61736365"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row18756373"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42871274"><a name="p42871274"></a><a name="p42871274"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p50021192"><a name="p50021192"></a><a name="p50021192"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row910544383116"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p122238832019"><a name="p122238832019"></a><a name="p122238832019"></a>AgentId</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1710634323116"><a name="p1710634323116"></a><a name="p1710634323116"></a>产生告警的Agent id。</p>
</td>
</tr>
<tr id="row47537545"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1259352420200"><a name="p1259352420200"></a><a name="p1259352420200"></a>部件类型</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p38945440"><a name="p38945440"></a><a name="p38945440"></a>产生告警的元素类型。</p>
</td>
</tr>
<tr id="row14964643"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p29641231152015"><a name="p29641231152015"></a><a name="p29641231152015"></a>部件名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2757266"><a name="p2757266"></a><a name="p2757266"></a>产生告警的元素名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section46600077"></a>

如果数据源有数据，Flume Source持续读取不到数据，数据采集会停止。

## 可能原因<a name="section16747515"></a>

-   Flume Source故障，导致数据无法发送。
-   网络故障，导致数据无法发送。

## 处理步骤<a name="section16509910"></a>

**检查Flume Source是否故障。**

1.  本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“type = spooldir”关键字确认Flume Source是否是spooldir类型。
    -   是，执行[2](#li3561010711655)。
    -   否，执行[3](#li3862672011655)。

2.  <a name="li3561010711655"></a>查看设置的spoolDir监控目录，是否所有的文件均已传输完毕。
    -   是，处理完毕。
    -   否，执行[5](#li2692021011655)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >spooDir的监控目录为用户自定义配置文件properties.properties中.spoolDir的参数值。若监控目录文件已传输完毕，则该监控目录下的所有文件文件以.COMPLETED后缀结尾。


3.  <a name="li3862672011655"></a>本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“org.apache.flume.source.kafka.KafkaSource”关键字确认Flume Source是否是Kafka类型。
    -   是，执行[4](#li4027383611655)。
    -   否，执行[7](#li5944850711655)。

4.  <a name="li4027383611655"></a>查看Kafka Source配置的topic数据是否已经消费完毕。
    -   是，处理完毕。
    -   否，执行[5](#li2692021011655)。

5.  <a name="li2692021011655"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Flume \> 实例”。
6.  单击进入故障节点的Flume实例页面，查看监控指标“Source速度指标”，检查告警中的Source速度是否为0。
    -   是，执行[11](#li1313046711655)。
    -   否，执行步骤[7](#li5944850711655)。


**检查Flume Source配置的IP所在节点与故障节点的网络状态。**

1.  <a name="li5944850711655"></a>本地打开用户自定义配置文件properties.properties，搜索配置文件中是否有“type = avro”关键字确认Flume Source是否是avro类型。
    -   是，执行[8](#li6550564111655)。
    -   否，执行[11](#li1313046711655)。

2.  <a name="li6550564111655"></a>以**root**用户登录故障节点所在主机，执行**ping **_Flume Source__配置的IP__地址_命令查看对端主机是否可以ping通，用户密码为安装前用户自定义，请咨询系统管理员。
    -   是，执行[11](#li1313046711655)。
    -   否，执行[9](#li5267986211655)。

3.  <a name="li5267986211655"></a>联系网络管理员恢复网络。
4.  等待一段时间后，在告警列表中，查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[11](#li1313046711655)。


**收集故障信息**。

1.  <a name="li1313046711655"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Flume”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section14371463"></a>

无。

