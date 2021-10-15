# ALM-14012 Journalnode数据不同步<a name="ALM-14012"></a>

## 告警解释<a name="section10941635"></a>

在主NameNode节点上，系统每5分钟检测一次集群中所有JournalNode节点的数据同步性。如果有JournalNode节点的数据不同步，系统产生该告警。

当Journalnode数据同步5分钟后，告警恢复。

## 告警属性<a name="section31365854"></a>

<a name="table36563777"></a>
<table><thead align="left"><tr id="row51923907"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p45086976"><a name="p45086976"></a><a name="p45086976"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p28166429"><a name="p28166429"></a><a name="p28166429"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p66888258"><a name="p66888258"></a><a name="p66888258"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row49239832"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p29003462"><a name="p29003462"></a><a name="p29003462"></a>14012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p470261"><a name="p470261"></a><a name="p470261"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p38091213"><a name="p38091213"></a><a name="p38091213"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section13857234"></a>

<a name="table40375969115124"></a>
<table><thead align="left"><tr id="row51138187115124"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p48552443115124"><a name="p48552443115124"></a><a name="p48552443115124"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p40433783115124"><a name="p40433783115124"></a><a name="p40433783115124"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row242721411319"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row53911016115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46469064115124"><a name="p46469064115124"></a><a name="p46469064115124"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row15568399115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4575151115124"><a name="p4575151115124"></a><a name="p4575151115124"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row41176362115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p44935135115124"><a name="p44935135115124"></a><a name="p44935135115124"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row1763031115124"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p8587829115124"><a name="p8587829115124"></a><a name="p8587829115124"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24525588115124"><a name="p24525588115124"></a><a name="p24525588115124"></a>产生告警的NameService名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section57606249"></a>

当一个JournalNode节点工作状态异常时，其数据就会与其他JournalNode节点的数据不同步。如果超过一半的JournalNode节点的数据不同步时，NameNode将无法工作，导致HDFS服务不可用。

## 可能原因<a name="section48694194"></a>

-   JournalNode实例不存在（被删除或被迁移）。
-   JournalNode实例未启动或已停止。
-   JournalNode实例运行状态异常。
-   JournalNode节点的网络不可达。

## 处理步骤<a name="section35594568"></a>

**查看JournalNode实例是否启动。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，在告警列表中单击此告警。
2.  查看“定位信息”，获取告警产生的JournalNode节点IP地址。
3.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，在实例列表中查看告警节点上是否存在JournalNode实例。
    -   是，执行[5](#li15222114643411)。
    -   否，执行[4](#li184781433124215)。

4.  <a name="li184781433124215"></a>选择“运维 \> 告警 \> 告警”，在告警列表中单击此告警“操作”栏中的“清除”，在弹出窗口中单击“确定”，处理完毕。
5.  <a name="li15222114643411"></a>单击该JournalNode实例，查看其“配置状态”是否为“已同步”。
    -   是，执行[8](#li477165609343)。
    -   否，执行[6](#li565766669343)。

6.  <a name="li565766669343"></a>勾选该JournalNode实例，单击“启动实例”，等待启动完成。
7.  等待5分钟后，查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[15](#li479334659343)。


**查看JournalNode实例运行状态是否正常。**

1.  <a name="li477165609343"></a>查看该JournalNode实例的“运行状态”是否为“良好”。
    -   是，执行[11](#li113484899343)。
    -   否，执行[9](#li267958629343)。

2.  <a name="li267958629343"></a>勾选该JournalNode实例，选择“更多 \> 重启实例”，等待启动完成。
3.  等待5分钟后，查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[15](#li479334659343)。


**查看JournalNode节点网络是否可达。**

1.  <a name="li113484899343"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，查看主NameNode节点的业务IP地址。
2.  以**root**用户登录主NameNode节点，用户密码为安装前用户自定义，请咨询系统管理员。
3.  使用**ping**命令检查主NameNode与该JournalNode之间的网络状况，是否有超时或者网络不可达的情况。

    **ping **_JournalNode__的业务IP__地址_

    -   是，执行[14](#li276955619343)。
    -   否，执行[15](#li479334659343)。

4.  <a name="li276955619343"></a>联系网络管理员处理网络故障，故障恢复后等待5分钟，查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[15](#li479334659343)。


**收集故障信息。**

1.  <a name="li479334659343"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后30分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section51915659"></a>

无。

