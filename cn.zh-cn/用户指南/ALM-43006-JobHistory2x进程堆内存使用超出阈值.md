# ALM-43006 JobHistory2x进程堆内存使用超出阈值<a name="ALM-43006"></a>

## 告警解释<a name="se69fda89b528499cbd041f504060dda6"></a>

系统每30秒周期性检测JobHistory2x进程堆内存使用状态，当检测到JobHistory2x进程堆内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="s51d99308442b4b7d987f37e2bb7f3a0b"></a>

<a name="td11b871cc1dc45858d4967c40c944501"></a>
<table><thead align="left"><tr id="r75eeb1a0acad4ffdba4324b500dfeb8a"><th class="cellrowborder" valign="top" width="33.373337333733375%" id="mcps1.1.4.1.1"><p id="a3dcce4180c234371b0225091c787e8da"><a name="a3dcce4180c234371b0225091c787e8da"></a><a name="a3dcce4180c234371b0225091c787e8da"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.29332933293329%" id="mcps1.1.4.1.2"><p id="a686c17fc40c3494ca454c0ba129945a6"><a name="a686c17fc40c3494ca454c0ba129945a6"></a><a name="a686c17fc40c3494ca454c0ba129945a6"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="ae70f3093395a493a90d8130e2aa57928"><a name="ae70f3093395a493a90d8130e2aa57928"></a><a name="ae70f3093395a493a90d8130e2aa57928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="r57b1f92cb8954e1fbca5da34962440f4"><td class="cellrowborder" valign="top" width="33.373337333733375%" headers="mcps1.1.4.1.1 "><p id="ae2fedc1b3f334fa8a66b549825862830"><a name="ae2fedc1b3f334fa8a66b549825862830"></a><a name="ae2fedc1b3f334fa8a66b549825862830"></a>43006</p>
</td>
<td class="cellrowborder" valign="top" width="33.29332933293329%" headers="mcps1.1.4.1.2 "><p id="a0aaeea0e89da4e5fba9296c3bc286c88"><a name="a0aaeea0e89da4e5fba9296c3bc286c88"></a><a name="a0aaeea0e89da4e5fba9296c3bc286c88"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="abf8635d3205147e2841e9170b340a18c"><a name="abf8635d3205147e2841e9170b340a18c"></a><a name="abf8635d3205147e2841e9170b340a18c"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s1bcc1bc150634d639c341b9f6c08f950"></a>

<a name="ta7a26a0d476b4e3eb2accd1e4a62e8db"></a>
<table><thead align="left"><tr id="r2751e9e8a7a74c339db02b39c7ef45ba"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="ac3a1703c309e4e598e2056f4147d8d3b"><a name="ac3a1703c309e4e598e2056f4147d8d3b"></a><a name="ac3a1703c309e4e598e2056f4147d8d3b"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="aa9b461a4e9c24020bd6761a387f78b5d"><a name="aa9b461a4e9c24020bd6761a387f78b5d"></a><a name="aa9b461a4e9c24020bd6761a387f78b5d"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1912841841316"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="ra00d7dce80f0407783a02d5c8a8ae2fa"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a29fbdf6ec6b04d15bffc457d3ac08a1f"><a name="a29fbdf6ec6b04d15bffc457d3ac08a1f"></a><a name="a29fbdf6ec6b04d15bffc457d3ac08a1f"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r02059bfd8aa2498d9e8cef82c0a19ea6"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="abf7794fb50cc4170bf66e32bcb84007d"><a name="abf7794fb50cc4170bf66e32bcb84007d"></a><a name="abf7794fb50cc4170bf66e32bcb84007d"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r4bf1f48884e84a2f80cdf7f111411d38"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa5b54262f92946df9512f26316094362"><a name="aa5b54262f92946df9512f26316094362"></a><a name="aa5b54262f92946df9512f26316094362"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="rc73339d2a67d45bc83b82ed004b10148"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a50f08780fcdf4ce2986e5d671d8eabdc"><a name="a50f08780fcdf4ce2986e5d671d8eabdc"></a><a name="a50f08780fcdf4ce2986e5d671d8eabdc"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a7fc690a9201c472d852631a9b5f1f380"><a name="a7fc690a9201c472d852631a9b5f1f380"></a><a name="a7fc690a9201c472d852631a9b5f1f380"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="s6390126534a84b2d9a8afb7a6d5292a5"></a>

JobHistory2x进程堆内存使用率过高，会影响JobHistory2x进程运行的性能，甚至造成内存溢出导致JobHistory2x进程不可用。

## 可能原因<a name="se5bac60b57c44f66baad2d26ef452d86"></a>

该节点JobHistory2x进程堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="sdd18773a72ec43b2b4f1bbbc6480e25a"></a>

检查堆内存使用率

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43006”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JobHistory2x内存使用率统计”，单击“确定”，查看JobHistory2x进程使用的堆内存是否已达到JobHistory2x进程设定的最大堆内存的阈值（默认95%）。

    -   是，执行[3](#li4800192612341)。
    -   否，执行[7](#li131017814534)。

    **图 1**  JobHistory2x内存使用率统计<a name="fig174723591719"></a>  
    ![](figures/JobHistory2x内存使用率统计.png "JobHistory2x内存使用率统计")

3.  <a name="li4800192612341"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> 内存 \> JobHistory2x进程的堆内存统计”，单击“确定”，根据告警产生时间，查看对应时间段的“JobHistory2x进程使用的堆内存”的值，获取最大值。

    **图 2**  jobHistory2x进程的堆内存统计<a name="fig42561657121717"></a>  
    ![](figures/jobHistory2x进程的堆内存统计.png "jobHistory2x进程的堆内存统计")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“JobHistory2x \> 默认”，“SPARK\_DAEMON\_MEMORY”参数默认值为4G，可根据如下方案调整该参数值：告警时间段内JobHistory2x使用堆内存的最大值和“JobHistory2x堆内存使用率统计 \(JobHistory2x\)”阈值的比值。若参数值调整后，仍偶现告警，可以按0.5倍速率调大。若频繁出现告警，可以按1倍速率调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> JobHistory2x堆内存使用率统计 \(JobHistory2x\)”，可查看“阈值”。

5.  重启所有的JobHistory2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li131017814534)。


收集故障信息

1.  <a name="li131017814534"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s8eded8f2f2bb41dea8e1ae5007ebc1d5"></a>

无。

