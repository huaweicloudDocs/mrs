# ALM-16006 Hive服务进程直接内存使用超出阈值<a name="ALM-16006"></a>

## 告警解释<a name="section17680197"></a>

系统每30秒周期性检测Hive直接内存使用率，并把实际的Hive直接内存使用率和阈值相比较。当Hive直接内存使用率超出阈值（默认为最大直接内存的95%）时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Hive”修改阈值。

当Hive直接内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section24904045"></a>

<a name="table11615769"></a>
<table><thead align="left"><tr id="row20121249"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19208479"><a name="p19208479"></a><a name="p19208479"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p12383006"><a name="p12383006"></a><a name="p12383006"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p63499462"><a name="p63499462"></a><a name="p63499462"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row43182782"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p8144430"><a name="p8144430"></a><a name="p8144430"></a>16006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p55719103"><a name="p55719103"></a><a name="p55719103"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p16953496"><a name="p16953496"></a><a name="p16953496"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section22809813"></a>

<a name="table31055970"></a>
<table><thead align="left"><tr id="row7203881"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p46643471"><a name="p46643471"></a><a name="p46643471"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p20024843"><a name="p20024843"></a><a name="p20024843"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row59301658112415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row11399554"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33204231"><a name="p33204231"></a><a name="p33204231"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row30402628"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24099025"><a name="p24099025"></a><a name="p24099025"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row15564636"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46998150"><a name="p46998150"></a><a name="p46998150"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row20330169"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p36130962"><a name="p36130962"></a><a name="p36130962"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p40926771"><a name="p40926771"></a><a name="p40926771"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section3961726"></a>

Hive直接内存使用率过高，会影响Hive任务运行的性能，甚至造成内存溢出导致Hive服务不可用。

## 可能原因<a name="section35655537"></a>

该节点Hive实例直接内存使用量过大，或分配的直接内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section52464384"></a>

**检查直接内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“16006”的告警，查看“定位信息”中的角色名并确定实例的IP地址。
    -   告警上报的角色是HiveServer，执行[2](#li17213084163227)。
    -   告警上报的角色是MetaStore，执行[3](#li62413668163227)。

2.  <a name="li17213084163227"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的HiveServer，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“HiveServer内存使用率统计” ，单击“确定”，查看HiveServer进程使用的直接内存是否已达到HiveServer进程设定的最大直接内存的阈值（默认95%）。

    -   是，执行[4](#li24852103163227)。
    -   否，执行[7](#li62079693163227)。

    **图 1**  勾选HiveServer内存使用率统计<a name="fig159981629181710"></a>  
    ![](figures/勾选HiveServer内存使用率统计-83.png "勾选HiveServer内存使用率统计-83")

3.  <a name="li62413668163227"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，单击告警上报的MetaStore，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> CPU和内存”，勾选“MetaStore内存使用率统计” ，单击“确定”，查看MetaStore进程使用的直接内存是否已达到MetaStore进程设定的最大直接内存的阈值（默认95%）。

    -   是，执行[4](#li24852103163227)。
    -   否，执行[7](#li62079693163227)。

    **图 2**  勾选MetaStore内存使用率统计<a name="fig11061536182011"></a>  
    ![](figures/勾选MetaStore内存使用率统计-84.png "勾选MetaStore内存使用率统计-84")

4.  <a name="li24852103163227"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 配置”，选择“全部配置”， 选择“HiveServer/MetaStore \> JVM”，将“HIVE\_GC\_OPTS/METASTORE\_GC\_OPTS”参数中“-XX:MaxDirectMemorySize”的值根据如下建议进行调整，并单击“保存”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >1.  HiveServer的GC参数配置建议
    >    -   建议将“-XX:MaxDirectMemorySize”值设置为“-Xmx”值的1/8，比如：当“-Xmx”设置为8G时，“-XX:MaxDirectMemorySize”设置为1024M，“-Xmx”设置为4G时，“-XX:MaxDirectMemorySize”设置为512M。并且建议“-XX:MaxDirectMemorySize”值不小于512M。
    >2.  MetaServer的GC参数配置建议
    >    -   建议将“-XX:MaxDirectMemorySize”值设置为“-Xmx”值的1/8，比如：当“-Xmx”设置为8G时，“-XX:MaxDirectMemorySize”设置为1024M，“-Xmx”设置为4G时，“-XX:MaxDirectMemorySize”设置为512M。并且建议“-XX:MaxDirectMemorySize”值不小于512M。

5.  选择“更多 \> 重启服务”重启服务。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li62079693163227)。


**收集故障信息。**

1.  <a name="li62079693163227"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section2417410"></a>

无。

