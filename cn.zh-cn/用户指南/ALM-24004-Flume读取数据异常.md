# ALM-24004 Flume读取数据异常<a name="alm_24004"></a>

## 告警解释<a name="zh-cn_topic_0191813945_section19665522175625"></a>

告警模块对Flume Source的状态进行监控，当Source读取不到数据的时长超过阈值时，系统发送告警。

用户可通过配置修改阈值。

当Source读取到数据，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813945_section42254989175625"></a>

<a name="zh-cn_topic_0191813945_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813945_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813945_p34183898175625"><a name="zh-cn_topic_0191813945_p34183898175625"></a><a name="zh-cn_topic_0191813945_p34183898175625"></a><strong id="zh-cn_topic_0191813945_b39219631175625"><a name="zh-cn_topic_0191813945_b39219631175625"></a><a name="zh-cn_topic_0191813945_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813945_p22673543175625"><a name="zh-cn_topic_0191813945_p22673543175625"></a><a name="zh-cn_topic_0191813945_p22673543175625"></a><strong id="zh-cn_topic_0191813945_b2735300175625"><a name="zh-cn_topic_0191813945_b2735300175625"></a><a name="zh-cn_topic_0191813945_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813945_p20232782175625"><a name="zh-cn_topic_0191813945_p20232782175625"></a><a name="zh-cn_topic_0191813945_p20232782175625"></a><strong id="zh-cn_topic_0191813945_b47877317175625"><a name="zh-cn_topic_0191813945_b47877317175625"></a><a name="zh-cn_topic_0191813945_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813945_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813945_p9444863162919"><a name="zh-cn_topic_0191813945_p9444863162919"></a><a name="zh-cn_topic_0191813945_p9444863162919"></a>24004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813945_p26836421162919"><a name="zh-cn_topic_0191813945_p26836421162919"></a><a name="zh-cn_topic_0191813945_p26836421162919"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813945_p26266529162919"><a name="zh-cn_topic_0191813945_p26266529162919"></a><a name="zh-cn_topic_0191813945_p26266529162919"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813945_section27218191175625"></a>

<a name="zh-cn_topic_0191813945_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813945_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813945_p9726186175625"><a name="zh-cn_topic_0191813945_p9726186175625"></a><a name="zh-cn_topic_0191813945_p9726186175625"></a><strong id="zh-cn_topic_0191813945_b20426813175625"><a name="zh-cn_topic_0191813945_b20426813175625"></a><a name="zh-cn_topic_0191813945_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813945_p43959148175625"><a name="zh-cn_topic_0191813945_p43959148175625"></a><a name="zh-cn_topic_0191813945_p43959148175625"></a><strong id="zh-cn_topic_0191813945_b60088019175625"><a name="zh-cn_topic_0191813945_b60088019175625"></a><a name="zh-cn_topic_0191813945_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813945_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813945_p15769878162931"><a name="zh-cn_topic_0191813945_p15769878162931"></a><a name="zh-cn_topic_0191813945_p15769878162931"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813945_p2291730162931"><a name="zh-cn_topic_0191813945_p2291730162931"></a><a name="zh-cn_topic_0191813945_p2291730162931"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813945_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813945_p60058435162931"><a name="zh-cn_topic_0191813945_p60058435162931"></a><a name="zh-cn_topic_0191813945_p60058435162931"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813945_p32895061162931"><a name="zh-cn_topic_0191813945_p32895061162931"></a><a name="zh-cn_topic_0191813945_p32895061162931"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813945_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813945_p22635261162931"><a name="zh-cn_topic_0191813945_p22635261162931"></a><a name="zh-cn_topic_0191813945_p22635261162931"></a>ComponentType</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813945_p21516863162931"><a name="zh-cn_topic_0191813945_p21516863162931"></a><a name="zh-cn_topic_0191813945_p21516863162931"></a>产生告警的元素类型。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813945_row30712252162928"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813945_p49428385162931"><a name="zh-cn_topic_0191813945_p49428385162931"></a><a name="zh-cn_topic_0191813945_p49428385162931"></a>ComponentName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813945_p44276286162931"><a name="zh-cn_topic_0191813945_p44276286162931"></a><a name="zh-cn_topic_0191813945_p44276286162931"></a>产生告警的元素名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813945_section23922301175625"></a>

如果数据源有数据，Flume Source持续读取不到数据，数据采集会停止。

## 可能原因<a name="zh-cn_topic_0191813945_section58162349175625"></a>

-   Flume Source故障，导致数据无法发送。
-   网络故障，导致数据无法发送。

## 处理步骤<a name="zh-cn_topic_0191813945_section51182191175625"></a>

1.  检查Flume Source是否故障。
    1.  确认Flume Source是否是spooldir类型。
        -   是，执行[1.b](#zh-cn_topic_0191813945_li57424576173633)。
        -   否，执行[1.c](#zh-cn_topic_0191813945_li27889489173633)。

    2.  <a name="zh-cn_topic_0191813945_li57424576173633"></a>查看设置的spoolDir目录，是否所有的文件均已传输完毕。
        -   是，处理完毕。
        -   否，执行[1.e](#zh-cn_topic_0191813945_li1487713813414)。

    3.  <a name="zh-cn_topic_0191813945_li27889489173633"></a>确认Flume Source是否是Kafka类型。
        -   是，执行[1.d](#zh-cn_topic_0191813945_li35944619173633)。
        -   否，执行[1.e](#zh-cn_topic_0191813945_li1487713813414)。

    4.  <a name="zh-cn_topic_0191813945_li35944619173633"></a>使用Kafka客户端，执行以下命令查看Kafka Source配置的topic数据是否已经消费完毕。

        **cd /opt/client/Kafka/kafka/bin**

        **./kafka-consumer-groups.sh --bootstrap-server** _Kafka集群IP_**:21007** **--new-consumer --describe --group example-group1 --command-config**

        **../config/consumer.properties**

        -   是，处理完毕。
        -   否，执行[1.e](#zh-cn_topic_0191813945_li1487713813414)。

    5.  <a name="zh-cn_topic_0191813945_li1487713813414"></a>登录MRS集群详情页面，选择“组件管理”。
    6.  单击“Flume  \>  实例“。
    7.  单击进入故障节点的Flume实例页面，查看监控指标“Source速度指标”，检查告警中的Source速度是否为0。
        -   是，执行[2.a](#zh-cn_topic_0191813945_li39514043173729)。
        -   否，处理完毕。

2.  检查Flume Source配置的IP所在节点与故障节点的网络状态。
    1.  <a name="zh-cn_topic_0191813945_li39514043173729"></a>确认Flume Source是否是avro类型。
        -   是，执行[2.c](#zh-cn_topic_0191813945_li52369777173729)。
        -   否，执行[3](#zh-cn_topic_0191813945_li572522141314)。

    2.  登录故障节点所在主机，执行以下命令切换root用户。

        **sudo su - root**

    3.  <a name="zh-cn_topic_0191813945_li52369777173729"></a>执行**ping** _Flume Source配置的IP地址_命令查看对端主机是否可以ping通。
        -   是，执行[3](#zh-cn_topic_0191813945_li572522141314)。
        -   否，执行[2.d](#zh-cn_topic_0191813945_li27478632173729)。

    4.  <a name="zh-cn_topic_0191813945_li27478632173729"></a>联系网络管理员恢复网络。
    5.  等待一段时间后，在告警列表中，查看告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813945_li572522141314)。

3.  <a name="zh-cn_topic_0191813945_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813945_section20269844175625"></a>

无。

