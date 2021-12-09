# ALM-19018 HBase合并队列超出阈值<a name="ALM-19018"></a>

## 告警解释<a name="section49280276"></a>

系统每300秒周期性检测HBase服务的compaction队列长度，当检测到HBase服务的compaction队列长度超过告警的阈值（默认100）时产生该告警。当compaction队列长度小于告警的阈值时，告警恢复。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如“定位信息”中显示服务名=HBase-1，处理步骤中的操作对象也应由HBase调整为HBase-1。

## 告警属性<a name="section40869308"></a>

<a name="table2694484"></a>
<table><thead align="left"><tr id="row57848198"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p55192461"><a name="p55192461"></a><a name="p55192461"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p41404348"><a name="p41404348"></a><a name="p41404348"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65417916"><a name="p65417916"></a><a name="p65417916"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row64359861"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p45766222"><a name="p45766222"></a><a name="p45766222"></a>19018</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p16076463"><a name="p16076463"></a><a name="p16076463"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p27125121"><a name="p27125121"></a><a name="p27125121"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section32279454"></a>

<a name="table49651179"></a>
<table><thead align="left"><tr id="row461818"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p37407293"><a name="p37407293"></a><a name="p37407293"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10091901"><a name="p10091901"></a><a name="p10091901"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1975212412175"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row12137633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43900087"><a name="p43900087"></a><a name="p43900087"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row59556464"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p42160567"><a name="p42160567"></a><a name="p42160567"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row43900785"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1810620"><a name="p1810620"></a><a name="p1810620"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section22079637"></a>

产生该告警表示HBase服务的compaction队列长度已经超过规定的阈值，如果不及时处理，可能会导致集群性能下降，影响数据读写。

## 可能原因<a name="section64499009"></a>

-   HBase regionserver数太少。
-   HBase 单个regionserver上region数过多。
-   HBase regionserver堆大小较小。
-   资源不足。
-   相关参数配置不合理。

## 处理步骤<a name="section375714160309"></a>

**检查相关配置是否合理**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否存在告警ID为“19011”的告警。
    -   是，单击对应告警右侧的“查看帮助”并按照帮助文档进行处理，执行[3](#li5814142393624)。
    -   否，执行[2](#li1681162011376)。

2.  <a name="li1681162011376"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> HBase \> 配置 \> 全部配置，搜索“hbase.hstore.compaction.min”，“hbase.hstore.compaction.max”，“hbase.hstore.compactionThreshold”，“hbase.regionserver.thread.compaction.small”和“hbase.regionserver.thread.compaction.throttle”，适当调大其值。
3.  <a name="li5814142393624"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[4](#li5351076393624)。


**收集故障信息**

1.  <a name="li5351076393624"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HBase”。
3.  单击右上角的![](figures/zh-cn_image_0263895551.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section57037220"></a>

无。

