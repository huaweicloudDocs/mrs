# ALM-18009 MapReduce JobHistoryServer堆内存使用率超过阈值<a name="ZH-CN_TOPIC_0093195106"></a>

## 告警解释<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section46467513"></a>

系统每30秒周期性检测Mapreduce JobHistoryServer堆内存使用率，并把实际的Mapreduce JobHistoryServer堆内存使用率和阈值相比较。当Mapreduce JobHistoryServer堆内存使用率超出阈值（默认为最大堆内存的80%）时产生该告警。

用户可通过“系统设置 \> 阈值配置 \> 服务 \> Mapreduce”修改阈值。当MapReduce JobHistoryServer堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section15554440"></a>

<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_table29676093"></a>
<table><thead align="left"><tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row40212317"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p35972254"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p35972254"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p35972254"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28071463"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28071463"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28071463"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p59196065"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p59196065"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p59196065"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row30151988"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p26391943"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p26391943"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p26391943"></a>18009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p57372610"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p57372610"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p57372610"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p16669838"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p16669838"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p16669838"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section5772232"></a>

<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_table8079634"></a>
<table><thead align="left"><tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row17444750"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p3738651"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p3738651"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p3738651"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p34395333"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p34395333"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p34395333"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row34558579"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p47781518"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p47781518"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p47781518"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p45097725"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p45097725"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p45097725"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row3226344"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p60007281"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p60007281"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p60007281"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28751554"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28751554"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p28751554"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row57437397"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p21917606"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p21917606"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p21917606"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p30495700"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p30495700"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p30495700"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_row6025849"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p18331773"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p18331773"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p18331773"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p8478608"><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p8478608"></a><a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_p8478608"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section51950091"></a>

Mapreduce JobHistoryServer堆内存使用率过高，会影响Mapreduce 服务日志归档的性能，甚至造成内存溢出导致Mapreduce服务不可用。

## 可能原因<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section64897643"></a>

该节点Mapreduce JobHistoryServer实例堆内存使用量过大，或分配的堆内存不合理，导致使用量超过阈值。

## 处理步骤<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section47207880"></a>

1.  检查堆内存使用率。
    1.  在MRS Manager首页，选中“告警ID”为“18009”的告警，查看“定位信息”中的实例的IP地址及角色名。
    2.  在MRS Manager首页，单击“服务管理 \> MapReduce \> 实例 \> JobHistoryServer（对应上报告警实例IP地址） \> 定制 \> JobHistoryServer堆内存使用百分比统计“。查看堆内存使用情况。
    3.  查看JobHistoryServer使用的堆内存是否已达到JobHistoryServer设定的最大堆内存的80%。
        -   是，执行[1.d](#zh-cn_topic_0087154425_li1011493181634)。
        -   否，执行[2](#zh-cn_topic_0087154425_li40881691175629)。

    4.  <a name="zh-cn_topic_0087154425_li1011493181634"></a>在MRS Manager首页，单击“服务管理 \> MapReduce \> 服务配置 \> 全部配置 \> JobHistoryServer \> 系统“。将GC\_OPTS参数中-Xmx的值根据实际情况调大，并单击“保存配置”，勾选“重新启动角色实例。”，单击“确定”进行重启。
    5.  观察界面告警是否清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0087154425_li40881691175629)。


2.  <a name="zh-cn_topic_0087154425_li40881691175629"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0087154425_zh-cn_topic_0087039367_section22217739"></a>

无。

