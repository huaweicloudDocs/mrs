# ALM-16000 连接到HiveServer的session数占最大允许数的百分比超过阈值<a name="ALM-16000"></a>

## 告警解释<a name="section14753556"></a>

系统每30秒周期性检测连接到HiveServer的Session数占HiveServer允许的最大session数的百分比，该指标可通过“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例 \>_ 具体的HiveServer__实例_”查看。连接到HiveServer的session数占最大允许数的百分比指标默认提供一个阈值范围（90%），当检测到百分比指标超过阈值范围产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Hive \> 连接到HiveServer的session数占最大允许session数的百分比”修改阈值。

平滑次数为1，百分比指标小于或等于阈值时，告警恢复；平滑次数大于1，百分比指标小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section65673142"></a>

<a name="table2697805"></a>
<table><thead align="left"><tr id="row10450762"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41205356"><a name="p41205356"></a><a name="p41205356"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p49299555"><a name="p49299555"></a><a name="p49299555"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p33841047"><a name="p33841047"></a><a name="p33841047"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row56770287"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p34990548"><a name="p34990548"></a><a name="p34990548"></a>16000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p15662125"><a name="p15662125"></a><a name="p15662125"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p60672611"><a name="p60672611"></a><a name="p60672611"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section54187374"></a>

<a name="table15534429"></a>
<table><thead align="left"><tr id="row48561591"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p41174828"><a name="p41174828"></a><a name="p41174828"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p46826794"><a name="p46826794"></a><a name="p46826794"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1687144862510"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row34873944"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33829733"><a name="p33829733"></a><a name="p33829733"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row36032144"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49481274"><a name="p49481274"></a><a name="p49481274"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row42678285"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p34048007"><a name="p34048007"></a><a name="p34048007"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row37996610"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p57826595"><a name="p57826595"></a><a name="p57826595"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p53442657"><a name="p53442657"></a><a name="p53442657"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section17924324"></a>

发生连接数告警时，表示连接到HiveServer的session数过多，将会导致无法建立新的连接。

## 可能原因<a name="section27101193"></a>

连接HiveServer的客户端过多。

## 处理步骤<a name="section42584150"></a>

**增加Hive最大连接数配置。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 配置”，选择“全部配置”。
2.  然后查找“hive.server.session.control.maxconnections”，调大该配置项的数值。设该配置项的值为A，阈值为B，连接到HiveServer的session数为C，调整策略为A x B \> C ，连接到HiveServer的session数可在Hive的监控界面查看监控指标“HiveServer的session数统计”。
3.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[4](#li19517422154756)。


**收集故障信息。**

1.  <a name="li19517422154756"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section47713037"></a>

无。

