# ALM-43012 JDBCServer2x进程直接内存使用超出阈值<a name="ALM-43012"></a>

## 告警解释<a name="sc21fe29c411e41409776a7f363f27627"></a>

系统每30秒周期性检测JDBCServer2x进程直接内存使用状态，当检测到JDBCServer2x进程直接内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="s4090a0887ac94f6ea0c313fc93558621"></a>

<a name="t8f99cc5400c44ffa97ab609a58c35834"></a>
<table><thead align="left"><tr id="r7c7f9b98ceca4ec0a0800ecf76ccef9e"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="a384abf8fd5d4496eb3f24e3659360208"><a name="a384abf8fd5d4496eb3f24e3659360208"></a><a name="a384abf8fd5d4496eb3f24e3659360208"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a9fb6fed3911b489d82df1a64bde4b070"><a name="a9fb6fed3911b489d82df1a64bde4b070"></a><a name="a9fb6fed3911b489d82df1a64bde4b070"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="a822c4dd1c3a9441a8112bb1f236f3815"><a name="a822c4dd1c3a9441a8112bb1f236f3815"></a><a name="a822c4dd1c3a9441a8112bb1f236f3815"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="rfea230e6015b4acf959f0f8c1aee9d3e"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="a8708f4e87bc341ff8f0cd0d2584d3ffa"><a name="a8708f4e87bc341ff8f0cd0d2584d3ffa"></a><a name="a8708f4e87bc341ff8f0cd0d2584d3ffa"></a>43012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="af37be87b74214641ba5b07a6bb7c9eb2"><a name="af37be87b74214641ba5b07a6bb7c9eb2"></a><a name="af37be87b74214641ba5b07a6bb7c9eb2"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="a6498abf69ae84417a67ec941de431a88"><a name="a6498abf69ae84417a67ec941de431a88"></a><a name="a6498abf69ae84417a67ec941de431a88"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s0b7620cc8d904f908eab3fd94fc26272"></a>

<a name="t68d85ce289c84a24ae299d43425ff8ae"></a>
<table><thead align="left"><tr id="r3e98675c76d14517b23a76d0cb501e87"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a5d03d695bf0b4c43a5caf3d367a4c0a5"><a name="a5d03d695bf0b4c43a5caf3d367a4c0a5"></a><a name="a5d03d695bf0b4c43a5caf3d367a4c0a5"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="a90bb9bc2e82a426bb93b0b2f7053fc1f"><a name="a90bb9bc2e82a426bb93b0b2f7053fc1f"></a><a name="a90bb9bc2e82a426bb93b0b2f7053fc1f"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row19850194112121"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r9ded483eb9844736ac68a17c358d7da2"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a56301b53d00544029a8c8ddafa6d31ff"><a name="a56301b53d00544029a8c8ddafa6d31ff"></a><a name="a56301b53d00544029a8c8ddafa6d31ff"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r510741ebfe864dd981b589f5f8595102"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ad76b983a401944ca91e141a3a69f8ad1"><a name="ad76b983a401944ca91e141a3a69f8ad1"></a><a name="ad76b983a401944ca91e141a3a69f8ad1"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r03c3304824734d9fa9a737747e27b53a"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a57618ecf6f7645a59e09d708b6c95e65"><a name="a57618ecf6f7645a59e09d708b6c95e65"></a><a name="a57618ecf6f7645a59e09d708b6c95e65"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="red34012f122e4af9a640d3c1332a6922"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a32a03a9c53d54278812ea7a1ed559514"><a name="a32a03a9c53d54278812ea7a1ed559514"></a><a name="a32a03a9c53d54278812ea7a1ed559514"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a7b936a21a6e5475881a69a1c6d9c30a6"><a name="a7b936a21a6e5475881a69a1c6d9c30a6"></a><a name="a7b936a21a6e5475881a69a1c6d9c30a6"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="sb4c2a4c4b87c4f90b322a83ec9b6d735"></a>

JDBCServer2x进程直接内存使用率过高，会影响JDBCServer2x进程运行的性能，甚至造成内存溢出导致JDBCServer2x进程不可用。

## 可能原因<a name="sd4ce190e23f7470ea72265183e1c0f77"></a>

该节点JDBCServer2x进程直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="sae5cf50702da4f6aad4abfc28250e890"></a>

检查直接内存使用率

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43012”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JDBCServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JDBCServer2x内存使用率统计”，单击“确定”，查看JDBCServer2x进程使用的直接内存是否已达到JDBCServer2x进程设定的最大直接内存的阈值。

    -   是，执行[3](#li1586716293291)。
    -   否，执行[7](#li128333120587)。

    **图 1**  JDBCServer2x内存使用率统计<a name="fig23084995813"></a>  
    ![](figures/JDBCServer2x内存使用率统计-135.png "JDBCServer2x内存使用率统计-135")

3.  <a name="li1586716293291"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JDBCServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JDBCServer2x直接内存” ，单击“确定”，根据告警产生时间，查看对应时间段的“JDBCServer2x进程使用的直接内存”的值，获取最大值。

    **图 2**  JDBCServer2x直接内存<a name="fig3230350126"></a>  
    ![](figures/JDBCServer2x直接内存.png "JDBCServer2x直接内存")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“JDBCServer2x \> 性能”，“spark.driver.extraJavaOptions”参数中-XX:MaxDirectMemorySize的默认值为512M，可根据如下方案调整：告警时间段内JDBCServer2x使用的直接内存的最大值和“JDBCServer2x直接内存使用率统计 \(JDBCServer2x\)”阈值的比值。若参数值调整后，仍偶现告警，可以按0.5倍速率调大。若频繁出现告警，可以按1倍速率调大。建议不要超过“SPARK\_DRIVER\_MEMORY”的参数值。多业务量、高并发的情况可以考虑增加实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> JDBCServer2x直接内存使用率统计 \(JDBCServer2x\)”，可查看“阈值”。

5.  重启所有的JDBCServer2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li128333120587)。


**收集故障信息**

1.  <a name="li128333120587"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s7833451ce9564e0d8e771dfc18982cb8"></a>

无。

