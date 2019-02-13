# ALM-14004 损坏的HDFS块数量超过阈值<a name="ZH-CN_TOPIC_0093195050"></a>

## 告警解释<a name="zh-cn_topic_0035998724_section31497787"></a>

系统每30秒周期性检测损坏的块数量，并把损坏的块数量和阈值相比较。损坏的块数量指标默认提供一个阈值范围。当检测到损坏的块数量超出阈值范围时产生该告警。

当损坏的块数量小于或等于阈值时，告警恢复。建议使用命令（hdfs fsck /）验证是否有文件完全损坏。

## 告警属性<a name="zh-cn_topic_0035998724_section15044627"></a>

<a name="zh-cn_topic_0035998724_table32368095"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998724_row53402119"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998724_p30604389"><a name="zh-cn_topic_0035998724_p30604389"></a><a name="zh-cn_topic_0035998724_p30604389"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998724_p63036484"><a name="zh-cn_topic_0035998724_p63036484"></a><a name="zh-cn_topic_0035998724_p63036484"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998724_p5681612"><a name="zh-cn_topic_0035998724_p5681612"></a><a name="zh-cn_topic_0035998724_p5681612"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998724_row57557412"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998724_p31638772"><a name="zh-cn_topic_0035998724_p31638772"></a><a name="zh-cn_topic_0035998724_p31638772"></a>14004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998724_p12603749"><a name="zh-cn_topic_0035998724_p12603749"></a><a name="zh-cn_topic_0035998724_p12603749"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998724_p14270750"><a name="zh-cn_topic_0035998724_p14270750"></a><a name="zh-cn_topic_0035998724_p14270750"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998724_section1183915"></a>

<a name="zh-cn_topic_0035998724_table15080136"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998724_row66592127"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998724_p25253189"><a name="zh-cn_topic_0035998724_p25253189"></a><a name="zh-cn_topic_0035998724_p25253189"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998724_p32242465"><a name="zh-cn_topic_0035998724_p32242465"></a><a name="zh-cn_topic_0035998724_p32242465"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998724_row61502840"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998724_p15674164"><a name="zh-cn_topic_0035998724_p15674164"></a><a name="zh-cn_topic_0035998724_p15674164"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998724_p61647805"><a name="zh-cn_topic_0035998724_p61647805"></a><a name="zh-cn_topic_0035998724_p61647805"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998724_row17959338"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998724_p45420240"><a name="zh-cn_topic_0035998724_p45420240"></a><a name="zh-cn_topic_0035998724_p45420240"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998724_p55160823"><a name="zh-cn_topic_0035998724_p55160823"></a><a name="zh-cn_topic_0035998724_p55160823"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998724_row26685362"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998724_p14030717"><a name="zh-cn_topic_0035998724_p14030717"></a><a name="zh-cn_topic_0035998724_p14030717"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998724_p62746268"><a name="zh-cn_topic_0035998724_p62746268"></a><a name="zh-cn_topic_0035998724_p62746268"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998724_row27845503"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998724_p40893240"><a name="zh-cn_topic_0035998724_p40893240"></a><a name="zh-cn_topic_0035998724_p40893240"></a>NSName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998724_p24018105"><a name="zh-cn_topic_0035998724_p24018105"></a><a name="zh-cn_topic_0035998724_p24018105"></a>产生告警的NameService名称</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998724_row14836356"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998724_p60894213"><a name="zh-cn_topic_0035998724_p60894213"></a><a name="zh-cn_topic_0035998724_p60894213"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998724_p33484259"><a name="zh-cn_topic_0035998724_p33484259"></a><a name="zh-cn_topic_0035998724_p33484259"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998724_section10655236"></a>

数据损坏，HDFS读取文件异常。

## 可能原因<a name="zh-cn_topic_0035998724_section28788263"></a>

-   DataNode实例异常。
-   数据校验信息被破坏。

## 处理步骤<a name="zh-cn_topic_0035998724_section57767782"></a>

请联系运维人员，并发送已收集的故障日志信息。

## 参考信息<a name="zh-cn_topic_0035998724_section50147992"></a>

无。

