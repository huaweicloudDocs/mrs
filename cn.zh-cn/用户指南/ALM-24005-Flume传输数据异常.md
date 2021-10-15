# ALM-24005 Flume传输数据异常<a name="alm_24005"></a>

## 告警解释<a name="zh-cn_topic_0191813885_section19665522175625"></a>

告警模块对Flume Channel的容量状态进行监控，当Channel满的时长超过阈值，或Source向Channel放数据失败的次数超过阈值后，系统发送告警。

用户可通过配置修改阈值：修改对应channel的“channelfullcount”参数。

当Flume Channel空间被释放，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813885_section42254989175625"></a>

<a name="zh-cn_topic_0191813885_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813885_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813885_p34183898175625"><a name="zh-cn_topic_0191813885_p34183898175625"></a><a name="zh-cn_topic_0191813885_p34183898175625"></a><strong id="zh-cn_topic_0191813885_b39219631175625"><a name="zh-cn_topic_0191813885_b39219631175625"></a><a name="zh-cn_topic_0191813885_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813885_p22673543175625"><a name="zh-cn_topic_0191813885_p22673543175625"></a><a name="zh-cn_topic_0191813885_p22673543175625"></a><strong id="zh-cn_topic_0191813885_b2735300175625"><a name="zh-cn_topic_0191813885_b2735300175625"></a><a name="zh-cn_topic_0191813885_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813885_p20232782175625"><a name="zh-cn_topic_0191813885_p20232782175625"></a><a name="zh-cn_topic_0191813885_p20232782175625"></a><strong id="zh-cn_topic_0191813885_b47877317175625"><a name="zh-cn_topic_0191813885_b47877317175625"></a><a name="zh-cn_topic_0191813885_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813885_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813885_p63628609163045"><a name="zh-cn_topic_0191813885_p63628609163045"></a><a name="zh-cn_topic_0191813885_p63628609163045"></a>24005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813885_p53643687163045"><a name="zh-cn_topic_0191813885_p53643687163045"></a><a name="zh-cn_topic_0191813885_p53643687163045"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813885_p50171427163045"><a name="zh-cn_topic_0191813885_p50171427163045"></a><a name="zh-cn_topic_0191813885_p50171427163045"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813885_section27218191175625"></a>

<a name="zh-cn_topic_0191813885_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813885_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813885_p9726186175625"><a name="zh-cn_topic_0191813885_p9726186175625"></a><a name="zh-cn_topic_0191813885_p9726186175625"></a><strong id="zh-cn_topic_0191813885_b20426813175625"><a name="zh-cn_topic_0191813885_b20426813175625"></a><a name="zh-cn_topic_0191813885_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813885_p43959148175625"><a name="zh-cn_topic_0191813885_p43959148175625"></a><a name="zh-cn_topic_0191813885_p43959148175625"></a><strong id="zh-cn_topic_0191813885_b60088019175625"><a name="zh-cn_topic_0191813885_b60088019175625"></a><a name="zh-cn_topic_0191813885_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813885_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813885_p32188096163058"><a name="zh-cn_topic_0191813885_p32188096163058"></a><a name="zh-cn_topic_0191813885_p32188096163058"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813885_p57098960163058"><a name="zh-cn_topic_0191813885_p57098960163058"></a><a name="zh-cn_topic_0191813885_p57098960163058"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813885_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813885_p17646605163058"><a name="zh-cn_topic_0191813885_p17646605163058"></a><a name="zh-cn_topic_0191813885_p17646605163058"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813885_p20088914163058"><a name="zh-cn_topic_0191813885_p20088914163058"></a><a name="zh-cn_topic_0191813885_p20088914163058"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813885_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813885_p15086183163058"><a name="zh-cn_topic_0191813885_p15086183163058"></a><a name="zh-cn_topic_0191813885_p15086183163058"></a>ComponentType</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813885_p14021290163058"><a name="zh-cn_topic_0191813885_p14021290163058"></a><a name="zh-cn_topic_0191813885_p14021290163058"></a>产生告警的元素类型。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813885_row60420241163054"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813885_p20973185163058"><a name="zh-cn_topic_0191813885_p20973185163058"></a><a name="zh-cn_topic_0191813885_p20973185163058"></a>ComponentName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813885_p21106461163058"><a name="zh-cn_topic_0191813885_p21106461163058"></a><a name="zh-cn_topic_0191813885_p21106461163058"></a>产生告警的元素名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813885_section23922301175625"></a>

Flume Channel的磁盘空间使用量有继续增长的趋势，将会使数据导入到指定目的地的时间增长，当Flume Channel的磁盘空间使用量达到100%时会导致Flume Agent进程暂停工作。

## 可能原因<a name="zh-cn_topic_0191813885_section58162349175625"></a>

-   Flume Sink故障，导致数据无法发送。
-   网络故障，导致数据无法发送。

## 处理步骤<a name="zh-cn_topic_0191813885_section51182191175625"></a>

1.  检查Flume Sink是否故障。
    1.  确认Flume Sink是否是HDFS类型。
        -   是，执行[1.b](#zh-cn_topic_0191813885_li35603802172029)。
        -   否，执行[1.c](#zh-cn_topic_0191813885_li17206137172029)。

    2.  <a name="zh-cn_topic_0191813885_li35603802172029"></a>在MRS的告警列表中查看是否有“ALM-14000 HDFS服务不可用”告警产生，服务列表中HDFS服务是否已停止。
        -   是，如果有告警参考“ALM-14000 HDFS服务不可用”的处理步骤处理该故障；如果HDFS服务已停止，启动HDFS服务，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。
        -   否，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。

    3.  <a name="zh-cn_topic_0191813885_li17206137172029"></a>确认Flume Sink是否是HBase类型。
        -   是，执行[1.d](#zh-cn_topic_0191813885_li23959037172029)。
        -   否，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。

    4.  <a name="zh-cn_topic_0191813885_li23959037172029"></a>在MRS的告警列表中，查看是否有“ALM-19000 HBase服务不可用”告警产生，服务列表中HBase服务是否已停止。
        -   是，如果有告警参考“ALM-19000 HBase服务不可用”的处理步骤处理该故障，如果HBase服务已停止，启动HBase服务。执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。
        -   否，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。

    5.  确认Flume Sink是否是Kafka类型。
        -   是，执行[1.f](#zh-cn_topic_0191813885_li13075641172029)。
        -   否，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。

    6.  <a name="zh-cn_topic_0191813885_li13075641172029"></a>在MRS的告警列表中，查看是否有“ALM-38000 Kafka服务不可用”告警产生，服务列表中Kafka服务是否已停止。
        -   是，如果有告警参考“ALM-38000 Kafka服务不可用”的处理步骤处理该故障；如果Kafka服务已停止，启动Kafka服务，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。
        -   否，执行[1.g](#zh-cn_topic_0191813885_li1487713813414)。

    7.  <a name="zh-cn_topic_0191813885_li1487713813414"></a>登录MRS集群详情页面，选择“组件管理”。
    8.  单击“Flume  \>  实例“。
    9.  单击进入故障节点的Flume实例页面，查看指标“Sink速度指标”，检查其速度是否为0。
        -   是，执行[2.a](#zh-cn_topic_0191813885_li60707704172341)。
        -   否，处理完毕。

2.  检查Flume Sink配置的IP所在节点与故障节点的网络状态。
    1.  <a name="zh-cn_topic_0191813885_li60707704172341"></a>确认Flume Sink是否是avro类型。
        -   是，执行[2.c](#zh-cn_topic_0191813885_li31163561172341)。
        -   否，执行[3](#zh-cn_topic_0191813885_li572522141314)。

    2.  登录故障节点所在主机，执行以下命令切换root用户。

        **sudo su - root**

    3.  <a name="zh-cn_topic_0191813885_li31163561172341"></a>执行**ping** _Flume Sink配置的IP地址_命令查看对端主机是否可以ping通。
        -   是，执行[3](#zh-cn_topic_0191813885_li572522141314)。
        -   否，执行[2.d](#zh-cn_topic_0191813885_li35581265172341)。

    4.  <a name="zh-cn_topic_0191813885_li35581265172341"></a>联系网络管理员恢复网络。
    5.  等待一段时间后，在告警列表中，查看告警是否清除。
        -   是，处理完毕。
        -   否， 执行[3](#zh-cn_topic_0191813885_li572522141314)。

3.  <a name="zh-cn_topic_0191813885_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813885_section20269844175625"></a>

无。

