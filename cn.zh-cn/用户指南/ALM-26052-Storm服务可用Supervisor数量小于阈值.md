# ALM-26052 Storm服务可用Supervisor数量小于阈值<a name="ZH-CN_TOPIC_0093195076"></a>

## 告警解释<a name="zh-cn_topic_0053790966_section65438733175616"></a>

系统每60秒周期性检测Supervisor数量，并把实际Supervisor数量和阈值相比较。当检测到Supervisor数量低于阈值时产生该告警。

用户可通过“系统设置 \> 阈值配置“修改阈值。

当Supervisor数量大于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0053790966_section48127703175616"></a>

<a name="zh-cn_topic_0053790966_table6029859175616"></a>
<table><thead align="left"><tr id="zh-cn_topic_0053790966_row66041856175616"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0053790966_p47790158175616"><a name="zh-cn_topic_0053790966_p47790158175616"></a><a name="zh-cn_topic_0053790966_p47790158175616"></a><strong id="zh-cn_topic_0053790966_b27458243175616"><a name="zh-cn_topic_0053790966_b27458243175616"></a><a name="zh-cn_topic_0053790966_b27458243175616"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0053790966_p9525223175616"><a name="zh-cn_topic_0053790966_p9525223175616"></a><a name="zh-cn_topic_0053790966_p9525223175616"></a><strong id="zh-cn_topic_0053790966_b18618143175616"><a name="zh-cn_topic_0053790966_b18618143175616"></a><a name="zh-cn_topic_0053790966_b18618143175616"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0053790966_p31674610175616"><a name="zh-cn_topic_0053790966_p31674610175616"></a><a name="zh-cn_topic_0053790966_p31674610175616"></a><strong id="zh-cn_topic_0053790966_b16636039175616"><a name="zh-cn_topic_0053790966_b16636039175616"></a><a name="zh-cn_topic_0053790966_b16636039175616"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0053790966_row5341908175616"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0053790966_p1273205618542"><a name="zh-cn_topic_0053790966_p1273205618542"></a><a name="zh-cn_topic_0053790966_p1273205618542"></a>26052</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0053790966_p2466361218542"><a name="zh-cn_topic_0053790966_p2466361218542"></a><a name="zh-cn_topic_0053790966_p2466361218542"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0053790966_p5159558518542"><a name="zh-cn_topic_0053790966_p5159558518542"></a><a name="zh-cn_topic_0053790966_p5159558518542"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0053790966_section25180541175616"></a>

<a name="zh-cn_topic_0053790966_table26357972175616"></a>
<table><thead align="left"><tr id="zh-cn_topic_0053790966_row23116700175616"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0053790966_p60513421175616"><a name="zh-cn_topic_0053790966_p60513421175616"></a><a name="zh-cn_topic_0053790966_p60513421175616"></a><strong id="zh-cn_topic_0053790966_b7749881175616"><a name="zh-cn_topic_0053790966_b7749881175616"></a><a name="zh-cn_topic_0053790966_b7749881175616"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0053790966_p23760638175616"><a name="zh-cn_topic_0053790966_p23760638175616"></a><a name="zh-cn_topic_0053790966_p23760638175616"></a><strong id="zh-cn_topic_0053790966_b12519152175616"><a name="zh-cn_topic_0053790966_b12519152175616"></a><a name="zh-cn_topic_0053790966_b12519152175616"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0053790966_row7418419175616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790966_p2087641818550"><a name="zh-cn_topic_0053790966_p2087641818550"></a><a name="zh-cn_topic_0053790966_p2087641818550"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790966_p1326827918550"><a name="zh-cn_topic_0053790966_p1326827918550"></a><a name="zh-cn_topic_0053790966_p1326827918550"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0053790966_row30682157175616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790966_p889946618550"><a name="zh-cn_topic_0053790966_p889946618550"></a><a name="zh-cn_topic_0053790966_p889946618550"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790966_p4976812318550"><a name="zh-cn_topic_0053790966_p4976812318550"></a><a name="zh-cn_topic_0053790966_p4976812318550"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0053790966_row12742758175616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790966_p4217574618550"><a name="zh-cn_topic_0053790966_p4217574618550"></a><a name="zh-cn_topic_0053790966_p4217574618550"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790966_p6079225018550"><a name="zh-cn_topic_0053790966_p6079225018550"></a><a name="zh-cn_topic_0053790966_p6079225018550"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0053790966_row598874311860"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0053790966_p22516311866"><a name="zh-cn_topic_0053790966_p22516311866"></a><a name="zh-cn_topic_0053790966_p22516311866"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0053790966_p308264801866"><a name="zh-cn_topic_0053790966_p308264801866"></a><a name="zh-cn_topic_0053790966_p308264801866"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0053790966_section22579298175616"></a>

-   集群已经存在的任务无法运行。
-   集群可接收新的Storm任务，但是无法运行。

## 可能原因<a name="zh-cn_topic_0053790966_section18637087175616"></a>

集群中Supervisor处于异常状态。

## 处理步骤<a name="zh-cn_topic_0053790966_section66322784175616"></a>

1.  检查Supervisor状态。
    1.  选择“服务管理 \> Storm \> Supervisor“，进入Storm服务管理页面。
    2.  查看“角色“中是否存在状态为故障或者是恢复中的Supervisor实例。
        -   是，执行[1.c](#zh-cn_topic_0053790966_li65587069184020)。
        -   否，执行[2.a](#zh-cn_topic_0053790966_li5355854118406)。

    3.  <a name="zh-cn_topic_0053790966_li65587069184020"></a>勾选状态为“故障“或者“恢复中“的Supervisor角色实例，选择“更多 \> 重启实例“，查看是否重启成功。
        -   是，执行[1.d](#zh-cn_topic_0053790966_li52566748184020)。
        -   否，执行[2.a](#zh-cn_topic_0053790966_li5355854118406)。

    4.  <a name="zh-cn_topic_0053790966_li52566748184020"></a>等待30秒，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0053790966_li5355854118406)。


2.  收集故障信息。
    1.  <a name="zh-cn_topic_0053790966_li5355854118406"></a>在MRS Manager界面，单击“系统设置 \> 日志导出“。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0053790966_section51573706175616"></a>

无。

