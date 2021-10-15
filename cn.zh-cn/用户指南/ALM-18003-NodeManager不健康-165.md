# ALM-18003 NodeManager不健康<a name="ALM-18003"></a>

## 告警解释<a name="section8166535"></a>

系统每30秒周期性检测不健康NodeManager节点，并把不健康节点数和阈值相比较。“不健康的节点数”指标默认提供一个阈值。当检测到“不健康的节点数”的值超出阈值时产生该告警。

用户可通过选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置”，修改

“yarn.nodemanager.unhealthy.alarm.threshold”的值来配置阈值（修改该参数不用重启Yarn，就可以生效）。

阈值默认为零，当不健康节点数超过该值时，触发告警，小于阈值时会自动消除告警。

## 告警属性<a name="section6389956"></a>

<a name="table52669532"></a>
<table><thead align="left"><tr id="row44285256"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p30335989"><a name="p30335989"></a><a name="p30335989"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p41296063"><a name="p41296063"></a><a name="p41296063"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p56646797"><a name="p56646797"></a><a name="p56646797"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row24987848"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p10749783"><a name="p10749783"></a><a name="p10749783"></a>18003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65426083"><a name="p65426083"></a><a name="p65426083"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p65021331"><a name="p65021331"></a><a name="p65021331"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section57509608"></a>

<a name="table32236431"></a>
<table><thead align="left"><tr id="row53243715"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p17773671"><a name="p17773671"></a><a name="p17773671"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p30381210"><a name="p30381210"></a><a name="p30381210"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row08392520202"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row44958983"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32432553"><a name="p32432553"></a><a name="p32432553"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row23457527"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24209917"><a name="p24209917"></a><a name="p24209917"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row16562668"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18419788"><a name="p18419788"></a><a name="p18419788"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row31560365"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p6252801"><a name="p6252801"></a><a name="p6252801"></a>Unhealthy Host</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36714873"><a name="p36714873"></a><a name="p36714873"></a>不健康节点的主机列表。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section47824428"></a>

-   故障的NodeManager节点无法提供Yarn服务。
-   容器减少，集群性能下降。

## 可能原因<a name="section27766673"></a>

-   NodeManager节点所在主机的硬盘空间不足。
-   NodeManager节点本地目录**omm**用户无访问权限。

## 处理步骤<a name="section48573473"></a>

**检查主机的硬盘空间。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”，在告警列表中找到当前告警，单击![](figures/zh-cn_image_0263895536.png)获取告警详细信息，在“附加信息”中获取不健康状态的节点。
2.  <a name="li436626208439"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例”，选择对应主机的NodeManager实例，选择“实例配置 \> 全部配置”，搜索“yarn.nodemanager.local-dirs”和“yarn.nodemanager.log-dirs”对应的磁盘。
3.  选择“运维 \> 告警 \> 告警”，在告警列表中查看对应的磁盘是否存在“ALM-12017 磁盘容量不足”告警。
    -   是，执行[4](#li534257698439)。
    -   否，执行[5](#li247542268439)。

4.  <a name="li534257698439"></a>参考“ALM-12017 磁盘容量不足”操作步骤进行处理，故障恢复后，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li584281488439)。

5.  <a name="li247542268439"></a>选择“主机  \>  _待查看的主机名称_”，在主机的概览页面查看对应分区的磁盘使用情况。检查挂载磁盘使用空间百分比是否已经超过Yarn参数“yarn.nodemanager.disk-health-checker.max-disk-utilization-per-disk-percentage”所配置的值。
    -   是，执行[6](#li602848088439)。
    -   否，执行[7](#li584281488439)。

6.  <a name="li602848088439"></a>将磁盘使用率降到该配置值以下，等待10-20分钟，然后检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li584281488439)。


**检查NodeManager节点本地目录的访问权限。**

1.  <a name="li584281488439"></a>获取[2](#li436626208439)中查看到的NodeManager目录，以**root**用户登录每个NodeManager节点，并进入获取到的目录，用户密码为安装前用户自定义，请咨询系统管理员。
2.  执行**ll**命令查看对应localdir的文件夹和containerlogs文件夹权限，确认权限是否是“755”，且“用户:属组”是否为“omm:ficommon”。
    -   是，处理完毕。
    -   否，执行[9](#li426458378439)。

3.  <a name="li426458378439"></a>执行如下命令将文件夹权限修改为“755”，并将“用户:属组”修改为“omm:ficommon”。

    **chmod 755 **_<folder\_name\>_

    **chown omm:ficommon **_<folder\_name\>_

4.  等待10～20分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li175356658439)。


**收集故障信息。**

1.  <a name="li175356658439"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section34508075"></a>

无。

