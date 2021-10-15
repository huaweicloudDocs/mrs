# ALM-14015 DataNode进程垃圾回收（GC）时间超过阈值<a name="ALM-14015"></a>

## 告警解释<a name="section48660305"></a>

系统每60秒周期性检测DataNode进程的垃圾回收（GC）占用时间，当检测到DataNode进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。

垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section35289568"></a>

<a name="table52541973"></a>
<table><thead align="left"><tr id="row34196896"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p18485183"><a name="p18485183"></a><a name="p18485183"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p20904879"><a name="p20904879"></a><a name="p20904879"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p15573656"><a name="p15573656"></a><a name="p15573656"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row53506593"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p39066738"><a name="p39066738"></a><a name="p39066738"></a>14015</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p10289204"><a name="p10289204"></a><a name="p10289204"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p28119182"><a name="p28119182"></a><a name="p28119182"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section49170660"></a>

<a name="table63061289"></a>
<table><thead align="left"><tr id="row36555336"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p8192248"><a name="p8192248"></a><a name="p8192248"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p59592332"><a name="p59592332"></a><a name="p59592332"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1349242752714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row62249581"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62063923"><a name="p62063923"></a><a name="p62063923"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row21704402"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p64686834"><a name="p64686834"></a><a name="p64686834"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row45310595"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57660687"><a name="p57660687"></a><a name="p57660687"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row49184140"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p24492438"><a name="p24492438"></a><a name="p24492438"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p37730489"><a name="p37730489"></a><a name="p37730489"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section39882758"></a>

DataNode进程的垃圾回收时间过长，可能影响该DataNode进程正常提供服务。

## 可能原因<a name="section23400503"></a>

该节点DataNode实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section9277936"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ALM-14015 DataNode进程垃圾回收（GC）时间超过阈值”所在行的下拉菜单，在“定位信息”中查看告警上报的角色名并确定实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例 \> DataNode（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 垃圾回收”，勾选“DataNode垃圾回收（GC）时间”。查看DataNode每分钟的垃圾回收时间统计情况。

    **图 1**  DataNode垃圾回收（GC）时间<a name="fig18978958174212"></a>  
    ![](figures/DataNode垃圾回收（GC）时间.png "DataNode垃圾回收（GC）时间")

3.  查看DataNode每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li5741089793257)。
    -   否，执行[7](#li1451284193257)。

4.  <a name="li5741089793257"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置 \> DataNode \> 系统”。将“GC\_OPTS”参数值根据实际情况调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单个DataNode实例平均Block数量和DataNode内存的对应关系参考值如下：
    >-   单个DataNode实例平均Block数量达到2,000,000，DataNode的JVM参数参考值为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M
    >-   单个DataNode实例平均Block数量达到5,000,000，DataNode的JVM参数参考值为：-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G

5.  保存配置，并重启该DataNode实例。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li1451284193257)。


**收集故障信息。**

1.  <a name="li1451284193257"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“DataNode”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section16392562"></a>

无。

