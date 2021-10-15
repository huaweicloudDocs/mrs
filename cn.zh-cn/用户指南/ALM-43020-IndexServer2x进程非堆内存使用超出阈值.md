# ALM-43020 IndexServer2x进程非堆内存使用超出阈值<a name="ALM-43020"></a>

## 告警解释<a name="s654199794cb646f5baa4518aefce49a3"></a>

系统每30秒周期性检测IndexServer2x进程非堆内存使用状态，当检测到IndexServer2x进程非堆内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="sa26ae86d3dad41409f83a1377a9ffcfa"></a>

<a name="tcf229e81dd344017b6e4cffa8812ea38"></a>
<table><thead align="left"><tr id="r71b321b2dfa44544b9d38c31a7c564c0"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="a8c676edf82c34fe9ac00e771db46396a"><a name="a8c676edf82c34fe9ac00e771db46396a"></a><a name="a8c676edf82c34fe9ac00e771db46396a"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a49e228ba3e9744a9ba62df793cb9f48a"><a name="a49e228ba3e9744a9ba62df793cb9f48a"></a><a name="a49e228ba3e9744a9ba62df793cb9f48a"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="acf332948bf634701b2eb985488faaf8b"><a name="acf332948bf634701b2eb985488faaf8b"></a><a name="acf332948bf634701b2eb985488faaf8b"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="r97968a0e761c4d90b952c9bfc25f44f9"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="a441c0b910dff45a3822b47f0c38788b2"><a name="a441c0b910dff45a3822b47f0c38788b2"></a><a name="a441c0b910dff45a3822b47f0c38788b2"></a>43020</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a3ea3972a589749afb36b6cb0998f8acf"><a name="a3ea3972a589749afb36b6cb0998f8acf"></a><a name="a3ea3972a589749afb36b6cb0998f8acf"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="a14026af7cc9948e494ecb783327d2acd"><a name="a14026af7cc9948e494ecb783327d2acd"></a><a name="a14026af7cc9948e494ecb783327d2acd"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s8847e557c6b3453aaee9f6581c60c7f0"></a>

<a name="ta4b460384c754c91b30862b9ff824f4f"></a>
<table><thead align="left"><tr id="r99aa4ff1011848d48389427aebb04c06"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="aecb6aec3722f463da013cd6a9681d943"><a name="aecb6aec3722f463da013cd6a9681d943"></a><a name="aecb6aec3722f463da013cd6a9681d943"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="ab6eca64948c8482f8161c84f93f75401"><a name="ab6eca64948c8482f8161c84f93f75401"></a><a name="ab6eca64948c8482f8161c84f93f75401"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row88669469128"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r6d7be8e0e35a4cf08993625fc62e4301"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="afadd76ad17914fd18b2494f51b17997f"><a name="afadd76ad17914fd18b2494f51b17997f"></a><a name="afadd76ad17914fd18b2494f51b17997f"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r5e5fd6c56f564e7ea629ac99dc22bcce"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ad6d4ca57de514e04b1eb96e905a2938f"><a name="ad6d4ca57de514e04b1eb96e905a2938f"></a><a name="ad6d4ca57de514e04b1eb96e905a2938f"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r9a551a22222e4651b10174987c965499"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa6ded27644dd42aba2f76e0ecd52a010"><a name="aa6ded27644dd42aba2f76e0ecd52a010"></a><a name="aa6ded27644dd42aba2f76e0ecd52a010"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="rb39a34fe9a5d406d8ffdb11e868ddecd"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a22165862128b459a910b476586ac7149"><a name="a22165862128b459a910b476586ac7149"></a><a name="a22165862128b459a910b476586ac7149"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a082c50ad862e4407b31c3d7e28fc781a"><a name="a082c50ad862e4407b31c3d7e28fc781a"></a><a name="a082c50ad862e4407b31c3d7e28fc781a"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="s7e65a524bbfd4a28ae8d0ad568b2d9bd"></a>

IndexServer2x进程非堆内存使用率过高，会影响IndexServer2x进程运行的性能，甚至造成内存溢出导致IndexServer2x进程不可用。

## 可能原因<a name="s01cd2ae89bd34527b0a20a4ae96da722"></a>

该节点IndexServer2x进程非堆内存使用率过大，或配置的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section39311354121312"></a>

**检查非堆内存使用率**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43020”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的IndexServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> IndexServer2x内存使用率统计”，单击“确定”，查看IndexServer2x进程使用的非堆内存是否已达到IndexServer2x进程设定的最大非堆内存的阈值（默认95%）。

    -   是，执行[3](#li311482053120)。
    -   否，执行[7](#li141131720123116)。

    **图 1**  IndexServer2x内存使用率统计<a name="fig64913557268"></a>  
    ![](figures/IndexServer2x内存使用率统计-136.png "IndexServer2x内存使用率统计-136")

3.  <a name="li311482053120"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的IndexServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> IndexServer2x进程的非堆内存统计” ，单击“确定”，根据告警产生时间，查看对应时间段的“IndexServer2x进程使用的非堆内存”的值，获取最大值。

    **图 2**  IndexServer2x进程的非堆内存统计<a name="fig18804913142810"></a>  
    ![](figures/IndexServer2x进程的非堆内存统计.png "IndexServer2x进程的非堆内存统计")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“IndexServer2x \> 性能”，将“spark.driver.extraJavaOptions”参数中-XX:MaxMetaspaceSize的值根据如下原则调整：告警时间段内IndexServer2x使用的非堆内存的最大值和“IndexServer2x非堆内存使用率统计（IndexServer2x）”阈值的比值。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> IndexServer2x非堆内存使用率统计（IndexServer2x）”，可查看“阈值”。

5.  重启所有的IndexServer2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li141131720123116)。


**收集故障信息**

1.  <a name="li141131720123116"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895527.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s9121af30e9174ff4a8ea197579ce835d"></a>

无。

