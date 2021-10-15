# ALM-14002 DataNode磁盘空间使用率超过阈值<a name="ALM-14002"></a>

## 告警解释<a name="section7524158"></a>

系统每30秒周期性检测DataNode磁盘空间使用率，并把实际磁盘使用率和阈值相比较。DataNode磁盘空间使用率指标默认提供一个阈值范围。当检测到DataNode磁盘空间使用率指标超出阈值范围时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

平滑次数为1，DataNode磁盘空间使用率指标的值小于或等于阈值时，告警恢复；平滑次数大于1，DataNode磁盘空间使用率指标的值小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section608563"></a>

<a name="table40343619"></a>
<table><thead align="left"><tr id="row45326725"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p47586108"><a name="p47586108"></a><a name="p47586108"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p29269531"><a name="p29269531"></a><a name="p29269531"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p22021835"><a name="p22021835"></a><a name="p22021835"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row38938228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p66988733"><a name="p66988733"></a><a name="p66988733"></a>14002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57378254"><a name="p57378254"></a><a name="p57378254"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p17126992"><a name="p17126992"></a><a name="p17126992"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section5477075"></a>

<a name="table45109098"></a>
<table><thead align="left"><tr id="row29250257"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p20460612"><a name="p20460612"></a><a name="p20460612"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p46696884"><a name="p46696884"></a><a name="p46696884"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row3352617113212"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row24351240"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p49391998"><a name="p49391998"></a><a name="p49391998"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row41874799"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p63982358"><a name="p63982358"></a><a name="p63982358"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row38970312"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66558579"><a name="p66558579"></a><a name="p66558579"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row62156303"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1495784"><a name="p1495784"></a><a name="p1495784"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p54049714"><a name="p54049714"></a><a name="p54049714"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section49293677"></a>

DataNode容量不足，会影响到HDFS的数据写入。

## 可能原因<a name="section40989916"></a>

-   集群磁盘容量已满。
-   DataNode节点间数据倾斜。

## 处理步骤<a name="section33364928"></a>

**检查集群磁盘容量是否已满。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”页面，查看是否存在“ALM-14001 HDFS磁盘空间使用率超过阈值”告警。
    -   是，执行[2](#li48847933162749)。
    -   否，执行[4](#li49504103162749)。

2.  <a name="li48847933162749"></a>参考“ALM-14001 HDFS磁盘空间使用率超过阈值”进行处理，查看对应告警是否清除。
    -   是，执行[3](#li5500455162749)。
    -   否，执行[11](#li17443443162749)。

3.  <a name="li5500455162749"></a>在“运维 \> 告警 \> 告警”页面查看本告警是否清除。
    -   是，处理完毕。
    -   否，执行[4](#li49504103162749)。


**检查DataNode节点平衡状态。**

1.  <a name="li49504103162749"></a>在FusionInsight Manager首页，单击“主机”，查看各个机架上的DatNode节点数目分布是否大致相等，如果差异过大，调整DataNode节点所属机架，保证各个机架上的DataNode数量大致相等。重启HDFS服务生效。
2.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”。
3.  在“基本信息”区域，单击“NameNode\(主\)”，进入HDFS WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

4.  在HDFS WebUI的“Summary”区域，查看“DataNodes usages”中“Max”的值是否比“Median”的值大10%。
    -   是，执行[8](#li25048823162749)。
    -   否，执行[11](#li17443443162749)。

5.  <a name="li25048823162749"></a>数据倾斜，需要均衡集群中的数据。以**root**用户登录MRS客户端，用户密码为安装前用户自定义，请咨询系统管理员。如果集群为普通模式，执行**su - omm**切换到**omm**用户。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**。如果集群采用安全版本，要进行安全认证。执行**kinit hdfs**命令，按提示输入密码。向管理员获取密码。
6.  执行以下命令，均衡数据分布：

    **hdfs balancer -threshold 10**

7.  等待几分钟，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[11](#li17443443162749)。


**收集故障信息。**

1.  <a name="li17443443162749"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section31848898"></a>

无。

