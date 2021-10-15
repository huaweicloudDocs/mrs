# ALM-14011 DataNode数据目录配置不合理<a name="ALM-14011"></a>

## 告警解释<a name="section18087034"></a>

DataNode的配置参数“dfs.datanode.data.dir”指定了DataNode的数据目录。当所配置的目录路径无法创建、与系统关键目录使用同一磁盘或多个目录使用同一磁盘时，系统即刻产生此告警。

当修改DataNode的数据目录合理后，重启该DataNode，告警清除。

## 告警属性<a name="section28565585"></a>

<a name="table18898922"></a>
<table><thead align="left"><tr id="row15701897"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p63894178"><a name="p63894178"></a><a name="p63894178"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p8045935"><a name="p8045935"></a><a name="p8045935"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p47741017"><a name="p47741017"></a><a name="p47741017"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row41817159"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p31746722"><a name="p31746722"></a><a name="p31746722"></a>14011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p21347665"><a name="p21347665"></a><a name="p21347665"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p51439293"><a name="p51439293"></a><a name="p51439293"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section55763678"></a>

<a name="table5833165"></a>
<table><thead align="left"><tr id="row39879378"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p9004205"><a name="p9004205"></a><a name="p9004205"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p58252017"><a name="p58252017"></a><a name="p58252017"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1487192016315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row20792900"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57011518"><a name="p57011518"></a><a name="p57011518"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row43341616"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24088486"><a name="p24088486"></a><a name="p24088486"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row15469783"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28650366"><a name="p28650366"></a><a name="p28650366"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section32111058"></a>

如果将DataNode数据目录挂载在根目录等系统关键目录，长时间运行后会将根目录写满，导致系统故障。

不合理的DataNode数据目录配置，会造成HDFS的性能下降。

## 可能原因<a name="section20564070"></a>

-   DataNode数据目录创建失败。
-   DataNode数据目录与系统关键目录（“/”或“/boot”）使用同一磁盘。
-   DataNode数据目录中多个目录使用同一磁盘。

## 处理步骤<a name="section50858907"></a>

**查看告警原因和产生告警的DataNode节点信息。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中单击此告警。
2.  通过“定位信息”的“主机名”，获取告警产生的DataNode节点的主机名。

**删除DataNode数据目录中与磁盘规划不符的目录。**

1.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，在实例列表中单击产生告警的节点主机上的DataNode实例。
2.  单击“实例配置”，查看DataNode数据目录配置参数“dfs.datanode.data.dir”的值。
3.  查看所有的DataNode数据目录，是否有与磁盘规划不一致的目录。
    -   是，执行[6](#li22147925173246)。
    -   否，执行[9](#li51341222173246)。

4.  <a name="li22147925173246"></a>修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，删除错误的路径。
5.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，重启该DataNode实例。
6.  检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[9](#li51341222173246)。

7.  <a name="li51341222173246"></a>以**root**用户登录到产生告警的DataNode的节点，用户密码为安装前用户自定义，请咨询系统管理员。
    -   如果告警原因为“DataNode数据目录创建失败”，执行[10](#li48113921173246)。
    -   如果告警原因为“DataNode数据目录与系统关键目录（/或/boot）使用同一磁盘”，执行[17](#li36131883173246)。
    -   如果告警原因为“DataNode数据目录中多个目录使用同一磁盘”，执行[21](#li7154725173246)。


**检查DataNode数据目录是否创建失败。**

1.  <a name="li48113921173246"></a>执行**su - omm**命令，切换到**omm**用户。
2.  使用**ls**命令查看DataNode数据目录中的每个目录是否存在。
    -   是，执行[26](#li20154080173246)。
    -   否，执行[12](#li55040384173246)。

3.  <a name="li55040384173246"></a>使用**mkdir **_数据目录_命令创建该目录，查看是否可以创建成功。
    -   是，执行[24](#li29074367173246)。
    -   否，执行[13](#li43329692173246)。

4.  <a name="li43329692173246"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否存在告警“ALM-12017 磁盘容量不足”。
    -   是，执行[14](#li55131325173246)。
    -   否，执行[15](#li24319703173246)。

5.  <a name="li55131325173246"></a>参考“ALM-12017 磁盘容量不足”对磁盘容量问题进行处理，查看“ALM-12017 磁盘容量不足”告警是否消除。
    -   是，执行[12](#li55040384173246)。
    -   否，执行[15](#li24319703173246)。

6.  <a name="li24319703173246"></a>查看**omm**用户对该目录的所有上层目录是否有“rwx”或者“x”权限。（例如“/tmp/abc/”，“tmp”目录有“x”权限，“abc”目录有“rwx”权限。）
    -   是，执行[24](#li29074367173246)。
    -   否，执行[16](#li60926900173246)。

7.  <a name="li60926900173246"></a>在**root**用户下，执行**chmod u+rwx **_path_或者**chmod u+x **_path_命令给这些路径添加**omm**用户的“rwx”或者“x”权限，然后执行[12](#li55040384173246)。

**检查DataNode数据目录是否与系统关键目录使用同一磁盘。**

1.  <a name="li36131883173246"></a>分别使用**df**命令获取DataNode数据目录中的每个目录的磁盘挂载情况。
2.  查看命令结果的磁盘挂载目录是否为系统关键目录（“/”或“/boot”）。
    -   是，执行[19](#li7514622173246)。
    -   否，执行[24](#li29074367173246)。

3.  <a name="li7514622173246"></a>修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，删除与系统关键目录使用同一磁盘的目录。
4.  继续执行[24](#li29074367173246)。

**检查DataNode数据目录中是否多个目录使用同一磁盘。**

1.  <a name="li7154725173246"></a>分别使用**df**命令获取DataNode数据目录中每个目录的磁盘挂载情况。记录命令结果的磁盘挂载目录。
2.  修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，对于其中磁盘挂载目录相同的DataNode目录，仅保留其中的一个目录，删除其他目录。
3.  继续执行[24](#li29074367173246)。

**重启DataNode，检查告警是否消除。**

1.  <a name="li29074367173246"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，重启该DataNode实例。
2.  检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[26](#li20154080173246)。


**收集故障信息。**

1.  <a name="li20154080173246"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section55076987"></a>

无。

