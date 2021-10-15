# ALM-18006 执行MapReduce任务超时<a name="alm_18006"></a>

## 告警解释<a name="zh-cn_topic_0191813946_section6587942"></a>

告警模块每30秒周期性检测MapReduce任务。任务提交后，当检测到MapReduce任务执行时间超过指定时间时，产生该告警。

该告警需要手动清除。

## 告警属性<a name="zh-cn_topic_0191813946_section59291480"></a>

<a name="zh-cn_topic_0191813946_table58038438"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813946_row33645886"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813946_p40962215"><a name="zh-cn_topic_0191813946_p40962215"></a><a name="zh-cn_topic_0191813946_p40962215"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813946_p29605080"><a name="zh-cn_topic_0191813946_p29605080"></a><a name="zh-cn_topic_0191813946_p29605080"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813946_p49201274"><a name="zh-cn_topic_0191813946_p49201274"></a><a name="zh-cn_topic_0191813946_p49201274"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813946_row25880244"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813946_p15925039"><a name="zh-cn_topic_0191813946_p15925039"></a><a name="zh-cn_topic_0191813946_p15925039"></a>18006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813946_p14859795"><a name="zh-cn_topic_0191813946_p14859795"></a><a name="zh-cn_topic_0191813946_p14859795"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813946_p62792710"><a name="zh-cn_topic_0191813946_p62792710"></a><a name="zh-cn_topic_0191813946_p62792710"></a>否</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813946_section63861276"></a>

<a name="zh-cn_topic_0191813946_table53044787"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813946_row2530563"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813946_p3649016"><a name="zh-cn_topic_0191813946_p3649016"></a><a name="zh-cn_topic_0191813946_p3649016"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813946_p27134857"><a name="zh-cn_topic_0191813946_p27134857"></a><a name="zh-cn_topic_0191813946_p27134857"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813946_row50439840"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813946_p59095202"><a name="zh-cn_topic_0191813946_p59095202"></a><a name="zh-cn_topic_0191813946_p59095202"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813946_p21982073"><a name="zh-cn_topic_0191813946_p21982073"></a><a name="zh-cn_topic_0191813946_p21982073"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813946_row63620936"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813946_p53022201"><a name="zh-cn_topic_0191813946_p53022201"></a><a name="zh-cn_topic_0191813946_p53022201"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813946_p66939890"><a name="zh-cn_topic_0191813946_p66939890"></a><a name="zh-cn_topic_0191813946_p66939890"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813946_row65588106"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813946_p11036355"><a name="zh-cn_topic_0191813946_p11036355"></a><a name="zh-cn_topic_0191813946_p11036355"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813946_p21529561"><a name="zh-cn_topic_0191813946_p21529561"></a><a name="zh-cn_topic_0191813946_p21529561"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813946_row59548322"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813946_p58684749"><a name="zh-cn_topic_0191813946_p58684749"></a><a name="zh-cn_topic_0191813946_p58684749"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813946_p55844233"><a name="zh-cn_topic_0191813946_p55844233"></a><a name="zh-cn_topic_0191813946_p55844233"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813946_section37880580"></a>

提交的MapReduce任务执行超时，所以无执行结果返回。故障修复后重新执行该任务。

## 可能原因<a name="zh-cn_topic_0191813946_section5380904"></a>

执行MapReduce任务需要较长时间。但指定的时间少于所需的执行时间。

## 处理步骤<a name="zh-cn_topic_0191813946_section48428136"></a>

1.  检查时间是否正确设置。

    把“-Dapplication.timeout.interval”设置成较大的值，或者不对参数进行设置。查看MapReduce任务是否能成功执行。

    -   是，执行[2.e](#zh-cn_topic_0191813946_clean)。
    -   否，执行[2.b](#zh-cn_topic_0191813946_substep_03d21a89)。

2.  检查Yarn服务状态。
    1.  登录MRS集群详情页面，选择“告警管理”。
    2.  <a name="zh-cn_topic_0191813946_substep_03d21a89"></a>在告警列表中，查看是否有“ALM-18000 Yarn服务不可用”产生。
        -   是，执行[2.c](#zh-cn_topic_0191813946_substep_03d82569)。
        -   否，执行[3](#zh-cn_topic_0191813946_li12092809151957)。

    3.  <a name="zh-cn_topic_0191813946_substep_03d82569"></a>参考[ALM-18000 Yarn服务不可用](ALM-18000-Yarn服务不可用.md)的处理步骤处理该故障。
    4.  再次执行MapReduce任务命令，查看MapReduce任务是否能成功执行。
        -   是，执行[2.e](#zh-cn_topic_0191813946_clean)。
        -   否，执行[4](#zh-cn_topic_0191813946_li572522141314)。

    5.  <a name="zh-cn_topic_0191813946_clean"></a>在告警列表中，单击该告警“操作”列下面的![](figures/icon_mrs_almOpretion.png)，手动清除告警。操作结束。

3.  <a name="zh-cn_topic_0191813946_li12092809151957"></a>调整超时阈值。

    在MRS Manager界面，单击“系统设置 \> 阈值配置 \> 服务 \> Yarn \> 超时的任务”，增大当前阈值规则的允许超时的任务个数，然后查看本告警是否消除。

    -   是，处理完毕。
    -   否，执行[4](#zh-cn_topic_0191813946_li572522141314)。

4.  <a name="zh-cn_topic_0191813946_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813946_section33200047"></a>

无。

