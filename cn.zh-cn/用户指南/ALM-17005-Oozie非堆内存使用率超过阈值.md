# ALM-17005 Oozie非堆内存使用率超过阈值<a name="ALM-17005"></a>

## 告警解释<a name="section41852036"></a>

系统每30秒周期性检测Oozie服务非堆内存使用状态，当检测到Oozie实例非堆内存使用率超出阈值（最大内存的80%）时产生该告警。非堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section41124012"></a>

<a name="table51538867"></a>
<table><thead align="left"><tr id="row55464715"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p63456919"><a name="p63456919"></a><a name="p63456919"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p39736775"><a name="p39736775"></a><a name="p39736775"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p64562179"><a name="p64562179"></a><a name="p64562179"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row62154036"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1312194"><a name="p1312194"></a><a name="p1312194"></a>17005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p39178900"><a name="p39178900"></a><a name="p39178900"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p19374355"><a name="p19374355"></a><a name="p19374355"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section34571792"></a>

<a name="table25818918"></a>
<table><thead align="left"><tr id="row2151805"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p40078531"><a name="p40078531"></a><a name="p40078531"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p25135585"><a name="p25135585"></a><a name="p25135585"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1143823817213"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row22716544"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61572960"><a name="p61572960"></a><a name="p61572960"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row17285729"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p64802221"><a name="p64802221"></a><a name="p64802221"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row46349082"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26070279"><a name="p26070279"></a><a name="p26070279"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row33305921"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13425051"><a name="p13425051"></a><a name="p13425051"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13687329"><a name="p13687329"></a><a name="p13687329"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section42710672"></a>

非堆内存溢出可能导致服务崩溃。

## 可能原因<a name="section48851735"></a>

该节点Oozie实例非堆内存使用率过大，或配置的非堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section37012437"></a>

**检查非堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> Oozie非堆内存使用率超过阈值”，检查该告警的“定位信息”。查看告警上报的实例主机名。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Oozie \> 实例”，选择上报告警实例主机名对应的角色，单击图表区域右上角的下拉菜单，选择“定制 \> 内存”中的“Oozie非堆内存使用率”，单击“确定”。

    **图 1**  定制Oozie非堆内存使用率<a name="fig25911418193912"></a>  
    ![](figures/定制Oozie非堆内存使用率.png "定制Oozie非堆内存使用率")

3.  查看Oozie使用的非堆内存是否已达到Oozie设定的阈值（默认值为最大非堆内存的80%）。
    -   是，执行[4](#l3672051debd1416aa3b54541a7a480cb)。
    -   否，执行[6](#d0e31729)。

4.  <a name="l3672051debd1416aa3b54541a7a480cb"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务\> Oozie \> 配置”，选择“全部配置”，在搜索栏里搜索“GC\_OPTS”参数，查看参数中是否有“-XX: MaxPermSize”。如果是，将“-XX: MaxPermSize”的值根据实际情况调大。如果否，手动添加“-XX: MaxPermSize”并将值设置成为“-Xmx”大小的1/8。单击“保存”，单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >Oozie的GC参数配置建议：
    >建议将“-XX:MaxPermSize”值设置成为“-Xmx”大小的1/8，比如：“-Xmx”设置为2G时，“-XX:MaxPermSize”设置为256M；“-Xmx”设置为4G时，“-XX:MaxPermSize”设置为512M。

5.  重启受影响的服务或实例，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#d0e31729)。


**收集故障信息。**

1.  <a name="d0e31729"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Oozie”。
3.  单击右上角的![](figures/zh-cn_image_0263895663.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

