# ALM-12027 主机PID使用率超过阈值<a name="ALM-12027"></a>

## 告警解释<a name="section46043251"></a>

系统每30秒周期性检测PID使用率，并把实际PID使用率和阈值进行比较，PID使用率默认提供一个阈值。当检测到PID使用率超出阈值时产生该告警。

平滑次数为1，主机PID使用率小于或等于阈值时，告警恢复；平滑次数大于1，主机PID使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section11736077"></a>

<a name="table55804946"></a>
<table><thead align="left"><tr id="row18735406"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41172942"><a name="p41172942"></a><a name="p41172942"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p46674023"><a name="p46674023"></a><a name="p46674023"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p22499488"><a name="p22499488"></a><a name="p22499488"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row10519201"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46748947"><a name="p46748947"></a><a name="p46748947"></a>12027</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p28568349"><a name="p28568349"></a><a name="p28568349"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p32334952"><a name="p32334952"></a><a name="p32334952"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section38515830"></a>

<a name="table1885468"></a>
<table><thead align="left"><tr id="row1397439"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p46083715"><a name="p46083715"></a><a name="p46083715"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p41793428"><a name="p41793428"></a><a name="p41793428"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row411915211413"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row29824473"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66972090"><a name="p66972090"></a><a name="p66972090"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56030241"><a name="p56030241"></a><a name="p56030241"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row34510121"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p43856401"><a name="p43856401"></a><a name="p43856401"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62707569"><a name="p62707569"></a><a name="p62707569"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row27497214"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p12681862"><a name="p12681862"></a><a name="p12681862"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20597915"><a name="p20597915"></a><a name="p20597915"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row51163509"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p50603592"><a name="p50603592"></a><a name="p50603592"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5250267"><a name="p5250267"></a><a name="p5250267"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section11098151"></a>

无法分配PID给新的业务进程，业务进程不可用。

## 可能原因<a name="section32774497"></a>

节点同时运行的进程过多，需要扩展pid\_max值。

## 处理步骤<a name="section26535021"></a>

**扩展pid\_max值。**

1.  打开FusionInsight Manager页面，在实时告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，获取告警所在主机IP地址。
2.  以**root**用户登录告警所在主机，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行命令**cat /proc/sys/kernel/pid\_max**，查看系统当前运行的PID最大值pid\_max。
4.  若PID使用率超过阈值，将pid\_max值增大一倍，执行命令**echo **_新pid\_max__值 _**\> /proc/sys/kernel/pid\_max**。

    示例：**echo 65536 \> /proc/sys/kernel/pid\_max**

5.  等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[6](#li651285989611)。


**收集故障信息。**

1.  <a name="li651285989611"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选所有服务，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895796.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后30分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section37488605"></a>

无。

