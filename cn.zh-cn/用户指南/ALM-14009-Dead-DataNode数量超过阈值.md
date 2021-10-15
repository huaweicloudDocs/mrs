# ALM-14009 Dead DataNode数量超过阈值<a name="ALM-14009"></a>

## 告警解释<a name="section49259524"></a>

系统每30秒周期性检测HDFS集群处于故障状态的DataNode数量，并把实际的故障状态的DataNode数量和阈值相比较。故障状态的DataNode数量指标默认提供一个阈值范围。当HDFS集群故障状态的DataNode数量超出阈值范围时，产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> HDFS”修改阈值。

平滑次数为1，故障状态的DataNode数量小于或等于阈值时，告警恢复；平滑次数大于1，故障状态的DataNode数量小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section40682540"></a>

<a name="table25741704"></a>
<table><thead align="left"><tr id="row54998405"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p25685840"><a name="p25685840"></a><a name="p25685840"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p178308"><a name="p178308"></a><a name="p178308"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p14442951"><a name="p14442951"></a><a name="p14442951"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row29028420"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2491809"><a name="p2491809"></a><a name="p2491809"></a>14009</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p509958"><a name="p509958"></a><a name="p509958"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p41306652"><a name="p41306652"></a><a name="p41306652"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section30598541"></a>

<a name="table57504522"></a>
<table><thead align="left"><tr id="row10277147"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p27142594"><a name="p27142594"></a><a name="p27142594"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p51066534"><a name="p51066534"></a><a name="p51066534"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1180763812317"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row42748590"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p25560652"><a name="p25560652"></a><a name="p25560652"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row28719280"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52616382"><a name="p52616382"></a><a name="p52616382"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row3785394"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5696517"><a name="p5696517"></a><a name="p5696517"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row13486182622716"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37111817"><a name="p37111817"></a><a name="p37111817"></a>NameService名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p53267196"><a name="p53267196"></a><a name="p53267196"></a>产生告警的NameService名称。</p>
</td>
</tr>
<tr id="row51268659"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p59120737"><a name="p59120737"></a><a name="p59120737"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24050367"><a name="p24050367"></a><a name="p24050367"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section6951418"></a>

故障状态的DataNode节点无法提供HDFS服务。

## 可能原因<a name="section62562762"></a>

-   DataNode故障或者负荷过高。
-   NameNode和DataNode之间的网络断连或者繁忙。
-   NameNode负荷过高。
-   DataNode被删除后，没有重启NameNode。

## 处理步骤<a name="section26193952"></a>

**查看DataNode是否故障。**

1.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS”。
2.  在“基本信息”区域，单击“NameNode\(主\)”，进入HDFS WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

3.  在HDFS WebUI，单击“Datanodes”页签，在“In operation”区域，打开“Filter”下拉菜单，查看是否有“down”选项。
    -   是，选择“down”，记录筛选出的DataNode节点的信息，执行[4](#li4328027917212)。
    -   否，执行[8](#li1289079617212)。

4.  <a name="li4328027917212"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，在实例列表中，检查已记录的DataNode节点是否存在。
    -   所有已记录的DataNode节点都存在时，执行[5](#li1334319581768)。
    -   所有已记录的DataNode节点都不存在时，执行[6](#li13933129133213)。
    -   部分已记录的DataNode节点存在时，执行[7](#li2289670317212)。

5.  <a name="li1334319581768"></a>勾选对应的DataNode实例，选择“更多 \> 重启实例”进行重启，重启结束后，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[8](#li1289079617212)。

6.  <a name="li13933129133213"></a>勾选所有的NameNode实例，选择“更多 \> 滚动重启实例”进行重启，重启结束后，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[16](#li3428026817212)。

7.  <a name="li2289670317212"></a>勾选所有的NameNode实例，选择“更多 \> 滚动重启实例”进行重启。重启完成后，勾选对应的DataNode实例，选择“更多 \> 重启实例”进行重启，重启结束后，查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[8](#li1289079617212)。


**查看NameNode和DataNode之间的网络情况。**

1.  <a name="li1289079617212"></a>以**root**用户登录管理页面上存在且处于故障状态DataNode的业务平面IP节点，用户密码为安装前用户自定义，请咨询系统管理员，执行**ping **_NameNode__的IP__地址_命令以检查DataNode和NameNode之间的网络是否异常。

    在FusionInsight Manager界面，单击“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 实例”，在实例列表中可查看处于故障状态DataNode的业务平面IP地址。

    -   是，执行[9](#li2367820817212)。
    -   否，执行[10](#li5499908917212)。

2.  <a name="li2367820817212"></a>修复网络故障，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[10](#li5499908917212)。


**查看DataNode是否负荷过高。**

1.  <a name="li5499908917212"></a>在FusionInsight Manager首页，单击“运维 \> 告警 \> 告警”，查看否存在“ALM-14008 HDFS DataNode内存使用率超过阈值”的告警。
    -   是，执行[11](#li4519735617212)。
    -   否，执行[13](#li1045416417212)。

2.  <a name="li4519735617212"></a>参考“ALM-14008 HDFS DataNode内存使用率超过阈值”的处理步骤，对该异常告警进行处理，查看是否消除该告警。
    -   是，执行[12](#li5684090817212)。
    -   否，执行[13](#li1045416417212)。

3.  <a name="li5684090817212"></a>在告警列表中查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li1045416417212)。


**查看NameNode是否负荷过高。**

1.  <a name="li1045416417212"></a>在FusionInsight Manager首页，单击“运维 \> 告警 \> 告警”，查看是否存在“ALM-14007 HDFS NameNode内存使用率超过阈值”的告警。
    -   是，执行[14](#li183523517212)。
    -   否，执行[16](#li3428026817212)。

2.  <a name="li183523517212"></a>参考“ALM-14007 HDFS NameNode内存使用率超过阈值”的处理步骤，对该异常告警进行处理，查看是否消除告警。
    -   是，执行[15](#li2617854017212)。
    -   否，执行[16](#li3428026817212)。

3.  <a name="li2617854017212"></a>在告警列表中查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[16](#li3428026817212)。


**收集故障信息。**

1.  <a name="li3428026817212"></a>在FusionInsight Manager首页，单击“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HDFS”。
3.  单击右上角的![](figures/zh-cn_image_0263895680.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section34418980"></a>

无。

