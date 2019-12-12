# ALM-24000 Flume服务不可用<a name="ZH-CN_TOPIC_0191883126"></a>

## 告警解释<a name="zh-cn_topic_0191813917_section19665522175625"></a>

告警模块按180秒周期检测Flume服务状态，当检测到Flume服务异常时，系统产生此告警。

当系统检测到Flume服务恢复正常，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813917_section42254989175625"></a>

<a name="zh-cn_topic_0191813917_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813917_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813917_p34183898175625"><a name="zh-cn_topic_0191813917_p34183898175625"></a><a name="zh-cn_topic_0191813917_p34183898175625"></a><strong id="zh-cn_topic_0191813917_b39219631175625"><a name="zh-cn_topic_0191813917_b39219631175625"></a><a name="zh-cn_topic_0191813917_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813917_p22673543175625"><a name="zh-cn_topic_0191813917_p22673543175625"></a><a name="zh-cn_topic_0191813917_p22673543175625"></a><strong id="zh-cn_topic_0191813917_b2735300175625"><a name="zh-cn_topic_0191813917_b2735300175625"></a><a name="zh-cn_topic_0191813917_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813917_p20232782175625"><a name="zh-cn_topic_0191813917_p20232782175625"></a><a name="zh-cn_topic_0191813917_p20232782175625"></a><strong id="zh-cn_topic_0191813917_b47877317175625"><a name="zh-cn_topic_0191813917_b47877317175625"></a><a name="zh-cn_topic_0191813917_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813917_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813917_p64045571162527"><a name="zh-cn_topic_0191813917_p64045571162527"></a><a name="zh-cn_topic_0191813917_p64045571162527"></a>24000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813917_p20308775162527"><a name="zh-cn_topic_0191813917_p20308775162527"></a><a name="zh-cn_topic_0191813917_p20308775162527"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813917_p34398042162527"><a name="zh-cn_topic_0191813917_p34398042162527"></a><a name="zh-cn_topic_0191813917_p34398042162527"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813917_section27218191175625"></a>

<a name="zh-cn_topic_0191813917_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813917_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813917_p9726186175625"><a name="zh-cn_topic_0191813917_p9726186175625"></a><a name="zh-cn_topic_0191813917_p9726186175625"></a><strong id="zh-cn_topic_0191813917_b20426813175625"><a name="zh-cn_topic_0191813917_b20426813175625"></a><a name="zh-cn_topic_0191813917_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813917_p43959148175625"><a name="zh-cn_topic_0191813917_p43959148175625"></a><a name="zh-cn_topic_0191813917_p43959148175625"></a><strong id="zh-cn_topic_0191813917_b60088019175625"><a name="zh-cn_topic_0191813917_b60088019175625"></a><a name="zh-cn_topic_0191813917_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813917_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813917_p59799763162535"><a name="zh-cn_topic_0191813917_p59799763162535"></a><a name="zh-cn_topic_0191813917_p59799763162535"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813917_p11942641162535"><a name="zh-cn_topic_0191813917_p11942641162535"></a><a name="zh-cn_topic_0191813917_p11942641162535"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813917_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813917_p49142552162535"><a name="zh-cn_topic_0191813917_p49142552162535"></a><a name="zh-cn_topic_0191813917_p49142552162535"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813917_p21123738162535"><a name="zh-cn_topic_0191813917_p21123738162535"></a><a name="zh-cn_topic_0191813917_p21123738162535"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813917_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813917_p31275648162535"><a name="zh-cn_topic_0191813917_p31275648162535"></a><a name="zh-cn_topic_0191813917_p31275648162535"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813917_p50299569162535"><a name="zh-cn_topic_0191813917_p50299569162535"></a><a name="zh-cn_topic_0191813917_p50299569162535"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813917_section23922301175625"></a>

当Flume服务不可用时，Flume不能正常工作，数据传输业务中断。

## 可能原因<a name="zh-cn_topic_0191813917_section58162349175625"></a>

-   HDFS服务不可用。
-   LdapServer服务不可用。

## 处理步骤<a name="zh-cn_topic_0191813917_section51182191175625"></a>

1.  检查HDFS的服务状态。
    1.  登录MRS集群详情页面，选择“告警管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“告警管理”。  

    2.  查看是否有“ALM-14000 HDFS服务不可用”告警产生。
        -   是，参考“ALM-14000 HDFS服务不可用”的处理步骤处理该告警。
        -   否，执行[2](#zh-cn_topic_0191813917_li56731580163419)。

2.  <a name="zh-cn_topic_0191813917_li56731580163419"></a>检查LdapServer的服务状态。

    查看是否有“ALM-25000 LdapServer服务不可用”告警产生。

    -   是，参考“ALM-25000 LdapServer服务不可用”的处理步骤处理该告警。
    -   否，执行[3.b](#zh-cn_topic_0191813917_li950355316374)。

3.  检查HDFS、LdapServer的服务是否已停止。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  <a name="zh-cn_topic_0191813917_li950355316374"></a>在MRS的服务列表中，查看HDFS、LdapServer服务是否已停止。
        -   是，启动HDFS、LdapServer服务，执行[3.c](#zh-cn_topic_0191813917_li4163406916374)。
        -   否，执行[4](#zh-cn_topic_0191813917_li572522141314)。

    3.  <a name="zh-cn_topic_0191813917_li4163406916374"></a>在告警列表中查看“ALM-24000 Flume服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0191813917_li572522141314)。

4.  <a name="zh-cn_topic_0191813917_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813917_section20269844175625"></a>

无。

