# ALM-25000 LdapServer服务不可用<a name="ALM-25000"></a>

## 告警解释<a name="section61405329"></a>

系统按30秒周期性检测LdapServer的服务状态，当检测到两个LdapServer服务均异常时产生该告警。

当检测到一个或两个LdapServer服务恢复时告警恢复。

## 告警属性<a name="section15777053"></a>

<a name="table37159314"></a>
<table><thead align="left"><tr id="row59241974"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p33870598"><a name="p33870598"></a><a name="p33870598"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p59163898"><a name="p59163898"></a><a name="p59163898"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p27546427"><a name="p27546427"></a><a name="p27546427"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row16668080"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p7937217"><a name="p7937217"></a><a name="p7937217"></a>25000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p38934872"><a name="p38934872"></a><a name="p38934872"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66716890"><a name="p66716890"></a><a name="p66716890"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section7775756"></a>

<a name="table35359025"></a>
<table><thead align="left"><tr id="row24140394"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p9214932"><a name="p9214932"></a><a name="p9214932"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p8212055"><a name="p8212055"></a><a name="p8212055"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1241112051512"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row61196698"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66312065"><a name="p66312065"></a><a name="p66312065"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row59937677"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p60265248"><a name="p60265248"></a><a name="p60265248"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row5516328"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20951452"><a name="p20951452"></a><a name="p20951452"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2872941"></a>

告警发生时，不能对集群中的KrbServer和LdapServer用户进行任何操作。例如，无法在FusionInsight Manager页面添加、删除或修改任何用户、用户组或角色，也无法修改用户密码。集群中原有的用户验证不受影响。

## 可能原因<a name="section25856475"></a>

-   LdapServer服务所在节点故障。
-   LdapServer进程故障。

## 处理步骤<a name="section31381686"></a>

**检查LdapServer服务的两个SlapdServer实例所在节点是否故障。**

1.  <a name="li3266702391835"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer \> 实例”。进入LdapServer实例页面获取两个SlapdServer实例所在节点的主机名。
2.  选择“运维 \> 告警 \> 告警”，在告警列表中查看是否有“节点故障”告警产生。
    -   是，执行[3](#li5361869791835)。
    -   否，执行[6](#li128149191835)。

3.  <a name="li5361869791835"></a>查看告警信息里的主机名是否和[1](#li3266702391835)主机名一致。
    -   是，执行[4](#li4814722691835)。
    -   否，执行[6](#li128149191835)。

4.  <a name="li4814722691835"></a>按“ALM-12006 节点故障”提供的步骤处理该告警。
5.  在告警列表中查看“LdapServer服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[10](#li4248878791835)。


****检查LdapServer进程是否正常。****

1.  <a name="li128149191835"></a>选择“运维 \> 告警 \> 告警”，在告警列表中查看是否有“进程故障”告警产生。
    -   是，执行[7](#li1646475891835)。
    -   否，执行[10](#li4248878791835)。

2.  <a name="li1646475891835"></a>查看告警信息中的服务名和主机名是否和LdapServer服务名和主机名一致。
    -   是，执行[8](#li5857705491835)。
    -   否，执行[10](#li4248878791835)。

3.  <a name="li5857705491835"></a>按“ALM-12007 进程故障”提供的步骤处理该告警。
4.  在告警列表中查看“LdapServer服务不可用”告警是否清除。
    -   是，处理完毕。
    -   否，执行[10](#li4248878791835)。


**收集故障信息。**

1.  <a name="li4248878791835"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“LdapServer”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section13999719"></a>

无。

