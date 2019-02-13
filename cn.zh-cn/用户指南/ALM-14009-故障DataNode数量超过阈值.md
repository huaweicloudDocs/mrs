# ALM-14009 故障DataNode数量超过阈值<a name="ZH-CN_TOPIC_0093195054"></a>

## 告警解释<a name="zh-cn_topic_0035998728_section4477025"></a>

系统每30秒周期性检测HDFS集群处于故障状态的DataNode数量，并把实际的故障状态的DataNode数量和阈值相比较。故障状态的DataNode数量指标默认提供一个阈值范围。当HDFS集群故障状态的DataNode数量超出阈值范围时，产生该告警。

故障状态的DataNode数量小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0035998728_section40293226"></a>

<a name="zh-cn_topic_0035998728_table18759701"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998728_row48616240"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998728_p45601378"><a name="zh-cn_topic_0035998728_p45601378"></a><a name="zh-cn_topic_0035998728_p45601378"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998728_p2724161"><a name="zh-cn_topic_0035998728_p2724161"></a><a name="zh-cn_topic_0035998728_p2724161"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998728_p19330484"><a name="zh-cn_topic_0035998728_p19330484"></a><a name="zh-cn_topic_0035998728_p19330484"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998728_row22265380"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998728_p58665336"><a name="zh-cn_topic_0035998728_p58665336"></a><a name="zh-cn_topic_0035998728_p58665336"></a>14009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998728_p54271769"><a name="zh-cn_topic_0035998728_p54271769"></a><a name="zh-cn_topic_0035998728_p54271769"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998728_p33937134"><a name="zh-cn_topic_0035998728_p33937134"></a><a name="zh-cn_topic_0035998728_p33937134"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998728_section27094719"></a>

<a name="zh-cn_topic_0035998728_table64553311"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998728_row25037822"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998728_p14797678"><a name="zh-cn_topic_0035998728_p14797678"></a><a name="zh-cn_topic_0035998728_p14797678"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998728_p57761279"><a name="zh-cn_topic_0035998728_p57761279"></a><a name="zh-cn_topic_0035998728_p57761279"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998728_row48152024"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998728_p7999906"><a name="zh-cn_topic_0035998728_p7999906"></a><a name="zh-cn_topic_0035998728_p7999906"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998728_p44012677"><a name="zh-cn_topic_0035998728_p44012677"></a><a name="zh-cn_topic_0035998728_p44012677"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998728_row60569775"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998728_p7204713"><a name="zh-cn_topic_0035998728_p7204713"></a><a name="zh-cn_topic_0035998728_p7204713"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998728_p46710863"><a name="zh-cn_topic_0035998728_p46710863"></a><a name="zh-cn_topic_0035998728_p46710863"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998728_row17744591"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998728_p28025763"><a name="zh-cn_topic_0035998728_p28025763"></a><a name="zh-cn_topic_0035998728_p28025763"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998728_p55494360"><a name="zh-cn_topic_0035998728_p55494360"></a><a name="zh-cn_topic_0035998728_p55494360"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998728_row29687198"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998728_p55852871"><a name="zh-cn_topic_0035998728_p55852871"></a><a name="zh-cn_topic_0035998728_p55852871"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998728_p27788708"><a name="zh-cn_topic_0035998728_p27788708"></a><a name="zh-cn_topic_0035998728_p27788708"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998728_section42525879"></a>

故障状态的DataNode节点无法提供HDFS服务。

## 可能原因<a name="zh-cn_topic_0035998728_section47188597"></a>

-   DataNode故障或者负荷过高。
-   NameNode和DataNode之间的网络断连或者繁忙。
-   NameNode负荷过高。

## 处理步骤<a name="zh-cn_topic_0035998728_section22044193"></a>

1.  查看DataNode是否故障。
    1.  在集群节点使用客户端，执行**hdfs dfsadmin -report**命令，可以查看Dead datanodes项对应的数量显示以及处于故障状态的的DataNode信息。
        -   是，执行[1.b](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step4)。
        -   否，执行[2.a](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step6)。

    2.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step4"></a>在MRS Manager界面单击“服务管理 \> HDFS \> 实例”，检查对应DataNode是否处于停止状态。
        -   是，执行[1.c](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step5)。
        -   否，执行[2.a](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step6)。

    3.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step5"></a>勾选对应的DataNode实例，单击“更多 \> 重启实例”进行重启，等待5分钟后，然后查看本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step6)。


2.  查看NameNode和DataNode之间的网络情况。
    1.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step6"></a>登录处于故障状态DataNode的业务平面IP节点，执行**ping** _NameNode__的IP__地址_命令以检查DataNode和NameNode之间的网络是否异常。
        -   是，执行[2.b](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step7)。
        -   否，执行[3.a](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step8)。

    2.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step7"></a>修复网络故障，等待5分钟后，查看该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3.a](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step8)。


3.  查看DataNode是否负荷过高。
    1.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step8"></a>在MRS Manager界面单击“告警管理”，查看否存在“ALM-14008 HDFS DataNode内存使用率超过阈值”的告警。
        -   是，执行[3.b](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step13)。
        -   否，执行[4.a](#zh-cn_topic_0035998728_step9)。

    2.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step13"></a>参考[ALM-14008 HDFS DataNode内存使用率超过阈值](ALM-14008-HDFS-DataNode内存使用率超过阈值.md#ZH-CN_TOPIC_0093195053)的处理步骤，对该异常告警进行处理，查看是否消除该告警。
        -   是，执行[3.c](#zh-cn_topic_0035998728_ss10)。
        -   否，执行[4.a](#zh-cn_topic_0035998728_step9)。

    3.  <a name="zh-cn_topic_0035998728_ss10"></a>等待5分钟后，在告警列表中查看本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0035998728_step9)。


4.  查看NameNode是否负荷过高。
    1.  <a name="zh-cn_topic_0035998728_step9"></a>在MRS Manager界面单击“告警管理”，查看是否存在“ALM-14007 HDFS NameNode内存使用率超过阈值”的告警。
        -   是，执行[4.b](#zh-cn_topic_0035998728_alm14007_3_mmccppss_step14)。
        -   否，执行[5](#zh-cn_topic_0035998728_li183032841605)。

    2.  <a name="zh-cn_topic_0035998728_alm14007_3_mmccppss_step14"></a>参考[ALM-14007 HDFS NameNode内存使用率超过阈值](ALM-14007-HDFS-NameNode内存使用率超过阈值.md#ZH-CN_TOPIC_0093195052)的处理步骤，对该异常告警进行处理，查看是否消除告警。
        -   是，执行[4.c](#zh-cn_topic_0035998728_ss13)。
        -   否，执行[5](#zh-cn_topic_0035998728_li183032841605)。

    3.  <a name="zh-cn_topic_0035998728_ss13"></a>等待5分钟后，在告警列表中查看本告警是否恢复。
        -   是，处理完毕。
        -   否，执行[5](#zh-cn_topic_0035998728_li183032841605)。


5.  <a name="zh-cn_topic_0035998728_li183032841605"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035998728_section64180012"></a>

无。

