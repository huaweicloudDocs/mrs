# ALM-18008 ResourceManager堆内存使用率超过阈值<a name="ALM-18008"></a>

## 告警解释<a name="section1335609"></a>

系统每30秒周期性检测Yarn ResourceManager堆内存使用率，并把实际的Yarn ResourceManager堆内存使用率和阈值相比较。当Yarn ResourceManager堆内存使用率超出阈值（默认为最大堆内存的95%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Yarn”修改阈值。

平滑次数为1，Yarn ResourceManager堆内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，Yarn ResourceManager堆内存使用率小于或等于阈值的95%时，告警恢复。

## 告警属性<a name="section12020482"></a>

<a name="table9634977"></a>
<table><thead align="left"><tr id="row15805238"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p5155867"><a name="p5155867"></a><a name="p5155867"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p14972060"><a name="p14972060"></a><a name="p14972060"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p4777379"><a name="p4777379"></a><a name="p4777379"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row51423381"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p4544348"><a name="p4544348"></a><a name="p4544348"></a>18008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p32547936"><a name="p32547936"></a><a name="p32547936"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p19137160"><a name="p19137160"></a><a name="p19137160"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section41075474"></a>

<a name="table6606141"></a>
<table><thead align="left"><tr id="row49320909"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35570664"><a name="p35570664"></a><a name="p35570664"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p62651540"><a name="p62651540"></a><a name="p62651540"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row822014158206"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row41609976"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4199435"><a name="p4199435"></a><a name="p4199435"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row37794916"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5195099"><a name="p5195099"></a><a name="p5195099"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row46755894"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10805765"><a name="p10805765"></a><a name="p10805765"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row30143027"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p25666111"><a name="p25666111"></a><a name="p25666111"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p65689071"><a name="p65689071"></a><a name="p65689071"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section34134946"></a>

Yarn ResourceManager堆内存使用率过高，会影响Yarn任务提交和运行的性能，甚至造成内存溢出导致Yarn服务不可用。

## 可能原因<a name="section38779059"></a>

该节点Yarn ResourceManager实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section13467214"></a>

**检查堆内存使用量。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警 \> Yarn ResourceManager堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> ResourceManager（对应上报告警实例主机名）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“ResourceManager内存使用率”。查看堆内存使用情况。

    **图 1**  定制ResourceManager内存使用率<a name="fig743115719441"></a>  
    ![](figures/定制ResourceManager内存使用率.png "定制ResourceManager内存使用率")

3.  查看ResourceManager使用的堆内存是否已达到ResourceManager设定的最大堆内存的95%。
    -   是，执行[4](#li4185479883010)。
    -   否，执行[6](#li3256645983010)。

4.  <a name="li4185479883010"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> ResourceManager \> 系统”。将“GC\_OPTS”参数根据实际情况调大，并单击“保存”，保存完成后重启角色实例。

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
    -   否，执行[6](#li3256645983010)。


**收集故障信息。**

1.  <a name="li3256645983010"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   Yarn

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section54096069"></a>

无。

