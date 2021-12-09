# ALM-23003 Loader任务执行失败<a name="ALM-23003"></a>

## 告警解释<a name="section50367549"></a>

当系统检测到Loader任务执行失败时即时产生该告警。当用户手动处理执行失败的任务后该告警恢复。该告警需要手动清除。

## 告警属性<a name="section50654763"></a>

<a name="table45565875"></a>
<table><thead align="left"><tr id="row12064822"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p37726520"><a name="p37726520"></a><a name="p37726520"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p35949266"><a name="p35949266"></a><a name="p35949266"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p26209453"><a name="p26209453"></a><a name="p26209453"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row42590961"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p27315780"><a name="p27315780"></a><a name="p27315780"></a>23003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65094609"><a name="p65094609"></a><a name="p65094609"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p38171966"><a name="p38171966"></a><a name="p38171966"></a>否</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section53239689"></a>

<a name="table4921523"></a>
<table><thead align="left"><tr id="row29670295"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p54483726"><a name="p54483726"></a><a name="p54483726"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p51105648"><a name="p51105648"></a><a name="p51105648"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row984919519171"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row45916839"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8695731"><a name="p8695731"></a><a name="p8695731"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row11152720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24340221"><a name="p24340221"></a><a name="p24340221"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row17735399"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62292359"><a name="p62292359"></a><a name="p62292359"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row23760327"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p45538331"><a name="p45538331"></a><a name="p45538331"></a>任务ID</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p64726224"><a name="p64726224"></a><a name="p64726224"></a>执行失败的Loader任务的ID。</p>
</td>
</tr>
<tr id="row45665110"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p7886463"><a name="p7886463"></a><a name="p7886463"></a>任务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p34823772"><a name="p34823772"></a><a name="p34823772"></a>执行失败的任务名称。</p>
</td>
</tr>
<tr id="row44978498"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p19379721"><a name="p19379721"></a><a name="p19379721"></a>用户标识</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26253560"><a name="p26253560"></a><a name="p26253560"></a>提交Loader任务的用户。</p>
</td>
</tr>
<tr id="row2713161816442"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1624673963311"><a name="p1624673963311"></a><a name="p1624673963311"></a>Details</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p124623918333"><a name="p124623918333"></a><a name="p124623918333"></a>对告警信息补充。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section9395161"></a>

执行提交的Loader任务时发生异常导致执行失败。没有返回执行结果。故障修复后需重新执行任务。

## 可能原因<a name="section17447586"></a>

-   任务参数没有正确设置。
-   Yarn执行任务时出现异常。

## 处理步骤<a name="section22810551"></a>

**检查任务参数是否没有正确设置。**

1.  打开FusionInsight Manager页面，选择“运维 \> 告警 \> 告警”在告警列表中，打开告警下拉页面，获取告警原因。
2.  如果告警原因是“提交任务失败”，则查看“附加信息”中的错误细节信息，同时到Loader界面查看该任务的历史执行记录。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

3.  重新提交任务。
4.  查看任务是否成功执行。
    -   是，执行[9](#li34300587102152)。
    -   否，执行[5](#li36673094102152)。


**检查Yarn执行任务时是否出现异常。**

1.  <a name="li36673094102152"></a>打开FusionInsight Manager页面，在告警列表中，打开告警下拉页面，获取告警原因。
2.  在告警原因中查看Yarn活动是否正常执行，如果告警原因是“Yarn执行失败”则表示异常。
    -   是，执行[7](#li11020130102152)。
    -   否，执行[10](#li40269833102152)。

3.  <a name="li11020130102152"></a>重新提交任务。
4.  查看任务是否成功执行。
    -   是，执行[9](#li34300587102152)。
    -   否，执行[10](#li40269833102152)。

5.  <a name="li34300587102152"></a>在告警列表中，单击该告警“操作”列下面的“清除”，手动清除告警。操作结束。

**收集故障信息。**

1.  <a name="li40269833102152"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的如下节点信息。
    -   DBService
    -   HDFS
    -   Loader
    -   Mapreduce
    -   Yarn
    -   ZooKeeper

3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统不会自动清除此告警，需手工清除。

## 参考信息<a name="section3968367"></a>

无。

