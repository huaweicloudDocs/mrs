# ALM-12005 OKerberos资源异常<a name="ZH-CN_TOPIC_0093195023"></a>

## 告警解释<a name="zh-cn_topic_0035461473_section3611620154337"></a>

告警模块对Manager中的Kerberos资源的状态进行监控，当Kerberos资源异常时，系统产生此告警。

当Kerberos资源恢复时，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0035461473_section5997119154348"></a>

<a name="zh-cn_topic_0035461473_table16546421115637"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035461473_row41815116115637"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035461473_p48061440115637"><a name="zh-cn_topic_0035461473_p48061440115637"></a><a name="zh-cn_topic_0035461473_p48061440115637"></a><strong id="zh-cn_topic_0035461473_b44071970115637"><a name="zh-cn_topic_0035461473_b44071970115637"></a><a name="zh-cn_topic_0035461473_b44071970115637"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035461473_p5986098115637"><a name="zh-cn_topic_0035461473_p5986098115637"></a><a name="zh-cn_topic_0035461473_p5986098115637"></a><strong id="zh-cn_topic_0035461473_b53229242115637"><a name="zh-cn_topic_0035461473_b53229242115637"></a><a name="zh-cn_topic_0035461473_b53229242115637"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035461473_p61212049115637"><a name="zh-cn_topic_0035461473_p61212049115637"></a><a name="zh-cn_topic_0035461473_p61212049115637"></a><strong id="zh-cn_topic_0035461473_b24682889115637"><a name="zh-cn_topic_0035461473_b24682889115637"></a><a name="zh-cn_topic_0035461473_b24682889115637"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035461473_row33839554115637"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035461473_p47289336115637"><a name="zh-cn_topic_0035461473_p47289336115637"></a><a name="zh-cn_topic_0035461473_p47289336115637"></a>12005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035461473_p1023065115637"><a name="zh-cn_topic_0035461473_p1023065115637"></a><a name="zh-cn_topic_0035461473_p1023065115637"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035461473_p13421197115637"><a name="zh-cn_topic_0035461473_p13421197115637"></a><a name="zh-cn_topic_0035461473_p13421197115637"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035461473_section32465194154357"></a>

<a name="zh-cn_topic_0035461473_table1097365115637"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035461473_row44291394115637"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035461473_p64459248115637"><a name="zh-cn_topic_0035461473_p64459248115637"></a><a name="zh-cn_topic_0035461473_p64459248115637"></a><strong id="zh-cn_topic_0035461473_b14940802115637"><a name="zh-cn_topic_0035461473_b14940802115637"></a><a name="zh-cn_topic_0035461473_b14940802115637"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035461473_p40507805115637"><a name="zh-cn_topic_0035461473_p40507805115637"></a><a name="zh-cn_topic_0035461473_p40507805115637"></a><strong id="zh-cn_topic_0035461473_b2497342115637"><a name="zh-cn_topic_0035461473_b2497342115637"></a><a name="zh-cn_topic_0035461473_b2497342115637"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035461473_row33742982115637"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461473_p42662311115637"><a name="zh-cn_topic_0035461473_p42662311115637"></a><a name="zh-cn_topic_0035461473_p42662311115637"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461473_p36711144115637"><a name="zh-cn_topic_0035461473_p36711144115637"></a><a name="zh-cn_topic_0035461473_p36711144115637"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035461473_row12863466115637"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461473_p26536069115637"><a name="zh-cn_topic_0035461473_p26536069115637"></a><a name="zh-cn_topic_0035461473_p26536069115637"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461473_p21373907115637"><a name="zh-cn_topic_0035461473_p21373907115637"></a><a name="zh-cn_topic_0035461473_p21373907115637"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035461473_row36105975115637"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461473_p11065798115637"><a name="zh-cn_topic_0035461473_p11065798115637"></a><a name="zh-cn_topic_0035461473_p11065798115637"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461473_p13553340115637"><a name="zh-cn_topic_0035461473_p13553340115637"></a><a name="zh-cn_topic_0035461473_p13553340115637"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035461473_section792090615442"></a>

Manager中的Kerberos资源异常，认证服务不可用，无法对Web上层服务提供安全认证功能，可能引起无法登录MRS Manager。

## 可能原因<a name="zh-cn_topic_0035461473_section2555755115446"></a>

Okerberos依赖的OLdap资源异常。

## 处理步骤<a name="zh-cn_topic_0035461473_section53015814154410"></a>

1.  检查Manager中的OKerberos依赖的OLdap资源是否异常。
    1.  登录主管理节点。
    2.  执行以下命令，查询当前HA管理的OLdap资源状态是否正常。

        **sh $\{BIGDATA\_HOME\}/OMSV100R001C00x8664/workspace0/ha/module/hacom/script/status\_ha.sh**

        OLdap资源在主节点为Active\_normal状态，在备节点为Standby\_normal状态表示正常：

        -   是，执行[3](#zh-cn_topic_0035461473_li5127445161135)。
        -   否，执行[2](#zh-cn_topic_0035461473_li29509559161240)。


2.  <a name="zh-cn_topic_0035461473_li29509559161240"></a>参考[ALM-12004 OLdap资源异常](ALM-12004-OLdap资源异常.md#ZH-CN_TOPIC_0093195022)处理OLdap资源，状态恢复后，观察当前OKerberos资源状态是否恢复正常。
    -   是，操作结束。
    -   否，执行[3](#zh-cn_topic_0035461473_li5127445161135)。

3.  <a name="zh-cn_topic_0035461473_li5127445161135"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035461473_section6463524415544"></a>

无。

