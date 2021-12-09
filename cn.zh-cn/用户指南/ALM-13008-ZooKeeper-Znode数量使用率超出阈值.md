# ALM-13008 ZooKeeper Znode数量使用率超出阈值<a name="ALM-13008"></a>

## 告警解释<a name="section18794533"></a>

系统每小时周期性检测ZooKeeper服务数据目录下二级znode状态，当检测到二级znode的总数量超过阈值时产生该告警。

## 告警属性<a name="section34933073"></a>

<a name="table52262125"></a>
<table><thead align="left"><tr id="row24697033"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p54302662"><a name="p54302662"></a><a name="p54302662"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p36439520"><a name="p36439520"></a><a name="p36439520"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65919998"><a name="p65919998"></a><a name="p65919998"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row37919625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1163219417345"><a name="p1163219417345"></a><a name="p1163219417345"></a>13008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1663217423418"><a name="p1663217423418"></a><a name="p1663217423418"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p16632104193412"><a name="p16632104193412"></a><a name="p16632104193412"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section45962205"></a>

<a name="table51772816"></a>
<table><thead align="left"><tr id="row55869420"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p29129184"><a name="p29129184"></a><a name="p29129184"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10653667"><a name="p10653667"></a><a name="p10653667"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row707525323"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p77584302119"><a name="p77584302119"></a><a name="p77584302119"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row57640736"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22422626"><a name="p22422626"></a><a name="p22422626"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row477048"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p38640893"><a name="p38640893"></a><a name="p38640893"></a>服务目录</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p42904606"><a name="p42904606"></a><a name="p42904606"></a>产生告警的目录名称。</p>
</td>
</tr>
<tr id="row111316194717"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39186745"><a name="p39186745"></a><a name="p39186745"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20009785"><a name="p20009785"></a><a name="p20009785"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row50597141"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p4727789"><a name="p4727789"></a><a name="p4727789"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p47406613"><a name="p47406613"></a><a name="p47406613"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section11006666"></a>

向ZooKeeper数据目录空间写入大量数据，导致ZooKeeper无法对外正常提供服务。

## 可能原因<a name="section31951138"></a>

-   往ZooKeeper数据目录空间写入大量数据。
-   自定义阈值设置不合理。

## 处理步骤<a name="section1719813447116"></a>

**检查告警目录是否写入大量数据**

1.  登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper”，单击“资源”，在精细化监控“资源使用（按二级Znode）”中单击“按Znode数量”，查看监控中是否有顶级Znode被写入较多数据。
    -   是，执行[2](#li151971257113310)。
    -   否，执行[4](#li10279134491613)。

2.  <a name="li151971257113310"></a>登录FusionInsight Manager，选择“运维 \> 告警 \> 告警”，打开告警“ALM-13008 ZooKeeper Znode数量使用率超出阈值”左侧下拉菜单，在“定位信息”的“服务目录”中获取告警的Znode路径。
3.  以集群用户登录ZooKeeper客户端，删除告警对应Znode下的无用数据。
4.  <a name="li10279134491613"></a>登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 配置 \> 全部配置”，搜索“max.znode.count”，即ZooKeeper目录的数量配额的最大值，告警阈值为该值的80%，修改调大该配置项，单击“保存”，重启服务使配置生效。
5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li57092876161840)。


**收集故障信息**

1.  <a name="li57092876161840"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895572.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section37905371"></a>

无。

