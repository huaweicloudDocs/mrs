# ALM-14020 HDFS目录条目数量超过阈值<a name="ALM-14020"></a>

## 告警解释<a name="section15079333"></a>

系统每一个小时获取指定目录下直接子文件/目录的数量，判断其是否达到HDFS目录最大子文件/目录个数的百分比阈值（默认为“90%”），如果超过该阈值，则触发告警。

当发出告警的目录的子目录/文件数所占百分比低于阈值后，该告警将自动恢复。当监控开关关闭，所有目录对应的该告警都将自动恢复。当从监控列表中移除指定目录时，该目录对应的告警也会自动恢复。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   HDFS目录的子文件/目录最大个数由参数“dfs.namenode.fs-limits.max-directory-items”指定，默认值为“1048576”。如果一个目录的子文件/目录数量超过该值，则无法再在该目录下创建新的子文件/目录。
>-   要监控的目录列表由参数“dfs.namenode.directory-items.monitor”指定，默认值为“/tmp,/SparkJobHistory,/mr-history”。
>-   监控开关由参数“dfs.namenode.directory-items.monitor.enabled”指定，默认值为“true”，即该检测默认开启。

## 告警属性<a name="section1496275"></a>

<a name="table56711048"></a>
<table><thead align="left"><tr id="row52804377"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p49296111"><a name="p49296111"></a><a name="p49296111"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p33562054"><a name="p33562054"></a><a name="p33562054"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p34171845"><a name="p34171845"></a><a name="p34171845"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row16456085"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p57874526"><a name="p57874526"></a><a name="p57874526"></a>14020</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57324999"><a name="p57324999"></a><a name="p57324999"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p12813304"><a name="p12813304"></a><a name="p12813304"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section13466476"></a>

<a name="table31244698"></a>
<table><thead align="left"><tr id="row11302604"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p43095755"><a name="p43095755"></a><a name="p43095755"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p1095262"><a name="p1095262"></a><a name="p1095262"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row9555192192713"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row21607406"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32271651"><a name="p32271651"></a><a name="p32271651"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row22009403"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52530424"><a name="p52530424"></a><a name="p52530424"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row3011776"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42627266"><a name="p42627266"></a><a name="p42627266"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p30256537"><a name="p30256537"></a><a name="p30256537"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row3873384"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p45308697"><a name="p45308697"></a><a name="p45308697"></a>目录名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46125842"><a name="p46125842"></a><a name="p46125842"></a>产生告警的目录名称。</p>
</td>
</tr>
<tr id="row12479402"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p4198627"><a name="p4198627"></a><a name="p4198627"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4544505"><a name="p4544505"></a><a name="p4544505"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section54089427"></a>

当监控目录下的条目数超过系统阈值的90%触发该告警，但不影响对该目录继续增加条目。一旦超过系统最大阈值，继续增加条目会失败。

## 可能原因<a name="section17042800"></a>

监控目录的条目数超过系统阈值的90%。

## 处理步骤<a name="section19167476"></a>

**检查系统中是否有不需要的文件。**

1.  以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**命令设置环境变量。

    如果集群采用安全版本，要进行安全认证。

    执行**kinit hdfs**命令，按提示输入密码（向管理员获取密码）。

2.  执行如下命令，检查发出告警的目录下的文件或目录是否是可以删除的无用文件。

    **hdfs dfs -ls **_产生告警的目录路径_

    -   是，执行[3](#li5806229095637)。
    -   否，执行[5](#li513756095637)。

3.  <a name="li5806229095637"></a>执行如下命令。删除无用的文件。

    **hdfs dfs -rm -r -f **_文件或目录路径_

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >删除文件为高危操作，在执行操作前请务必确认对应文件是否不再需要。

4.  等待1个小时，检查该告警是否清除。
    -   是，处理完毕。
    -   否，执行[5](#li513756095637)。


**检查系统阈值是否正确设置。**

1.  <a name="li513756095637"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置”，搜索“dfs.namenode.fs-limits.max-directory-items”参数，确定当前值配置是否合理。
    -   是，执行[9](#li4057059995637)。
    -   否，执行[6](#li4623804895637)。

2.  <a name="li4623804895637"></a>增大该参数值。
3.  保存配置，选择“概览 \> 更多 \> 重启服务”。
4.  等待1个小时，检查该告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li4057059995637)。


**收集故障信息。**

1.  <a name="li4057059995637"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section38289560"></a>

无。

