# ALM-19012 HBase系统表目录或文件丢失<a name="ALM-19012"></a>

## 告警解释<a name="section42400121"></a>

系统按120秒周期性检测HBase在HDFS上的如下目录和文件是否存在，当检测到文件或者目录不存在时，上报该告警。当文件或目录都恢复后，告警恢复。

检查内容：

-   命名空间hbase在HDFS上的目录。
-   hbase.version文件。
-   hbase:meta表在HDFS上的目录、.tableinfo和.regioninfo文件。
-   hbase:namespace表在HDFS上的目录、.tableinfo和.regioninfo文件。
-   hbase:hindex表在HDFS上的目录、.tableinfo和.regioninfo文件。
-   hbase:acl表在HDFS上的目录、.tableinfo和.regioninfo文件\(该表在普通模式集群默认不存在\)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如HBase1服务不可用，则“定位信息”中显示服务名=HBase1，处理步骤中的操作对象也应由HBase调整为HBase1。

## 告警属性<a name="section46056776"></a>

<a name="table3909558"></a>
<table><thead align="left"><tr id="row9358345"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19828475"><a name="p19828475"></a><a name="p19828475"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62602629"><a name="p62602629"></a><a name="p62602629"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p37648208"><a name="p37648208"></a><a name="p37648208"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row29606020"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p49277383"><a name="p49277383"></a><a name="p49277383"></a>19012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p32045124"><a name="p32045124"></a><a name="p32045124"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p45518241"><a name="p45518241"></a><a name="p45518241"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section11857806"></a>

<a name="table63098886"></a>
<table><thead align="left"><tr id="row42029922"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p48980553"><a name="p48980553"></a><a name="p48980553"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p8001819"><a name="p8001819"></a><a name="p8001819"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1882112262176"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row44167618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7672494"><a name="p7672494"></a><a name="p7672494"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row1943587"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1196208"><a name="p1196208"></a><a name="p1196208"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row10765874"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36375218"><a name="p36375218"></a><a name="p36375218"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section39611396"></a>

HBase服务重启/启动失败。

## 可能原因<a name="section20958252"></a>

HDFS上的文件或者目录缺失。

## 处理步骤<a name="section13243105619817"></a>

**检查告警原因**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“19012”的告警，查看“告警原因”中的是否提示未知异常。
    -   是，执行[4](#li61221212393)。
    -   否，执行[2](#li101220116399)。

2.  <a name="li101220116399"></a>在FusionInsight Manager首页，选择“运维 \> 备份恢复 \> 备份管理”，查看任务名称为“default”的备份任务或者其他执行成功的用户自己配置的HBase元数据备份任务是否有执行成功的记录。
    -   是，执行[3](#li61221412391)。
    -   否，执行[4](#li61221212393)。

3.  <a name="li61221412391"></a>使用最近一次备份的元数据，对HBase服务的元数据进行恢复操作。

**收集故障信息**

1.  <a name="li61221212393"></a>在主备集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的有问题的HBase服务。
3.  单击右上角的![](figures/zh-cn_image_0263895788.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

