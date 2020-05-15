# ALM-12051 磁盘Inode使用率超过阈值<a name="ZH-CN_TOPIC_0191883144"></a>

## 告警解释<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section59276500"></a>

系统每30秒周期性检测磁盘Inode使用率，并把实际Inode使用率和阈值（系统默认阈值80%）进行比较，当检测到Inode使用率连续多次（默认值为5）超过阈值时产生该告警。

用户可通过“系统设置 \> 阈值配置 \> 设备 \> 主机 \> 磁盘 \> 磁盘inode使用率 \> 磁盘inode使用率”修改阈值。

平滑次数为1，磁盘Inode使用率小于或等于阈值时，告警恢复；平滑次数大于1，磁盘Inode使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section63726460"></a>

<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_table29292504"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row61554389"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p19849632"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p19849632"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p19849632"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64316372"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64316372"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64316372"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p42243607"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p42243607"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p42243607"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row66289044"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p703473"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p703473"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p703473"></a>12051</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p56981334"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p56981334"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p56981334"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52085356"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52085356"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52085356"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section36667229"></a>

<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_table58164314"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row47193835"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64604306"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64604306"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p64604306"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p65566326"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p65566326"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p65566326"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row9272190"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p12849939"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p12849939"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p12849939"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p34212124"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p34212124"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p34212124"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row39473664"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p43250195"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p43250195"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p43250195"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p13604878"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p13604878"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p13604878"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row55335042"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52953454"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52953454"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p52953454"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p61371349"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p61371349"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p61371349"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row15471235"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p45210545"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p45210545"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p45210545"></a>PartitionName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38175503"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38175503"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38175503"></a>产生告警的磁盘分区。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_row8035207"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p46872049"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p46872049"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p46872049"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38539615"><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38539615"></a><a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_p38539615"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section61569610"></a>

文件系统无法正常写入。

## 可能原因<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section17255578"></a>

-   磁盘小文件过多。
-   系统环境异常。

## 处理步骤<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section21082480"></a>

**磁盘小文件过多。**

1.  登录MRS集群详情页面，选择“告警管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“告警管理”。  

2.  在实时告警列表中，单击此告警。在“告警详情”区域，获取告警所在主机地址和磁盘分区。
3.  使用PuTTY工具，以**root**用户登录告警所在主机。
4.  执行命令**df -i** _分区名称_，查看磁盘当前Inode使用率。
5.  若Inode使用率超过阈值，手工排查该分区存在的小文件，确认是否能够删除这些文件。
    -   是，删除文件，执行[6](#zh-cn_topic_0191813886_zh-cn_topic_0087039294_li4609093115844)。
    -   否，容量调整。执行[7](#zh-cn_topic_0191813886_zh-cn_topic_0087039294_li946980415844)。

6.  <a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_li4609093115844"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#zh-cn_topic_0191813886_zh-cn_topic_0087039294_li946980415844)。


**检查系统环境是否异常。**

1.  <a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_li946980415844"></a>联系操作系统维护人员，检查操作系统是否存在异常。
    -   是，恢复操作系统故障，执行[8](#zh-cn_topic_0191813886_zh-cn_topic_0087039294_li1457809415844)。
    -   否，执行[9](#zh-cn_topic_0191813886_li572522141314)

2.  <a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_li1457809415844"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[9](#zh-cn_topic_0191813886_li572522141314)

3.  <a name="zh-cn_topic_0191813886_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813886_zh-cn_topic_0087039294_section55524596"></a>

无。

