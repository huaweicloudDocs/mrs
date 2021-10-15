# ALM-18025 Yarn被终止的任务数超过阈值<a name="ALM-18025"></a>

## 告警解释<a name="section31658481"></a>

告警模块按60秒周期检测Yarn root队列上被终止的应用的数量，当root队列上该监控周期内新增的被终止的应用的数量超过50，且连续发生3次以上时，触发该告警。

## 告警属性<a name="section16490876"></a>

<a name="table7825795184"></a>
<table><thead align="left"><tr id="row10829199161819"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p7830149181817"><a name="p7830149181817"></a><a name="p7830149181817"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p4832169171818"><a name="p4832169171818"></a><a name="p4832169171818"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p7834295185"><a name="p7834295185"></a><a name="p7834295185"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row11834698184"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p138359915188"><a name="p138359915188"></a><a name="p138359915188"></a>18025</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p108361599186"><a name="p108361599186"></a><a name="p108361599186"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1083810991819"><a name="p1083810991819"></a><a name="p1083810991819"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section14200159"></a>

<a name="table15448152818187"></a>
<table><thead align="left"><tr id="row2451192861813"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p445318287184"><a name="p445318287184"></a><a name="p445318287184"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p14455152871817"><a name="p14455152871817"></a><a name="p14455152871817"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row077613291817"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19312851019"><a name="p19312851019"></a><a name="p19312851019"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row8457102815185"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66771667"><a name="p66771667"></a><a name="p66771667"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row846182891817"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20205523"><a name="p20205523"></a><a name="p20205523"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row1863012571189"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55361472"><a name="p55361472"></a><a name="p55361472"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row76301557131813"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p26086497"><a name="p26086497"></a><a name="p26086497"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p32631511"><a name="p32631511"></a><a name="p32631511"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section60692571"></a>

大量应用任务被强制终止。

## 可能原因<a name="section9362234"></a>

-   人为强制终止大量任务。
-   系统出于某种错误终止任务。

## 处理步骤<a name="section18537579256"></a>

**检查告警详情。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”，打开告警页面。
2.  查看“Yarn被终止的任务数超过阈值”告警详情中的“附加信息”，确认监控阈值是否设置过小。
    -   是，执行[3](#li88991487294)。
    -   否，执行[4](#li195342313207)。

3.  <a name="li88991487294"></a>选择“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Yarn \> 其它 \> root队列下被杀死的任务数”，修改该监控的阈值。执行[6](#li64965179612)。
4.  <a name="li195342313207"></a>选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> ResourceManager\(主\)”，进入ResourceManager的WebUI页面。
5.  单击“Applications”下的“KILLED”，单击最上面的任务。查看“Diagnostics”对应的描述信息，根据定位的任务被终止的详情（例如：被某用户终止）处理相关问题。

    **图 1**  单击“KILLED”<a name="fig152618368711"></a>  
    ![](figures/单击-KILLED.png "单击-KILLED")

6.  <a name="li64965179612"></a>等待3分钟，查看该告警是否消除。
    -   是，处理完毕。
    -   否，执行[7](#li76841314475)。


**收集故障信息。**

1.  <a name="li76841314475"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Yarn”。
3.  单击右上角的![](figures/zh-cn_image_0263895873.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section20143465"></a>

无。

