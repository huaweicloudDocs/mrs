# ALM-16004 Hive服务不可用<a name="ZH-CN_TOPIC_0093195061"></a>

## 告警解释<a name="zh-cn_topic_0035998735_section28799665"></a>

系统每30秒周期性检测Hive服务状态。当Hive服务不可用时产生该告警。

当Hive服务恢复时，告警恢复。

## 告警属性<a name="zh-cn_topic_0035998735_section57870399"></a>

<a name="zh-cn_topic_0035998735_table22774600"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998735_row4640007"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998735_p40296320"><a name="zh-cn_topic_0035998735_p40296320"></a><a name="zh-cn_topic_0035998735_p40296320"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998735_p42776493"><a name="zh-cn_topic_0035998735_p42776493"></a><a name="zh-cn_topic_0035998735_p42776493"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998735_p42343927"><a name="zh-cn_topic_0035998735_p42343927"></a><a name="zh-cn_topic_0035998735_p42343927"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998735_row7306053"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998735_p54919424"><a name="zh-cn_topic_0035998735_p54919424"></a><a name="zh-cn_topic_0035998735_p54919424"></a>16004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998735_p19288335"><a name="zh-cn_topic_0035998735_p19288335"></a><a name="zh-cn_topic_0035998735_p19288335"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998735_p18851291"><a name="zh-cn_topic_0035998735_p18851291"></a><a name="zh-cn_topic_0035998735_p18851291"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998735_section51071544"></a>

<a name="zh-cn_topic_0035998735_table50559563"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998735_row19612160"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998735_p45081147"><a name="zh-cn_topic_0035998735_p45081147"></a><a name="zh-cn_topic_0035998735_p45081147"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998735_p27694303"><a name="zh-cn_topic_0035998735_p27694303"></a><a name="zh-cn_topic_0035998735_p27694303"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998735_row28646034"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998735_p38627455"><a name="zh-cn_topic_0035998735_p38627455"></a><a name="zh-cn_topic_0035998735_p38627455"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998735_p41816140"><a name="zh-cn_topic_0035998735_p41816140"></a><a name="zh-cn_topic_0035998735_p41816140"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998735_row40800942"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998735_p16541999"><a name="zh-cn_topic_0035998735_p16541999"></a><a name="zh-cn_topic_0035998735_p16541999"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998735_p64833508"><a name="zh-cn_topic_0035998735_p64833508"></a><a name="zh-cn_topic_0035998735_p64833508"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998735_row46630661"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998735_p18987236"><a name="zh-cn_topic_0035998735_p18987236"></a><a name="zh-cn_topic_0035998735_p18987236"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998735_p61571180"><a name="zh-cn_topic_0035998735_p61571180"></a><a name="zh-cn_topic_0035998735_p61571180"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998735_section56990719"></a>

系统无法提供数据加载，查询，提取服务。

## 可能原因<a name="zh-cn_topic_0035998735_section43154428"></a>

-   Hive服务不可用可能与ZooKeeper、HDFS、Yarn和DBService等基础服务有关，也可能由Hive自身的进程故障引起。
    -   ZooKeeper服务异常。
    -   HDFS服务异常。
    -   Yarn服务异常。
    -   DBService服务异常。
    -   Hive服务进程故障，如果告警由Hive进程故障引发，告警上报时间可能会延迟5分钟左右。

-   Hive服务和基础服务间的网络通信中断。

## 处理步骤<a name="zh-cn_topic_0035998735_section52845536"></a>

1.  检查HiveServer/MetaStore进程状态。
    1.  在MRS Manager界面，单击“服务管理 \> Hive \> 实例”，在Hive实例列表中，查看所有HiveSserver/MetaStore实例状态是否都呈现未知状态。
        -   是，执行[1.b](#zh-cn_topic_0035998735_li15736882153452)。
        -   否，执行[2](#zh-cn_topic_0035998735_li63276134153458)。

    2.  <a name="zh-cn_topic_0035998735_li15736882153452"></a>在Hive实例列表上方，单击“更多 \> 重启实例”，重启HiveServer/MetaStore进程。
    3.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0035998735_li63276134153458)。


2.  <a name="zh-cn_topic_0035998735_li63276134153458"></a>检查ZooKeeper服务状态。
    1.  在MRS Manager的告警列表中，查看是否有ALM-12007 进程故障产生。
        -   是，执行[2.b](#zh-cn_topic_0035998735_li17867059153452)。
        -   否，执行[3](#zh-cn_topic_0035998735_li315441715352)。

    2.  <a name="zh-cn_topic_0035998735_li17867059153452"></a>在ALM-12007 进程故障的“告警详情”区域，查看“ServiceName”是否为“ZooKeeper”。
        -   是，执行[2.c](#zh-cn_topic_0035998735_li26585804153452)。
        -   否，执行[3](#zh-cn_topic_0035998735_li315441715352)。

    3.  <a name="zh-cn_topic_0035998735_li26585804153452"></a>参考ALM-12007 进程故障的处理步骤处理该故障。
    4.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0035998735_li315441715352)。


3.  <a name="zh-cn_topic_0035998735_li315441715352"></a>检查HDFS服务状态。
    1.  在MRS Manager的告警列表中，查看是否有ALM-14000 HDFS服务不可用产生。
        -   是，执行[3.b](#zh-cn_topic_0035998735_li2196200153452)。
        -   否，执行[4](#zh-cn_topic_0035998735_li3789476315357)。

    2.  <a name="zh-cn_topic_0035998735_li2196200153452"></a>参考ALM-14000 HDFS服务不可用的处理步骤处理该故障。
    3.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0035998735_li3789476315357)。


4.  <a name="zh-cn_topic_0035998735_li3789476315357"></a>检查Yarn服务状态。
    1.  在MRS Manager的告警列表中，查看是否有ALM-18000 Yarn服务不可用产生。
        -   是，执行[4.b](#zh-cn_topic_0035998735_li64260695153452)。
        -   否，执行[4](#zh-cn_topic_0035998735_li3789476315357)。

    2.  <a name="zh-cn_topic_0035998735_li64260695153452"></a>参考ALM-18000 Yarn服务不可用的处理步骤处理该故障。
    3.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0035998735_li3789476315357)。


5.  检查DBService服务状态。
    1.  在MRS Manager的告警列表中，查看是否有“ALM-27001 DBService服务不可用”产生。
        -   是，执行[5.b](#zh-cn_topic_0035998735_li19704975153452)。
        -   否，执行[6](#zh-cn_topic_0035998735_li23165657153517)。

    2.  <a name="zh-cn_topic_0035998735_li19704975153452"></a>参考[ALM-27001 DBService服务不可用](ALM-27001-DBService服务不可用.md#ZH-CN_TOPIC_0093195071)的处理步骤处理该故障。
    3.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[6](#zh-cn_topic_0035998735_li23165657153517)。


6.  <a name="zh-cn_topic_0035998735_li23165657153517"></a>检查Hive与ZooKeeper、HDFS、Yarn和DBService之间的网络连接。
    1.  在MRS Manager界面，单击“服务管理 \> Hive”。
    2.  单击“实例”。

        显示HiveServer实例列表。

    3.  单击“HiveServer”行的“主机名”。

        弹出HiveServer主机状态页面。

    4.  <a name="zh-cn_topic_0035998735_li39788839153452"></a>记录“概要信息”下的IP地址。
    5.  通过[6.d](#zh-cn_topic_0035998735_li39788839153452)获取的IP地址登录HiveServer所在的主机。
    6.  执行**ping**命令，查看HiveServer所在主机与ZooKeeper、HDFS、Yarn和DBService服务所在主机的网络连接是否正常。（获取ZooKeeper、HDFS、Yarn和DBService服务所在主机的IP地址的方式和获取HiveServer IP地址的方式相同。）
        -   是，执行[7](#zh-cn_topic_0035998735_li27995708153452)。
        -   否，执行[6.g](#zh-cn_topic_0035998735_li44761520153452)。

    7.  <a name="zh-cn_topic_0035998735_li44761520153452"></a>联系公有云运维人员恢复网络。
    8.  在告警列表中，查看“ALM-16004 Hive服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[7](#zh-cn_topic_0035998735_li27995708153452)。


7.  <a name="zh-cn_topic_0035998735_li27995708153452"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035998735_section5847780"></a>

无。

