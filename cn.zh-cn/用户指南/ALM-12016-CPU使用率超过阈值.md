# ALM-12016 CPU使用率超过阈值<a name="ZH-CN_TOPIC_0093195029"></a>

## 告警解释<a name="zh-cn_topic_0035469888_section44995779104420"></a>

系统每30秒周期性检测CPU使用率，并把实际CPU使用率和阈值相比较。CPU使用率默认提供一个阈值。当检测到CPU使用率连续多次（可配置，默认值为10）超过该阈值时产生该告警。

当平均CPU使用率小于或等于阈值的90%时，告警恢复。

## **告警属性**<a name="zh-cn_topic_0035469888_section58728046104442"></a>

<a name="zh-cn_topic_0035469888_table17210170104414"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035469888_row57423022104414"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035469888_p20753233104414"><a name="zh-cn_topic_0035469888_p20753233104414"></a><a name="zh-cn_topic_0035469888_p20753233104414"></a><strong id="zh-cn_topic_0035469888_b52561371104414"><a name="zh-cn_topic_0035469888_b52561371104414"></a><a name="zh-cn_topic_0035469888_b52561371104414"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035469888_p29612629104414"><a name="zh-cn_topic_0035469888_p29612629104414"></a><a name="zh-cn_topic_0035469888_p29612629104414"></a><strong id="zh-cn_topic_0035469888_b65187071104414"><a name="zh-cn_topic_0035469888_b65187071104414"></a><a name="zh-cn_topic_0035469888_b65187071104414"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035469888_p45661403104414"><a name="zh-cn_topic_0035469888_p45661403104414"></a><a name="zh-cn_topic_0035469888_p45661403104414"></a><strong id="zh-cn_topic_0035469888_b8299447104414"><a name="zh-cn_topic_0035469888_b8299447104414"></a><a name="zh-cn_topic_0035469888_b8299447104414"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035469888_row7586159104414"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035469888_p10499172104414"><a name="zh-cn_topic_0035469888_p10499172104414"></a><a name="zh-cn_topic_0035469888_p10499172104414"></a>12016</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035469888_p45126626104414"><a name="zh-cn_topic_0035469888_p45126626104414"></a><a name="zh-cn_topic_0035469888_p45126626104414"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035469888_p31378064104414"><a name="zh-cn_topic_0035469888_p31378064104414"></a><a name="zh-cn_topic_0035469888_p31378064104414"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035469888_section62831052104450"></a>

<a name="zh-cn_topic_0035469888_table57594954104414"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035469888_row48560076104414"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035469888_p41052101104414"><a name="zh-cn_topic_0035469888_p41052101104414"></a><a name="zh-cn_topic_0035469888_p41052101104414"></a><strong id="zh-cn_topic_0035469888_b33924590104414"><a name="zh-cn_topic_0035469888_b33924590104414"></a><a name="zh-cn_topic_0035469888_b33924590104414"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035469888_p63537230104414"><a name="zh-cn_topic_0035469888_p63537230104414"></a><a name="zh-cn_topic_0035469888_p63537230104414"></a><strong id="zh-cn_topic_0035469888_b34964159104414"><a name="zh-cn_topic_0035469888_b34964159104414"></a><a name="zh-cn_topic_0035469888_b34964159104414"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035469888_row46241978104414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035469888_p54612763104414"><a name="zh-cn_topic_0035469888_p54612763104414"></a><a name="zh-cn_topic_0035469888_p54612763104414"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035469888_p61557721104414"><a name="zh-cn_topic_0035469888_p61557721104414"></a><a name="zh-cn_topic_0035469888_p61557721104414"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035469888_row17148582104414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035469888_p46857914104414"><a name="zh-cn_topic_0035469888_p46857914104414"></a><a name="zh-cn_topic_0035469888_p46857914104414"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035469888_p37394653104414"><a name="zh-cn_topic_0035469888_p37394653104414"></a><a name="zh-cn_topic_0035469888_p37394653104414"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035469888_row1007565104414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035469888_p14503949104414"><a name="zh-cn_topic_0035469888_p14503949104414"></a><a name="zh-cn_topic_0035469888_p14503949104414"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035469888_p33969201104414"><a name="zh-cn_topic_0035469888_p33969201104414"></a><a name="zh-cn_topic_0035469888_p33969201104414"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035469888_row37287356104414"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035469888_p377010104414"><a name="zh-cn_topic_0035469888_p377010104414"></a><a name="zh-cn_topic_0035469888_p377010104414"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035469888_p30537856104414"><a name="zh-cn_topic_0035469888_p30537856104414"></a><a name="zh-cn_topic_0035469888_p30537856104414"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035469888_section49050226104458"></a>

业务进程响应缓慢或不可用。

## 可能原因<a name="zh-cn_topic_0035469888_section10569495104528"></a>

-   告警阈值配置或者平滑次数配置不合理。
-   CPU配置无法满足业务需求，CPU使用率达到上限。

## 处理步骤<a name="zh-cn_topic_0035469888_section38136361104545"></a>

1.  检查告警阈值配置或者平滑次数配置是否合理。
    1.  登录MRS Manager，基于实际CPU使用情况，修改告警阈值和平滑次数配置项。
    2.  根据实际服务的使用情况在“系统设置 \> 阈值配置 \> 设备 \> 主机 \> CPU \> CPU使用率 \> CPU使用率”中更改告警阈值。
    3.  根据实际服务的使用情况在“系统设置 \> 阈值配置 \> 设备 \> 主机 \> CPU \> CPU使用率 \> CPU使用率”中更改告警的“平滑次数”选项。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >该选项的含义为告警检查阶段，“频率”为告警检查周期，“平滑次数”为告警连续检查多少次超过阈值，则发送告警。  

    4.  等待2分钟，查看告警是否自动恢复。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0035469888_li23374914104744)。


2.  <a name="zh-cn_topic_0035469888_li23374914104744"></a>对系统进行扩容。
    1.  打开MRS Manager页面，在告警列表中，单击此告警所在行，在告警详情中，查看该告警的节点地址。
    2.  登录告警节点。
    3.  执行**cat /proc/stat | awk 'NR==1'|awk '\{for\(i=2;i<=NF;i++\)j+=$i;print "" 100 - \($5+$6\) \* 100 / j;\}'**命令，查看系统当前CPU使用率。
    4.  若CPU使用率超过阈值，扩容CPU。
    5.  检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0035469888_li32413777102351)。


3.  <a name="zh-cn_topic_0035469888_li32413777102351"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## **参考信息**<a name="zh-cn_topic_0035469888_section13081136172452"></a>

无。

