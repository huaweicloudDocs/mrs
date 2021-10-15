# ALM-23004 Loader堆内存使用率超过阈值<a name="ALM-23004"></a>

## 告警解释<a name="section12734291"></a>

系统每60秒周期性检测Loader服务堆内存使用状态，当连续10次检测到Loader实例堆内存使用率超出阈值（最大内存的95%）时产生该告警。堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section47499760"></a>

<a name="table66652465"></a>
<table><thead align="left"><tr id="row49677463"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p64451546"><a name="p64451546"></a><a name="p64451546"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p53192709"><a name="p53192709"></a><a name="p53192709"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p13642177"><a name="p13642177"></a><a name="p13642177"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row31274549"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p50210570"><a name="p50210570"></a><a name="p50210570"></a>23004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p40524392"><a name="p40524392"></a><a name="p40524392"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p61250294"><a name="p61250294"></a><a name="p61250294"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section24844657"></a>

<a name="table62326748"></a>
<table><thead align="left"><tr id="row14960745"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p3860808"><a name="p3860808"></a><a name="p3860808"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p44290020"><a name="p44290020"></a><a name="p44290020"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row264919571161"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row30721828"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p37995953"><a name="p37995953"></a><a name="p37995953"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row6419265"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39544768"><a name="p39544768"></a><a name="p39544768"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row20358592"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26085635"><a name="p26085635"></a><a name="p26085635"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row33444125"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p24619586"><a name="p24619586"></a><a name="p24619586"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p48029464"><a name="p48029464"></a><a name="p48029464"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section22275329"></a>

堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section66260240"></a>

该节点Loader实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section59471256"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Loader堆内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制”，勾选“内存”中的“Loader堆内存使用率”，单击“确定”。

    **图 1**  Loader堆内存使用率<a name="fig15393165119414"></a>  
    ![](figures/Loader堆内存使用率.png "Loader堆内存使用率")

3.  查看Loader使用的堆内存是否已达到Loader设定的阈值（默认值为最大堆内存的95%）。
    -   是，执行[4](#d0e41176)。
    -   否，执行[6](#d0e41197)。

4.  <a name="d0e41176"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Loader \> 配置”，选择“全部配置”。在搜索栏里搜索“GC\_OPTS”参数，将“-Xmx”的值根据实际情况调大，并单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   出现此告警时，说明当前Loader实例设置的堆内存无法满足当前数据传输所需的堆内存，建议打开实例监控界面，在页面上调出“Loader堆内存资源状况”监控图表，观察该监控图表中“Loader使用的堆内存大小”的变化趋势，根据当前堆内存使用的大小，调整“-Xmx”的值为当前堆内存使用量的两倍（或根据实际情况进行调整）。
    >-   注意堆内存设置时，可以设置“-Xms” “-Xmx”近似相等，从而避免每次GC后调整堆的大小，从而引起性能下降。
    >-   同时，并且“-Xmx”与“XX:MaxPermSize”之和不得大于该节点服务器的实际物理内存值。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e41197)。


**收集故障信息。**

1.  <a name="d0e41197"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Loader”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

