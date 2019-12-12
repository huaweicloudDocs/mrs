# ALM-14006 HDFS文件数超过阈值<a name="ZH-CN_TOPIC_0191883095"></a>

## 告警解释<a name="zh-cn_topic_0191813952_section38788755"></a>

系统每30秒周期性检测HDFS文件数，并把实际文件数和阈值相比较。HDFS文件数。当检测到HDFS文件数指标超出阈值范围时产生该告警。

当HDFS文件数指标的值小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813952_section13554483"></a>

<a name="zh-cn_topic_0191813952_table60344938"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813952_row59011071"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813952_p15167431"><a name="zh-cn_topic_0191813952_p15167431"></a><a name="zh-cn_topic_0191813952_p15167431"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813952_p20602375"><a name="zh-cn_topic_0191813952_p20602375"></a><a name="zh-cn_topic_0191813952_p20602375"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813952_p58179688"><a name="zh-cn_topic_0191813952_p58179688"></a><a name="zh-cn_topic_0191813952_p58179688"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813952_row14934289"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813952_p1717931"><a name="zh-cn_topic_0191813952_p1717931"></a><a name="zh-cn_topic_0191813952_p1717931"></a>14006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813952_p4934750"><a name="zh-cn_topic_0191813952_p4934750"></a><a name="zh-cn_topic_0191813952_p4934750"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813952_p64170449"><a name="zh-cn_topic_0191813952_p64170449"></a><a name="zh-cn_topic_0191813952_p64170449"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813952_section54881489"></a>

<a name="zh-cn_topic_0191813952_table30423852"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813952_row60888739"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813952_p33040847"><a name="zh-cn_topic_0191813952_p33040847"></a><a name="zh-cn_topic_0191813952_p33040847"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813952_p59062984"><a name="zh-cn_topic_0191813952_p59062984"></a><a name="zh-cn_topic_0191813952_p59062984"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813952_row19372405"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813952_p25660991"><a name="zh-cn_topic_0191813952_p25660991"></a><a name="zh-cn_topic_0191813952_p25660991"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813952_p65274381"><a name="zh-cn_topic_0191813952_p65274381"></a><a name="zh-cn_topic_0191813952_p65274381"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813952_row50598521"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813952_p4839561"><a name="zh-cn_topic_0191813952_p4839561"></a><a name="zh-cn_topic_0191813952_p4839561"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813952_p56460178"><a name="zh-cn_topic_0191813952_p56460178"></a><a name="zh-cn_topic_0191813952_p56460178"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813952_row38379555"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813952_p21736211"><a name="zh-cn_topic_0191813952_p21736211"></a><a name="zh-cn_topic_0191813952_p21736211"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813952_p15802639"><a name="zh-cn_topic_0191813952_p15802639"></a><a name="zh-cn_topic_0191813952_p15802639"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813952_row8006030"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813952_p44508680"><a name="zh-cn_topic_0191813952_p44508680"></a><a name="zh-cn_topic_0191813952_p44508680"></a>NSName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813952_p48433347"><a name="zh-cn_topic_0191813952_p48433347"></a><a name="zh-cn_topic_0191813952_p48433347"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813952_row33246944"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813952_p8647967"><a name="zh-cn_topic_0191813952_p8647967"></a><a name="zh-cn_topic_0191813952_p8647967"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813952_p29396722"><a name="zh-cn_topic_0191813952_p29396722"></a><a name="zh-cn_topic_0191813952_p29396722"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813952_section24171358"></a>

HDFS文件数过多，磁盘存储不足可能造成数据入库失败。对HDFS系统性能产生影响。

## 可能原因<a name="zh-cn_topic_0191813952_section16215635"></a>

HDFS文件数超过阈值。

## 处理步骤<a name="zh-cn_topic_0191813952_section11722994"></a>

1.  检查系统中是否有不需要的文件。
    1.  在集群节点使用客户端，执行**hdfs dfs -ls** _文件或目录路径_命令，检查该目录下的文件或目录是否是可以删除的无用文件。
        -   是，执行[1.b](#zh-cn_topic_0191813952_alm-14006_mmccppss_step4)。
        -   否，执行[2.a](#zh-cn_topic_0191813952_yt16)。

    2.  <a name="zh-cn_topic_0191813952_alm-14006_mmccppss_step4"></a>执行**hdfs dfs -rm -r** _文件或目录路径_命令。确认删除无用的文件，等待5分钟后，检查本告警是否清除。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813952_yt16)。

2.  检查系统中文件数量。
    1.  <a name="zh-cn_topic_0191813952_yt16"></a>在MRS Manager首页，单击“系统设置 \> 阈值配置”，进入阈值配置页面。
    2.  在左侧的导航列表中，单击“服务 \> HDFS \> HDFS文件 \> HDFS文件总数”。
    3.  修改页面右侧的规则中的阈值，以适应当前的HDFS文件数。

        HDFS文件数可以通单击“服务管理 \> HDFS”，在右侧“实时”区域中单击“定制”按钮，选择“HDFS File”监控项查看。

    4.  等待5分钟后，检查本告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813952_li572522141314)。

3.  <a name="zh-cn_topic_0191813952_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813952_section38398082"></a>

无。

