# ALM-18012 JobHistoryServer进程垃圾回收（GC）时间超过阈值<a name="ALM-18012"></a>

## 告警解释<a name="section50697487"></a>

系统每60秒周期性检测JobHistoryServer进程的垃圾回收（GC）占用时间，当检测到JobHistoryServer进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。

垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section53624206"></a>

<a name="table20063603"></a>
<table><thead align="left"><tr id="row29477662"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p38880413"><a name="p38880413"></a><a name="p38880413"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62305773"><a name="p62305773"></a><a name="p62305773"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p13602870"><a name="p13602870"></a><a name="p13602870"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row28090655"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p60750544"><a name="p60750544"></a><a name="p60750544"></a>18012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p21847026"><a name="p21847026"></a><a name="p21847026"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p24778668"><a name="p24778668"></a><a name="p24778668"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section12855810"></a>

<a name="table60915111"></a>
<table><thead align="left"><tr id="row8425846"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p11404934"><a name="p11404934"></a><a name="p11404934"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p51384442"><a name="p51384442"></a><a name="p51384442"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row18299174521918"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row1390267"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61845569"><a name="p61845569"></a><a name="p61845569"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row19739216"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56003376"><a name="p56003376"></a><a name="p56003376"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row34268337"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19870205"><a name="p19870205"></a><a name="p19870205"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row44614122"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p56974164"><a name="p56974164"></a><a name="p56974164"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p51504599"><a name="p51504599"></a><a name="p51504599"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section48593428"></a>

JobHistoryServer进程的垃圾回收时间过长，可能影响该JobHistoryServer进程正常提供服务。

## 可能原因<a name="section34687669"></a>

该节点JobHistoryServer实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section43753566"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18012 JobHistoryServer进程垃圾回收（GC）时间超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> MapReduce \> 实例 \> JobHistoryServer（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 垃圾回收”，勾选“JobHistoryServer垃圾回收（GC）时间”。查看JobHistoryServer每分钟的垃圾回收时间统计情况。
3.  查看JobHistoryServer每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li5017863184050)。
    -   否，执行[7](#li5903334084050)。

4.  <a name="li5017863184050"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Mapreduce \> 配置 \> 全部配置 \> JobHistoryServer \> 系统”。将“GC\_OPTS”参数根据实际情况调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >历史任务数10000和JobHistoryServer内存的对应关系如下：
    >-Xms30G -Xmx30G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  保存配置，并重启JobHistoryServer实例。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li5903334084050)。


**收集故障信息。**

1.  <a name="li5903334084050"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“JobHistoryServer”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section58237776"></a>

无。

