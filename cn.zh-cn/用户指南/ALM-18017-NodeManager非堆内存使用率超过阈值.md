# ALM-18017 NodeManager非堆内存使用率超过阈值<a name="ALM-18017"></a>

## 告警解释<a name="section51497752"></a>

系统每30秒周期性检测Yarn NodeManager非堆内存使用率，并把实际的Yarn NodeManager非堆内存使用率和阈值相比较。当Yarn NodeManager非堆内存使用率超出阈值（默认为最大非堆内存的90%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Yarn”修改阈值。

当Yarn NodeManager非堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section60826586"></a>

<a name="table30640066"></a>
<table><thead align="left"><tr id="row25770166"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p7008729"><a name="p7008729"></a><a name="p7008729"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p30836156"><a name="p30836156"></a><a name="p30836156"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p14700679"><a name="p14700679"></a><a name="p14700679"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row49904355"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p15720951"><a name="p15720951"></a><a name="p15720951"></a>18017</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65437548"><a name="p65437548"></a><a name="p65437548"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p65950058"><a name="p65950058"></a><a name="p65950058"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section10568364"></a>

<a name="table40354456"></a>
<table><thead align="left"><tr id="row55843024"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p26991099"><a name="p26991099"></a><a name="p26991099"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p38795386"><a name="p38795386"></a><a name="p38795386"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row97989101919"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row55418550"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5281410"><a name="p5281410"></a><a name="p5281410"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row47532697"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7136174"><a name="p7136174"></a><a name="p7136174"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row64225571"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7419413"><a name="p7419413"></a><a name="p7419413"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row66774722"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p40043391"><a name="p40043391"></a><a name="p40043391"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22289220"><a name="p22289220"></a><a name="p22289220"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section28006415"></a>

Yarn NodeManager非堆内存使用率过高，会影响Yarn任务提交和运行的性能，甚至造成内存溢出导致Yarn服务不可用。

## 可能原因<a name="section50731149"></a>

该节点Yarn NodeManager实例非堆内存使用量过大，或分配的非堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="section53927157"></a>

**检查非堆内存使用量。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警 \> ALM-18017 Yarn NodeManager非堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的主机名。
2.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> NodeManager（对应上报告警实例主机名）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“NodeManager内存使用率”。查看非堆内存使用情况。

    **图 1**  定制NodeManager内存使用率<a name="fig267352845611"></a>  
    ![](figures/定制NodeManager内存使用率-88.png "定制NodeManager内存使用率-88")

3.  查看NodeManager使用的非堆内存是否已达到NodeManager设定的最大非堆内存的90%。
    -   是，执行[4](#li521882608531)。
    -   否，执行[6](#li573525018531)。

4.  <a name="li521882608531"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> NodeManager \> 系统”。对NodeManager的内存参数“GC\_OPTS”进行调整，并单击“保存”，在弹出的对话框中单击“确定”并重启角色实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >集群中的NodeManager实例数量和NodeManager内存大小的对应关系参考如下：
    >-   集群中的NodeManager实例数据达到100，NodeManager实例的JVM参数建议配置为：-Xms2G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到200，NodeManager实例的JVM参数建议配置为：-Xms4G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到500以上，NodeManager实例的JVM参数建议配置为：-Xms8G -Xmx8G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li573525018531)。


**收集故障信息。**

1.  <a name="li573525018531"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”下拉框中勾选待操作集群的如下节点信息，单击“确定”。
    -   NodeAgent
    -   Yarn

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section15582370"></a>

无。

