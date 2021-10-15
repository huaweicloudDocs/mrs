# ALM-45175 OBS元数据接口调用平均时间超过阈值<a name="ALM-45175"></a>

## 告警解释<a name="section13447226"></a>

系统每30秒周期性检测OBS元数据接口调用平均时间是否超过阈值，当检测到连续超过所设置阈值次数大于平滑次数时就会产生该告警 。

当OBS元数据接口调用平均时间小于阈值时，该告警会自动清除。

## 告警属性<a name="section53916176"></a>

<a name="table33817547"></a>
<table><thead align="left"><tr id="row8931076"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p52328576"><a name="p52328576"></a><a name="p52328576"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p10756297"><a name="p10756297"></a><a name="p10756297"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65953734"><a name="p65953734"></a><a name="p65953734"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row40652256"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p179511920165120"><a name="p179511920165120"></a><a name="p179511920165120"></a>45175</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p28828553"><a name="p28828553"></a><a name="p28828553"></a>次要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p53411432"><a name="p53411432"></a><a name="p53411432"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section15483537"></a>

<a name="table31358724"></a>
<table><thead align="left"><tr id="row33518103"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p30611809"><a name="p30611809"></a><a name="p30611809"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p63637484"><a name="p63637484"></a><a name="p63637484"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row163311621185116"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row54362592"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56463136"><a name="p56463136"></a><a name="p56463136"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row38406179"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56266616"><a name="p56266616"></a><a name="p56266616"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row36637496"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61773077"><a name="p61773077"></a><a name="p61773077"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row7466123884718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p57854422"><a name="p57854422"></a><a name="p57854422"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55696635"><a name="p55696635"></a><a name="p55696635"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section5134112"></a>

OBS元数据接口调用平均时间超过阈值，会影响上层大数据计算业务的性能，导致某些计算任务的执行时间超过阈值。

## 可能原因<a name="section46207013"></a>

OBS服务端出现卡顿，或OBS客户端到OBS服务端之间的网络不稳定。

## 处理步骤<a name="section18511446101016"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> OBS元数据接口调用平均时间超过阈值”，查看“定位信息”中的角色名并确定实例的IP地址。
2.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> meta \> 实例 \> meta（对应上报告警实例IP地址）”。单击图表区域右上角的下拉菜单，选择“定制”，在“OBS元数据操作”中勾选“OBS接口调用平均时间”，单击“确定”，查看OBS元数据接口调用平均时间，确定是否有接口调用时间超过阈值。

    -   是，执行[3](#li5868113155910)。
    -   否，执行[5](#li4749473185459)。

    **图 1**  OBS接口调用平均时间<a name="fig1150612457515"></a>  
    ![](figures/OBS接口调用平均时间.png "OBS接口调用平均时间")

3.  <a name="li5868113155910"></a>选择“集群 \>  _待操作集群的名称_  \> 运维 \> 告警 \> 阈值设置  \> meta \> OBS元数据接口调用平均时间”，将阈值或平滑次数参数的值根据实际情况调大。
4.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[5](#li4749473185459)。


**收集故障信息。**

1.  <a name="li4749473185459"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选操作OMS下面的“NodeAgent”、“NodeMetricAgent”、“OmmServer”、“OmmAgent”。
3.  单击右上角的![](figures/zh-cn_image_0276137859.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后30分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section51780573"></a>

无。

