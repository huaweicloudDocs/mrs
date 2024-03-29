# ALM-12031 omm用户或密码即将过期<a name="alm_12031"></a>

## 告警解释<a name="zh-cn_topic_0191813902_section22913051112229"></a>

系统每天零点开始，每8小时检测当前系统中**omm**用户和密码是否过期，如果用户或密码即将在15天内过期，则发送告警。

当系统中**omm**用户过期的期限修改或密码重置，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813902_section2423333112242"></a>

<a name="zh-cn_topic_0191813902_table20080275112150"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813902_row31482953112150"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813902_p67091225112150"><a name="zh-cn_topic_0191813902_p67091225112150"></a><a name="zh-cn_topic_0191813902_p67091225112150"></a><strong id="zh-cn_topic_0191813902_b66950114112150"><a name="zh-cn_topic_0191813902_b66950114112150"></a><a name="zh-cn_topic_0191813902_b66950114112150"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813902_p54250148112150"><a name="zh-cn_topic_0191813902_p54250148112150"></a><a name="zh-cn_topic_0191813902_p54250148112150"></a><strong id="zh-cn_topic_0191813902_b18489286112150"><a name="zh-cn_topic_0191813902_b18489286112150"></a><a name="zh-cn_topic_0191813902_b18489286112150"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813902_p21237236112150"><a name="zh-cn_topic_0191813902_p21237236112150"></a><a name="zh-cn_topic_0191813902_p21237236112150"></a><strong id="zh-cn_topic_0191813902_b56917401112150"><a name="zh-cn_topic_0191813902_b56917401112150"></a><a name="zh-cn_topic_0191813902_b56917401112150"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813902_row42494566112150"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813902_p19507845112150"><a name="zh-cn_topic_0191813902_p19507845112150"></a><a name="zh-cn_topic_0191813902_p19507845112150"></a>12031</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813902_p36631608112150"><a name="zh-cn_topic_0191813902_p36631608112150"></a><a name="zh-cn_topic_0191813902_p36631608112150"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813902_p14370280112150"><a name="zh-cn_topic_0191813902_p14370280112150"></a><a name="zh-cn_topic_0191813902_p14370280112150"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813902_section4525094112252"></a>

<a name="zh-cn_topic_0191813902_table6951519112150"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813902_row42472995112150"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813902_p17760602112150"><a name="zh-cn_topic_0191813902_p17760602112150"></a><a name="zh-cn_topic_0191813902_p17760602112150"></a><strong id="zh-cn_topic_0191813902_b25627690112150"><a name="zh-cn_topic_0191813902_b25627690112150"></a><a name="zh-cn_topic_0191813902_b25627690112150"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813902_p62576994112150"><a name="zh-cn_topic_0191813902_p62576994112150"></a><a name="zh-cn_topic_0191813902_p62576994112150"></a><strong id="zh-cn_topic_0191813902_b26322035112150"><a name="zh-cn_topic_0191813902_b26322035112150"></a><a name="zh-cn_topic_0191813902_b26322035112150"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813902_row35571730112150"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813902_p62737891112150"><a name="zh-cn_topic_0191813902_p62737891112150"></a><a name="zh-cn_topic_0191813902_p62737891112150"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813902_p48604412112150"><a name="zh-cn_topic_0191813902_p48604412112150"></a><a name="zh-cn_topic_0191813902_p48604412112150"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813902_row34786532112150"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813902_p66245693112150"><a name="zh-cn_topic_0191813902_p66245693112150"></a><a name="zh-cn_topic_0191813902_p66245693112150"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813902_p64300915112150"><a name="zh-cn_topic_0191813902_p64300915112150"></a><a name="zh-cn_topic_0191813902_p64300915112150"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813902_row41837324112150"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813902_p33380055112150"><a name="zh-cn_topic_0191813902_p33380055112150"></a><a name="zh-cn_topic_0191813902_p33380055112150"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813902_p19429939112150"><a name="zh-cn_topic_0191813902_p19429939112150"></a><a name="zh-cn_topic_0191813902_p19429939112150"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813902_section6062507011230"></a>

**omm**用户或密码过期，Manager各节点互信不可用，无法对服务提供管理功能。

## 可能原因<a name="zh-cn_topic_0191813902_section381058911234"></a>

系统**omm**用户或密码即将过期。

## 处理步骤<a name="zh-cn_topic_0191813902_section56658487112312"></a>

1.  检查系统中**omm**用户和密码是否正常。
    1.  登录故障节点。
    2.  执行以下命令来查看当前**omm**用户密码设置信息：

        **chage -l omm**

    3.  检查系统提示信息，是否用户已过期。

        1.  查找“Password expires”对应值，查看密码设置是否即将过期。
        2.  查找“Account expires”对应值，查看用户设置是否即将过期。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >如果参数值为“never”，则代表永不过期；如果为日期值，则查看是否在15天内过期。

        -   是，执行[1.d](#zh-cn_topic_0191813902_li2310249112814)。
        -   否，执行[2](#zh-cn_topic_0191813902_li572522141314)。

    4.  <a name="zh-cn_topic_0191813902_li2310249112814"></a>执行以下命令修改过期设置。
        -   设置**omm**用户过期的期限：

            **chage -E** _'指定日期'_ **omm**

        -   设置omm密码的有效天数：

            **chage -M** _'天数'_ **omm**

    5.  等待下周期检测，观察告警是否自动清除。
        -   是，操作结束。
        -   否，执行[2](#zh-cn_topic_0191813902_li572522141314)。

2.  <a name="zh-cn_topic_0191813902_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## **参考信息**<a name="zh-cn_topic_0191813902_section13081136172452"></a>

无。

