# ALM-43009 JobHistory2x进程GC时间超出阈值<a name="ALM-43009"></a>

## 告警解释<a name="s12fb9632716f495a8fceefb4ce14b24b"></a>

系统每60秒周期性检测JobHistory2x进程的GC时间，当检测到JobHistory2x进程的GC时间超出阈值（连续3次检测超过12秒）时产生该告警。用户可通过“运维 \>告警 \> 阈值设置 \>  _待操作集群的名称_  \> Spark2x \> GC时间 \> JobHistory2x的总GC时间”修改阈值。当JobHistory2x进程 GC时间小于或等于阈值时，告警恢复。

## 告警属性<a name="s06229c48076c4f6ca6220582fc142871"></a>

<a name="t080e9f87af4841efba6f7d699479e85d"></a>
<table><thead align="left"><tr id="rf5d4b0ff1a1644708cc37464deb323b1"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="ab0459e0102c740de9107bda13efc3e97"><a name="ab0459e0102c740de9107bda13efc3e97"></a><a name="ab0459e0102c740de9107bda13efc3e97"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a7a384de064cf4f86a52684a5e46ca987"><a name="a7a384de064cf4f86a52684a5e46ca987"></a><a name="a7a384de064cf4f86a52684a5e46ca987"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="a492f57f372a5459f9e9783d6be9241f8"><a name="a492f57f372a5459f9e9783d6be9241f8"></a><a name="a492f57f372a5459f9e9783d6be9241f8"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="raaad36490869425b8d1cca71ffd8794c"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="accd7dfa6a8564302b1bbb5cc6abb802b"><a name="accd7dfa6a8564302b1bbb5cc6abb802b"></a><a name="accd7dfa6a8564302b1bbb5cc6abb802b"></a>43009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a883e0813aa344689ae669d82ab3dfe2a"><a name="a883e0813aa344689ae669d82ab3dfe2a"></a><a name="a883e0813aa344689ae669d82ab3dfe2a"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="acb6cb271d487430d99f950f1e6e33669"><a name="acb6cb271d487430d99f950f1e6e33669"></a><a name="acb6cb271d487430d99f950f1e6e33669"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s185a9d9d31384ec59262d93974a97de6"></a>

<a name="t5114614edf8749929f4458729cc7f6c2"></a>
<table><thead align="left"><tr id="r3c9be5983b7a43c78b6d7bc171427942"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a8c201b5b8f194035bbce281897624f91"><a name="a8c201b5b8f194035bbce281897624f91"></a><a name="a8c201b5b8f194035bbce281897624f91"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="a00bd2e0666284d4a989807d845ffc11a"><a name="a00bd2e0666284d4a989807d845ffc11a"></a><a name="a00bd2e0666284d4a989807d845ffc11a"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row8265958191219"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r37b5d5a252854719b47b485621615e42"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a243b2e7e5c514a6f84aa73f4338ffacc"><a name="a243b2e7e5c514a6f84aa73f4338ffacc"></a><a name="a243b2e7e5c514a6f84aa73f4338ffacc"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="ra8d625fccbc4419d8964118488600058"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ae37c8e11c77e48669347f9962c0b5aac"><a name="ae37c8e11c77e48669347f9962c0b5aac"></a><a name="ae37c8e11c77e48669347f9962c0b5aac"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="re2ba32fd2b684781baa20342df0d233e"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a616b75e3fa5049c18cbf049984685012"><a name="a616b75e3fa5049c18cbf049984685012"></a><a name="a616b75e3fa5049c18cbf049984685012"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="rcbc682d3e1f7459d959bb546736d1ec2"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a8c10fb3c71a645939f831163e5efbae0"><a name="a8c10fb3c71a645939f831163e5efbae0"></a><a name="a8c10fb3c71a645939f831163e5efbae0"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="ab40d216cc9fc4b92aff9393d8c81a25a"><a name="ab40d216cc9fc4b92aff9393d8c81a25a"></a><a name="ab40d216cc9fc4b92aff9393d8c81a25a"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="s19c3f09bba9c4ebca0401a75acc9692f"></a>

GC时间超出阈值，会影响JobHistory2x进程运行的性能，甚至造成JobHistory2x进程不可用。

## 可能原因<a name="s654d4ddbd51d4b05bb7c7ace547ae836"></a>

该节点JobHistory2x进程堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="sd9c42fe7fabc43e78e490a45239d1bfc"></a>

检查GC时间

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43009”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的JobHistory2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> JobHistory2x的GC时间”，单击“确定”，查看JobHistory2x进程的GC时间是否大于阈值（默认12秒）。

    -   是，执行[3](#li17251131385614)。
    -   否，执行[6](#li532493465617)。

    **图 1**  JobHistory2x的GC时间<a name="fig712613181216"></a>  
    ![](figures/JobHistory2x的GC时间.png "JobHistory2x的GC时间")

3.  <a name="li17251131385614"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“JobHistory2x \> 默认”，将“SPARK\_DAEMON\_MEMORY”参数的值根据如下原则调整：“SPARK\_DAEMON\_MEMORY”参数默认值为4G，若偶现告警，可以按0.5倍速率调大。若告警次数比较频繁，可以按1倍速率调大。
4.  重启所有的JobHistory2x实例。
5.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li532493465617)。


收集故障信息

1.  <a name="li532493465617"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895574.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s108ff0c97f52428096e3703b205a2e8a"></a>

无。

