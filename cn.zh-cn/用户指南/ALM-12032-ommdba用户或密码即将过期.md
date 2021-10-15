# ALM-12032 ommdba用户或密码即将过期<a name="alm_12032"></a>

## 告警解释<a name="zh-cn_topic_0191813868_section50773295113227"></a>

系统每天零点开始，每8小时检测当前系统中**ommdba**用户和密码是否过期，如果用户或密码即将在15天内过期，则发送告警。

当系统中**ommdba**用户过期的期限修改或密码重置，且告警处理完成时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813868_section11603401113239"></a>

<a name="zh-cn_topic_0191813868_table19370806113018"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813868_row7991696113018"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813868_p43347674113018"><a name="zh-cn_topic_0191813868_p43347674113018"></a><a name="zh-cn_topic_0191813868_p43347674113018"></a><strong id="zh-cn_topic_0191813868_b54584753113018"><a name="zh-cn_topic_0191813868_b54584753113018"></a><a name="zh-cn_topic_0191813868_b54584753113018"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813868_p59288871113018"><a name="zh-cn_topic_0191813868_p59288871113018"></a><a name="zh-cn_topic_0191813868_p59288871113018"></a><strong id="zh-cn_topic_0191813868_b63837792113018"><a name="zh-cn_topic_0191813868_b63837792113018"></a><a name="zh-cn_topic_0191813868_b63837792113018"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813868_p3478635113018"><a name="zh-cn_topic_0191813868_p3478635113018"></a><a name="zh-cn_topic_0191813868_p3478635113018"></a><strong id="zh-cn_topic_0191813868_b31307719113018"><a name="zh-cn_topic_0191813868_b31307719113018"></a><a name="zh-cn_topic_0191813868_b31307719113018"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813868_row13334023113018"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813868_p6314075113018"><a name="zh-cn_topic_0191813868_p6314075113018"></a><a name="zh-cn_topic_0191813868_p6314075113018"></a>12032</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813868_p41678096113018"><a name="zh-cn_topic_0191813868_p41678096113018"></a><a name="zh-cn_topic_0191813868_p41678096113018"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813868_p20482638113018"><a name="zh-cn_topic_0191813868_p20482638113018"></a><a name="zh-cn_topic_0191813868_p20482638113018"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813868_section22985325113248"></a>

<a name="zh-cn_topic_0191813868_table33675420113018"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813868_row64277816113018"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813868_p39120632113018"><a name="zh-cn_topic_0191813868_p39120632113018"></a><a name="zh-cn_topic_0191813868_p39120632113018"></a><strong id="zh-cn_topic_0191813868_b16541374113018"><a name="zh-cn_topic_0191813868_b16541374113018"></a><a name="zh-cn_topic_0191813868_b16541374113018"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813868_p64782906113018"><a name="zh-cn_topic_0191813868_p64782906113018"></a><a name="zh-cn_topic_0191813868_p64782906113018"></a><strong id="zh-cn_topic_0191813868_b46175242113018"><a name="zh-cn_topic_0191813868_b46175242113018"></a><a name="zh-cn_topic_0191813868_b46175242113018"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813868_row12923994113018"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813868_p40210566113018"><a name="zh-cn_topic_0191813868_p40210566113018"></a><a name="zh-cn_topic_0191813868_p40210566113018"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813868_p35830439113018"><a name="zh-cn_topic_0191813868_p35830439113018"></a><a name="zh-cn_topic_0191813868_p35830439113018"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813868_row54038503113018"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813868_p15042642113018"><a name="zh-cn_topic_0191813868_p15042642113018"></a><a name="zh-cn_topic_0191813868_p15042642113018"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813868_p10494502113018"><a name="zh-cn_topic_0191813868_p10494502113018"></a><a name="zh-cn_topic_0191813868_p10494502113018"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813868_row27341654113018"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813868_p81497113018"><a name="zh-cn_topic_0191813868_p81497113018"></a><a name="zh-cn_topic_0191813868_p81497113018"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813868_p6601305113018"><a name="zh-cn_topic_0191813868_p6601305113018"></a><a name="zh-cn_topic_0191813868_p6601305113018"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813868_section52461929113258"></a>

**ommdba**用户或密码过期，OMS数据库无法管理，数据不能访问。

## 可能原因<a name="zh-cn_topic_0191813868_section4045493811333"></a>

系统**ommdb**a用户或密码即将过期。

## 处理步骤<a name="zh-cn_topic_0191813868_section38760256113311"></a>

1.  检查系统中**ommdba**用户和密码是否正常。
    1.  登录故障节点。
    2.  执行以下命令来查看当前**ommdba**用户密码设置信息：

        **chage -l ommdba**

    3.  检查系统提示信息，是否用户已过期。

        1.  查找“Password expires”对应值，查看密码设置是否即将过期。
        2.  查找“Account expires”对应值，查看用户设置是否即将过期。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >如果参数值为“never”，则代表永不过期；如果为日期值，则查看是否在15天内过期。

        -   是，执行[1.d](#zh-cn_topic_0191813868_li2310249112814)。
        -   否，执行[2](#zh-cn_topic_0191813868_li572522141314)。

    4.  <a name="zh-cn_topic_0191813868_li2310249112814"></a>执行以下命令修改过期设置。
        -   设置**ommdba**用户过期的期限：

            **chage -E** _'指定日期'_ **ommdba**

        -   设置ommdba密码的有效天数：

            **chage -M** _'天数'_ **ommdba**

    5.  等待下周期检测，观察告警是否自动清除。
        -   是，操作结束。
        -   否，执行[2](#zh-cn_topic_0191813868_li572522141314)。

2.  <a name="zh-cn_topic_0191813868_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## **参考信息**<a name="zh-cn_topic_0191813868_section13081136172452"></a>

无。

