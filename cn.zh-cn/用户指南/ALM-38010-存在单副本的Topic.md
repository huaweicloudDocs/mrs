# ALM-38010 存在单副本的Topic<a name="ALM-38010"></a>

## 告警解释<a name="section20231696"></a>

系统在Kafka的Controller所在节点上，每60秒周期性检测各个Topic的副本数，当检测到某个Topic的副本数为1时，产生该告警。

## 告警属性<a name="section47867540"></a>

<a name="table9347550"></a>
<table><thead align="left"><tr id="row4979446"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p681951"><a name="p681951"></a><a name="p681951"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p55238032"><a name="p55238032"></a><a name="p55238032"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p45095602"><a name="p45095602"></a><a name="p45095602"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row28865132"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56374375"><a name="p56374375"></a><a name="p56374375"></a>38010</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p2921675"><a name="p2921675"></a><a name="p2921675"></a>提示</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p35329086"><a name="p35329086"></a><a name="p35329086"></a>否</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section28154684"></a>

<a name="table43083755"></a>
<table><thead align="left"><tr id="row22744955"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p30402032"><a name="p30402032"></a><a name="p30402032"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p46645505"><a name="p46645505"></a><a name="p46645505"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row151892072"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row821712276310"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p115791925734"><a name="p115791925734"></a><a name="p115791925734"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row9216102720315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主题名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13579142518310"><a name="p13579142518310"></a><a name="p13579142518310"></a>产生告警的Topic名称列表。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section52065568"></a>

单副本的Topic存在单点故障风险，当副本所在节点异常时，会直接导致Partition没有leader，影响该Topic上的业务。

## 可能原因<a name="section65936928"></a>

Topic副本数配置不合理。

## 处理步骤<a name="section18196102918247"></a>

**检查Topic副本数配置。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击此告警所在行的![](figures/zh-cn_image_0263895881.png)，查看定位信息中上报告警的“主题名”列表。
2.  确认发生告警Topic是否需要增加副本。
    -   是，执行[3](#li10597143618506)。
    -   否，执行[5](#li18741632013)。

3.  <a name="li10597143618506"></a>在FusionInsight客户端，对相关Topic的副本进行重新规划，在**add-replicas-reassignment.json**文件中描述该Topic的Partition分布信息，其中json文件中的内容格式为：\{"partitions":\[\{"topic": "_topicName_","partition": 1,"replicas": \[1,2\] \}\],"version":1\}，并执行如下命令增加副本：

    **kafka-reassign-partitions.sh --zookeeper **_\{zk\_host\}:\{port\}_**/kafka** **--reassignment-json-file_ _**_\{manual assignment json file path\}_ **--execute**

    例如：

    **/opt/Bigdata/client/Kafka/kafka/bin/kafka-reassign-partitions.sh --zookeeper 192.168.0.90:2181,192.168.0.91:2181,192.168.0.92:2181/kafka --reassignment-json-file add-replicas-reassignment.json --execute**

4.  执行如下命令进行确认任务执行进度：

    **kafka-reassign-partitions.sh --zookeeper **_\{zk\_host\}:\{port\}_**/kafka** **--reassignment-json-file_ _**_\{manual assignment json file path\}_ **--verify**

    例如：

    **/opt/Bigdata/client/Kafka/kafka/bin/kafka-reassign-partitions.sh --zookeeper 192.168.0.90:2181,192.168.0.91:2181,192.168.0.92:2181/kafka --reassignment-json-file add-replicas-reassignment.json --verify**

5.  <a name="li18741632013"></a>确认处理完成或者告警无影响后，可在FusionInsight Manager页面，手动清除该告警。
6.  观察一段时间，检查告警是否清除或者告警无影响后，可在FusionInsight Manager页面，手动清除该告警。
    -   是，操作结束。
    -   否，执行[7](#li1473912318017)。


**收集故障信息。**

1.  <a name="li1473912318017"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Kafka”。
3.  单击右上角的![](figures/zh-cn_image_0000001122008439.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section19548318471"></a>

确认告警已无影响，可手工清除告警。

## 参考信息<a name="section39290981"></a>

无。

