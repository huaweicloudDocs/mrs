# ALM-14008 DataNode堆内存使用率超过阈值<a name="ALM-14008"></a>

## 告警解释<a name="section17658421"></a>

系统每30秒周期性检测HDFS DataNode堆内存使用率，并把实际的HDFS DataNode堆内存使用率和阈值相比较。HDFS DataNode堆内存使用率指标默认提供一个阈值范围。当HDFS DataNode堆内存使用率超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

平滑次数为1，HDFS DataNode堆内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，HDFS DataNode堆内存使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section24708061"></a>

<a name="table36760852"></a>
<table><thead align="left"><tr id="row28821924"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p52874479"><a name="p52874479"></a><a name="p52874479"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p54974411"><a name="p54974411"></a><a name="p54974411"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p23742303"><a name="p23742303"></a><a name="p23742303"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row44078420"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p13582290"><a name="p13582290"></a><a name="p13582290"></a>14008</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p26423680"><a name="p26423680"></a><a name="p26423680"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p59943302"><a name="p59943302"></a><a name="p59943302"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section21045962"></a>

<a name="table23569293"></a>
<table><thead align="left"><tr id="row39583906"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p52179806"><a name="p52179806"></a><a name="p52179806"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p65814718"><a name="p65814718"></a><a name="p65814718"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row14883124423113"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row29391914"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36586825"><a name="p36586825"></a><a name="p36586825"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row60845974"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46916557"><a name="p46916557"></a><a name="p46916557"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row19595837"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p54815905"><a name="p54815905"></a><a name="p54815905"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row23581100"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p31020962"><a name="p31020962"></a><a name="p31020962"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p29670000"><a name="p29670000"></a><a name="p29670000"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55195931"></a>

HDFS DataNode堆内存使用率过高，会影响到HDFS的数据读写性能。

## 可能原因<a name="section27001339"></a>

HDFS DataNode配置的堆内存不足。

## 处理步骤<a name="section41685466"></a>

**清除无用文件。**

1.  以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**。

    如果集群采用安全版本，要进行安全认证。

    执行**kinit hdfs**命令，按提示输入密码。向管理员获取密码。

2.  执行**hdfs dfs -rm -r **_文件或目录路径_命令，确认删除无用的文件。
3.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li6209007816589)。


**查看DataNode JVM内存使用情况和当前配置。**

1.  <a name="li6209007816589"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”。
2.  在“基本信息”区域，单击“NameNode\(主\)”，显示HDFS WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

3.  <a name="li6324043616589"></a>在HDFS WebUI，单击“DataNodes”页签，查看所有告警DataNode节点的Block数量。
4.  <a name="li2220169816589"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置”。在“搜索”中，输入“GC\_OPTS”，确定当前“HDFS-\>DataNode”的“GC\_OPTS”内存参数。

**对系统进行调整。**

1.  根据[6](#li6324043616589)中的Block数量和[7](#li2220169816589)中DataNode配置的堆内存参数，检查当前配置的内存是否不合理。

    -   是，执行[9](#li4769989016589)。
    -   否，执行[11](#li4549818616589)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >单个DataNode实例平均Block数量和DataNode内存的对应关系参考值如下：
    >-   单个DataNode实例平均Block数量达到2,000,000，DataNode的JVM参数参考值为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M
    >-   单个DataNode实例平均Block数量达到5,000,000，DataNode的JVM参数参考值为：-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G

2.  <a name="li4769989016589"></a>按照Block数量和内存对应关系，对DataNode的堆内存参数进行修改，并单击“保存”，选择“概览 \> 更多 \> 重启服务”进行重启。
3.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li4549818616589)。


**收集故障信息。**

1.  <a name="li4549818616589"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section39624882"></a>

无。

