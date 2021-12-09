# ALM-27003 DBService主备节点间心跳中断<a name="ALM-27003"></a>

## 告警解释<a name="section66514996"></a>

DBService主节点或备节点超过7秒未收到对端的心跳消息后，系统产生告警。

当心跳恢复后，该告警恢复。

## 告警属性<a name="section61764053"></a>

<a name="table64410899"></a>
<table><thead align="left"><tr id="row38904557"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p64261390"><a name="p64261390"></a><a name="p64261390"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p37790133"><a name="p37790133"></a><a name="p37790133"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p41101895"><a name="p41101895"></a><a name="p41101895"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row40919214"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p26122066"><a name="p26122066"></a><a name="p26122066"></a>27003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p35512602"><a name="p35512602"></a><a name="p35512602"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p57948527"><a name="p57948527"></a><a name="p57948527"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section19005568"></a>

<a name="table63319096"></a>
<table><thead align="left"><tr id="row26078602"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p31992022"><a name="p31992022"></a><a name="p31992022"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p41216986"><a name="p41216986"></a><a name="p41216986"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row181627357121"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row50241599"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p63504971"><a name="p63504971"></a><a name="p63504971"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row34673827"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p63043579"><a name="p63043579"></a><a name="p63043579"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row30521303"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p64532912"><a name="p64532912"></a><a name="p64532912"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row43925297"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1179265"><a name="p1179265"></a><a name="p1179265"></a>Local DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p28411613"><a name="p28411613"></a><a name="p28411613"></a>本地DBService HA名称。</p>
</td>
</tr>
<tr id="row54377932"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p42536358"><a name="p42536358"></a><a name="p42536358"></a>Peer DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22892993"><a name="p22892993"></a><a name="p22892993"></a>对端DBService HA名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section36832391"></a>

DBService主备间心跳中断时只有一个节点提供服务，一旦该节点故障，再无法切换到备节点，就会服务不可用。

## 可能原因<a name="section63056065"></a>

主备DBService节点间链路异常。

## 处理步骤<a name="section30633681"></a>

**检查主备DBService服务器间的网络是否正常。**

1.  在FusionInsight Manager页面，在告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，查看该告警的DBService备服务器地址。
2.  以**root**用户登录主DBService服务器，用户密码为安装前用户自定义，请咨询系统管理员。

**向管理员获取登录密码。**

1.  执行**ping **_备DBService__心跳IP__地址_命令检查备DBService服务器是否可达。
    -   是，执行[6](#li60728989142921)。
    -   否，执行[4](#li61482471142921)。

2.  <a name="li61482471142921"></a>联系网络管理员查看是否为网络故障。
    -   是，执行[5](#li6747665142921)。
    -   否，执行[6](#li60728989142921)。

3.  <a name="li6747665142921"></a>修复网络故障，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#li60728989142921)。


**收集故障信息。**

1.  <a name="li60728989142921"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   DBService
    -   Controller
    -   NodeAgent

3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section7267679"></a>

无。

