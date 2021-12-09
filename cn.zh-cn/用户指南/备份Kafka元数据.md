# 备份Kafka元数据<a name="admin_guide_000211"></a>

## 操作场景<a name="sbf7de999ef6f4ec7ada122bb4f6bbc39"></a>

为了确保Kafka元数据安全，或者系统管理员需要对ZooKeeper进行重大操作（如升级或迁移等）时，需要对Kafka元数据进行备份，从而保证系统在出现异常或未达到预期结果时可以及时进行数据恢复，将对业务的影响降到最低。

系统管理员可以通过FusionInsight Manager创建备份Kafka任务并备份元数据。支持创建任务自动或手动备份数据。

## 前提条件<a name="s1b2b090a07e447b58ba4e60370d64404"></a>

-   如果数据要备份至远端HDFS中，需要准备一个用于备份数据的备集群，认证模式需要与主集群相同。其他备份方式不需要准备备集群。
-   如果主集群部署为安全模式，且主备集群不是由同一个FusionInsight Manager管理，则必须配置系统互信，请参见[配置跨Manager集群互信](配置跨Manager集群互信.md)。如果主集群部署为普通模式，则不需要配置互信。
-   主备集群必须已配置跨集群拷贝，请参见[启用集群间拷贝功能](启用集群间拷贝功能.md)。
-   主备集群上的时间必须一致，而且主备集群上的NTP服务必须使用同一个时间源。
-   根据业务需要，规划备份的类型、周期和策略等规格，并检查主备管理节点“_数据存放路径_/LocalBackup/”是否有充足的空间。

-   如果数据要备份至NAS中，需要提前部署好NAS服务端。
-   如果数据要备份至OBS中，需要当前集群已对接OBS，并具有访问OBS的权限。

## 操作步骤<a name="s44a3cf2d415149559092f1577be77b61"></a>

1.  在FusionInsight Manager，选择“运维 \> 备份恢复 \> 备份管理”。
2.  单击“创建”。
3.  在“任务名称”填写备份任务的名称。
4.  在“备份对象”选择待操作的集群。
5.  在“备份类型”选择备份任务的运行类型。

    “周期备份”表示按周期自动执行备份，“手动备份”表示由手工执行备份。

    **表 1**  周期备份参数

    <a name="zh-cn_topic_0165590410_table193081738154917"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0165590410_row430813818490"><th class="cellrowborder" valign="top" width="21.84%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0165590410_p113081938184918"><a name="zh-cn_topic_0165590410_p113081938184918"></a><a name="zh-cn_topic_0165590410_p113081938184918"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="78.16%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0165590410_p173081538114915"><a name="zh-cn_topic_0165590410_p173081538114915"></a><a name="zh-cn_topic_0165590410_p173081538114915"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0165590410_row18308838144917"><td class="cellrowborder" valign="top" width="21.84%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0165590410_p030893804920"><a name="zh-cn_topic_0165590410_p030893804920"></a><a name="zh-cn_topic_0165590410_p030893804920"></a>开始时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.16%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0165590410_p103081838144917"><a name="zh-cn_topic_0165590410_p103081838144917"></a><a name="zh-cn_topic_0165590410_p103081838144917"></a>任务第一次启动的时间。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0165590410_row1530813813494"><td class="cellrowborder" valign="top" width="21.84%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0165590410_p1930833815494"><a name="zh-cn_topic_0165590410_p1930833815494"></a><a name="zh-cn_topic_0165590410_p1930833815494"></a>周期</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.16%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0165590410_p7308183834918"><a name="zh-cn_topic_0165590410_p7308183834918"></a><a name="zh-cn_topic_0165590410_p7308183834918"></a>任务下次启动，与上一次运行的时间间隔，支持“按小时”或“按天”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0165590410_row7308103810493"><td class="cellrowborder" valign="top" width="21.84%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0165590410_p16308153834910"><a name="zh-cn_topic_0165590410_p16308153834910"></a><a name="zh-cn_topic_0165590410_p16308153834910"></a>备份策略</p>
    </td>
    <td class="cellrowborder" valign="top" width="78.16%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0165590410_ul17277134745017"></a><a name="zh-cn_topic_0165590410_ul17277134745017"></a><ul id="zh-cn_topic_0165590410_ul17277134745017"><li>首次全量备份，后续增量备份</li><li>每次都全量备份</li><li>每n次进行一次全量备份</li></ul>
    <div class="note" id="zh-cn_topic_0165590410_note181551254522"><a name="zh-cn_topic_0165590410_note181551254522"></a><a name="zh-cn_topic_0165590410_note181551254522"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0165590410_ul61731492817"></a><a name="zh-cn_topic_0165590410_ul61731492817"></a><ul id="zh-cn_topic_0165590410_ul61731492817"><li>备份Manager数据和组件元数据时不支持增量备份，仅支持“每次都全量备份”。</li><li>如果“路径类型”要使用NFS或CIFS，不能使用增量备份功能。因为在NFS或CIFS备份时使用增量备份时，每次增量备份都会刷新最近一次全量备份的备份数据，所以不会产生新的恢复点。</li></ul>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

6.  在“备份配置”，勾选“Kafka”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若安装了多个Kafka服务，默认备份所有Kafka服务，可单击“指定服务”指定需要备份的Kafka服务。

7.  在“Kafka”的“路径类型”，选择一个备份目录的类型。

    备份目录支持以下类型：

    -   “LocalDir”：表示将备份文件保存在主管理节点的本地磁盘上，备管理节点将自动同步备份文件。默认保存目录为“_数据存放路径_/LocalBackup/”。

        选择此参数值，还需要配置“最大备份数”，表示备份目录中可保留的备份文件集数量。

    -   “LocalHDFS”：表示将备份文件保存在当前集群的HDFS目录。

        选择此参数值，还需要配置以下参数：

        -   “目的端路径”：填写备份文件在HDFS中保存的目录。不支持填写HDFS中的隐藏目录，例如快照或回收站目录；也不支持默认的系统目录，例如“/hbase”或“/user/hbase/backup”。
        -   “最大备份数”：填写备份目录中可保留的备份文件集数量。
        -   “目标NameService名称”：选择备份目录对应的NameService名称。默认值为“hacluster”。

    -   “RemoteHDFS”：表示将备份文件保存在备集群的HDFS目录。

        选择此参数值，还需要配置以下参数：

        -   “目的端NameService名称”：填写备集群的NameService名称。可以输入集群内置的远端集群的NameService名称（haclusterX，haclusterX1，haclusterX2，haclusterX3，haclusterX4），也可输入其他已配置的远端集群NameService名称。

        -   “IP 模式”：目标IP的IP地址模式。系统会根据集群网络类型自动选择对应的IP模式，如IPv4或者IPv6。
        -   “目的端NameNode IP地址”：填写备集群NameNode业务平面IP地址，支持主节点或备节点。
        -   “目的端路径”：填写备集群保存备份数据的HDFS目录。不支持填写HDFS中的隐藏目录，例如快照或回收站目录；也不支持默认的系统目录，例如“/hbase”或“/user/hbase/backup”。
        -   “最大备份数”：填写备份目录中可保留的备份文件集数量。
        -   “队列名称”：填写备份任务执行时使用的YARN队列的名称。需和集群中已存在且状态正常的队列名称相同。

    -   “NFS”：表示将备份文件通过NFS协议保存在NAS中。

        选择此参数值，还需要配置以下参数：

        -   “IP 模式”：目标IP的IP地址模式。系统会根据集群网络类型自动选择对应的IP模式，如IPv4或者IPv6。

        -   “服务器IP地址”：填写NAS服务器IP地址。
        -   “服务器共享路径”：填写用户配置的NAS服务器共享目录。
        -   “最大备份数”：填写备份目录中可保留的备份文件集数量。

    -   “CIFS”：表示将备份文件通过CIFS协议保存在NAS中。

        选择此参数值，还需要配置以下参数：

        -   “IP 模式”：目标IP的IP地址模式。系统会根据集群网络类型自动选择对应的IP模式，如IPv4或者IPv6。

        -   “服务器IP地址”：填写NAS服务器IP地址。
        -   “端口号”：填写CIFS协议连接NAS服务器使用的端口号，默认值为“445”。
        -   “用户名”：填写配置CIFS协议时设置的用户名。
        -   “密码”：填写配置CIFS协议时设置的密码。
        -   “服务器共享路径”：填写用户配置的NAS服务器共享目录。
        -   “最大备份数”：填写备份目录中可保留的备份文件集数量。

    -   “OBS”：表示将备份文件保存在OBS中。

        选择此参数值，还需要配置以下参数：

        -   “目的端路径”：填写保存备份数据的OBS目录。
        -   “最大备份数”：填写备份目录中可保留的备份文件集数量。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >MRS 3.1.0及之后版本才支持备份数据到OBS。


8.  单击“确定”保存。
9.  在备份任务列表中已创建任务的“操作”列，选择“更多 \> 即时备份”，开始执行备份任务。

    备份任务执行完成后，系统自动在备份目录中为每个备份任务创建子目录，目录名为_“备份任务名\_任务创建时间”_，用于保存数据源的备份文件。备份文件的名称为_版本号\_数据源\_任务执行时间.tar.gz_。


