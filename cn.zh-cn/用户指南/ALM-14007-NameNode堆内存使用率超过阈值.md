# ALM-14007 NameNode堆内存使用率超过阈值<a name="ALM-14007"></a>

## 告警解释<a name="section18478403"></a>

系统每30秒周期性检测HDFS NameNode堆内存使用率，并把实际的HDFS NameNode堆内存使用率和阈值相比较。HDFS NameNode堆内存使用率指标默认提供一个阈值范围。当HDFS NameNode堆内存使用率超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

平滑次数为1，HDFS NameNode堆内存使用率小于或等于阈值时，告警恢复；平滑次数大于1，HDFS NameNode堆内存使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section32087900"></a>

<a name="table18896743"></a>
<table><thead align="left"><tr id="row65236322"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p49650740"><a name="p49650740"></a><a name="p49650740"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62287027"><a name="p62287027"></a><a name="p62287027"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p12084422"><a name="p12084422"></a><a name="p12084422"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row39314134"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p30328266"><a name="p30328266"></a><a name="p30328266"></a>14007</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p40670475"><a name="p40670475"></a><a name="p40670475"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5974144"><a name="p5974144"></a><a name="p5974144"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section20355649"></a>

<a name="table14143633"></a>
<table><thead align="left"><tr id="row64733184"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p8896528"><a name="p8896528"></a><a name="p8896528"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p49530177"><a name="p49530177"></a><a name="p49530177"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row187992533315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row52521402"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56016807"><a name="p56016807"></a><a name="p56016807"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row34389217"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7652801"><a name="p7652801"></a><a name="p7652801"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row1766353"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46320410"><a name="p46320410"></a><a name="p46320410"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row14230512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p11820857"><a name="p11820857"></a><a name="p11820857"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p17965366"><a name="p17965366"></a><a name="p17965366"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section48983113"></a>

HDFS NameNode堆内存使用率过高，会影响HDFS的数据读写性能。

## 可能原因<a name="section38194839"></a>

HDFS NameNode配置的堆内存不足。

## 处理步骤<a name="section8209235"></a>

**清除无用文件。**

1.  以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**。

    如果集群采用安全版本，要进行安全认证。

    执行**kinit hdfs**命令，按提示输入密码。向管理员获取密码。

2.  执行**hdfs dfs -rm -r **_文件或目录路径_命令，确认删除无用的文件。
3.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li5159765816514)。


**查看NameNode JVM内存使用情况和当前配置。**

1.  <a name="li5159765816514"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”。
2.  在“基本信息”区域，单击“NameNode\(主\)”，显示HDFS WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

3.  <a name="li1866075416514"></a>在HDFS WebUI，单击“Overview”页签，查看Summary部分显示的HDFS中当前文件数量，目录数量和块数量信息。
4.  <a name="li3512608216514"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置 \> 全部配置”，在“搜索”中，输入“GC\_OPTS”，确定当前“HDFS-\>NameNode”的“GC\_OPTS”内存参数。

**对系统进行调整。**

1.  根据[6](#li1866075416514)中的文件数据量和[7](#li3512608216514)中NameNode配置的堆内存参数，检查当前配置的内存是否不合理。

    -   是，执行[9](#li4682169216514)。
    -   否，执行[11](#li6080133416514)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >HDFS的文件对象数量（filesystem objects=files+blocks）和NameNode配置的JVM参数的对应关系建议如下：
    >-   文件对象数量达到10,000,000，则JVM参数建议配置为：-Xms6G -Xmx6G -XX:NewSize=512M -XX:MaxNewSize=512M
    >-   文件对象数量达到20,000,000，则JVM参数建议配置为：-Xms12G -Xmx12G -XX:NewSize=1G -XX:MaxNewSize=1G
    >-   文件对象数量达到50,000,000，则JVM参数建议配置为：-Xms32G -Xmx32G -XX:NewSize=3G -XX:MaxNewSize=3G
    >-   文件对象数量达到100,000,000，则JVM参数建议配置为：-Xms64G -Xmx64G -XX:NewSize=6G -XX:MaxNewSize=6G
    >-   文件对象数量达到200,000,000，则JVM参数建议配置为：-Xms96G -Xmx96G -XX:NewSize=9G -XX:MaxNewSize=9G
    >-   文件对象数量达到300,000,000，则JVM参数建议配置为：-Xms164G -Xmx164G -XX:NewSize=12G -XX:MaxNewSize=12G

2.  <a name="li4682169216514"></a>按照文件对象数量和内存对应关系，对NameNode的堆内存参数进行修改，并单击“保存”，选择“概览 \> 更多 \> 重启服务”进行重启。
3.  检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li6080133416514)。


**收集故障信息。**

1.  <a name="li6080133416514"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   ZooKeeper
    -   HDFS

3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section6774254"></a>

无。

