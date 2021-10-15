# ALM-12005 OKerberos资源异常<a name="ALM-12005"></a>

## 告警解释<a name="section35885451"></a>

告警模块对Manager中的Kerberos资源的状态按80秒周期进行监控，当连续6次监控到Kerberos资源异常时，系统产生此告警。

当Kerberos资源恢复时，且告警处理完成时，告警恢复。

## 告警属性<a name="section54533606"></a>

<a name="table5426060"></a>
<table><thead align="left"><tr id="row30491115"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p53861246"><a name="p53861246"></a><a name="p53861246"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p684814"><a name="p684814"></a><a name="p684814"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p55469954"><a name="p55469954"></a><a name="p55469954"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row63881283"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p7001400"><a name="p7001400"></a><a name="p7001400"></a>12005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p30242505"><a name="p30242505"></a><a name="p30242505"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p33723872"><a name="p33723872"></a><a name="p33723872"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section21040409"></a>

<a name="table47279074"></a>
<table><thead align="left"><tr id="row53338937"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p25486642"><a name="p25486642"></a><a name="p25486642"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p51152156"><a name="p51152156"></a><a name="p51152156"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row137961710134311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row49683999"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p64980962"><a name="p64980962"></a><a name="p64980962"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28966541"><a name="p28966541"></a><a name="p28966541"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row59372281"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p44425493"><a name="p44425493"></a><a name="p44425493"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p41695148"><a name="p41695148"></a><a name="p41695148"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row39712018"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p62556912"><a name="p62556912"></a><a name="p62556912"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33945086"><a name="p33945086"></a><a name="p33945086"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55145957"></a>

Manager中的Kerberos资源异常，组件WebUI认证服务不可用，无法对Web上层服务提供安全认证功能，可能引起无法登录FusionInsight Manager和组件的WebUI。

## 可能原因<a name="section26551572"></a>

Okerberos依赖的OLdap资源异常。

## 处理步骤<a name="section37637557"></a>

**检查Manager中的OKerberos依赖的OLdap资源是否异常。**

1.  以**omm**用户登录到集群中Manager所在节点主机。

    通过登录FusionInsight Manager浮动IP节点，执行**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**脚本来查看当前Manager的双机信息。

2.  执行**sh $\{BIGDATA\_HOME\}/om-server/OMS/workspace0/ha/module/hacom/script/status\_ha.sh**，查询当前HA管理的OLdap资源状态是否正常（单机模式下面，OLdap资源为Active\_normal状态；双机模式下，OLdap资源在主节点为Active\_normal状态，在备节点为Standby\_normal状态。）。
    -   是，执行[4](#li6152360163635)。
    -   否，执行[3](#li57649063163811)。

3.  <a name="li57649063163811"></a>参考[ALM-12004 OLdap资源异常](ALM-12004-OLdap资源异常-123.md)的处理步骤进行处理，OLdap资源状态恢复后，观察当前OKerberos资源状态是否恢复正常。
    -   是，操作结束。
    -   否，执行[4](#li6152360163635)。


**收集故障信息。**

1.  <a name="li6152360163635"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OmsKerberos”和“OmmServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895607.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section3193699"></a>

无。

