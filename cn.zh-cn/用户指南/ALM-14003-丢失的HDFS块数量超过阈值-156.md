# ALM-14003 丢失的HDFS块数量超过阈值<a name="ALM-14003"></a>

## 告警解释<a name="section8243740"></a>

系统每30秒周期性检测丢失的块数量，并把丢失的块数量和阈值相比较。丢失的块数量指标默认提供一个阈值范围。当检测到丢失的HDFS块数量超出阈值范围时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

平滑次数为1，丢失的HDFS块数量小于或等于阈值时，告警恢复；平滑次数大于1，丢失的HDFS块数量小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section7084804"></a>

<a name="table38418539"></a>
<table><thead align="left"><tr id="row53418480"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p31929608"><a name="p31929608"></a><a name="p31929608"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p36161432"><a name="p36161432"></a><a name="p36161432"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p43394889"><a name="p43394889"></a><a name="p43394889"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row25325122"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p38069036"><a name="p38069036"></a><a name="p38069036"></a>14003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p63693103"><a name="p63693103"></a><a name="p63693103"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p58867698"><a name="p58867698"></a><a name="p58867698"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section63763242"></a>

<a name="table3554205"></a>
<table><thead align="left"><tr id="row22865724"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p40184376"><a name="p40184376"></a><a name="p40184376"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p33709057"><a name="p33709057"></a><a name="p33709057"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5538101328"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row46079102"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66669494"><a name="p66669494"></a><a name="p66669494"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row63154538"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26802723"><a name="p26802723"></a><a name="p26802723"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row39897916"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45657288"><a name="p45657288"></a><a name="p45657288"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row8262415"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65275865"><a name="p65275865"></a><a name="p65275865"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52853732"><a name="p52853732"></a><a name="p52853732"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row5921545"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p9883160"><a name="p9883160"></a><a name="p9883160"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62338491"><a name="p62338491"></a><a name="p62338491"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section36998271"></a>

HDFS存储数据丢失，HDFS可能会进入安全模式，无法提供写服务。丢失的块数据无法恢复。

## 可能原因<a name="section64548988"></a>

-   DataNode实例异常。
-   数据被删除。

## 处理步骤<a name="section44069987"></a>

**检查DataNode实例。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”。
2.  查看所有DataNode实例的状态是否为“良好”。
    -   是，执行[11](#li19356361163156)。
    -   否，执行[3](#li6471267163156)。

3.  <a name="li6471267163156"></a>重启DataNode实例，查看能否成功启动。
    -   是，执行[4](#li177391556152310)。
    -   否，执行[5](#li58241411163156)。

4.  <a name="li177391556152310"></a>选择“运维 \> 告警 \> 告警”，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li58241411163156)。


**删除被破坏的文件。**

1.  <a name="li58241411163156"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> NameNode\(主\)”，在HDFS的WebUI页面，查看列出的丢失块信息。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果有丢块，WebUI上会有一行红字显示。
    >-   **admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

2.  用户确认丢失块所在的文件是否有用。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >MapReduce任务运行过程中在“/mr-history“、“/tmp/hadoop-yarn“、“/tmp/logs“这三个目录中生成的文件不属于有用文件。

    -   是，执行[7](#li7098948163156)。
    -   否，执行[8](#li2696171714538)。

3.  <a name="li7098948163156"></a>用户确认丢失块所在的文件是否已备份。
    -   是，执行[8](#li2696171714538)。
    -   否，执行[11](#li19356361163156)。

4.  <a name="li2696171714538"></a>以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行如下命令：
    -   安全模式：

        **cd **_客户端安装目录_

        **source bigdata\_env**

        **kinit hdfs**

    -   普通模式：

        **su - omm**

        **cd **_客户端安装目录_

        **source bigdata\_env**

5.  在节点客户端执行**hdfs fsck / -delete**，删除丢失文件。如果丢失块所在的文件为有用文件，需要再次写入文件，恢复数据。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >删除文件为高危操作，在执行操作前请务必确认对应文件是否不再需要。

6.  选择“运维 \> 告警 \> 告警”，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li19356361163156)。


**收集故障信息。**

1.  <a name="li19356361163156"></a>在FusionInsight Manager首页，单击“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section61085563"></a>

无。

