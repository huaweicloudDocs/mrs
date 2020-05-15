# ALM-14000 HDFS服务不可用<a name="ZH-CN_TOPIC_0191883090"></a>

## 告警解释<a name="zh-cn_topic_0191813870_section18389930"></a>

系统每30秒周期性检测NameService的服务状态，当检测到所有的NameService服务都异常时，就会认为HDFS服务不可用，此时产生该告警。

至少一个NameService服务正常后，系统认为HDFS服务恢复，告警清除。

## 告警属性<a name="zh-cn_topic_0191813870_section31291646"></a>

<a name="zh-cn_topic_0191813870_table21421675"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813870_row9119245"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813870_p461342"><a name="zh-cn_topic_0191813870_p461342"></a><a name="zh-cn_topic_0191813870_p461342"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813870_p37368736"><a name="zh-cn_topic_0191813870_p37368736"></a><a name="zh-cn_topic_0191813870_p37368736"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813870_p6968762"><a name="zh-cn_topic_0191813870_p6968762"></a><a name="zh-cn_topic_0191813870_p6968762"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813870_row27598869"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813870_p20915929"><a name="zh-cn_topic_0191813870_p20915929"></a><a name="zh-cn_topic_0191813870_p20915929"></a>14000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813870_p16468652"><a name="zh-cn_topic_0191813870_p16468652"></a><a name="zh-cn_topic_0191813870_p16468652"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813870_p58892473"><a name="zh-cn_topic_0191813870_p58892473"></a><a name="zh-cn_topic_0191813870_p58892473"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813870_section13189358"></a>

<a name="zh-cn_topic_0191813870_table5560998"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813870_row7715150"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813870_p20947391"><a name="zh-cn_topic_0191813870_p20947391"></a><a name="zh-cn_topic_0191813870_p20947391"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813870_p19017142"><a name="zh-cn_topic_0191813870_p19017142"></a><a name="zh-cn_topic_0191813870_p19017142"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813870_row63993496"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813870_p16090703"><a name="zh-cn_topic_0191813870_p16090703"></a><a name="zh-cn_topic_0191813870_p16090703"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813870_p28278595"><a name="zh-cn_topic_0191813870_p28278595"></a><a name="zh-cn_topic_0191813870_p28278595"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813870_row53180767"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813870_p12674872"><a name="zh-cn_topic_0191813870_p12674872"></a><a name="zh-cn_topic_0191813870_p12674872"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813870_p20031746"><a name="zh-cn_topic_0191813870_p20031746"></a><a name="zh-cn_topic_0191813870_p20031746"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813870_row46067993"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813870_p40519951"><a name="zh-cn_topic_0191813870_p40519951"></a><a name="zh-cn_topic_0191813870_p40519951"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813870_p60890569"><a name="zh-cn_topic_0191813870_p60890569"></a><a name="zh-cn_topic_0191813870_p60890569"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813870_section51595365"></a>

无法为基于HDFS服务的HBase和MapReduce等上层部件提供服务。用户无法读写文件。

## 可能原因<a name="zh-cn_topic_0191813870_section61705107"></a>

-   ZooKeeper服务异常。
-   所有NameService服务异常。

## 处理步骤<a name="zh-cn_topic_0191813870_section18475057"></a>

1.  检查ZooKeeper服务状态。
    1.  登录MRS集群详情页面，在“组件管理”页签，查看ZooKeeper服务的健康状态是否为“良好”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面在“服务管理”页签查看。  

        -   是，执行[1.b](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss2)。
        -   否，执行[2.a](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss4)。

    2.  <a name="zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss2"></a>参考[ALM-13000 ZooKeeper服务不可用](ALM-13000-ZooKeeper服务不可用.md#ZH-CN_TOPIC_0191883087)对ZooKeeper服务状态异常进行处理，然后查看ZooKeeper服务的健康状态是否恢复为“良好”。
        -   是，执行[1.c](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss3)。
        -   否，执行[3](#zh-cn_topic_0191813870_li572522141314)。

    3.  <a name="zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss3"></a>等待5分钟后，在“告警管理”页面，查看本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss4)。

2.  处理NameService服务异常告警。
    1.  <a name="zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss4"></a>登录MRS集群详情页面，在“告警管理”页面查看所有NameService服务是否存在异常告警。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面在“告警管理”页签查看告警信息。  

        -   是，执行[2.b](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss5)。
        -   否，执行[3](#zh-cn_topic_0191813870_li572522141314)。

    2.  <a name="zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_ss5"></a>按照[ALM-14010 NameService服务异常](ALM-14010-NameService服务异常.md#ZH-CN_TOPIC_0191883099)的处理方法，依次对这些服务异常的NameService进行处理，然后查看是否消除各个NameService服务异常告警。
        -   是，执行[2.c](#zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_checkbk_5)。
        -   否，执行[3](#zh-cn_topic_0191813870_li572522141314)。

    3.  <a name="zh-cn_topic_0191813870_cn_58_42_000001_4_mmccppss_checkbk_5"></a>等待5分钟后，在“告警管理”页签，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813870_li572522141314)。

3.  <a name="zh-cn_topic_0191813870_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813870_section32057793"></a>

无。

