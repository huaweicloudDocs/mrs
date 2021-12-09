# ALM-29004 Impalad进程内存占用率超过阈值<a name="ALM-29004"></a>

## 告警解释<a name="section8280367"></a>

以30s为周期检测Impalad进程系统内存占用率，当检测到的超过默认阈值（80%）时，系统产生此告警。

当系统检测到进程内存占用率下降到阈值以下时，告警将自动解除。

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
<tbody><tr id="row60910108"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p16488194717492"><a name="p16488194717492"></a><a name="p16488194717492"></a>29004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p588994817496"><a name="p588994817496"></a><a name="p588994817496"></a>次要</p>
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
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p837170125015"><a name="p837170125015"></a><a name="p837170125015"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row31170320"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p172628810500"><a name="p172628810500"></a><a name="p172628810500"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row8175713133714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18175513173712"><a name="p18175513173712"></a><a name="p18175513173712"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row144886177375"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p24881417123717"><a name="p24881417123717"></a><a name="p24881417123717"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13488417133716"><a name="p13488417133716"></a><a name="p13488417133716"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row1688158103712"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p688484371"><a name="p688484371"></a><a name="p688484371"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19884817379"><a name="p19884817379"></a><a name="p19884817379"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section63699172"></a>

内存使用过高，部分查询任务可能因为内存不足而失败。

## 可能原因<a name="section36421639"></a>

Impalad进程正在执行较大量查询任务。

## 处理步骤<a name="section2425015133012"></a>

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 阈值设置 \> Impala \> CPU和内存 \> Impalad进程的内存占用率（Impalad）" ，检查阈值大小。

    ![](figures/zh-cn_image_0295292652.png)

2.  如阈值较小（小于80%），可根据实际需要适当增大告警阈值，检查告警是否消除。
    -   是，处理完毕。
    -   否，执行[3](#li54643151153)。

3.  <a name="li54643151153"></a>如阈值已超过80%，请检查告警出现时刻是否有突发的大量并发查询任务，突发大量任务将会导致内存占用飙升，待任务执行完成后告警将自动消失，期间可能有因内存不足而执行失败或取消的任务，请重试。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如内存占用超过阈值为常态化状态，需要考虑集群扩容。


## 告警清除<a name="section169311343318"></a>

突发并发任务执行结束后告警自动清除。

## 参考信息<a name="section53362350"></a>

无

