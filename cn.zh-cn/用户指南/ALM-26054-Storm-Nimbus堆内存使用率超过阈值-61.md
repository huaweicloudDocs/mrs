# ALM-26054 Storm Nimbus堆内存使用率超过阈值<a name="ZH-CN_TOPIC_0174499379"></a>

## 告警解释<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section52867048175622"></a>

系统每30秒周期性检测Storm Nimbus堆内存使用率，并把实际的Storm Nimbus堆内存使用率和阈值相比较。当Storm Nimbus堆内存使用率超出阈值（默认值为80%）时产生该告警。

用户可通过“系统设置 \> 阈值配置 \> 服务 \> Storm“修改阈值。

当Storm Nimbus堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section42094531175622"></a>

<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_table54213857175622"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row20974176175622"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21186672175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21186672175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21186672175622"></a><strong id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b56462325175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b56462325175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b56462325175622"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10045613175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10045613175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10045613175622"></a><strong id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b23301658175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b23301658175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b23301658175622"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p8386180175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p8386180175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p8386180175622"></a><strong id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b8366763175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b8366763175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b8366763175622"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row6619201175622"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5823288181035"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5823288181035"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5823288181035"></a>26054</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p1924359181035"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p1924359181035"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p1924359181035"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21655423181035"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21655423181035"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21655423181035"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section21896613175622"></a>

<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_table28795258175622"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row61056662175622"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p46642608175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p46642608175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p46642608175622"></a><strong id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b17130291175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b17130291175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b17130291175622"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p45376322175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p45376322175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p45376322175622"></a><strong id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b5733721175622"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b5733721175622"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_b5733721175622"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row61778232175622"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21304470181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21304470181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p21304470181047"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p47940503181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p47940503181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p47940503181047"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row39212469175622"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52017453181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52017453181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52017453181047"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52664204181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52664204181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p52664204181047"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row67081279175622"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5935158181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5935158181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p5935158181047"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10985805181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10985805181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p10985805181047"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_row36970648181040"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p22697645181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p22697645181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p22697645181047"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p26569958181047"><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p26569958181047"></a><a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_p26569958181047"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section48891955175622"></a>

Storm Nimbus堆内存使用率过高时，可能造成频繁的内存垃圾回收，甚至造成内存溢出，进而影响Storm任务提交。

## 可能原因<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section7429107175622"></a>

该节点Storm Nimbus实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section51268453175622"></a>

1.  检查堆内存使用量。
    1.  在MRS Manager首页，单击“告警管理 \> ALM-26054 Storm Nimbus堆内存使用率超过阈值 \> 定位信息“，查看告警上报的实例的HostName。
    2.  在MRS Manager首页，单击“服务管理 \> Storm \> 实例 \> Nimbus（对应上报告警实例HostName） \> 定制 \> Nimbus堆内存使用率“，查看堆内存使用情况。
    3.  查看Nimbus使用的堆内存是否已达到Nimbus设定的最大堆内存的80%。
        -   是，执行[1.d](#zh-cn_topic_0093195078_zh-cn_topic_0053790968_li3532012320227)。
        -   否，执行[2.a](#zh-cn_topic_0093195078_zh-cn_topic_0053790968_li19762023183457)。

    4.  <a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_li3532012320227"></a>调整堆内存。

        在MRS Manager首页，单击“服务管理 \> Storm \> 服务配置 \> 全部配置 \> Nimbus \> 系统“。将“NIMBUS\_GC\_OPTS“参数中“-Xmx“的值根据实际情况调大，然后单击“保存配置“，勾选“重新启动角色实例。“，单击“确定“进行重启。

    5.  观察Manager告警是否清除。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0093195078_zh-cn_topic_0053790968_li19762023183457)。

2.  收集故障信息。
    1.  <a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_li19762023183457"></a>在MRS Manager界面，单击“系统设置 \> 日志导出“。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195078_zh-cn_topic_0053790968_section19043946175622"></a>

无。

