# ALM-18016 ResourceManager非堆内存使用率超过阈值<a name="ALM-18016"></a>

## 告警解释<a name="section37519834"></a>

系统每30秒周期性检测Yarn ResourceManager非堆内存使用率，并把实际的Yarn ResourceManager非堆内存使用率和阈值相比较。当Yarn ResourceManager非堆内存使用率超出阈值（默认为最大非堆内存的90%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Yarn”修改阈值。

当Yarn ResourceManager非堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section2134188"></a>

<a name="table62675811"></a>
<table><thead align="left"><tr id="row17694464"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p23965442"><a name="p23965442"></a><a name="p23965442"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62152665"><a name="p62152665"></a><a name="p62152665"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p1201133"><a name="p1201133"></a><a name="p1201133"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row30182949"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p28899818"><a name="p28899818"></a><a name="p28899818"></a>18016</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p59183907"><a name="p59183907"></a><a name="p59183907"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p29167161"><a name="p29167161"></a><a name="p29167161"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section19207700"></a>

<a name="table13729811"></a>
<table><thead align="left"><tr id="row56549341"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p17093938"><a name="p17093938"></a><a name="p17093938"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p42431760"><a name="p42431760"></a><a name="p42431760"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row197111614191918"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row14420510"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56577259"><a name="p56577259"></a><a name="p56577259"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row39433286"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17122224"><a name="p17122224"></a><a name="p17122224"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row19882291"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55189229"><a name="p55189229"></a><a name="p55189229"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row26941016"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p34738713"><a name="p34738713"></a><a name="p34738713"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62372407"><a name="p62372407"></a><a name="p62372407"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section38651578"></a>

Yarn ResourceManager非堆内存使用率过高，会影响Yarn任务提交和运行的性能，甚至造成内存溢出导致Yarn服务不可用。

## 可能原因<a name="section12319887"></a>

该节点Yarn ResourceManager实例非堆内存使用量过大，或分配的非堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section43770124"></a>

**检查非堆内存使用量。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警 \> ALM-18016 Yarn ResourceManager非堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> ResourceManager（对应上报告警实例主机名）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“ResourceManager内存使用率”。查看非堆内存使用情况。

    **图 1**  定制ResourceManager内存使用率<a name="fig67465141016"></a>  
    ![](figures/定制ResourceManager内存使用率-87.png "定制ResourceManager内存使用率-87")

3.  查看ResourceManager使用的非堆内存是否已达到ResourceManager设定的最大非堆内存的90%。
    -   是，执行[4](#li4804656085044)。
    -   否，执行[6](#li3192337385044)。

4.  <a name="li4804656085044"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> ResourceManager \> 系统”。对ResourceManager 的内存参数“GC\_OPTS”进行调整。保存配置，并重启ResourceManager实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >集群中的NodeManager实例数量和ResourceManager内存大小的对应关系参考如下：
    >-   集群中的NodeManager实例数据达到100，ResourceManager实例的JVM参数建议配置为：-Xms4G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到200，ResourceManager实例的JVM参数建议配置为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到500，ResourceManager实例的JVM参数建议配置为：-Xms10G -Xmx10G -XX:NewSize=1G -XX:MaxNewSize=2G
    >-   集群中的NodeManager实例数据达到1000，ResourceManager实例的JVM参数建议配置为：-Xms20G -Xmx20G -XX:NewSize=1G -XX:MaxNewSize=2G
    >-   集群中的NodeManager实例数据达到2000，ResourceManager实例的JVM参数建议配置为：-Xms40G -Xmx40G -XX:NewSize=2G -XX:MaxNewSize=4G
    >-   集群中的NodeManager实例数据达到3000，ResourceManager实例的JVM参数建议配置为：-Xms60G -Xmx60G -XX:NewSize=2G -XX:MaxNewSize=4G
    >-   集群中的NodeManager实例数据达到4000，ResourceManager实例的JVM参数建议配置为：-Xms80G -Xmx80G -XX:NewSize=2G -XX:MaxNewSize=4G
    >-   集群中的NodeManager实例数据达到5000，ResourceManager实例的JVM参数建议配置为：-Xms100G -Xmx100G -XX:NewSize=3G -XX:MaxNewSize=6G

5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li3192337385044)。


**收集故障信息。**

1.  <a name="li3192337385044"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   Yarn

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section58386803"></a>

无。

