# ALM-25000 LdapServer服务不可用<a name="ZH-CN_TOPIC_0191883112"></a>

## 告警解释<a name="zh-cn_topic_0191813909_section2601186"></a>

系统按30秒周期性检测LdapServer的服务状态。当检测到两个LdapServer服务均异常时产生该告警。

当检测到一个LdapServer服务恢复时告警恢复。

## 告警属性<a name="zh-cn_topic_0191813909_section23410681"></a>

<a name="zh-cn_topic_0191813909_table66898905"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813909_row21436848"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813909_p58663159"><a name="zh-cn_topic_0191813909_p58663159"></a><a name="zh-cn_topic_0191813909_p58663159"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813909_p54095401"><a name="zh-cn_topic_0191813909_p54095401"></a><a name="zh-cn_topic_0191813909_p54095401"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813909_p19651376"><a name="zh-cn_topic_0191813909_p19651376"></a><a name="zh-cn_topic_0191813909_p19651376"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813909_row48257652"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813909_p16555740"><a name="zh-cn_topic_0191813909_p16555740"></a><a name="zh-cn_topic_0191813909_p16555740"></a>25000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813909_p65946577"><a name="zh-cn_topic_0191813909_p65946577"></a><a name="zh-cn_topic_0191813909_p65946577"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813909_p40072506"><a name="zh-cn_topic_0191813909_p40072506"></a><a name="zh-cn_topic_0191813909_p40072506"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813909_section9369539"></a>

<a name="zh-cn_topic_0191813909_table24647552"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813909_row23371976"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813909_p14081900"><a name="zh-cn_topic_0191813909_p14081900"></a><a name="zh-cn_topic_0191813909_p14081900"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813909_p66892145"><a name="zh-cn_topic_0191813909_p66892145"></a><a name="zh-cn_topic_0191813909_p66892145"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813909_row49554687"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813909_p54506685"><a name="zh-cn_topic_0191813909_p54506685"></a><a name="zh-cn_topic_0191813909_p54506685"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813909_p52965331"><a name="zh-cn_topic_0191813909_p52965331"></a><a name="zh-cn_topic_0191813909_p52965331"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813909_row6925935"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813909_p24129853"><a name="zh-cn_topic_0191813909_p24129853"></a><a name="zh-cn_topic_0191813909_p24129853"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813909_p8361080"><a name="zh-cn_topic_0191813909_p8361080"></a><a name="zh-cn_topic_0191813909_p8361080"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813909_row8140857"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813909_p55429698"><a name="zh-cn_topic_0191813909_p55429698"></a><a name="zh-cn_topic_0191813909_p55429698"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813909_p60620523"><a name="zh-cn_topic_0191813909_p60620523"></a><a name="zh-cn_topic_0191813909_p60620523"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813909_section17216995"></a>

告警发生时，不能对集群中的KrbServer和LdapServer用户进行任何操作。例如，无法在MRS Manager页面添加、删除或修改任何用户、用户组或角色，也无法修改用户密码。集群中原有的用户验证不受影响。

## 可能原因<a name="zh-cn_topic_0191813909_section20735233"></a>

-   LdapServer服务所在节点故障。
-   LdapServer进程故障。

## 处理步骤<a name="zh-cn_topic_0191813909_section52399374"></a>

1.  检查LdapServer服务的两个SlapdServer实例所在节点是否故障。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  <a name="zh-cn_topic_0191813909_aalm-25000_mmccppss_id"></a>选择“LdapServer \> 实例”。进入LdapServer实例页面获取两个SlapdServer实例所在节点的主机名。
    3.  在“告警管理”页面，查看是否有ALM-12006 节点故障告警产生。
        -   是，执行[1.d](#zh-cn_topic_0191813909_aalm-25000_mmccppss_step_4)。
        -   否，执行[2.a](#zh-cn_topic_0191813909_li192616463126)。

    4.  <a name="zh-cn_topic_0191813909_aalm-25000_mmccppss_step_4"></a>查看告警信息里的主机名是否和[1.b](#zh-cn_topic_0191813909_aalm-25000_mmccppss_id)主机名一致。
        -   是，执行[1.e](#zh-cn_topic_0191813909_aalm-25000_mmccppss_alarm53003)。
        -   否，执行[2.a](#zh-cn_topic_0191813909_li192616463126)。

    5.  <a name="zh-cn_topic_0191813909_aalm-25000_mmccppss_alarm53003"></a>按ALM-12006 节点故障提供的步骤处理该告警。
    6.  在告警列表中查看“ALM-25000 LdapServer服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813909_li572522141314)。

2.  检查LdapServer进程是否正常。
    1.  <a name="zh-cn_topic_0191813909_li192616463126"></a>登录MRS集群详情页面，选择“告警管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“告警管理”。  

    2.  查看是否有ALM-12007 进程故障告警产生。
        -   是，执行[2.c](#zh-cn_topic_0191813909_aalm-25000_mmccppss_step_8)。
        -   否，执行[3](#zh-cn_topic_0191813909_li572522141314)。

    3.  <a name="zh-cn_topic_0191813909_aalm-25000_mmccppss_step_8"></a>查看告警信息中的服务名和主机名是否和LdapServer服务名和主机名一致。
        -   是，执行[2.d](#zh-cn_topic_0191813909_alarm53004)。
        -   否，执行[3](#zh-cn_topic_0191813909_li572522141314)。

    4.  <a name="zh-cn_topic_0191813909_alarm53004"></a>按ALM-12007 进程故障提供的步骤处理该告警。
    5.  在告警列表中查看“ALM-25000 LdapServer服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813909_li572522141314)。

3.  <a name="zh-cn_topic_0191813909_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813909_section1832323"></a>

无。

