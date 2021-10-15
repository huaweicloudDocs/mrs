# ALM-16004 Hive服务不可用<a name="ALM-16004"></a>

## 告警解释<a name="section27621550"></a>

系统每60秒周期性检测Hive服务状态。当Hive服务不可用时产生该告警。

当Hive服务恢复时，告警恢复。

>![](public_sys-resources/icon-note.gif) **说明：** 
>MRS 3.X支持Hive多实例，若集群启用了多实例功能且安装了多个Hive服务，请根据“定位信息”的“服务名”值来确定具体产生告警的Hive服务。例如Hive1服务不可用，则“定位信息”中显示服务名=Hive1，处理步骤中的操作对象也应由Hive调整为Hive1。

## 告警属性<a name="section47267361"></a>

<a name="table4510519"></a>
<table><thead align="left"><tr id="row13556155"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p24306760"><a name="p24306760"></a><a name="p24306760"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p22690525"><a name="p22690525"></a><a name="p22690525"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p25993251"><a name="p25993251"></a><a name="p25993251"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row25078593"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p18100192"><a name="p18100192"></a><a name="p18100192"></a>16004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p56829480"><a name="p56829480"></a><a name="p56829480"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p39785152"><a name="p39785152"></a><a name="p39785152"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section22753069"></a>

<a name="table1371856"></a>
<table><thead align="left"><tr id="row6362194"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p45575691"><a name="p45575691"></a><a name="p45575691"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p643489"><a name="p643489"></a><a name="p643489"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row810213158255"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row52122619"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56843037"><a name="p56843037"></a><a name="p56843037"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row41825285"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7555640"><a name="p7555640"></a><a name="p7555640"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row891897"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13268752"><a name="p13268752"></a><a name="p13268752"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section3451036"></a>

系统无法提供数据加载，查询，提取服务。

## 可能原因<a name="section31059325"></a>

-   Hive服务不可用可能与ZooKeeper、HDFS、Yarn和DBService等基础服务有关，也可能由Hive自身的进程故障引起。
    -   ZooKeeper服务异常。
    -   HDFS服务异常。
    -   Yarn服务异常。
    -   DBService服务异常。
    -   Hive服务进程故障，如果告警由Hive进程故障引发，告警上报时间可能会延迟5分钟左右。

-   Hive服务和基础服务间的网络通信中断。

## 处理步骤<a name="section11098475"></a>

**检查HiveServer/MetaStore进程状态。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，在Hive实例列表中，查看所有HiveServer或MetaStore实例状态是否都呈现未知状态。
    -   是，执行[2](#li24833719161349)。
    -   否，执行[4](#li43869374161349)。

2.  <a name="li24833719161349"></a>在Hive实例列表上方，选择“更多 \> 重启实例”，重启HiveServer/MetaStore进程。
3.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[4](#li43869374161349)。


**检查ZooKeeper服务状态。**

1.  <a name="li43869374161349"></a>在FusionInsight Manager的告警列表中，查看是否有“进程故障”产生。
    -   是，执行[5](#li60791811161349)。
    -   否，执行[8](#li31008574161349)。

2.  <a name="li60791811161349"></a>在“进程故障”，查看“服务名”是否为“ZooKeeper”。
    -   是，执行[6](#li25189643161349)。
    -   否，执行[8](#li31008574161349)。

3.  <a name="li25189643161349"></a>参考“ALM-12007 进程故障”的处理步骤处理该故障。
4.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li31008574161349)。


**检查HDFS服务状态。**

1.  <a name="li31008574161349"></a>在FusionInsight Manager的告警列表中，查看是否有“HDFS服务不可用”产生。
    -   是，执行[9](#li28666548161349)。
    -   否，执行[11](#li20005630161349)。

2.  <a name="li28666548161349"></a>参考“ALM-14000 HDFS服务不可用”的处理步骤处理该故障。
3.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[11](#li20005630161349)。


**检查Yarn服务状态。**

1.  <a name="li20005630161349"></a>在FusionInsight Manager的告警列表中，查看是否有“Yarn服务不可用”产生。
    -   是，执行[12](#li9843325161349)。
    -   否，执行[14](#li63534578161349)。

2.  <a name="li9843325161349"></a>参考“ALM-18000 Yarn服务不可用”的处理步骤处理该故障。
3.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[14](#li63534578161349)。


**检查DBService服务状态。**

1.  <a name="li63534578161349"></a>在FusionInsight Manager的告警列表中，查看是否有“DBService服务不可用”产生。
    -   是，执行[15](#li46027204161349)。
    -   否，执行[17](#li24705688161349)。

2.  <a name="li46027204161349"></a>参考“ALM-27001 DBService服务不可用”的处理步骤处理该故障。
3.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[17](#li24705688161349)。


**检查Hive与ZooKeeper、HDFS、Yarn和DBService之间的网络连接。**

1.  <a name="li24705688161349"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive”。
2.  单击“实例”。

    显示HiveServer实例列表。

3.  单击“HiveServer”行的“主机名称”。

    弹出HiveServer主机状态页面。

4.  <a name="li33700880161349"></a>记录“基本信息”下的IP地址。
5.  以**omm**用户通过[20](#li33700880161349)获取的IP地址登录HiveServer所在的主机。

**向管理员获取密码。**

1.  执行**ping**命令，查看HiveServer所在主机与ZooKeeper、HDFS、Yarn和DBService服务所在主机的网络连接是否正常。（获取ZooKeeper、HDFS、Yarn和DBService服务所在主机的IP地址的方式和获取HiveServer IP地址的方式相同。）
    -   是，执行[25](#li38650106161349)。
    -   否，执行[23](#li3776733161349)。

2.  <a name="li3776733161349"></a>联系网络管理员恢复网络。
3.  在告警列表中，查看“Hive服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[25](#li38650106161349)。


**收集故障信息。**

1.  <a name="li38650106161349"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   ZooKeeper
    -   HDFS
    -   Yarn
    -   DBService
    -   Hive

3.  单击右上角的![](figures/zh-cn_image_0263895897.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section32777414"></a>

无。

