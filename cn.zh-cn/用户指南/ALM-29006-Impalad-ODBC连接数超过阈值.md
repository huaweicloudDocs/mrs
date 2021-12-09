# ALM-29006 Impalad ODBC连接数超过阈值<a name="ALM-29006"></a>

## 告警解释<a name="section8280367"></a>

以30s为周期检测连接到该Impalad节点的客户端连接数，当检测到的连接数超过自定义阈值（默认60）时，系统产生此告警。

当系统检测到客户端连接数减少到阈值以下时，告警将自动解除。

## 告警属性<a name="section7414445"></a>

<a name="table45079949"></a>
<table><thead align="left"><tr id="row5683496"><th class="cellrowborder" valign="top" width="33.3033303330333%" id="mcps1.1.4.1.1"><p id="p57710042"><a name="p57710042"></a><a name="p57710042"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.36333633363336%" id="mcps1.1.4.1.2"><p id="p44001849"><a name="p44001849"></a><a name="p44001849"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7380012"><a name="p7380012"></a><a name="p7380012"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row60910108"><td class="cellrowborder" valign="top" width="33.3033303330333%" headers="mcps1.1.4.1.1 "><p id="p16488194717492"><a name="p16488194717492"></a><a name="p16488194717492"></a>29006</p>
</td>
<td class="cellrowborder" valign="top" width="33.36333633363336%" headers="mcps1.1.4.1.2 "><p id="p588994817496"><a name="p588994817496"></a><a name="p588994817496"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p34071398"><a name="p34071398"></a><a name="p34071398"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section66730009"></a>

<a name="table8319831"></a>
<table><thead align="left"><tr id="row40868022"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p21975462"><a name="p21975462"></a><a name="p21975462"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p35182007"><a name="p35182007"></a><a name="p35182007"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row594512751512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p8838358184914"><a name="p8838358184914"></a><a name="p8838358184914"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p837170125015"><a name="p837170125015"></a><a name="p837170125015"></a>产生告警的集群名称</p>
</td>
</tr>
<tr id="row31170320"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p172628810500"><a name="p172628810500"></a><a name="p172628810500"></a>产生告警的服务名称</p>
</td>
</tr>
<tr id="row883552454311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1583622417439"><a name="p1583622417439"></a><a name="p1583622417439"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p783622419433"><a name="p783622419433"></a><a name="p783622419433"></a>产生告警的角色名称</p>
</td>
</tr>
<tr id="row164912316433"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p154923174310"><a name="p154923174310"></a><a name="p154923174310"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1349163115432"><a name="p1349163115432"></a><a name="p1349163115432"></a>产生告警的主机名</p>
</td>
</tr>
<tr id="row1305193818439"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1130583818431"><a name="p1130583818431"></a><a name="p1130583818431"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33051338164316"><a name="p33051338164316"></a><a name="p33051338164316"></a>系统当前指标取值满足自定义的告警设置条件</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63699172"></a>

后续新建立客户端连接可能会阻塞甚至失败。

## 可能原因<a name="section36421639"></a>

该Impalad服务维护的客户端连接过多，或者阈值设定的太小。

## 处理步骤<a name="section2425015133012"></a>

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \> Impala \> 连接数 \> 已经连接到Impalad进程的ODBC数量" ，检查阈值大小。

    ![](figures/zh-cn_image_0295292260.png)

2.  检查连接到当前Impalad进程的ODBC应用数，并关闭闲置的应用，观察告警是否自动清除。
    -   是，处理完毕。
    -   否，执行[3](#li1507754134111)，修改并发Impalad支持的并发连接数。

3.  <a name="li1507754134111"></a>在FusionInsight Manager首页，选择“集群 \> Impala \> 配置 \> 全部配置 \> Impalad \> 自定义”，增加自定义参数 --fe\_service\_threads，该参数默认值64，请按照需要修改该值，单击“保存”按钮保存配置。

    ![](figures/zh-cn_image_0295291957.png)

4.  在所有客户端的查询任务都执行完成后，选择“实例”页签，勾选所有“Impalad”实例并重启。

    ![](figures/zh-cn_image_0295292043.png)

5.  重启完成后告警将消失，请重新运行使用ODBC方式连接Impalad的应用。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section53362350"></a>

无

