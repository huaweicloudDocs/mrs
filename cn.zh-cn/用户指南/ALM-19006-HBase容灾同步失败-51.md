# ALM-19006 HBase容灾同步失败<a name="ZH-CN_TOPIC_0174499368"></a>

## 告警解释<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section18389930"></a>

当同步容灾数据到备集群失败时，发送该告警。

当容灾数据同步成功后，告警清除。

## 告警属性<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section31291646"></a>

<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_table57434139"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row461342"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p37368736"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p37368736"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p37368736"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p6968762"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p6968762"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p6968762"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p27598869"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p27598869"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p27598869"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row20915929"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p16468652"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p16468652"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p16468652"></a>19006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p58892473"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p58892473"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p58892473"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p5560998"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p5560998"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p5560998"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section13189358"></a>

<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_table47787675"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row20947391"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p19017142"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p19017142"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p19017142"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p63993496"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p63993496"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p63993496"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row16090703"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p28278595"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p28278595"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p28278595"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p8864859"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p8864859"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p8864859"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row12674872"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p20031746"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p20031746"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p20031746"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p11958757"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p11958757"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p11958757"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_row40519951"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p60890569"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p60890569"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p60890569"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p33189039"><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p33189039"></a><a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_p33189039"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section51595365"></a>

无法同步集群中HBase的数据到备集群，导致主备集群数据不一致。

## 可能原因<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section61705107"></a>

-   备集群HBase服务异常。
-   网络异常。

## 处理步骤<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section18475057"></a>

1.  观察告警是否自动修复。
    1.  登录主集群的MRS Manager界面，单击“告警管理”。
    2.  在告警列表中单击该告警，从“告警详情”的“产生时间”处获得告警的产生时间，查看告警是否持续超过5分钟。
        -   是，执行[2.a](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_status)。
        -   否，执行[1.c](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_step3)。

    3.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_step3"></a>等待5分钟后检查本告警是否自动恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_status)。

2.  检查备集群HBase服务状态。
    1.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_status"></a>登录主集群MRS Manager界面，单击“告警管理”。
    2.  在告警列表中单击该告警，从“告警详情”的“定位信息”处获得“HostName”。
    3.  登录主集群HBase客户端所在节点。执行以下命令切换用户：

        **sudo su - root**

        **su - omm**

    4.  执行**status 'replication', 'source'**命令查看故障节点的容灾同步状态。

        节点的容灾同步状态如下：

        ```
        10-10-10-153: 
         SOURCE: PeerID=abc, SizeOfLogQueue=0, ShippedBatches=2, ShippedOps=2, ShippedBytes=320, LogReadInBytes=1636, LogEditsRead=5, LogEditsFiltered=3, SizeOfLogToReplicate=0, TimeForLogToReplicate=0, ShippedHFiles=0, SizeOfHFileRefsQueue=0, AgeOfLastShippedOp=0, TimeStampsOfLastShippedOp=Mon Jul 18 09:53:28 CST 2016, Replication Lag=0, FailedReplicationAttempts=0 
         SOURCE: PeerID=abc1, SizeOfLogQueue=0, ShippedBatches=1, ShippedOps=1, ShippedBytes=160, LogReadInBytes=1636, LogEditsRead=5, LogEditsFiltered=3, SizeOfLogToReplicate=0, TimeForLogToReplicate=0, ShippedHFiles=0, SizeOfHFileRefsQueue=0, AgeOfLastShippedOp=16788, TimeStampsOfLastShippedOp=Sat Jul 16 13:19:00 CST 2016, Replication Lag=16788, FailedReplicationAttempts=5
        ```

    5.  找到“FailedReplicationAttempts”的值大于0的记录所对应的“PeerID”值。

        如上步骤中，故障节点“10-10-10-153”同步数据到“PeerID”为“abc1”的备集群失败。

    6.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_peerid"></a>继续执行**list\_peers**命令，查找该“PeerID”对应的集群和HBase实例。

        ```
        PEER_ID CLUSTER_KEY STATE TABLE_CFS 
         abc1 10.10.10.110,10.10.10.119,10.10.10.133:24002:/hbase2 ENABLED  
         abc 10.10.10.110,10.10.10.119,10.10.10.133:24002:/hbase ENABLED 
        ```

        如上所示，**/hbase2**表示数据是同步到备集群的HBase2实例。

    7.  在备集群MRS Manager的服务列表中，查看通过[2.f](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_peerid)获取的HBase实例健康状态是否为“良好”。
        -   是，执行[3.a](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_net)。
        -   否，执行[2.h](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_alm-19000)。

    8.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_alm-19000"></a>在告警列表中，查看是否有“ALM-19000 HBase服务不可用”告警产生。
        -   是，执行[2.i](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_process)。
        -   否，执行[3.a](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_net)。

    9.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_process"></a>参考ALM-19000 HBase服务不可用的处理步骤处理该故障。
    10. 等待几分钟后检查本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3.a](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_net)。

3.  检查主备集群RegionServer之间的网络连接。
    1.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_aalm-19006_mmccppss_net"></a>登录主集群MRS Manager界面，单击“告警管理”。
    2.  在告警列表中单击该告警，从“告警详情”的“定位信息”处获得“HostName”。
    3.  登录故障RegionServer节点。
    4.  执行**ping**命令，查看故障RegionServer节点和备集群RegionServer所在主机的网络连接是否正常。
        -   是，执行[4](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_li979634915155)。
        -   否，执行[3.e](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_s1)。

    5.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_s1"></a>联系运维人员恢复网络。
    6.  网络恢复后，在告警列表中，查看本告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0093195067_zh-cn_topic_0035998741_li979634915155)。

4.  <a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_li979634915155"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195067_zh-cn_topic_0035998741_section32057793"></a>

无。

