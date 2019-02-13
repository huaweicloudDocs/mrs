# ALM-20002 Hue服务不可用<a name="ZH-CN_TOPIC_0093195107"></a>

## 告警解释<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section42400121"></a>

系统按60秒周期性检测Hue服务状态。当Hue服务不可用时产生该告警。

当Hue服务恢复时，告警恢复。

## 告警属性<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section46056776"></a>

<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_table3909558"></a>
<table><thead align="left"><tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row9358345"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p19828475"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p19828475"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p19828475"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p62602629"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p62602629"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p62602629"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p37648208"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p37648208"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p37648208"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row29606020"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p49277383"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p49277383"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p49277383"></a>20002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p32045124"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p32045124"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p32045124"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p45518241"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p45518241"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p45518241"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section11857806"></a>

<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_table63098886"></a>
<table><thead align="left"><tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row42029922"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p48980553"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p48980553"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p48980553"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p8001819"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p8001819"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p8001819"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row44167618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p20807334"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p20807334"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p20807334"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p7672494"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p7672494"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p7672494"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row1943587"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p23212893"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p23212893"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p23212893"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p1196208"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p1196208"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p1196208"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_row10765874"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p66729436"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p66729436"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p66729436"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p36375218"><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p36375218"></a><a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_p36375218"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section39611396"></a>

系统无法提供数据加载，查询，提取服务。

## 可能原因<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section20958252"></a>

-   Hue服务所依赖内部服务KrbServer故障。
-   Hue服务所依赖内部服务DBService故障。
-   与DBService连接的网络异常。

## 处理步骤<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section54406541"></a>

**检查KrbServer服务是否正常。**

1.  在MRS Manager界面，单击“服务管理”，在服务列表中查看“KrbServer”的“健康状态”是否为“良好”。
    -   是，执行[4](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3163376094312)。
    -   否，执行[2](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3201870494312)。

2.  <a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3201870494312"></a>单击KrbServer服务的“操作”列的“重启”，重启该服务。
3.  等待几分钟。检查“ALM-20002 Hue服务不可用”告警是否恢复。
    -   是，处理完毕。
    -   否，执行[4](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3163376094312)。


**检查DBService是否正常**

1.  <a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3163376094312"></a>登录MRS Manager界面，单击“服务管理”。
2.  在服务列表中查看DBService服务健康状态是否为“良好”。
    -   是，执行[8](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3066850394312)。
    -   否，执行[6](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li6300946494312)。

3.  <a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_li6300946494312"></a>单击DBService服务的“操作”列的“重启”，重启该服务。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >重启服务需要输入MRS Manager管理员密码并勾选“同时重启或启动相关的服务。”。  

4.  等待几分钟。检查“ALM-20002 Hue服务不可用”告警是否恢复。
    -   是，操作结束。
    -   否，执行[8](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3066850394312)。


**检查与DBService连接的网络是否正常。**

1.  <a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_li3066850394312"></a>在MRS Manager界面，单击“服务管理 \> Hue \> 实例”，记录主Hue的IP地址。
2.  使用PuTTY工具登录主Hue的IP地址。
3.  执行**ping**命令，查看主Hue所在主机与DBService服务所在主机的网络连接是否正常。（获取DBService服务IP地址的方式和获取主Hue IP地址的方式相同。）
    -   是，执行[16](#zh-cn_topic_0087154426_li8901153153924)。
    -   否，执行[11](#zh-cn_topic_0087154426_zh-cn_topic_0087039274_li4180632994312)。

4.  <a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_li4180632994312"></a>联系网络管理员恢复网络。
5.  等待几分钟。检查“ALM-20002 Hue服务不可用”告警是否恢复。

    -   是，处理完毕。
    -   否，执行[16](#zh-cn_topic_0087154426_li8901153153924)。

    **收集故障信息**。

6.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
7.  在“服务”下拉框中勾选如下节点信息，单击“确定”。
    -   Hue
    -   Controller

8.  设置日志收集的“开始时间”和“结束时间”分别为产生告警的前后10分钟，选择导出类型，单击“确定”，收集对应的故障日志信息。

**Hue重新启动。**

1.  <a name="zh-cn_topic_0087154426_li8901153153924"></a>在MRS Manager界面，单击“服务管理 \> Hue”。
2.  选择“更多 \> 重启服务”，单击“确定”。
3.  检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[19](#zh-cn_topic_0087154426_li16946055154531)。


1.  <a name="zh-cn_topic_0087154426_li16946055154531"></a>请联系运维人员，并发送已收集的故障日志信息。

## 参考信息<a name="zh-cn_topic_0087154426_zh-cn_topic_0087039274_section19896826"></a>

无。

