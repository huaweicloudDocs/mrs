# ALM-14026 DataNode块数超过阈值<a name="ALM-14026"></a>

## 告警解释<a name="section14753556"></a>

系统每30秒周期性检测每个DataNode上的块数，当检测到当前的DataNode节点上块数超过阈值时产生该告警。

如果平滑次数为1，DataNode节点上的块数小于或等于阈值时，告警恢复；如果平滑次数大于1，DataNode节点上的块数小于或等于阈值的90%时，告警恢复。

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
<tbody><tr id="row56770287"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p34990548"><a name="p34990548"></a><a name="p34990548"></a>14026</p>
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
<tbody><tr id="row135623149261"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
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

上报DataNode块数超过阈值告警时，表示该DataNode节点上块数太多，继续写入可能会由于磁盘空间不足导致写入HDFS数据失败。

## 可能原因<a name="section26588641115124"></a>

-   告警阈值配置不合理。

-   DataNode节点间数据倾斜。
-   HDFS集群配置的磁盘空间不足。

## 处理步骤<a name="section290805983653"></a>

**修改阈值配置**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> HDFS \> 配置 \> 全部配置”，查找HDFS-\>DataNode下的GC\_OPTS参数。
2.  配置DataNode块数阈值：修改GC\_OPTS参数中Xmx的值（Xmx内存值对应节点块数阈值为每GB对应500000块数，用户根据需要调整内存值），确认GC\_PROFILE的值为custom，保存配置。
3.  选择“集群 \>  _待操作集群的名称_  \> HDFS \> 实例”勾选状态为“配置过期”的DataNode实例，选择“更多 \> 重启实例”使GC\_OPTS配置生效。
4.  等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li10750133111389)。


**查看是否有关联告警**

1.  <a name="li10750133111389"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”中查看是否存在告警“ALM-14002 DataNode磁盘空间使用率超过阈值”。
    -   是，执行[6](#li5750123115384)。
    -   否，执行[8](#li4795431151710)。

2.  <a name="li5750123115384"></a>参考“ALM-14002 DataNode磁盘空间使用率超过阈值”进行处理，查看对应告警是否清除。
    -   是，执行[7](#li10751231113815)。
    -   否，执行[8](#li4795431151710)。

3.  <a name="li10751231113815"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[8](#li4795431151710)。


**对DataNode进行扩容**

1.  <a name="li4795431151710"></a>对DataNode进行扩容。
2.  在FusionInsight Manager首页，等待5分钟后，查看本告警是否清除。
    -   是，处理完毕。
    -   否，执行[10](#li10844183481711)。


**收集故障信息**

1.  <a name="li10844183481711"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS“。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后20分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section12763521144142"></a>

**DataNode JVM参数配置规则**

DataNode JVM参数“GC\_OPTS”默认值为：

-Xms2G -Xmx4G -XX:NewSize=128M -XX:MaxNewSize=256M -XX:MetaspaceSize=128M -XX:MaxMetaspaceSize=128M -XX:+UseConcMarkSweepGC -XX:+CMSParallelRemarkEnabled -XX:CMSInitiatingOccupancyFraction=65 -XX:+PrintGCDetails -Dsun.rmi.dgc.client.gcInterval=0x7FFFFFFFFFFFFFE -Dsun.rmi.dgc.server.gcInterval=0x7FFFFFFFFFFFFFE -XX:-OmitStackTraceInFastThrow -XX:+PrintGCDateStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=10 -XX:GCLogFileSize=1M -Djdk.tls.ephemeralDHKeySize=2048

集群中每个DataNode实例平均保存的Blocks= HDFS Block \* 3÷DataNode节点数，单个DataNode实例平均Block数量变化时请修改默认值中的“-Xms2G -Xmx4G -XX:NewSize=128M -XX:MaxNewSize=256M”。参考值如下表所示。

**表 1**  DataNode JVM配置

<a name="td322224489704ac6a8d18c21146d6686"></a>
<table><thead align="left"><tr id="r5fc0d03f19d54d1082a536369f32ab95"><th class="cellrowborder" valign="top" width="42.29%" id="mcps1.2.3.1.1"><p id="a55dc1e45920f45a4b1fadbcc65df9c71"><a name="a55dc1e45920f45a4b1fadbcc65df9c71"></a><a name="a55dc1e45920f45a4b1fadbcc65df9c71"></a>单个DataNode实例平均Block数量</p>
</th>
<th class="cellrowborder" valign="top" width="57.709999999999994%" id="mcps1.2.3.1.2"><p id="a6dca2c4d47794c5eb0adffb5d0324682"><a name="a6dca2c4d47794c5eb0adffb5d0324682"></a><a name="a6dca2c4d47794c5eb0adffb5d0324682"></a>参考值</p>
</th>
</tr>
</thead>
<tbody><tr id="r00929d1b71584e8e8f30505a9e2872b3"><td class="cellrowborder" valign="top" width="42.29%" headers="mcps1.2.3.1.1 "><p id="a416aecf87e5e458c996f243204ef02ff"><a name="a416aecf87e5e458c996f243204ef02ff"></a><a name="a416aecf87e5e458c996f243204ef02ff"></a>2,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="57.709999999999994%" headers="mcps1.2.3.1.2 "><p id="a3d30bc343740499aaaee64ad55b721e9"><a name="a3d30bc343740499aaaee64ad55b721e9"></a><a name="a3d30bc343740499aaaee64ad55b721e9"></a>“-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M”</p>
</td>
</tr>
<tr id="r0e83ba2dd9ed4f1695730d71f1457c24"><td class="cellrowborder" valign="top" width="42.29%" headers="mcps1.2.3.1.1 "><p id="a67fbb2a910984d69b4b8d77a94c40c8d"><a name="a67fbb2a910984d69b4b8d77a94c40c8d"></a><a name="a67fbb2a910984d69b4b8d77a94c40c8d"></a>5,000,000</p>
</td>
<td class="cellrowborder" valign="top" width="57.709999999999994%" headers="mcps1.2.3.1.2 "><p id="a692858cc5d8746d1b0136271ef662183"><a name="a692858cc5d8746d1b0136271ef662183"></a><a name="a692858cc5d8746d1b0136271ef662183"></a>“-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G”</p>
</td>
</tr>
</tbody>
</table>

Xmx内存值对应DataNode节点块数阈值，每GB对应500000块数，用户可根据需要调整内存值。

