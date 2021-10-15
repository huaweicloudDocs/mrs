# ALM-26052 Storm服务可用Supervisor数量小于阈值<a name="ALM-26052"></a>

## 告警解释<a name="section26885712"></a>

系统每60秒周期性检测Supervisor数量，并把实际Supervisor数量和阈值相比较。当检测到Supervisor数量低于阈值时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_”修改阈值。

当Supervisor数量大于或等于阈值时，告警恢复。

## 告警属性<a name="section40644822"></a>

<a name="table56150510"></a>
<table><thead align="left"><tr id="row55952213"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p35835398"><a name="p35835398"></a><a name="p35835398"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p16986091"><a name="p16986091"></a><a name="p16986091"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p33696108"><a name="p33696108"></a><a name="p33696108"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row45030259"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p23572325"><a name="p23572325"></a><a name="p23572325"></a>26052</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p30310188"><a name="p30310188"></a><a name="p30310188"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p39206192"><a name="p39206192"></a><a name="p39206192"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section30259081"></a>

<a name="table21584984"></a>
<table><thead align="left"><tr id="row40213994"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p36108061"><a name="p36108061"></a><a name="p36108061"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p39071800"><a name="p39071800"></a><a name="p39071800"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row9753628181415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row10699236"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1818637"><a name="p1818637"></a><a name="p1818637"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row16367739"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p14559137"><a name="p14559137"></a><a name="p14559137"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row63923375"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p37975429"><a name="p37975429"></a><a name="p37975429"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row6234548"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35236355"><a name="p35236355"></a><a name="p35236355"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p35572495"><a name="p35572495"></a><a name="p35572495"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section3896274"></a>

集群已经存在的任务无法运行；集群可接收新的Storm任务，但是无法运行。

## 可能原因<a name="section35066466"></a>

集群中Supervisor处于异常状态。

## 处理步骤<a name="section47162738"></a>

**检查Supervisor状态**

1.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> Supervisor”，进入Storm服务管理页面。
2.  查看“角色”中是否存在状态为故障或者是正在恢复的Supervisor实例。
    -   是，执行[3](#li6288877320930)。
    -   否，执行[5](#li4115026220930)。

3.  <a name="li6288877320930"></a>勾选状态为故障或者正在恢复的Supervisor角色实例，选择“更多 \> 重启实例”，查看是否重启成功。
    -   是，执行[4](#li4931149420930)。
    -   否，执行[5](#li4115026220930)。

4.  <a name="li4931149420930"></a>等待30秒，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li4115026220930)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >Supervisor重启过程中，业务会出现中断，待Supervisor重启成功后业务恢复。



**收集故障信息**

1.  <a name="li4115026220930"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Storm”和“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section21811459"></a>

无。

