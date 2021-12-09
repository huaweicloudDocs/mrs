# ALM-26051 Storm服务不可用<a name="ALM-26051"></a>

## 告警解释<a name="section37185649"></a>

系统按照30秒的周期检测Storm服务是否可用，当集群全部的Nimbus节点异常时，Storm服务不可用，系统产生此告警。

当Storm服务恢复正常，告警自动清除。

## 告警属性<a name="section66235391"></a>

<a name="table21607765"></a>
<table><thead align="left"><tr id="row53468795"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p36005118"><a name="p36005118"></a><a name="p36005118"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p30733417"><a name="p30733417"></a><a name="p30733417"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p6378853"><a name="p6378853"></a><a name="p6378853"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row46925081"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p42835246"><a name="p42835246"></a><a name="p42835246"></a>26051</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p47102924"><a name="p47102924"></a><a name="p47102924"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p57240474"><a name="p57240474"></a><a name="p57240474"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section59247607"></a>

<a name="table5966784"></a>
<table><thead align="left"><tr id="row11121133"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p28396556"><a name="p28396556"></a><a name="p28396556"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p18419688"><a name="p18419688"></a><a name="p18419688"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row2217734151412"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row15599720"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p8746357"><a name="p8746357"></a><a name="p8746357"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row11608357"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p60983332"><a name="p60983332"></a><a name="p60983332"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row11979076"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10240775"><a name="p10240775"></a><a name="p10240775"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63466420"></a>

集群无法对外提供Storm服务，用户无法执行新的Storm任务。

## 可能原因<a name="section34326869"></a>

-   Kerberos集群故障。
-   ZooKeeper集群故障或假死。
-   Storm集群中主备Nimbus状态异常。

## 处理步骤<a name="section40506373"></a>

**检查Kerberos集群状态（普通模式集群跳过此步骤）**

1.  在FusionInsight Manager管理界面，选择“集群 \>  _待操作集群的名称_  \> 服务”。
2.  查看Kerberos服务的运行状态是否为“良好”。
    -   是，执行[5](#li42874189394)。
    -   否，执行[3](#li11288151863919)。

3.  <a name="li11288151863919"></a>参考“ALM-25500 KrbServer服务不可用”的相关维护信息进行操作。
4.  查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[5](#li42874189394)。


**检查ZooKeeper集群状态**

1.  <a name="li42874189394"></a>查看ZooKeeper服务的运行状态是否为“良好”。
    -   是，执行[8](#li34206127201223)。
    -   否，执行[6](#li20287191816396)。

2.  <a name="li20287191816396"></a>如果Zookeeper服务停止运行，则启动服务，否则参考“ALM-13000 ZooKeeper服务不可用”的相关维护信息进行操作。
3.  查看告警是否清除。
    -   是，处理完毕。
    -   否，执行[8](#li34206127201223)。


**检查主备Nimbus状态**

1.  <a name="li34206127201223"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> Nimbus”，进入Nimbus实例页面。
2.  查看“角色”中是否存在且仅存在一个状态为主的Nimbus节点。
    -   是，执行[13](#li51454142201223)。
    -   否，执行[10](#li51789495201223)。

3.  <a name="li51789495201223"></a>勾选两个Nimbus角色实例，选择“更多 \> 重启实例”，查看是否重启成功。
    -   是，执行[11](#li38539002201223)。
    -   否，执行[13](#li51454142201223)。

4.  <a name="li38539002201223"></a>重新登录FusionInsight Manager管理界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> Nimbus”，查看运行状态是否为“良好”。
    -   是，执行[12](#li50456369201223)。
    -   否，执行[13](#li51454142201223)。

5.  <a name="li50456369201223"></a>等待30秒，查看告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li51454142201223)。


**收集故障信息**

1.  <a name="li51454142201223"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   KrbServer

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >普通模式不需要下载KrbServer日志。

    -   ZooKeeper
    -   Storm

3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section29013044"></a>

无。

