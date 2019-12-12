# ALM-14011 HDFS DataNode数据目录配置不合理<a name="ZH-CN_TOPIC_0174499356"></a>

## 告警解释<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section63081244"></a>

DataNode的配置参数“dfs.datanode.data.dir”指定了DataNode的数据目录。当所配置的目录路径无法创建、与系统关键目录使用同一磁盘或多个目录使用同一磁盘时，系统产生此告警。

当修改DataNode的数据目录合理后，重启该DataNode，告警清除。

## 告警属性<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section30860289"></a>

<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_table41052960"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row577635"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46788488"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46788488"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46788488"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p31771169"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p31771169"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p31771169"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23327895"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23327895"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23327895"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row10511313"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46110007"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46110007"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p46110007"></a>14011</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p43923123"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p43923123"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p43923123"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p1003178"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p1003178"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p1003178"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section9307148"></a>

<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_table14148614"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row23313778"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p9367865"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p9367865"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p9367865"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p20599592"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p20599592"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p20599592"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row57954280"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p63785121"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p63785121"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p63785121"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p66321146"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p66321146"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p66321146"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row60019402"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p29733366"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p29733366"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p29733366"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p59592471"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p59592471"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p59592471"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_row66570199"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23477058"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23477058"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p23477058"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p22593558"><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p22593558"></a><a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_p22593558"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section16655470"></a>

如果将DataNode数据目录挂载在根目录等系统关键目录，长时间运行后会将根目录写满，导致系统故障。

不合理的DataNode数据目录配置，会造成HDFS的性能下降。

## 可能原因<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section15681504"></a>

-   DataNode数据目录创建失败。
-   DataNode数据目录与系统关键目录（“/”或“/boot”）使用同一磁盘。
-   DataNode数据目录中多个目录使用同一磁盘。

## 处理步骤<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section6915811"></a>

1.  查看告警原因和产生告警的DataNode节点信息。
    1.  在MRS Manager首页，单击“告警管理”，在告警列表中单击此告警。
    2.  在“告警详情”区域，查看“告警原因”，可知产生该告警的原因。 通过“定位信息”的“HostName”，获取告警产生的DataNode节点的主机名。

2.  删除DataNode数据目录中与磁盘规划不符的目录。
    1.  单击“服务管理 \> HDFS \> 实例”，在实例列表中单击产生告警的节点主机上的DataNode实例。
    2.  单击“实例配置”，查看DataNode数据目录配置参数“dfs.datanode.data.dir”的值。
    3.  查看所有的DataNode数据目录，是否有与磁盘规划不一致的目录。
        -   是，执行[2.d](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s6)。
        -   否，执行[2.g](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s9)。

    4.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s6"></a>修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，删除错误的路径。
    5.  单击“服务管理 \> HDFS \> 实例”，重启该DataNode实例。
    6.  检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.g](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s9)。

    7.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s9"></a>登录到产生告警的DataNode的节点。
        -   如果告警原因为“DataNode数据目录创建失败”，执行[3.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s10)。
        -   如果告警原因为“DataNode数据目录与系统关键目录（/或/boot）使用同一磁盘”，执行[4.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s16)。
        -   如果告警原因为“DataNode数据目录中多个目录使用同一磁盘”，执行[5.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s20)。

3.  检查DataNode数据目录是否创建失败。
    1.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s10"></a>执行以下命令切换用户：

        **sudo su - root**

        **su - omm**

    2.  使用**ls**命令查看DataNode数据目录中的每个目录是否存在。
        -   是，执行[7](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_li43237556162643)。
        -   否，执行[3.c](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s12)。

    3.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s12"></a>使用**mkdir** _数据目录_命令创建该目录，查看是否可以创建成功。
        -   是，执行[6.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23)。
        -   否，执行[3.d](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s1233)。

    4.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s1233"></a>在MRS Manager首页，单击“告警管理”，查看是否存在告警“ALM-12017 磁盘容量不足”。
        -   是，执行[3.e](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s154)。
        -   否，执行[3.f](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s13)。

    5.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s154"></a>参考[ALM-12017 磁盘容量不足](ALM-12017-磁盘容量不足-14.md#ZH-CN_TOPIC_0174499330)对磁盘容量问题进行处理，查看“ALM-12017 磁盘容量不足”告警是否消除。
        -   是，执行[3.c](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s12)。
        -   否，执行[7](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_li43237556162643)。

    6.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s13"></a>查看**omm**用户对该目录的所有上层目录是否有“rwx”或者“x”权限。（例如“/tmp/abc/”，“tmp”目录有“x”权限，“abc”目录有“rwx”权限。）
        -   是，执行[6.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23)。
        -   否，执行[3.g](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s14)。

    7.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s14"></a>在**root**用户下，执行**chmod u+rwx** _path_或者**chmod u+x** _path_命令给这些路径添加**omm**用户的“rwx”或者“x”权限，然后执行[3.c](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_alm14011_mmccppss_s12)。

4.  检查DataNode数据目录是否与系统关键目录使用同一磁盘。
    1.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s16"></a>分别使用**df**命令获取DataNode数据目录中的每个目录的磁盘挂载情况。
    2.  查看命令结果的磁盘挂载目录是否为系统关键目录（“/”或“/boot”）。
        -   是，执行[4.c](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s18)。
        -   否，执行[6.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23)。

    3.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s18"></a>修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，删除与系统关键目录使用同一磁盘的目录。
    4.  继续执行[6.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23)。

5.  检查DataNode数据目录中是否多个目录使用同一磁盘。
    1.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s20"></a>分别使用**df**命令获取DataNode数据目录中每个目录的磁盘挂载情况。记录命令结果的磁盘挂载目录。
    2.  修改该DataNode节点的配置参数“dfs.datanode.data.dir”的值，对于其中磁盘挂载目录相同的DataNode目录，仅保留其中的一个目录，删除其他目录。
    3.  继续执行[6.a](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23)。

6.  重启DataNode，检查告警是否消除。
    1.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_s23"></a>在MRS Manager界面，单击“服务管理 \> HDFS \> 实例”，重启该DataNode实例。
    2.  检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[7](#zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_li43237556162643)。

7.  <a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_li43237556162643"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195056_zh-cn_topic_0041039540_zh-cn_topic_0035998730_section62242305"></a>

无。

