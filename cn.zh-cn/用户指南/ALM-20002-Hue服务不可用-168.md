# ALM-20002 Hue服务不可用<a name="ALM-20002"></a>

## 告警解释<a name="section42400121"></a>

系统按60秒周期性检测Hue服务状态。当Hue服务不可用时产生该告警。

当Hue服务恢复时，告警恢复。

## 告警属性<a name="section46056776"></a>

<a name="table3909558"></a>
<table><thead align="left"><tr id="row9358345"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p19828475"><a name="p19828475"></a><a name="p19828475"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62602629"><a name="p62602629"></a><a name="p62602629"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p37648208"><a name="p37648208"></a><a name="p37648208"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row29606020"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p49277383"><a name="p49277383"></a><a name="p49277383"></a>20002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p32045124"><a name="p32045124"></a><a name="p32045124"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p45518241"><a name="p45518241"></a><a name="p45518241"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section11857806"></a>

<a name="table63098886"></a>
<table><thead align="left"><tr id="row42029922"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p48980553"><a name="p48980553"></a><a name="p48980553"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p8001819"><a name="p8001819"></a><a name="p8001819"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row88451931718"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row44167618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p7672494"><a name="p7672494"></a><a name="p7672494"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row1943587"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1196208"><a name="p1196208"></a><a name="p1196208"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row10765874"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p36375218"><a name="p36375218"></a><a name="p36375218"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section39611396"></a>

系统无法提供数据加载，查询，提取服务。

## 可能原因<a name="section20958252"></a>

-   Hue服务所依赖内部服务KrbServer故障。
-   Hue服务所依赖内部服务DBService故障。
-   与DBService连接的网络异常。

## 处理步骤<a name="section54406541"></a>

**检查KrbServer服务是否正常。**

1.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务”，在服务列表中查看“KrbServer”的“运行状态”是否为“良好”。
    -   是，执行[4](#li3163376094312)。
    -   否，执行[2](#li3201870494312)。

2.  <a name="li3201870494312"></a>手动重启KrbServer服务。
3.  等待几分钟。检查“Hue服务不可用”告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#li3163376094312)。


**检查DBService是否正常**

1.  <a name="li3163376094312"></a>登录FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务”。
2.  在服务列表中查看DBService服务运行状态是否为“良好”。
    -   是，执行[8](#li3066850394312)。
    -   否，执行[6](#li6300946494312)。

3.  <a name="li6300946494312"></a>重启DBService服务。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >重启服务需要输入FusionInsight Manager管理员密码。

4.  等待几分钟。检查“Hue服务不可用”告警是否恢复。
    -   是，操作结束。
    -   否，执行[8](#li3066850394312)。


**检查与DBService连接的网络是否正常**

1.  <a name="li3066850394312"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hue \> 实例”，记录主Hue的IP地址。
2.  登录主Hue的IP地址。
3.  执行**ping**命令，查看主Hue所在主机与DBService服务所在主机的网络连接是否正常。（获取DBService服务IP地址的方式和获取主Hue IP地址的方式相同。）
    -   是，执行[13](#li310027094312)。
    -   否，执行[11](#li4180632994312)。

4.  <a name="li4180632994312"></a>联系网络管理员恢复网络。
5.  等待几分钟。检查“Hue服务不可用”告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li310027094312)。


**收集故障信息**

1.  <a name="li310027094312"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选如下节点信息。
    -   Hue
    -   Controller

3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Hue”。
5.  选择“更多 \> 重启服务”，单击“确定”。

1.  检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[19](#li307709594312)。

2.  <a name="li307709594312"></a>请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19896826"></a>

无。

