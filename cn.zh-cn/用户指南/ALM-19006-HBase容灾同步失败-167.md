# ALM-19006 HBase容灾同步失败<a name="ALM-19006"></a>

## 告警解释<a name="section16194462"></a>

告警模块每30s检查一次HBase容灾数据的同步状态，当同步容灾数据到备集群失败时，发送该告警。

当容灾数据同步成功后，告警清除。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如HBase1服务不可用，则“定位信息”中显示服务名=HBase1，处理步骤中的操作对象也应由HBase调整为HBase1。

## 告警属性<a name="section11532435"></a>

<a name="table42311111"></a>
<table><thead align="left"><tr id="row28099143"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p61438120"><a name="p61438120"></a><a name="p61438120"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p10431825"><a name="p10431825"></a><a name="p10431825"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p39671531"><a name="p39671531"></a><a name="p39671531"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row59277470"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p36745745"><a name="p36745745"></a><a name="p36745745"></a>19006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p23615340"><a name="p23615340"></a><a name="p23615340"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p33794392"><a name="p33794392"></a><a name="p33794392"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section36683058"></a>

<a name="table52991228"></a>
<table><thead align="left"><tr id="row61180168"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p56646581"><a name="p56646581"></a><a name="p56646581"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p24970367"><a name="p24970367"></a><a name="p24970367"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row146159619182"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row9333837"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36024087"><a name="p36024087"></a><a name="p36024087"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row55781330"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36671468"><a name="p36671468"></a><a name="p36671468"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row61607759"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p11824270"><a name="p11824270"></a><a name="p11824270"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row117210213234"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p26086497"><a name="p26086497"></a><a name="p26086497"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32631511"><a name="p32631511"></a><a name="p32631511"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section61712066"></a>

无法同步集群中HBase的数据到备集群，导致主备集群数据不一致。

## 可能原因<a name="section18537685"></a>

-   备集群HBase服务异常。
-   网络异常。

## 处理步骤<a name="section32621445"></a>

**观察告警是否自动修复。**

1.  在主集群的FusionInsight Manager界面，选择“运维  \>   告警  \>   告警“。
2.  在告警列表中单击该告警，从完整的告警信息中的“产生时间”处获得告警的产生时间，查看告警是否持续超过5分钟。
    -   是，执行[4](#li5409984192042)。
    -   否，执行[3](#li601109392042)。

3.  <a name="li601109392042"></a>等待5分钟后检查本告警是否自动恢复。
    -   是，处理完毕。
    -   否，执行[4](#li5409984192042)。


**检查备集群HBase服务状态。**

1.  <a name="li5409984192042"></a>登录主集群FusionInsight Manager界面，选择“运维  \>   告警  \>   告警“。
2.  在告警列表中单击该告警，从完整的告警信息中的“定位信息”处获得“主机名”。
3.  以**omm**用户进入主集群HBase客户端所在节点。

    如果集群采用了安全版本，要进行安全认证，然后使用**hbase**用户进入**hbase shell**界面。

    **cd /opt/Bigdata/client**

    **source ./bigdata\_env**

    **kinit **_hbaseuser_

4.  执行**status 'replication', 'source'**命令查看故障节点的容灾同步状态。

    节点的容灾同步状态如下：

    ```
    10-10-10-153: 
    SOURCE: PeerID=abc, SizeOfLogQueue=0, ShippedBatches=2, ShippedOps=2, ShippedBytes=320, LogReadInBytes=1636, LogEditsRead=5, LogEditsFiltered=3, SizeOfLogToReplicate=0, TimeForLogToReplicate=0, ShippedHFiles=0, SizeOfHFileRefsQueue=0, AgeOfLastShippedOp=0, TimeStampsOfLastShippedOp=Mon Jul 18 09:53:28 CST 2016, Replication Lag=0, FailedReplicationAttempts=0 
    SOURCE: PeerID=abc1, SizeOfLogQueue=0, ShippedBatches=1, ShippedOps=1, ShippedBytes=160, LogReadInBytes=1636, LogEditsRead=5, LogEditsFiltered=3, SizeOfLogToReplicate=0, TimeForLogToReplicate=0, ShippedHFiles=0, SizeOfHFileRefsQueue=0, AgeOfLastShippedOp=16788, TimeStampsOfLastShippedOp=Sat Jul 16 13:19:00 CST 2016, Replication Lag=16788, FailedReplicationAttempts=5
    ```

5.  找到“FailedReplicationAttempts”的值大于0的记录所对应的“PeerID”值。

    如上步骤中，故障节点“10-10-10-153”同步数据到“PeerID”为“abc1”的备集群失败。

6.  <a name="li4898434092042"></a>继续执行**list\_peers**命令，查找该“PeerID”对应的集群和HBase实例。

    ```
    PEER_ID CLUSTER_KEY STATE TABLE_CFS 
    abc1 10.10.10.110,10.10.10.119,10.10.10.133:2181:/hbase2 ENABLED  
    abc 10.10.10.110,10.10.10.119,10.10.10.133:2181:/hbase ENABLED 
    ```

    如上所示，**/hbase2**表示数据是同步到备集群的HBase2实例。

7.  在备集群FusionInsight Manager的服务列表中，查看通过[9](#li4898434092042)获取的HBase实例运行状态是否为“良好”。
    -   是，执行[14](#li2515814492042)。
    -   否，执行[11](#li1244067892042)。

8.  <a name="li1244067892042"></a>在告警列表中，查看是否有“ALM-19000 HBase服务不可用”告警产生。
    -   是，执行[12](#li106198292042)。
    -   否，执行[14](#li2515814492042)。

9.  <a name="li106198292042"></a>参考“ALM-19000 HBase服务不可用”的处理步骤处理该故障。
10. 等待几分钟后检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[14](#li2515814492042)。


**检查主备集群RegionServer之间的网络连接。**

1.  <a name="li2515814492042"></a>登录主集群FusionInsight Manager界面，选择“运维  \>   告警  \>   告警“。
2.  <a name="li2509670692042"></a>在告警列表中单击该告警，从完整的告警信息中“定位信息”处获得“主机名”。
3.  以**omm**用户通过[15](#li2509670692042)获取的IP地址登录故障RegionServer节点。
4.  执行**ping**命令，查看故障RegionServer节点和备集群RegionServer所在主机的网络连接是否正常。
    -   是，执行[20](#li6380778692042)。
    -   否，执行[18](#li2304669092042)。

5.  <a name="li2304669092042"></a>联系网络管理员恢复网络。
6.  网络恢复后，在告警列表中，查看本告警是否清除。
    -   是，处理完毕。
    -   否，执行[20](#li6380778692042)。


**收集故障信息。**

1.  <a name="li6380778692042"></a>在主备集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HBase”。
3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section25157554"></a>

无。

