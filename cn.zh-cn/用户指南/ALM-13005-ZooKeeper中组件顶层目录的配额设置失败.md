# ALM-13005 ZooKeeper中组件顶层目录的配额设置失败<a name="ALM-13005"></a>

## 告警解释<a name="section12083490"></a>

系统每5小时周期性为组件和“customized.quota”配置项中的每个ZooKeeper顶层目录设置配额，当设置某个目录的配额失败时，会产生该告警。

当设置失败的目录重新设置配额成功时，告警恢复。

## 告警属性<a name="section41642549"></a>

<a name="table1578615"></a>
<table><thead align="left"><tr id="row12934337"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41048411"><a name="p41048411"></a><a name="p41048411"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p36587022"><a name="p36587022"></a><a name="p36587022"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p10758785"><a name="p10758785"></a><a name="p10758785"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row66155228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56973256"><a name="p56973256"></a><a name="p56973256"></a>13005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p51431020"><a name="p51431020"></a><a name="p51431020"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5163121"><a name="p5163121"></a><a name="p5163121"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section39238623"></a>

<a name="table15559679"></a>
<table><thead align="left"><tr id="row63147375"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p14663741"><a name="p14663741"></a><a name="p14663741"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p46912376"><a name="p46912376"></a><a name="p46912376"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row970511873313"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p77584302119"><a name="p77584302119"></a><a name="p77584302119"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row41806087"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p15811907"><a name="p15811907"></a><a name="p15811907"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row8089436"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51264574"><a name="p51264574"></a><a name="p51264574"></a>服务目录</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58789816"><a name="p58789816"></a><a name="p58789816"></a>产生告警的目录名称。</p>
</td>
</tr>
<tr id="row58321318"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p26406311"><a name="p26406311"></a><a name="p26406311"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p58536412"><a name="p58536412"></a><a name="p58536412"></a>产生告警的具体原因。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section17603289"></a>

组件可以向对应的ZooKeeper顶层目录中写入大量数据，导致Zookeeper服务不可用。

## 可能原因<a name="section24211876"></a>

告警目录对应的配额值不合理。

## 处理步骤<a name="section322125891210"></a>

**检查告警目录对应的配额值是否合理。**

1.  在FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 配置 \> 全部配置 \> 配额”。查看“customized.quota”配置项中，是否有产生该告警的告警目录及对应的配额值。
    -   是，执行[5](#li45018069174323)。
    -   否，执行[2](#li8446514299)。

2.  <a name="li8446514299"></a>查看下表中的组件告警目录列中，是否有产生该告警的告警目录。

    **表 1**  各组件告警目录

    <a name="table1261919586239"></a>
    <table><thead align="left"><tr id="row16620185819234"><th class="cellrowborder" valign="top" width="42.76%" id="mcps1.2.3.1.1"><p id="p2052025614720"><a name="p2052025614720"></a><a name="p2052025614720"></a>组件名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="57.24%" id="mcps1.2.3.1.2"><p id="p4620145822319"><a name="p4620145822319"></a><a name="p4620145822319"></a>组件告警目录</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row262065822317"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p1352019561173"><a name="p1352019561173"></a><a name="p1352019561173"></a>Hbase</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p36202583234"><a name="p36202583234"></a><a name="p36202583234"></a>/hbase</p>
    </td>
    </tr>
    <tr id="row11620175814237"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p1452025617717"><a name="p1452025617717"></a><a name="p1452025617717"></a>Hive</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p66202585231"><a name="p66202585231"></a><a name="p66202585231"></a>/beelinesql</p>
    </td>
    </tr>
    <tr id="row126201258112316"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p115201256679"><a name="p115201256679"></a><a name="p115201256679"></a>Yarn</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p146209589236"><a name="p146209589236"></a><a name="p146209589236"></a>/rmstore</p>
    </td>
    </tr>
    <tr id="row2062075892318"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p2520156571"><a name="p2520156571"></a><a name="p2520156571"></a>Storm</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p16200587233"><a name="p16200587233"></a><a name="p16200587233"></a>/stormroot</p>
    </td>
    </tr>
    <tr id="row9620758112319"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p65205563716"><a name="p65205563716"></a><a name="p65205563716"></a>Streaming</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p8620175822313"><a name="p8620175822313"></a><a name="p8620175822313"></a>/storm</p>
    </td>
    </tr>
    <tr id="row10620135892314"><td class="cellrowborder" valign="top" width="42.76%" headers="mcps1.2.3.1.1 "><p id="p175204566716"><a name="p175204566716"></a><a name="p175204566716"></a>Kafka</p>
    </td>
    <td class="cellrowborder" valign="top" width="57.24%" headers="mcps1.2.3.1.2 "><p id="p146201358202310"><a name="p146201358202310"></a><a name="p146201358202310"></a>/kafka</p>
    </td>
    </tr>
    </tbody>
    </table>

    -   是，执行[3](#li1454514461317)。
    -   否，执行[7](#li64364171174323)。

3.  <a name="li1454514461317"></a>查看该表中告警目录对应的组件名称，并打开其相应的服务界面，选择“配置 \> 全部配置”，右上角搜索框输入“zk.quota”，搜索结果就是该告警目录对应的配额值。
4.  检查产生告警的目录对应的配额值是否不合理。合理的配额值应该大于等于目录当前的实际使用值，该值可以在告警参数“Trigger Condition”中获取。
5.  <a name="li45018069174323"></a>根据告警信息的提示，修改不合理的配额值，并保存配置。
6.  等待配置项“service.quotas.auto.check.cron.expression”中指定的定时时长后，查看告警是否消失。
    -   是，处理完毕。
    -   否，执行[7](#li64364171174323)。


**收集故障信息。**

1.  <a name="li64364171174323"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895653.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section15004954"></a>

无。

