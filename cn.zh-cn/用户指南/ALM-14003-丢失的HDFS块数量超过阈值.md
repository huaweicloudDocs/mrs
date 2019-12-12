# ALM-14003 丢失的HDFS块数量超过阈值<a name="ZH-CN_TOPIC_0191883093"></a>

## 告警解释<a name="zh-cn_topic_0191813959_section59880657"></a>

系统每30秒周期性检测丢失的块数量，并把丢失的块数量和阈值相比较。丢失的块数量指标默认提供一个阈值范围。当检测到丢失的块数量超出阈值范围时产生该告警。

当丢失的块数量小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813959_section2055005"></a>

<a name="zh-cn_topic_0191813959_table47050372"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813959_row2854726"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813959_p29906272"><a name="zh-cn_topic_0191813959_p29906272"></a><a name="zh-cn_topic_0191813959_p29906272"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813959_p6488958"><a name="zh-cn_topic_0191813959_p6488958"></a><a name="zh-cn_topic_0191813959_p6488958"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813959_p55843593"><a name="zh-cn_topic_0191813959_p55843593"></a><a name="zh-cn_topic_0191813959_p55843593"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813959_row27037160"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813959_p42526340"><a name="zh-cn_topic_0191813959_p42526340"></a><a name="zh-cn_topic_0191813959_p42526340"></a>14003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813959_p22081476"><a name="zh-cn_topic_0191813959_p22081476"></a><a name="zh-cn_topic_0191813959_p22081476"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813959_p43769104"><a name="zh-cn_topic_0191813959_p43769104"></a><a name="zh-cn_topic_0191813959_p43769104"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813959_section18495050"></a>

<a name="zh-cn_topic_0191813959_table55636561"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813959_row36019552"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813959_p31902563"><a name="zh-cn_topic_0191813959_p31902563"></a><a name="zh-cn_topic_0191813959_p31902563"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813959_p33970848"><a name="zh-cn_topic_0191813959_p33970848"></a><a name="zh-cn_topic_0191813959_p33970848"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813959_row175293"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813959_p14198754"><a name="zh-cn_topic_0191813959_p14198754"></a><a name="zh-cn_topic_0191813959_p14198754"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813959_p9248440"><a name="zh-cn_topic_0191813959_p9248440"></a><a name="zh-cn_topic_0191813959_p9248440"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813959_row16127101"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813959_p31226782"><a name="zh-cn_topic_0191813959_p31226782"></a><a name="zh-cn_topic_0191813959_p31226782"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813959_p46341445"><a name="zh-cn_topic_0191813959_p46341445"></a><a name="zh-cn_topic_0191813959_p46341445"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813959_row14419821"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813959_p27154837"><a name="zh-cn_topic_0191813959_p27154837"></a><a name="zh-cn_topic_0191813959_p27154837"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813959_p52058165"><a name="zh-cn_topic_0191813959_p52058165"></a><a name="zh-cn_topic_0191813959_p52058165"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813959_row65870306"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813959_p33894570"><a name="zh-cn_topic_0191813959_p33894570"></a><a name="zh-cn_topic_0191813959_p33894570"></a>NSName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813959_p61105663"><a name="zh-cn_topic_0191813959_p61105663"></a><a name="zh-cn_topic_0191813959_p61105663"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813959_row13080057"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813959_p52851724"><a name="zh-cn_topic_0191813959_p52851724"></a><a name="zh-cn_topic_0191813959_p52851724"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813959_p53131231"><a name="zh-cn_topic_0191813959_p53131231"></a><a name="zh-cn_topic_0191813959_p53131231"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813959_section32237730"></a>

HDFS存储数据丢失，HDFS可能会进入安全模式，无法提供写服务。丢失的块数据无法恢复。

## 可能原因<a name="zh-cn_topic_0191813959_section21704116"></a>

-   DataNode实例异常。
-   数据被删除。

## 处理步骤<a name="zh-cn_topic_0191813959_section61119323"></a>

1.  检查DataNode实例。
    1.  在MRS集群详情页面，单击“组件管理 \> HDFS \> 实例”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请打开MRS Manager页面，单击“服务管理 \> HDFS \> 实例”。  

    2.  查看所有DataNode实例的状态是否为“良好”。
        -   是，执行[3](#zh-cn_topic_0191813959_li572522141314)。
        -   否，执行[1.c](#zh-cn_topic_0191813959_li2677020115402)。

    3.  <a name="zh-cn_topic_0191813959_li2677020115402"></a>重启DataNode实例，查看能否成功启动。
        -   是，执行[2.b](#zh-cn_topic_0191813959_li4975462315402)。
        -   否，执行[2.a](#zh-cn_topic_0191813959_li435173115402)。

2.  删除被破坏的文件。
    1.  <a name="zh-cn_topic_0191813959_li435173115402"></a>在集群节点使用客户端。执行**hdfs fsck / -delete**，删除丢失文件。然后再次写入文件，恢复数据。
    2.  <a name="zh-cn_topic_0191813959_li4975462315402"></a>等待5分钟后，单击“告警管理”，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813959_li572522141314)。

3.  <a name="zh-cn_topic_0191813959_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813959_section13202999"></a>

无。

