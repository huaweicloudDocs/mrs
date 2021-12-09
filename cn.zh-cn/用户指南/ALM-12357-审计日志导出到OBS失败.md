# ALM-12357 审计日志导出到OBS失败<a name="alm_12357"></a>

## 告警解释<a name="zh-cn_topic_0191813876_section1610753917104"></a>

用户在MRS Manager界面配置审计日志导出OBS后，系统会周期性的将审计日志导出到OBS，当访问OBS失败时产生该告警。

导出成功后，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813876_section45831805171015"></a>

<a name="zh-cn_topic_0191813876_table75288017947"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813876_row859440417947"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813876_p2505811317947"><a name="zh-cn_topic_0191813876_p2505811317947"></a><a name="zh-cn_topic_0191813876_p2505811317947"></a><strong id="zh-cn_topic_0191813876_b2419642717947"><a name="zh-cn_topic_0191813876_b2419642717947"></a><a name="zh-cn_topic_0191813876_b2419642717947"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813876_p1375356417947"><a name="zh-cn_topic_0191813876_p1375356417947"></a><a name="zh-cn_topic_0191813876_p1375356417947"></a><strong id="zh-cn_topic_0191813876_b5667321217947"><a name="zh-cn_topic_0191813876_b5667321217947"></a><a name="zh-cn_topic_0191813876_b5667321217947"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813876_p2712746617947"><a name="zh-cn_topic_0191813876_p2712746617947"></a><a name="zh-cn_topic_0191813876_p2712746617947"></a><strong id="zh-cn_topic_0191813876_b4282061017947"><a name="zh-cn_topic_0191813876_b4282061017947"></a><a name="zh-cn_topic_0191813876_b4282061017947"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813876_row4984117717947"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813876_p1060356917947"><a name="zh-cn_topic_0191813876_p1060356917947"></a><a name="zh-cn_topic_0191813876_p1060356917947"></a>12357</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813876_p5358274517947"><a name="zh-cn_topic_0191813876_p5358274517947"></a><a name="zh-cn_topic_0191813876_p5358274517947"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813876_p4523506517947"><a name="zh-cn_topic_0191813876_p4523506517947"></a><a name="zh-cn_topic_0191813876_p4523506517947"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813876_section34160014171025"></a>

<a name="zh-cn_topic_0191813876_table2591060617947"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813876_row4753108817947"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813876_p2481289917947"><a name="zh-cn_topic_0191813876_p2481289917947"></a><a name="zh-cn_topic_0191813876_p2481289917947"></a><strong id="zh-cn_topic_0191813876_b2198950017947"><a name="zh-cn_topic_0191813876_b2198950017947"></a><a name="zh-cn_topic_0191813876_b2198950017947"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813876_p3631905817947"><a name="zh-cn_topic_0191813876_p3631905817947"></a><a name="zh-cn_topic_0191813876_p3631905817947"></a><strong id="zh-cn_topic_0191813876_b5843607417947"><a name="zh-cn_topic_0191813876_b5843607417947"></a><a name="zh-cn_topic_0191813876_b5843607417947"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813876_row5616262217947"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813876_p5287850117947"><a name="zh-cn_topic_0191813876_p5287850117947"></a><a name="zh-cn_topic_0191813876_p5287850117947"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813876_p5530020917947"><a name="zh-cn_topic_0191813876_p5530020917947"></a><a name="zh-cn_topic_0191813876_p5530020917947"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813876_row2793984117947"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813876_p4853462317947"><a name="zh-cn_topic_0191813876_p4853462317947"></a><a name="zh-cn_topic_0191813876_p4853462317947"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813876_p3899035717947"><a name="zh-cn_topic_0191813876_p3899035717947"></a><a name="zh-cn_topic_0191813876_p3899035717947"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813876_row1536889717947"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813876_p3692113517947"><a name="zh-cn_topic_0191813876_p3692113517947"></a><a name="zh-cn_topic_0191813876_p3692113517947"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813876_p3782196217947"><a name="zh-cn_topic_0191813876_p3782196217947"></a><a name="zh-cn_topic_0191813876_p3782196217947"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813876_section21969051171033"></a>

服务审计日志在系统本地最多保存7个压缩文件，如果该故障持续存在，本地服务审计日志可能会丢失。

管理审计日志每达到10万条会以文件形式转储到本地，存储在本地的文件最多保留50个，如果该故障持续存在，管理审计日志可能会丢失。

## 可能原因<a name="zh-cn_topic_0191813876_section43542384171038"></a>

-   无法连接OBS服务器。
-   指定的OBS文件系统不存在。
-   用户AK/SK信息失效。
-   本地OBS配置信息获取失败。

## 处理步骤<a name="zh-cn_topic_0191813876_section35154584171043"></a>

1.  登录OBS服务器，检查OBS服务器是否可以正常访问。
    -   是，执行[3](#zh-cn_topic_0191813876_li17073310143018)。
    -   否，执行[2](#zh-cn_topic_0191813876_li51875580143018)。

2.  <a name="zh-cn_topic_0191813876_li51875580143018"></a>联系运维人员恢复OBS，然后等任务再次启动后，检查告警是否恢复。
    -   是，执行完毕。
    -   否，执行[3](#zh-cn_topic_0191813876_li17073310143018)。

3.  <a name="zh-cn_topic_0191813876_li17073310143018"></a>在MRS Manager，单击“系统设置  \>  审计日志导出配置“，检查AK/SK信息、文件系统名和路径是否正确。
    -   是，执行[5](#zh-cn_topic_0191813876_li572522141314)。
    -   否，执行[4](#zh-cn_topic_0191813876_li52527297143018)。

4.  <a name="zh-cn_topic_0191813876_li52527297143018"></a>重新配置正确的导出信息，然后等任务再次启动后，检查告警是否恢复。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果希望及时核查故障是否恢复，可适当调整审计日志开始时间，设置开始时间为当前时间10分钟或30分钟之后，待任务启动并确认告警已恢复，再重新调整启动时间。

    -   是，执行完毕。
    -   否，执行[5](#zh-cn_topic_0191813876_li572522141314)。

5.  <a name="zh-cn_topic_0191813876_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813876_section5597720165321"></a>

无。

