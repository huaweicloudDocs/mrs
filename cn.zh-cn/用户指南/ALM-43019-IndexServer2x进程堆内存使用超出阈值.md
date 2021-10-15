# ALM-43019 IndexServer2x进程堆内存使用超出阈值<a name="ALM-43019"></a>

## 告警解释<a name="s003d1a897bb74496accc109e130a2b79"></a>

系统每30秒周期性检测IndexServer2x进程堆内存使用状态，当检测到IndexServer2x进程堆内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="s32061f2ab1e44d538c70b77f588c95cd"></a>

<a name="t62b2bf48fdb841b8b702dde8b4644920"></a>
<table><thead align="left"><tr id="r653f637d7ab844f1b2b15f5002adddc1"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="a6e2b2640000e4f428add13b685a783aa"><a name="a6e2b2640000e4f428add13b685a783aa"></a><a name="a6e2b2640000e4f428add13b685a783aa"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a7af8d14c415f4b68b43115fb4f53f3ef"><a name="a7af8d14c415f4b68b43115fb4f53f3ef"></a><a name="a7af8d14c415f4b68b43115fb4f53f3ef"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="a02d843fe6f624e84964ca5d1578740af"><a name="a02d843fe6f624e84964ca5d1578740af"></a><a name="a02d843fe6f624e84964ca5d1578740af"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="rbbe1f519640347c5aa24f4905dc8ef50"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="a212dce1b184242249ca42d3e8cfbf84e"><a name="a212dce1b184242249ca42d3e8cfbf84e"></a><a name="a212dce1b184242249ca42d3e8cfbf84e"></a>43019</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="af105557b1f4f47de89fbeccd88f9941a"><a name="af105557b1f4f47de89fbeccd88f9941a"></a><a name="af105557b1f4f47de89fbeccd88f9941a"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="a38e9a2fe39b6403aaaf4b4fb0e29f3e5"><a name="a38e9a2fe39b6403aaaf4b4fb0e29f3e5"></a><a name="a38e9a2fe39b6403aaaf4b4fb0e29f3e5"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s741e8ec04d9446768c01e82bd6e711e2"></a>

<a name="t9f47f89d18d243fab2094565e98d83e3"></a>
<table><thead align="left"><tr id="ra75bbb84f5d74453be996544228d00d2"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="ab21543f0c58a41a8913512dcfbf72944"><a name="ab21543f0c58a41a8913512dcfbf72944"></a><a name="ab21543f0c58a41a8913512dcfbf72944"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="abeda253959cb4662a594521d2dc72255"><a name="abeda253959cb4662a594521d2dc72255"></a><a name="abeda253959cb4662a594521d2dc72255"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row92491653161219"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r22ce027ef3024074aeff2607500388ab"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a035311a753c9400d8922b2eabd67b99f"><a name="a035311a753c9400d8922b2eabd67b99f"></a><a name="a035311a753c9400d8922b2eabd67b99f"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r25691c41a60c400e8f4cd09ecf91837b"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aefbdd0e3041747fb803e48abb240998a"><a name="aefbdd0e3041747fb803e48abb240998a"></a><a name="aefbdd0e3041747fb803e48abb240998a"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r3d53a6e9138a48ffbb3f6d327452b5d3"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa95e2e07ac7f454582df5a0e86a74e55"><a name="aa95e2e07ac7f454582df5a0e86a74e55"></a><a name="aa95e2e07ac7f454582df5a0e86a74e55"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="rde525935a2834a8895ddacf674450ba5"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a1f2fbce6a30747a5b50b4f4805460bd7"><a name="a1f2fbce6a30747a5b50b4f4805460bd7"></a><a name="a1f2fbce6a30747a5b50b4f4805460bd7"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="afb1ebb849d8540c2b1dee2196613eb15"><a name="afb1ebb849d8540c2b1dee2196613eb15"></a><a name="afb1ebb849d8540c2b1dee2196613eb15"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="sb3a2d017129345d888713064e79025cd"></a>

IndexServer2x进程堆内存使用率过高，会影响IndexServer2x进程运行的性能，甚至造成内存溢出导致IndexServer2x进程不可用。

## 可能原因<a name="sa5adbf6484b2466281b8b667bdc68717"></a>

该节点IndexServer2x进程堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section1876421013309"></a>

**检查堆内存使用率**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43019”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的IndexServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> IndexServer2x内存使用率统计”，单击“确定”，查看IndexServer2x进程使用的堆内存是否已达到IndexServer2x进程设定的最大堆内存的阈值（默认95%）。

    -   是，执行[3](#li1769491023514)。
    -   否，执行[7](#li1543255925610)。

    **图 1**  IndexServer2x内存使用率统计<a name="fig64913557268"></a>  
    ![](figures/IndexServer2x内存使用率统计.png "IndexServer2x内存使用率统计")

3.  <a name="li1769491023514"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的IndexServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> IndexServer2x进程堆内存统计” ，单击“确定”，根据告警产生时间，查看对应时间段的“IndexServer2x进程使用的堆内存”的值，获取最大值。

    **图 2**  IndexServer2x进程堆内存统计<a name="fig3721185213279"></a>  
    ![](figures/IndexServer2x进程堆内存统计.png "IndexServer2x进程堆内存统计")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“IndexServer2x \> 性能”，“SPARK\_DRIVER\_MEMORY”参数的值默认4G，可根据如下原则进行调整：告警时间段内IndexServer2x使用堆内存的最大值和“IndexServer2x堆内存使用率统计 \(IndexServer2x\)”阈值的比值。若参数值调整后，仍偶现告警，可以按0.5倍速率调大。若频繁出现告警，可以按1倍速率调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> IndexServer2x堆内存使用率统计 \(IndexServer2x\)”，可查看“阈值”。

5.  重启所有的IndexServer2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li1543255925610)。


**收集故障信息**

1.  <a name="li1543255925610"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895484.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s90cd5279899a47bab7f1ded21334fa68"></a>

无。

