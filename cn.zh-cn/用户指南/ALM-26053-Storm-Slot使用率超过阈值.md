# ALM-26053 Storm Slot使用率超过阈值<a name="ALM-26053"></a>

## 告警解释<a name="section6263908"></a>

系统每60秒周期性检测Slot使用率，并把实际Slot使用率和阈值相比较。当检测到Slot使用率高于阈值时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置”修改阈值。

当Slot使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section56375177"></a>

<a name="table64534230"></a>
<table><thead align="left"><tr id="row17026550"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p36973338"><a name="p36973338"></a><a name="p36973338"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p42050402"><a name="p42050402"></a><a name="p42050402"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50639415"><a name="p50639415"></a><a name="p50639415"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row8151936"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56327078"><a name="p56327078"></a><a name="p56327078"></a>26053</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p66199440"><a name="p66199440"></a><a name="p66199440"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p60554406"><a name="p60554406"></a><a name="p60554406"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section37614552"></a>

<a name="table5959890"></a>
<table><thead align="left"><tr id="row6667445"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p3192147"><a name="p3192147"></a><a name="p3192147"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p57237321"><a name="p57237321"></a><a name="p57237321"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row16365920141419"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row5711424"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p25909327"><a name="p25909327"></a><a name="p25909327"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row31857357"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39119049"><a name="p39119049"></a><a name="p39119049"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row16527122"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p53634862"><a name="p53634862"></a><a name="p53634862"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row12951716"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42456086"><a name="p42456086"></a><a name="p42456086"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p16390965"><a name="p16390965"></a><a name="p16390965"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2986648"></a>

用户无法执行新的Storm任务。

## 可能原因<a name="section26879835"></a>

-   集群中Supervisor处于异常状态。
-   集群中Supervisor的状态正常，但是处理能力不足。

## 处理步骤<a name="section40591931"></a>

**检查Supervisor状态**

1.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> 实例”，进入Storm实例管理页面。
2.  查看是否存在状态为“故障“或者是“正在恢复“的Supervisor实例。
    -   是，执行[3](#li1143121620331)。
    -   否，执行[5](#li2810132020331)。

3.  <a name="li1143121620331"></a>勾选状态为“故障“或者“正在恢复“的Supervisor角色实例，选择“更多 \> 重启实例”，查看是否重启成功。
    -   是，执行[4](#li1803544920331)。
    -   否，执行[10](#li3267726620331)。

4.  <a name="li1803544920331"></a>等待一段时间，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li2810132020331)。


**增加Supervisor Slot数量配置。**

1.  <a name="li2810132020331"></a>登录FusionInsight Manager管理界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> 配置 \> 全部配置”。
2.  适当增加每个Supervisor角色“supervisor.slots.ports”参数中的端口号数量，并重启实例。
3.  等待一段时间，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[8](#li2868126920331)。


1.  <a name="li2868126920331"></a>对Supervisor进行扩容。
2.  等待一段时间，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[10](#li3267726620331)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >Supervisor重启过程中，业务会出现中断，待Supervisor重启成功后业务恢复。



**收集故障信息。**

1.  <a name="li3267726620331"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”勾选待操作集群的“Storm”和“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section29783064"></a>

无。

