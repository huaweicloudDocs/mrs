# ALM-19000 HBase服务不可用<a name="ZH-CN_TOPIC_0191883110"></a>

## 告警解释<a name="zh-cn_topic_0191813964_section18389930"></a>

告警模块按30秒周期检测HBase服务状态。当HBase服务不可用时产生该告警。

HBase服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0191813964_section31291646"></a>

<a name="zh-cn_topic_0191813964_table57434139"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813964_row461342"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813964_p37368736"><a name="zh-cn_topic_0191813964_p37368736"></a><a name="zh-cn_topic_0191813964_p37368736"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813964_p6968762"><a name="zh-cn_topic_0191813964_p6968762"></a><a name="zh-cn_topic_0191813964_p6968762"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813964_p27598869"><a name="zh-cn_topic_0191813964_p27598869"></a><a name="zh-cn_topic_0191813964_p27598869"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813964_row20915929"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813964_p16468652"><a name="zh-cn_topic_0191813964_p16468652"></a><a name="zh-cn_topic_0191813964_p16468652"></a>19000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813964_p58892473"><a name="zh-cn_topic_0191813964_p58892473"></a><a name="zh-cn_topic_0191813964_p58892473"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813964_p5560998"><a name="zh-cn_topic_0191813964_p5560998"></a><a name="zh-cn_topic_0191813964_p5560998"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813964_section13189358"></a>

<a name="zh-cn_topic_0191813964_table47787675"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813964_row20947391"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813964_p19017142"><a name="zh-cn_topic_0191813964_p19017142"></a><a name="zh-cn_topic_0191813964_p19017142"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813964_p63993496"><a name="zh-cn_topic_0191813964_p63993496"></a><a name="zh-cn_topic_0191813964_p63993496"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813964_row16090703"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813964_p28278595"><a name="zh-cn_topic_0191813964_p28278595"></a><a name="zh-cn_topic_0191813964_p28278595"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813964_p8864859"><a name="zh-cn_topic_0191813964_p8864859"></a><a name="zh-cn_topic_0191813964_p8864859"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813964_row12674872"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813964_p20031746"><a name="zh-cn_topic_0191813964_p20031746"></a><a name="zh-cn_topic_0191813964_p20031746"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813964_p11958757"><a name="zh-cn_topic_0191813964_p11958757"></a><a name="zh-cn_topic_0191813964_p11958757"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813964_row40519951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813964_p60890569"><a name="zh-cn_topic_0191813964_p60890569"></a><a name="zh-cn_topic_0191813964_p60890569"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813964_p33189039"><a name="zh-cn_topic_0191813964_p33189039"></a><a name="zh-cn_topic_0191813964_p33189039"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813964_section51595365"></a>

无法进行数据读写和创建表等操作。

## 可能原因<a name="zh-cn_topic_0191813964_section61705107"></a>

-   ZooKeeper服务异常。
-   HDFS服务异常。
-   HBase服务异常。
-   网络异常。

## 处理步骤<a name="zh-cn_topic_0191813964_section18475057"></a>

1.  检查ZooKeeper服务状态。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  在服务列表中，查看ZooKeeper健康状态是否为“良好”。
        -   是，执行[2.a](#zh-cn_topic_0191813964_aalm-19000_mmccppss_hdfs)。
        -   否，执行[1.c](#zh-cn_topic_0191813964_aalm-19000_mmccppss_alm-53004)。

    3.  <a name="zh-cn_topic_0191813964_aalm-19000_mmccppss_alm-53004"></a>在告警列表中，查看是否有“ALM-13000 ZooKeeper服务不可用”告警产生。
        -   是，执行[1.d](#zh-cn_topic_0191813964_aalm-19000_mmccppss_process)。
        -   否，执行[2.a](#zh-cn_topic_0191813964_aalm-19000_mmccppss_hdfs)。

    4.  <a name="zh-cn_topic_0191813964_aalm-19000_mmccppss_process"></a>参考ALM-13000 ZooKeeper服务不可用的处理步骤处理该故障。
    5.  等待几分钟后检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813964_aalm-19000_mmccppss_hdfs)。

2.  检查HDFS服务状态。
    1.  <a name="zh-cn_topic_0191813964_aalm-19000_mmccppss_hdfs"></a>在告警列表中，查看是否有“ALM-14000 HDFS服务不可用”告警产生。
        -   是，执行[2.b](#zh-cn_topic_0191813964_alm)。
        -   否，执行[3](#zh-cn_topic_0191813964_li572522141314)。

    2.  <a name="zh-cn_topic_0191813964_alm"></a>参考ALM-14000 HDFS服务不可用的处理步骤处理该故障。
    3.  等待几分钟后检查本告警是否恢复。

3.  <a name="zh-cn_topic_0191813964_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813964_section32057793"></a>

无。

