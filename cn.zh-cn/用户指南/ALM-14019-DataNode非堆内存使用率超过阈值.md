# ALM-14019 DataNode非堆内存使用率超过阈值<a name="ALM-14019"></a>

## 告警解释<a name="section14450091"></a>

系统每30秒周期性检测HDFS DataNode非堆内存使用率，并把实际的HDFS DataNode非堆内存使用率和阈值相比较。HDFS DataNode非堆内存使用率指标默认提供一个阈值范围。当HDFS DataNode非堆内存使用率超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

当HDFS DataNode非堆内存使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="section62941962"></a>

<a name="table37860267"></a>
<table><thead align="left"><tr id="row53009842"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p65938784"><a name="p65938784"></a><a name="p65938784"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p39441254"><a name="p39441254"></a><a name="p39441254"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p40625005"><a name="p40625005"></a><a name="p40625005"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row2291100"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p51361436"><a name="p51361436"></a><a name="p51361436"></a>14019</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p66635669"><a name="p66635669"></a><a name="p66635669"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p28780078"><a name="p28780078"></a><a name="p28780078"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section29606751"></a>

<a name="table49484943"></a>
<table><thead align="left"><tr id="row49376809"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p40098603"><a name="p40098603"></a><a name="p40098603"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p26761434"><a name="p26761434"></a><a name="p26761434"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1661318515264"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row20192541"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10367873"><a name="p10367873"></a><a name="p10367873"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row26201996"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p45499472"><a name="p45499472"></a><a name="p45499472"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row6842072"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p62118993"><a name="p62118993"></a><a name="p62118993"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row22200031"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p53372063"><a name="p53372063"></a><a name="p53372063"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28169856"><a name="p28169856"></a><a name="p28169856"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section65134171"></a>

HDFS DataNode非堆内存使用率过高，会影响HDFS的数据读写性能。

## 可能原因<a name="section49336631"></a>

HDFS DataNode配置的非堆内存不足。

## 处理步骤<a name="section41376500"></a>

**清除无用文件。**

1.  以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**。

    如果集群采用安全版本，要进行安全认证。

    执行**kinit hdfs**命令，按提示输入密码。向管理员获取密码。

2.  执行**hdfs dfs -rm -r **_文件或目录路径_命令，确认删除无用的文件。
3.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li4041829095040)。


**查看DataNode JVM内存使用情况和当前配置。**

1.  <a name="li4041829095040"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”。
2.  在“基本信息”区域，单击“NameNode\(主\)”，显示HDFS WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

3.  <a name="li5265602195040"></a>在HDFS WebUI，单击“Datanodes”页签，查看所有告警DataNode节点的Block数量。
4.  <a name="li3727934695040"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置”，在“搜索”中，输入“GC\_OPTS”，确定当前“HDFS-\>DataNode”的“GC\_OPTS”内存参数。

**对系统进行调整。**

1.  根据[6](#li5265602195040)中的Block数量和[7](#li3727934695040)中DataNode配置的内存参数，检查当前配置的内存是否不合理。

    -   是，执行[9](#li521843995040)。
    -   否，执行[12](#li3777363695040)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单个DataNode实例上的平均Block数量和DataNode内存的对应关系参考值如下：
    >-   单个DataNode实例平均Block数量达到2,000,000，DataNode的JVM参数参考值为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M
    >-   单个DataNode实例平均Block数量达到5,000,000，DataNode的JVM参数参考值为：-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G

2.  <a name="li521843995040"></a>按照Block数量和内存对应关系，对DataNode的内存参数“GC\_OPTS”进行修改。
3.  保存配置，选择“概览 \> 更多 \> 重启服务”。
4.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[12](#li3777363695040)。


**收集故障信息。**

1.  <a name="li3777363695040"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下服务。
    -   ZooKeeper
    -   HDFS

3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section36844188"></a>

无。

