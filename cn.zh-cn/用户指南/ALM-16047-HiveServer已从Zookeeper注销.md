# ALM-16047 HiveServer已从Zookeeper注销<a name="ALM-16047"></a>

## 告警解释<a name="section144418461996"></a>

系统每60秒周期性检测Hive服务，若Hive在Zookeeper上的注册信息丢失，或者Hive无法连接上Zookeeper，将会发出告警。

## 告警属性<a name="section02124481013"></a>

<a name="table53284255"></a>
<table><thead align="left"><tr id="row47341147"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p9427704"><a name="p9427704"></a><a name="p9427704"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p25446578"><a name="p25446578"></a><a name="p25446578"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p47906928"><a name="p47906928"></a><a name="p47906928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55255963"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46547994"><a name="p46547994"></a><a name="p46547994"></a>16047</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p12291158"><a name="p12291158"></a><a name="p12291158"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56059702"><a name="p56059702"></a><a name="p56059702"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section11951012194719"></a>

<a name="table7221941"></a>
<table><thead align="left"><tr id="row38703738"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p47995043"><a name="p47995043"></a><a name="p47995043"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p62393236"><a name="p62393236"></a><a name="p62393236"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row206858329322"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row20687350"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1376621317100"><a name="p1376621317100"></a><a name="p1376621317100"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p35582507"><a name="p35582507"></a><a name="p35582507"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row51807112"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15766121315107"><a name="p15766121315107"></a><a name="p15766121315107"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p70810"><a name="p70810"></a><a name="p70810"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row637295"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2076651312109"><a name="p2076651312109"></a><a name="p2076651312109"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20545297"><a name="p20545297"></a><a name="p20545297"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section1123167144819"></a>

当无法在Zookeeper上读取到Hive的配置，将会导致hiveserver不可用。

## 可能原因<a name="section194330194913"></a>

-   网络故障。
-   ZooKeeper实例状态异常。

## 处理步骤<a name="section122691220163316"></a>

**重启相关实例。**

1.  登录FusionInsight Manager，在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“Hive解注Zookeeper”所在行的下拉菜单，在“定位信息”中查看告警上报的角色名并确定实例IP地址。
2.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hive \> 实例”，勾选上报告警IP对应的实例，选择“更多 \> 重启实例”。
3.  重启完成后，等待5分钟，查看告警是否消除。
    -   是，处理完毕。
    -   否，执行[4](#li57092876161840)。


**收集故障信息。**

1.  <a name="li57092876161840"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Hive”。
3.  单击右上角的![](figures/zh-cn_image_0263895811.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section141961271574"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

