# ALM-25500 KrbServer服务不可用<a name="ALM-25500"></a>

## 告警解释<a name="section49916765"></a>

系统按30秒周期性检测组件KrbServer的服务状态。当检测到组件KrbServer服务异常时产生该告警。

当检测到组件KrbServer服务恢复时告警恢复。

## 告警属性<a name="section46597704"></a>

<a name="table36235966"></a>
<table><thead align="left"><tr id="row54453757"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p48678192"><a name="p48678192"></a><a name="p48678192"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p50619488"><a name="p50619488"></a><a name="p50619488"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p6537844"><a name="p6537844"></a><a name="p6537844"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row59803349"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p12233066"><a name="p12233066"></a><a name="p12233066"></a>25500</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p51354267"><a name="p51354267"></a><a name="p51354267"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66054994"><a name="p66054994"></a><a name="p66054994"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section16726155"></a>

<a name="table48854260"></a>
<table><thead align="left"><tr id="row53611547"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p47568052"><a name="p47568052"></a><a name="p47568052"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p27807038"><a name="p27807038"></a><a name="p27807038"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row19673103910142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row37777633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26016911"><a name="p26016911"></a><a name="p26016911"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row32825611"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p16495358"><a name="p16495358"></a><a name="p16495358"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row14240500"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p16386848"><a name="p16386848"></a><a name="p16386848"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section16317671"></a>

告警发生时，不能对集群中的组件KrbServer进行任何操作。其它组件的KrbServer认证将受影响。集群中依赖KrbServer的组件运行状态将为故障。

## 可能原因<a name="section12641318"></a>

-   组件KrbServer服务所在节点故障。
-   OLdap服务不可用。

## 处理步骤<a name="section46662999"></a>

**检查组件KrbServer服务所在节点是否故障。**

1.  <a name="li10698868201911"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> KrbServer \> 实例”。进入KrbServer实例页面查看KrbServer服务所在节点的主机名。
2.  在FusionInsight Manager的“告警”页面，查看是否有“节点故障”告警产生。
    -   是，执行[3](#li51562352201911)。
    -   否，执行[6](#li61687950201911)。

3.  <a name="li51562352201911"></a>查看告警信息里的主机名是否和[1](#li10698868201911)主机名一致。
    -   是，执行[4](#li15800973201911)。
    -   否，执行[6](#li61687950201911)。

4.  <a name="li15800973201911"></a>按“ALM-12006 节点故障”提供的步骤处理该告警。
5.  在告警列表中查看“KrbServer服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li61687950201911)。


**检查OLdap服务是否不可用。**

1.  <a name="li61687950201911"></a>在FusionInsight Manager的“告警”页面，查看是否有“OLdap资源异常”告警产生。
    -   是，执行[7](#li30668082201911)。
    -   否，执行[9](#li13339868201911)。

2.  <a name="li30668082201911"></a>按“ALM-12004 OLdap资源异常”提供的步骤处理该告警。
3.  在告警列表中查看“KrbServer服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li13339868201911)。


**收集故障信息。**

1.  <a name="li13339868201911"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“KrbServer”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section17313813"></a>

无。

