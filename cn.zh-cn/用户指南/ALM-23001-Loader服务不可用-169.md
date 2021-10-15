# ALM-23001 Loader服务不可用<a name="ALM-23001"></a>

## 告警解释<a name="section8469747"></a>

系统每60秒周期性检测Loader服务的可用性。当Loader服务不可用时产生该告警。当Loader服务恢复时，告警恢复。

## 告警属性<a name="section9118864"></a>

<a name="table37883228"></a>
<table><thead align="left"><tr id="row41870811"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p36092564"><a name="p36092564"></a><a name="p36092564"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p37816577"><a name="p37816577"></a><a name="p37816577"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p43243915"><a name="p43243915"></a><a name="p43243915"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row13096217"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p54160660"><a name="p54160660"></a><a name="p54160660"></a>23001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p24937315"><a name="p24937315"></a><a name="p24937315"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p6656623"><a name="p6656623"></a><a name="p6656623"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section14960916"></a>

<a name="table2315551"></a>
<table><thead align="left"><tr id="row30224372"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p32255087"><a name="p32255087"></a><a name="p32255087"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p62525267"><a name="p62525267"></a><a name="p62525267"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row7292171341720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row31381830"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p6198144"><a name="p6198144"></a><a name="p6198144"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row55783298"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49585464"><a name="p49585464"></a><a name="p49585464"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row43615993"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p12340448"><a name="p12340448"></a><a name="p12340448"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section430520"></a>

如果Loader服务不可用，数据加载，导入，转换的功能也不可用。

## 可能原因<a name="section3874685"></a>

-   Loader服务依赖的内部服务异常。
    -   ZooKeeper服务异常。
    -   HDFS服务异常。
    -   DBService服务异常。
    -   Yarn服务异常。
    -   Mapreduce服务异常。

-   环境故障：网络异常，Loader服务无法与其依赖的内部服务通信，无法提供服务。
-   软件故障：Loader服务无法正常运行。

## 处理步骤<a name="section34872173"></a>

**检查ZooKeeper服务状态。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper”查看ZooKeeper的运行状态是否正常。
    -   是，执行[3](#li3338697594948)。
    -   否，执行[2](#li4477276894948)。

2.  <a name="li4477276894948"></a>选择“更多 \> 重启服务”重新启动ZooKeeper服务实例。重启完成后在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[3](#li3338697594948)。

3.  <a name="li3338697594948"></a>在FusionInsight Manager的告警列表中，查看是否有“进程故障”告警产生。
    -   是，执行[4](#li2687521594948)。
    -   否，执行[7](#li368641694948)。

4.  <a name="li2687521594948"></a>在“ALM-12007 进程故障”的“定位信息”中查看“服务名”是否为“ZooKeeper”。
    -   是，执行[5](#li2940879794948)。
    -   否，执行[7](#li368641694948)。

5.  <a name="li2940879794948"></a>参考“ALM-12007 进程故障”的处理步骤处理该故障。
6.  在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li368641694948)。


**检查HDFS服务状态。**

1.  <a name="li368641694948"></a>在FusionInsight Manager的告警列表中，查看是否有“HDFS服务不可用”告警产生。
    -   是，执行[8](#li3016431894948)。
    -   否，执行[10](#li4820416794948)。

2.  <a name="li3016431894948"></a>参考“ALM-14000 HDFS服务不可用”的处理步骤处理该故障。
3.  在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[10](#li4820416794948)。


**检查DBService服务状态。**

1.  <a name="li4820416794948"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> DBService”查看DBService的运行状态是否正常。
    -   是，执行[12](#li5188852994948)。
    -   否，执行[11](#li276758894948)。

2.  <a name="li276758894948"></a>选择“更多 \> 重启服务”重新启动DBService服务实例。重启完成后在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[12](#li5188852994948)。


**检查Mapreduce服务状态。**

1.  <a name="li5188852994948"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Mapreduce”查看Mapreduce的运行状态是否正常。
    -   是，执行[16](#li3322983294948)。
    -   否，执行[13](#li5580967194948)。

2.  <a name="li5580967194948"></a>选择“更多 \> 重启服务”重新启动Mapreduce服务。重启完成后在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[16](#li3322983294948)。


**检查Yarn服务状态。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn”查看Yarn的运行状态是否正常。
    -   是，执行[16](#li3322983294948)。
    -   否，执行[15](#li986571894948)。

2.  <a name="li986571894948"></a>选择“更多 \> 重启服务”重新启动Yarn服务实例。重启完成后在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[16](#li3322983294948)。

3.  <a name="li3322983294948"></a>在FusionInsight Manager的告警列表中，查看是否有“Yarn服务不可用”告警产生。
    -   是，执行[17](#li726187194948)。
    -   否，执行[19](#li3944766494948)。

4.  <a name="li726187194948"></a>参考“ALM-18000 Yarn服务不可用”的处理步骤处理该故障。
5.  在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[19](#li3944766494948)。


**检查Loader和依赖组件之间的网络连接。**

1.  <a name="li3944766494948"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader”。
2.  单击“实例”，显示LoaderServer实例列表。
3.  <a name="li4114417694948"></a>记录“LoaderServer\(主\)”行的“管理IP”。
4.  以**omm**用户通过[21](#li4114417694948)获取的IP地址登录主LoaderServer所在的主机。

1.  执行**ping**命令，查看主LoaderServer所在主机和依赖组件所在主机的网络连接是否正常。（依赖组件包括ZooKeeper、DBService、HDFS、Mapreduce和Yarn等，获取依赖组件所在主机的IP地址的方式和获取主LoaderServer IP地址的方式相同。）
    -   是，执行[26](#li4285171694948)。
    -   否，执行[24](#li572535994948)。

2.  <a name="li572535994948"></a>联系网络管理员恢复网络。
3.  在告警列表中，查看“Loader服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[26](#li4285171694948)。


**收集故障信息。**

1.  <a name="li4285171694948"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的如下节点信息。
    -   Zookeeper
    -   HDFS
    -   DBService
    -   Yarn
    -   Mapreduce
    -   Loader

3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Loader”。
5.  选择“更多 \> 重启服务”，单击“确定”。

1.  查看该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[32](#li3145865094948)。

2.  <a name="li3145865094948"></a>请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section45414103"></a>

无。

