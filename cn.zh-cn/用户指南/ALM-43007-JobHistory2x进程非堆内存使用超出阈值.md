# ALM-43007 JobHistory2x进程非堆内存使用超出阈值<a name="ALM-43007"></a>

## 告警解释<a name="s75a14a421fdb4ba4813b061ef0ce32a1"></a>

系统每30秒周期性检测JobHistory2x进程非堆内存使用状态，当检测到JobHistory2x进程非堆内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="sd610278c5a114e76bcdee07a1fd10e25"></a>

<a name="tb94fd3089f1b483b98b09cdecdcd8746"></a>
<table><thead align="left"><tr id="r7b7bdd2324df4bcdb4a3ca3481a0ef06"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="af31751d397bc4736b3468a84c4af0736"><a name="af31751d397bc4736b3468a84c4af0736"></a><a name="af31751d397bc4736b3468a84c4af0736"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="aac71aa845f0441c0893dd5f08410afaf"><a name="aac71aa845f0441c0893dd5f08410afaf"></a><a name="aac71aa845f0441c0893dd5f08410afaf"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="ae5aa653c403f47e28a7d2c12468231c0"><a name="ae5aa653c403f47e28a7d2c12468231c0"></a><a name="ae5aa653c403f47e28a7d2c12468231c0"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="re2c98e521d0f4e848d8c0adc2b58cdd7"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="abcb605a6246845b6a01698345541234e"><a name="abcb605a6246845b6a01698345541234e"></a><a name="abcb605a6246845b6a01698345541234e"></a>43007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a465a97cad2864a5c8c19faef364b426e"><a name="a465a97cad2864a5c8c19faef364b426e"></a><a name="a465a97cad2864a5c8c19faef364b426e"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="a486847d1b2034048b1e237beff1da330"><a name="a486847d1b2034048b1e237beff1da330"></a><a name="a486847d1b2034048b1e237beff1da330"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s4c3ebfb173544b1aacfeb52a57c89399"></a>

<a name="tf54514b8c160402b9d3b25da02711710"></a>
<table><thead align="left"><tr id="ra1dfff68b5894ac2b286d128c161c2c9"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="ae799d5401c9a439bb18b7b2147f1609f"><a name="ae799d5401c9a439bb18b7b2147f1609f"></a><a name="ae799d5401c9a439bb18b7b2147f1609f"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="a1985914890d94d638eb8c4fa93aa648b"><a name="a1985914890d94d638eb8c4fa93aa648b"></a><a name="a1985914890d94d638eb8c4fa93aa648b"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row411469181313"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r1d60f942453844e9850b4adac3d0bf95"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a1552abd4005044c49cb9ae35347db1ec"><a name="a1552abd4005044c49cb9ae35347db1ec"></a><a name="a1552abd4005044c49cb9ae35347db1ec"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="rd58c1e881dc34ee39641d21f3c30f145"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="afc09f234d16345d39e2e992f7ab63964"><a name="afc09f234d16345d39e2e992f7ab63964"></a><a name="afc09f234d16345d39e2e992f7ab63964"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r0ab2dc684c174723ab9068cf1e3a89e9"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa13a11b6887147d09812aa2e0df112c0"><a name="aa13a11b6887147d09812aa2e0df112c0"></a><a name="aa13a11b6887147d09812aa2e0df112c0"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="r1e3fbd822b5d4dad997066d8d4149d34"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="ab6ee8252fc06415fa74e0646de6f6089"><a name="ab6ee8252fc06415fa74e0646de6f6089"></a><a name="ab6ee8252fc06415fa74e0646de6f6089"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ab21dc52a7f9445e7a99c6c1c5e90c7a4"><a name="ab21dc52a7f9445e7a99c6c1c5e90c7a4"></a><a name="ab21dc52a7f9445e7a99c6c1c5e90c7a4"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="seff07e9438874a30a6b2723d3a847f58"></a>

JobHistory2x进程非堆内存使用率过高，会影响JobHistory2x进程运行的性能，甚至造成内存溢出导致JobHistory2x进程不可用。

## 可能原因<a name="sd00c242b932e4459b3333dd3fd70b17c"></a>

该节点JobHistory2x进程非堆内存使用率过大，或配置的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="sffedeb73c31541fd8ff9a992908ff5c3"></a>

检查非堆内存使用率

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43007”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JobHistory2x内存使用率统计”，单击“确定”，查看JobHistory2x进程使用的非堆内存是否已达到JobHistory2x进程设定的最大非堆内存的阈值（默认95%）。

    -   是，执行[3](#li52944162246)。
    -   否，执行[7](#li1780713935415)。

    **图 1**  JobHistory2x内存使用率统计<a name="fig174723591719"></a>  
    ![](figures/JobHistory2x内存使用率统计-95.png "JobHistory2x内存使用率统计-95")

3.  <a name="li52944162246"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> 内存 \> JobHistory2x进程的非堆内存统计”，单击“确定”，根据告警产生时间，查看对应时间段的“JobHistory2x进程使用的非堆内存”的值，获取最大值。

    **图 2**  JobHistory2x进程的非堆内存统计<a name="fig766135661916"></a>  
    ![](figures/JobHistory2x进程的非堆内存统计.png "JobHistory2x进程的非堆内存统计")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“JobHistory2x \> 默认”，根据如下原则调整“SPARK\_DAEMON\_JAVA\_OPTS”参数中-XX:MaxMetaspaceSize的值：告警时间段内JobHistory2x使用非堆内存的最大值和“JobHistory2x非堆内存使用率统计 \(JobHistory2x\)”阈值的比值。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> JobHistory2x非堆内存使用率统计 \(JobHistory2x\)”，可查看“阈值”。

5.  重启所有的JobHistory2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li1780713935415)。


收集故障信息

1.  <a name="li1780713935415"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s0a72d306357f4ee580395348edb819e1"></a>

无。

