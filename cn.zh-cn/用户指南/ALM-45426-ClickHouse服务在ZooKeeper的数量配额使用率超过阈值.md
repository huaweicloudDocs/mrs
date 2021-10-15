# ALM-45426 ClickHouse服务在ZooKeeper的数量配额使用率超过阈值<a name="ALM-45426"></a>

## 告警解释<a name="section8280367"></a>

告警模块按60秒周期检测ClickHouse服务在ZooKeeper的数量配额使用百分比，当检测到使用百分比超过阈值（90%），系统产生此告警。

当系统检测到使用百分比低于阈值，且告警处理完成时，告警恢复。

## 告警属性<a name="section7414445"></a>

<a name="table45079949"></a>
<table><thead align="left"><tr id="row5683496"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p57710042"><a name="p57710042"></a><a name="p57710042"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p44001849"><a name="p44001849"></a><a name="p44001849"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7380012"><a name="p7380012"></a><a name="p7380012"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row60910108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p16488194717492"><a name="p16488194717492"></a><a name="p16488194717492"></a>45426</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p588994817496"><a name="p588994817496"></a><a name="p588994817496"></a>重要（默认级别）</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p34071398"><a name="p34071398"></a><a name="p34071398"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66730009"></a>

<a name="table8319831"></a>
<table><thead align="left"><tr id="row40868022"><th class="cellrowborder" valign="top" width="33.56%" id="mcps1.1.3.1.1"><p id="p21975462"><a name="p21975462"></a><a name="p21975462"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="66.44%" id="mcps1.1.3.1.2"><p id="p35182007"><a name="p35182007"></a><a name="p35182007"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row594512751512"><td class="cellrowborder" valign="top" width="33.56%" headers="mcps1.1.3.1.1 "><p id="p8838358184914"><a name="p8838358184914"></a><a name="p8838358184914"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="66.44%" headers="mcps1.1.3.1.2 "><p id="p837170125015"><a name="p837170125015"></a><a name="p837170125015"></a>产生告警的集群或系统名称</p>
</td>
</tr>
<tr id="row31170320"><td class="cellrowborder" valign="top" width="33.56%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="66.44%" headers="mcps1.1.3.1.2 "><p id="p172628810500"><a name="p172628810500"></a><a name="p172628810500"></a>产生告警的服务名称</p>
</td>
</tr>
<tr id="row127661937150"><td class="cellrowborder" valign="top" width="33.56%" headers="mcps1.1.3.1.1 "><p id="p1276613716519"><a name="p1276613716519"></a><a name="p1276613716519"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="66.44%" headers="mcps1.1.3.1.2 "><p id="p07661337952"><a name="p07661337952"></a><a name="p07661337952"></a>产生告警的角色名称</p>
</td>
</tr>
<tr id="row11698143657"><td class="cellrowborder" valign="top" width="33.56%" headers="mcps1.1.3.1.1 "><p id="p1569854312513"><a name="p1569854312513"></a><a name="p1569854312513"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="66.44%" headers="mcps1.1.3.1.2 "><p id="p146981243956"><a name="p146981243956"></a><a name="p146981243956"></a>产生告警的主机名</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63699172"></a>

ClickHouse在ZooKeeper的数量配额超过阈值后，无法通过FusionInsight Manager对ClickHouse进行集群操作，无法使用ClickHouse服务功能。

## 可能原因<a name="section36421639"></a>

ClickHouse在使用过程中，如表创建、插入或删除表数据等操作时，ClickHouse会在ZooKeeper的节点中创建znode，随着业务量的增加该znode实际数量可能会超过配置的阈值。

## 处理步骤<a name="section2425015133012"></a>

**检查ClickHouse在ZooKeeper的znode节点创建数量**

1.  登录ZooKeeper客户端所在主机节点，执行以下命令登录ZooKeeper客户端工具。

    切换到客户端安装目录。

    例如**：cd /opt/client**

    执行以下命令配置环境变量。

    **source bigdata\_env**

    执行以下命令进行用户认证。\(普通模式跳过此步骤\)

    **kinit **_组件业务用户_

    执行以下命令登录客户端工具。

    **zkCli.sh -server **_ZooKeeper角色实例所在节点业务IP_**: **_clientPort_

2.  <a name="li169092437415"></a>执行如下命令查看ZooKeeper上ClickHouse使用的配额情况，计算返回的结果中Output stat的count值与Output quota的count值之比是否大于0.9。

    **listquota /clickhouse**

    ```
    absolute path is /zookeeper/quota/clickhouse
    Output quota for /clickhouse count=200000,bytes=1000000000
    Output stat for /clickhouse count=2667,bytes=60063
    ```

    如上，Output stat对应的count为：2667，Output quota的count为：200000。

    -   是，执行[4](#li1290974311419)。
    -   否，等待五分钟查看告警是否清除，如果还没有清除请执行[5](#li93321856123314)。

3.  在FusionInsight Manager首页，选择“集群 \> 服务 \> ClickHouse \> 配置 \> 全部配置”，搜索“clickhouse.zookeeper.quota.node.count”参数，将该参数的值调整为[2](#li169092437415)中Output stat的count值的2倍。
4.  <a name="li1290974311419"></a>重启告警信息对应的ClickHouse实例，等待五分钟，查看告警是否消除。
    -   是，处理完毕。
    -   否，再次执行[4](#li1290974311419)，等待五分钟，查看告警是否消除，如果还没有清除请执行[5](#li93321856123314)。


**收集故障信息**

1.  <a name="li93321856123314"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ClickHouse”。
3.  单击右上角的![](figures/zh-cn_image_0295705020.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无

