# ALM-14027 DataNode磁盘故障<a name="ALM-14027"></a>

## 告警解释<a name="section14753556"></a>

系统每60秒周期性检测DataNode节点上的磁盘状况，当检测到有磁盘出现故障时产生该告警。

当DataNode上故障磁盘都恢复正常后，手动清除该告警，并重启该DataNode。

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
<tbody><tr id="row56770287"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p34990548"><a name="p34990548"></a><a name="p34990548"></a>14027</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p15662125"><a name="p15662125"></a><a name="p15662125"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p60672611"><a name="p60672611"></a><a name="p60672611"></a>否</p>
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
<tbody><tr id="row7847914269"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
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
<tr id="row37996610"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p9643152813466"><a name="p9643152813466"></a><a name="p9643152813466"></a>Failed Volumes</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p21777528466"><a name="p21777528466"></a><a name="p21777528466"></a>故障的磁盘列表。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section17924324"></a>

上报DataNode磁盘故障告警时，表示该DataNode节点上存在故障的磁盘分区，可能会导致已写入的文件丢失。

## 可能原因<a name="section26588641115124"></a>

-   硬盘故障。
-   磁盘权限设置不正确。

## 处理步骤<a name="section290805983653"></a>

**查看是否存在磁盘告警**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”查看是否存在告警“ALM-12014 设备分区丢失”或“ALM-12033 慢盘故障”。
    -   是，执行[2](#li106705312711)。
    -   否，执行[4](#li76681531273)。

2.  <a name="li106705312711"></a>参考“ALM-12014 设备分区丢失”或“ALM-12033 慢盘故障”告警进行处理，查看对应告警是否清除。
    -   是，执行[3](#li1067073192717)。
    -   否，执行[4](#li76681531273)。

3.  <a name="li1067073192717"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li76681531273)。


**修改磁盘权限**

1.  <a name="li76681531273"></a>在“运维 \> 告警 \> 告警”页面，查看该告警的“定位信息”和“附加信息”，获取该告警上报的故障磁盘位置信息。
2.  以**root**用户登录上报告警的节点，用户密码为安装前用户自定义，请咨询系统管理员，进入故障磁盘所在目录，使用**ll**命令查看该故障磁盘的权限是否711，用户是否为**omm**。
    -   是，执行[8](#li206502049133310)。
    -   否，执行[6](#li188961329122819)。

3.  <a name="li188961329122819"></a>修改故障磁盘权限，如故障磁盘为data1，则执行以下命令：

    **chown omm:wheel data1**

    **chmod 711 data1**

4.  在Manager告警列表中，单击该告警“操作”列下面的“清除”，手动清除告警。然后选择“集群 \> 服务 \> HDFS \> 实例”勾选该DataNode，选择“更多 \> 重启实例”，等待5分钟，查看是否有新的告警上报。
    -   否，处理完毕。
    -   是，执行[8](#li206502049133310)。


**收集故障信息**

1.  <a name="li206502049133310"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS“和“OMS”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后20分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统不会自动清除此告警，需手工清除。

## 参考信息<a name="section12763521144142"></a>

无。

