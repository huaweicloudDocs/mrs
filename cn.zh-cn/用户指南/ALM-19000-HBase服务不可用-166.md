# ALM-19000 HBase服务不可用<a name="ALM-19000"></a>

## 告警解释<a name="section7720100"></a>

告警模块按120秒周期检测HBase服务状态。当HBase服务不可用时产生该告警。

HBase服务恢复时，告警清除。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如HBase1服务不可用，则“定位信息”中显示服务名=HBase1，处理步骤中的操作对象也应由HBase调整为HBase1。

## 告警属性<a name="section2372042"></a>

<a name="table10134191"></a>
<table><thead align="left"><tr id="row37452510"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p13754465"><a name="p13754465"></a><a name="p13754465"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p40369889"><a name="p40369889"></a><a name="p40369889"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p48735557"><a name="p48735557"></a><a name="p48735557"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55266038"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p47364059"><a name="p47364059"></a><a name="p47364059"></a>19000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p11283548"><a name="p11283548"></a><a name="p11283548"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p41552227"><a name="p41552227"></a><a name="p41552227"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section21348382"></a>

<a name="table10287189"></a>
<table><thead align="left"><tr id="row45935908"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p29821069"><a name="p29821069"></a><a name="p29821069"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p66696423"><a name="p66696423"></a><a name="p66696423"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row18190122316182"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row33701210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p57042344"><a name="p57042344"></a><a name="p57042344"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row43619052"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32410239"><a name="p32410239"></a><a name="p32410239"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row23256701"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p48772425"><a name="p48772425"></a><a name="p48772425"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section57917713"></a>

无法进行数据读写和创建表等操作。

## 可能原因<a name="section51497372"></a>

-   ZooKeeper服务异常。
-   HDFS服务异常。
-   HBase服务异常。
-   网络异常。

## 处理步骤<a name="section60823168"></a>

**检查ZooKeeper服务状态。**

1.  在FusionInsight Manager的服务列表中，查看ZooKeeper运行状态是否为“良好”。
    -   是，执行[5](#li620900869259)。
    -   否，执行[2](#li257033669259)。

2.  <a name="li257033669259"></a>在告警列表中，查看是否有“ALM-13000 ZooKeeper服务不可用”告警产生。
    -   是，执行[3](#li15979369259)。
    -   否，执行[5](#li620900869259)。

3.  <a name="li15979369259"></a>参考“ALM-13000 ZooKeeper服务不可用”的处理步骤处理该故障。
4.  等待几分钟后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li620900869259)。


**检查HDFS服务状态。**

1.  <a name="li620900869259"></a>在告警列表中，查看是否有“ALM-14000 HDFS服务不可用”告警产生。
    -   是，执行[6](#li632410929259)。
    -   否，执行[8](#li660818889259)。

2.  <a name="li632410929259"></a>参考“ALM-14000 HDFS服务不可用”的处理步骤处理该故障。
3.  等待几分钟后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[8](#li660818889259)。

4.  <a name="li660818889259"></a>在FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”，查看HDFS“安全模式”是否为“ON”。
    -   是，执行[9](#li193225719259)。
    -   否，执行[12](#li513508519259)。

5.  <a name="li193225719259"></a>以**root**用户登录HDFS客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行**cd**命令进入客户端安装目录，然后执行**source bigdata\_env**。

    如果集群采用安全版本，要进行安全认证。预先向管理员获取hdfs用户的密码，执行**kinit hdfs**命令，按提示输入密码。

6.  执行以下命令手动退出安全模式。

    **hdfs dfsadmin -safemode leave**

7.  等待几分钟后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[12](#li513508519259)。


**检查HBase服务状态。**

1.  <a name="li513508519259"></a>在FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase”。
2.  查看2个HMaster的状态是否为一“主”一“备”。
    -   是，执行[15](#li233523699259)。
    -   否，执行[14](#li547904909259)。

3.  <a name="li547904909259"></a>单击“实例”，选择非主状态的HMaster实例，单击“更多 \> 重启实例”重启HMaster，再次查看2个HMaster的状态是否为一“主”一“备”。
    -   是，执行[15](#li233523699259)。
    -   否，执行[21](#li50721779259)。

4.  <a name="li233523699259"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase \> HMaster\(主\)”，进入HMaster的WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

5.  查看Region Servers下是否存在至少一个RegionServer。
    -   是，执行[17](#li132400939259)。
    -   否，执行[21](#li50721779259)。

6.  <a name="li132400939259"></a>查看“Tables \> System Tables”，如[图1](#fig13618196577)，查看该标签的“Table Name”列下是否存在“hbase:meta”、“hbase:namespace”和“hbase:acl”。
    -   是，执行[18](#li658146339259)。
    -   否，执行[19](#li322889699259)。

        **图 1**  HBase系统表<a name="fig13618196577"></a>  
        ![](figures/HBase系统表.png "HBase系统表")

7.  <a name="li658146339259"></a>如[图1](#fig13618196577)，分别单击“hbase:meta”、“hbase:namespace”和“hbase:acl”超链接，查看所有页面是否能正常打开。如果页面能正常打开，说明表都正常。
    -   是，执行[19](#li322889699259)。
    -   否，执行[23](#li99991989259)。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >由于普通模式下的HBase默认未开启ACL权限控制，只有在手动开启ACL权限控制后才会存在“hbase:acl”表，需要检查该表，否则不需要检查该表。


8.  <a name="li322889699259"></a>查看HMaster的启动状态。

    如[图2](#fig605340209259)在“Tasks” 下有“RUNNING”的状态表示HMaster正在启动，“State”列有HMaster处于“RUNNING”状态的时间。如[图3](#fig134506439259)中的“COMPLETE”状态表示HMaster启动完成。

    查看HMaster是否持续了很长一段时间处于“RUNNING”状态。

    **图 2**  HMaster正在启动的状态<a name="fig605340209259"></a>  
    ![](figures/HMaster正在启动的状态.png "HMaster正在启动的状态")

    **图 3**  HMaster启动完成的状态<a name="fig134506439259"></a>  
    ![](figures/HMaster启动完成的状态.png "HMaster启动完成的状态")

    -   是，执行[20](#li71816449259)。
    -   否，执行[21](#li50721779259)。

9.  <a name="li71816449259"></a>查看HMaster页面是否有hbase:meta长时间处于“Region in Transition”的状态。

    **图 4**  Region处于Region in Transition的状态<a name="fig505565949259"></a>  
    ![](figures/Region处于Region-in-Transition的状态.png "Region处于Region-in-Transition的状态")

    -   是，执行[21](#li50721779259)。
    -   否，执行[22](#li11110229259)。

10. <a name="li50721779259"></a>确认在不影响业务的情况下，登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase \> 更多 \> 重启服务”，输入密码，单击“确定”。
    -   是，执行[22](#li11110229259)。
    -   否，执行[23](#li99991989259)。

11. <a name="li11110229259"></a>等待几分钟后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[23](#li99991989259)。


**检查HMaster和依赖组件之间的网络连接。**

1.  <a name="li99991989259"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HBase”。
2.  <a name="li228839209259"></a>单击“实例”，显示HMaster实例列表，记录“HMaster\(主\)”行的“管理IP”。
3.  以**omm**用户通过[24](#li228839209259)获取的IP地址登录主HMaster节点。
4.  执行**ping**命令，查看主HMaster节点和依赖组件所在主机的网络连接是否正常。（依赖组件包括ZooKeeper、HDFS和Yarn等，获取依赖组件所在主机的IP地址的方式和获取主HMaster的IP地址的方式相同。）
    -   是，执行[29](#li240314599259)。
    -   否，执行[27](#li135441579259)。

5.  <a name="li135441579259"></a>联系网络管理员恢复网络。
6.  在告警列表中，查看“HBase服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[29](#li240314599259)。


**收集故障信息。**

1.  <a name="li240314599259"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   ZooKeeper
    -   HDFS
    -   HBase

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section10537607"></a>

无。

