# ALM-18011 NodeManager进程垃圾回收（GC）时间超过阈值<a name="ALM-18011"></a>

## 告警解释<a name="section16517681"></a>

系统每60秒周期性检测NodeManager进程的垃圾回收（GC）占用时间，当检测到NodeManager进程的垃圾回收（GC）时间超出阈值（默认12秒）时，产生该告警。

垃圾回收（GC）时间小于阈值时，告警恢复。

## 告警属性<a name="section14441402"></a>

<a name="table24665974"></a>
<table><thead align="left"><tr id="row1557355"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p59036953"><a name="p59036953"></a><a name="p59036953"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p17263863"><a name="p17263863"></a><a name="p17263863"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p56195629"><a name="p56195629"></a><a name="p56195629"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55552100"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p3426243"><a name="p3426243"></a><a name="p3426243"></a>18011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p9090291"><a name="p9090291"></a><a name="p9090291"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p65224988"><a name="p65224988"></a><a name="p65224988"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section62863761"></a>

<a name="table48732645"></a>
<table><thead align="left"><tr id="row52976186"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p63212712"><a name="p63212712"></a><a name="p63212712"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p19956058"><a name="p19956058"></a><a name="p19956058"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5665450131914"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row5828025"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52731292"><a name="p52731292"></a><a name="p52731292"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row4819582"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13004313"><a name="p13004313"></a><a name="p13004313"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row49929958"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32090702"><a name="p32090702"></a><a name="p32090702"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row20380862"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p40237110"><a name="p40237110"></a><a name="p40237110"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p37980454"><a name="p37980454"></a><a name="p37980454"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section28902942"></a>

NodeManager进程的垃圾回收时间过长，可能影响该NodeManager进程正常提供服务。

## 可能原因<a name="section58799890"></a>

该NodeManager节点实例堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section59436966"></a>

**检查GC时间。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18011 NodeManager进程垃圾回收（GC）时间超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> NodeManager（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 垃圾回收”，勾选“NodeManager垃圾回收（GC）时间”。查看NodeManager每分钟的垃圾回收时间统计情况。

    **图 1**  定制NodeManager垃圾回收（GC）时间<a name="fig4235110205215"></a>  
    ![](figures/定制NodeManager垃圾回收（GC）时间.png "定制NodeManager垃圾回收（GC）时间")

3.  查看NodeManager每分钟的垃圾回收时间统计值是否大于告警阈值（默认12秒）。
    -   是，执行[4](#li2688022483816)。
    -   否，执行[7](#li4691665983816)。

4.  <a name="li2688022483816"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> NodeManager \> 系统”。将“GC\_OPTS”参数根据实际情况调大。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >集群中的NodeManager实例数量和NodeManager内存大小的对应关系参考如下：
    >-   集群中的NodeManager实例数据达到100，NodeManager实例的JVM参数建议配置为：-Xms2G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到200，NodeManager实例的JVM参数建议配置为：-Xms4G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到500以上，NodeManager实例的JVM参数建议配置为：-Xms8G -Xmx8G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  保存配置，并重启NodeManager实例。
6.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[7](#li4691665983816)。


**收集故障信息。**

1.  <a name="li4691665983816"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“NodeManager”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section65170651"></a>

无。

