# ALM-25500 KrbServer服务不可用<a name="alm_25500"></a>

## 告警解释<a name="zh-cn_topic_0191813953_section10722842"></a>

系统按30秒周期性检测组件KrbServer的服务状态。当检测到组件KrbServer服务异常时产生该告警。

当检测到组件KrbServer服务恢复时告警恢复。

## 告警属性<a name="zh-cn_topic_0191813953_section29396722"></a>

<a name="zh-cn_topic_0191813953_table4400500"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813953_row63695501"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813953_p59061958"><a name="zh-cn_topic_0191813953_p59061958"></a><a name="zh-cn_topic_0191813953_p59061958"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813953_p19289328"><a name="zh-cn_topic_0191813953_p19289328"></a><a name="zh-cn_topic_0191813953_p19289328"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813953_p18931763"><a name="zh-cn_topic_0191813953_p18931763"></a><a name="zh-cn_topic_0191813953_p18931763"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813953_row57077814"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813953_p59900193"><a name="zh-cn_topic_0191813953_p59900193"></a><a name="zh-cn_topic_0191813953_p59900193"></a>25500</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813953_p20077469"><a name="zh-cn_topic_0191813953_p20077469"></a><a name="zh-cn_topic_0191813953_p20077469"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813953_p15662289"><a name="zh-cn_topic_0191813953_p15662289"></a><a name="zh-cn_topic_0191813953_p15662289"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813953_section63243911"></a>

<a name="zh-cn_topic_0191813953_table60685926"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813953_row31278690"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813953_p50545980"><a name="zh-cn_topic_0191813953_p50545980"></a><a name="zh-cn_topic_0191813953_p50545980"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813953_p583706"><a name="zh-cn_topic_0191813953_p583706"></a><a name="zh-cn_topic_0191813953_p583706"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813953_row47280229"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813953_p4493316"><a name="zh-cn_topic_0191813953_p4493316"></a><a name="zh-cn_topic_0191813953_p4493316"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813953_p28414304"><a name="zh-cn_topic_0191813953_p28414304"></a><a name="zh-cn_topic_0191813953_p28414304"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813953_row54402144"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813953_p44497505"><a name="zh-cn_topic_0191813953_p44497505"></a><a name="zh-cn_topic_0191813953_p44497505"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813953_p47528147"><a name="zh-cn_topic_0191813953_p47528147"></a><a name="zh-cn_topic_0191813953_p47528147"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813953_row25100141"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813953_p19845579"><a name="zh-cn_topic_0191813953_p19845579"></a><a name="zh-cn_topic_0191813953_p19845579"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813953_p63988077"><a name="zh-cn_topic_0191813953_p63988077"></a><a name="zh-cn_topic_0191813953_p63988077"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813953_section32324290"></a>

告警发生时，不能对集群中的组件KrbServer进行任何操作。其它组件的KrbServer认证将受影响。集群中依赖KrbServer的组件健康状态将为故障。

## 可能原因<a name="zh-cn_topic_0191813953_section22483156"></a>

-   组件KrbServer服务所在节点故障。
-   OLdap服务不可用。

## 处理步骤<a name="zh-cn_topic_0191813953_section1021814"></a>

1.  检查组件KrbServer服务所在节点是否故障。
    1.  登录MRS集群详情页面，选择“组件管理”。
    2.  <a name="zh-cn_topic_0191813953_aalm-25500_mmccppss_id"></a>选择“KrbServer \> 实例”。进入KrbServer实例页面查看KrbServer服务所在节点的主机名。
    3.  在“告警管理”页面，查看是否有ALM-12006 节点故障告警产生。
        -   是，执行[1.d](#zh-cn_topic_0191813953_aalm-25500_mmccppss_step_4)。
        -   否，执行[2.a](#zh-cn_topic_0191813953_li14191191521615)。

    4.  <a name="zh-cn_topic_0191813953_aalm-25500_mmccppss_step_4"></a>查看告警信息里的主机名是否和[1.b](#zh-cn_topic_0191813953_aalm-25500_mmccppss_id)主机名一致。
        -   是，执行[1.e](#zh-cn_topic_0191813953_aalm-25500_mmccppss_alarm53003)。
        -   否，执行[2.a](#zh-cn_topic_0191813953_li14191191521615)。

    5.  <a name="zh-cn_topic_0191813953_aalm-25500_mmccppss_alarm53003"></a>按ALM-12006 节点故障提供的步骤处理该告警。
    6.  在告警列表中查看“ALM-25500 KrbServer服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813953_li572522141314)。

2.  检查OLdap服务是否不可用。
    1.  <a name="zh-cn_topic_0191813953_li14191191521615"></a>登录MRS集群详情页面，选择“告警管理”。
    2.  查看是否有ALM-12004 OLdap资源异常告警产生。
        -   是，执行[2.c](#zh-cn_topic_0191813953_aalm-25500_mmccppss_step_8)。
        -   否，执行[3](#zh-cn_topic_0191813953_li572522141314)。

    3.  <a name="zh-cn_topic_0191813953_aalm-25500_mmccppss_step_8"></a>按ALM-12004 OLdap资源异常提供的步骤处理该告警。
    4.  在告警列表中查看“ALM-25500 KrbServer服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0191813953_li572522141314)。

3.  <a name="zh-cn_topic_0191813953_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813953_section9196329"></a>

无。

