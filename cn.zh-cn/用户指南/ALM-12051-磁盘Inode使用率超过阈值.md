# ALM-12051 磁盘Inode使用率超过阈值<a name="ALM-12051"></a>

## 告警解释<a name="section59276500"></a>

系统每30秒周期性检测磁盘Inode使用率，并把实际Inode使用率和阈值（系统默认阈值80%）进行比较，当检测到Inode使用率连续多次（默认值为5）超过阈值时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> 主机 \> 磁盘 \> 磁盘inode使用率”修改阈值。

平滑次数为1，磁盘Inode使用率小于或等于阈值时，告警恢复；平滑次数大于1，磁盘Inode使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section63726460"></a>

<a name="table29292504"></a>
<table><thead align="left"><tr id="row61554389"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19849632"><a name="p19849632"></a><a name="p19849632"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p64316372"><a name="p64316372"></a><a name="p64316372"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p42243607"><a name="p42243607"></a><a name="p42243607"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row66289044"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p703473"><a name="p703473"></a><a name="p703473"></a>12051</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p56981334"><a name="p56981334"></a><a name="p56981334"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p52085356"><a name="p52085356"></a><a name="p52085356"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section36667229"></a>

<a name="table58164314"></a>
<table><thead align="left"><tr id="row47193835"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p64604306"><a name="p64604306"></a><a name="p64604306"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p65566326"><a name="p65566326"></a><a name="p65566326"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row182795517374"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row9272190"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p12849939"><a name="p12849939"></a><a name="p12849939"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p34212124"><a name="p34212124"></a><a name="p34212124"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row39473664"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p43250195"><a name="p43250195"></a><a name="p43250195"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13604878"><a name="p13604878"></a><a name="p13604878"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row55335042"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p52953454"><a name="p52953454"></a><a name="p52953454"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61371349"><a name="p61371349"></a><a name="p61371349"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row15471235"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p45210545"><a name="p45210545"></a><a name="p45210545"></a>设备分区</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p38175503"><a name="p38175503"></a><a name="p38175503"></a>产生告警的磁盘分区。</p>
</td>
</tr>
<tr id="row8035207"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p46872049"><a name="p46872049"></a><a name="p46872049"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p38539615"><a name="p38539615"></a><a name="p38539615"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section61569610"></a>

文件系统无法正常写入。

## 可能原因<a name="section17255578"></a>

磁盘写入的小文件过多。

## 处理步骤<a name="section21082480"></a>

**磁盘写入的小文件过多。**

1.  打开FusionInsight Manager页面，选择“运维 \> 告警 \> 告警”，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，获取告警所在主机地址和磁盘分区。
2.  以**root**用户登录告警所在主机，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行命令**df -i | grep -iE "**_分区名称|_**Filesystem"**，查看磁盘当前Inode使用率。

    ```
    # df -i | grep -iE "xvda2|Filesystem"
    Filesystem            Inodes   IUsed   IFree IUse% Mounted on
    /dev/xvda2           2359296  207420 2151876    9% /
    ```

4.  若Inode使用率超过阈值，手工排查该分区存在的小文件，确认是否能够删除这些文件。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >可使用命令**for i in /\*; do echo $i; find $i|wc -l; done**查看分区下的文件个数，使用时请替换“/\*”为需要检查的分区。

    ```
    # for i in /srv/*; do echo $i; find $i|wc -l; done
    /srv/BigData
    4284
    /srv/ftp
    1
    /srv/www
    13
    ```

    -   是，执行**rm -rf **_待删除文件或文件夹路径_命令，删除文件，执行[5](#li4609093115844)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >删除文件为高危操作，在执行操作前请务必确认对应文件是否不再需要。

    -   否，进行磁盘扩容，执行[5](#li4609093115844)。

5.  <a name="li4609093115844"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[6](#li6409398815844)。


**收集故障信息。**

1.  <a name="li6409398815844"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OMS”，单击“确定”。
3.  设置“主机”为告警所在节点和主OMS节点。
4.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后30分钟，单击“下载”。
5.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section55524596"></a>

无。

