# ALM-43008 JobHistory2x进程直接内存使用超出阈值<a name="ALM-43008"></a>

## 告警解释<a name="sd4a44f8becbc4c6da5595dcd761463b0"></a>

系统每30秒周期性检测JobHistory2x进程直接内存使用状态，当检测到JobHistory2x进程直接内存使用率超出阈值（最大内存的95%）时产生该告警。

## 告警属性<a name="s56696dba6d804cfab6443b5bb7e80bc9"></a>

<a name="t7a32d26aadff4f569a52ce2dae5dcb04"></a>
<table><thead align="left"><tr id="r598af654428d4605a5b61308e6dde344"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="afad47b78360c4d02a14257eb266ffd74"><a name="afad47b78360c4d02a14257eb266ffd74"></a><a name="afad47b78360c4d02a14257eb266ffd74"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a409694dff4234305b17e321eed124ef8"><a name="a409694dff4234305b17e321eed124ef8"></a><a name="a409694dff4234305b17e321eed124ef8"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="ab1387d0fd6794931b24f95406735c735"><a name="ab1387d0fd6794931b24f95406735c735"></a><a name="ab1387d0fd6794931b24f95406735c735"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="r7f5385bd9a4c4d5cb6f3e90e2f36261c"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="a6b1abe743c464087b4932a00d30aeb61"><a name="a6b1abe743c464087b4932a00d30aeb61"></a><a name="a6b1abe743c464087b4932a00d30aeb61"></a>43008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a278286834fdd4f8eaa344a65d118892e"><a name="a278286834fdd4f8eaa344a65d118892e"></a><a name="a278286834fdd4f8eaa344a65d118892e"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="ac16d4b5beb6b4ad395c6aff7433c8d3d"><a name="ac16d4b5beb6b4ad395c6aff7433c8d3d"></a><a name="ac16d4b5beb6b4ad395c6aff7433c8d3d"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s9aeb18861ba34fbabeb8ca4c56efaa9a"></a>

<a name="t6590fe2b227148c3a1fb9d390cf656f9"></a>
<table><thead align="left"><tr id="rb830e9472e0d4c9e867eedc295a17faa"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a29def5d79c8b4c668562a73fd2f47234"><a name="a29def5d79c8b4c668562a73fd2f47234"></a><a name="a29def5d79c8b4c668562a73fd2f47234"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="a2878a4765ff54e039995dbb7492dd17e"><a name="a2878a4765ff54e039995dbb7492dd17e"></a><a name="a2878a4765ff54e039995dbb7492dd17e"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row550193131310"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r986eb8e2fbb44ab1a2207b8084216f86"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a2d2982e2d28747d38292611fdcb5a27b"><a name="a2d2982e2d28747d38292611fdcb5a27b"></a><a name="a2d2982e2d28747d38292611fdcb5a27b"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r746fb7375f99417a89109e273ebe08d1"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a9a48d2c4ac8042ae8e0c2b78ecb11e54"><a name="a9a48d2c4ac8042ae8e0c2b78ecb11e54"></a><a name="a9a48d2c4ac8042ae8e0c2b78ecb11e54"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r49097e38ac0f4828b803acc93ffc606a"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ab890ccaff806492aa3798dbeae5c2161"><a name="ab890ccaff806492aa3798dbeae5c2161"></a><a name="ab890ccaff806492aa3798dbeae5c2161"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="r0bd8eeaf2fe4451b8eccfc807dc6f029"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a3b4e3ac57d614f8b9dca1db388bbe41b"><a name="a3b4e3ac57d614f8b9dca1db388bbe41b"></a><a name="a3b4e3ac57d614f8b9dca1db388bbe41b"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a0f6ddba9efb847528f89c674467eaa48"><a name="a0f6ddba9efb847528f89c674467eaa48"></a><a name="a0f6ddba9efb847528f89c674467eaa48"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="s70d934f61be748d7bba363b6d759423f"></a>

JobHistory2x进程直接内存使用率过高，会影响JobHistory2x进程运行的性能，甚至造成内存溢出导致JobHistory2x进程不可用。

## 可能原因<a name="s387d4fa92c644a8f876c3cd372445d1c"></a>

该节点JobHistory2x进程直接内存使用率过大，或配置的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="sebf77933862f453ea1eb16b7e4268e9b"></a>

检查直接内存使用率

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43008”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JobHistory2x内存使用率统计”，单击“确定”，查看JobHistory2x进程使用的直接内存是否已达到JobHistory2x进程设定的最大直接内存的阈值（默认95%）。

    -   是，执行[3](#li13835134472710)。
    -   否，执行[7](#li3188114513556)。

    **图 1**  JobHistory2x内存使用率统计<a name="fig174723591719"></a>  
    ![](figures/JobHistory2x内存使用率统计-96.png "JobHistory2x内存使用率统计-96")

3.  <a name="li13835134472710"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JobHistory2x直接内存”，单击“确定”，根据告警产生时间，查看对应时间段的“JobHistory2x进程使用的直接内存”的值，获取最大值。

    **图 2**  JobHistory2x直接内存<a name="fig162687514202"></a>  
    ![](figures/JobHistory2x直接内存.png "JobHistory2x直接内存")

4.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“JobHistory2x \> 默认”，“SPARK\_DAEMON\_JAVA\_OPTS”参数中“-XX:MaxDirectMemorySize”的默认值为512M，可根据如下原则调整: 告警时间段内JobHistory2x使用直接内存的最大值和“JobHistory2x直接内存使用率统计 \(JobHistory2x\)”阈值的比值。若参数值调整后，仍偶现告警，可以按0.5倍速率调大。若频繁出现告警，可以按1倍速率调大，建议不要超过参数SPARK\_DAEMON\_MEMORY的值。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \>_ 待操作集群名称_  \> Spark2x \> 内存 \> JobHistory2x直接内存使用率统计 \(JobHistory2x\)”，可查看“阈值”。

5.  重启所有的JobHistory2x实例。
6.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li3188114513556)。


收集故障信息

1.  <a name="li3188114513556"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s33aff0ddf721474ab93b4633c9243d9c"></a>

无。

