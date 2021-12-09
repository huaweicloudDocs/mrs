# ALM-12078 omm密码过期<a name="ALM-12078"></a>

## 告警解释<a name="section14673296256"></a>

系统每天零点开始，每8小时检测当前系统中**omm**密码是否过期，如果密码过期，则发送告警。

当系统中**omm**密码过期的期限修改，当前状态为正常，告警恢复。

## 告警属性<a name="section28308296"></a>

<a name="table36969235"></a>
<table><thead align="left"><tr id="row42433012"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p14521914"><a name="p14521914"></a><a name="p14521914"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p35424385"><a name="p35424385"></a><a name="p35424385"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50802928"><a name="p50802928"></a><a name="p50802928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row21396528"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p55397225"><a name="p55397225"></a><a name="p55397225"></a>12078</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57990210"><a name="p57990210"></a><a name="p57990210"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66695395"><a name="p66695395"></a><a name="p66695395"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section53448080"></a>

<a name="table33617909"></a>
<table><thead align="left"><tr id="row23730911"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p43155662"><a name="p43155662"></a><a name="p43155662"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p5947729"><a name="p5947729"></a><a name="p5947729"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row375818153518"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row12004049"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p32803893"><a name="p32803893"></a><a name="p32803893"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p39869670"><a name="p39869670"></a><a name="p39869670"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row23282710"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p6851364"><a name="p6851364"></a><a name="p6851364"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18089651"><a name="p18089651"></a><a name="p18089651"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row28589139"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p34018885"><a name="p34018885"></a><a name="p34018885"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4066316"><a name="p4066316"></a><a name="p4066316"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section14442155121012"></a>

**omm**密码过期，Manager各节点互信不可用，无法对服务提供管理功能。

## 可能原因<a name="section1680794119457"></a>

**omm**密码过期。

## 处理步骤<a name="section145831149194519"></a>

**检查系统中omm密码是否过期。**

1.  以**root**用户登录集群故障节点，用户密码为安装前用户自定义，请咨询系统管理员。

    执行**chage -l omm**命令来查看当前**omm**用户密码设置信息。

2.  查找“Password expires”对应值，查看密码设置是否过期。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果参数值为“never”，则代表永不过期。

    -   是，执行[3](#li45820492455)。
    -   否，执行[4](#li105821649164519)。


1.  <a name="li45820492455"></a>执行**chage -M**_ '__天数' _**omm**命令设置**omm**密码的有效天数，等待8小时，观察告警是否自动清除。
    -   是，操作结束。
    -   否，执行[4](#li105821649164519)。


**收集故障信息。**

1.  <a name="li105821649164519"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“NodeAgent”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895847.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section183241356931"></a>

无。

