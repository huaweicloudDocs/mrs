# ALM-12027 主机PID使用率超过阈值<a name="ZH-CN_TOPIC_0093195032"></a>

## 告警解释<a name="zh-cn_topic_0035509085_section632130571149"></a>

系统每30秒周期性检测PID使用率，并把实际PID使用率和阈值进行比较，PID使用率默认提供一个阈值。当检测到PID使用率超出阈值时产生该告警。

当主机PID使用率小于或等于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0035509085_section6029023311419"></a>

<a name="zh-cn_topic_0035509085_table11806311142"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035509085_row351915821142"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035509085_p319458681142"><a name="zh-cn_topic_0035509085_p319458681142"></a><a name="zh-cn_topic_0035509085_p319458681142"></a><strong id="zh-cn_topic_0035509085_b190773561142"><a name="zh-cn_topic_0035509085_b190773561142"></a><a name="zh-cn_topic_0035509085_b190773561142"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035509085_p17620221142"><a name="zh-cn_topic_0035509085_p17620221142"></a><a name="zh-cn_topic_0035509085_p17620221142"></a><strong id="zh-cn_topic_0035509085_b158582011142"><a name="zh-cn_topic_0035509085_b158582011142"></a><a name="zh-cn_topic_0035509085_b158582011142"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035509085_p94458961142"><a name="zh-cn_topic_0035509085_p94458961142"></a><a name="zh-cn_topic_0035509085_p94458961142"></a><strong id="zh-cn_topic_0035509085_b179042071142"><a name="zh-cn_topic_0035509085_b179042071142"></a><a name="zh-cn_topic_0035509085_b179042071142"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035509085_row269201361142"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035509085_p330474251142"><a name="zh-cn_topic_0035509085_p330474251142"></a><a name="zh-cn_topic_0035509085_p330474251142"></a>12027</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035509085_p595957381142"><a name="zh-cn_topic_0035509085_p595957381142"></a><a name="zh-cn_topic_0035509085_p595957381142"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035509085_p625254351142"><a name="zh-cn_topic_0035509085_p625254351142"></a><a name="zh-cn_topic_0035509085_p625254351142"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035509085_section6327235611426"></a>

<a name="zh-cn_topic_0035509085_table141237671142"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035509085_row325219741142"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035509085_p170342011142"><a name="zh-cn_topic_0035509085_p170342011142"></a><a name="zh-cn_topic_0035509085_p170342011142"></a><strong id="zh-cn_topic_0035509085_b190900891142"><a name="zh-cn_topic_0035509085_b190900891142"></a><a name="zh-cn_topic_0035509085_b190900891142"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035509085_p27933851142"><a name="zh-cn_topic_0035509085_p27933851142"></a><a name="zh-cn_topic_0035509085_p27933851142"></a><strong id="zh-cn_topic_0035509085_b251404671142"><a name="zh-cn_topic_0035509085_b251404671142"></a><a name="zh-cn_topic_0035509085_b251404671142"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035509085_row249376131142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035509085_p66807661142"><a name="zh-cn_topic_0035509085_p66807661142"></a><a name="zh-cn_topic_0035509085_p66807661142"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035509085_p42711391142"><a name="zh-cn_topic_0035509085_p42711391142"></a><a name="zh-cn_topic_0035509085_p42711391142"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035509085_row384402521142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035509085_p266527471142"><a name="zh-cn_topic_0035509085_p266527471142"></a><a name="zh-cn_topic_0035509085_p266527471142"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035509085_p113889311142"><a name="zh-cn_topic_0035509085_p113889311142"></a><a name="zh-cn_topic_0035509085_p113889311142"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035509085_row353915171142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035509085_p481406441142"><a name="zh-cn_topic_0035509085_p481406441142"></a><a name="zh-cn_topic_0035509085_p481406441142"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035509085_p70781201142"><a name="zh-cn_topic_0035509085_p70781201142"></a><a name="zh-cn_topic_0035509085_p70781201142"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035509085_row637030841142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035509085_p596761811142"><a name="zh-cn_topic_0035509085_p596761811142"></a><a name="zh-cn_topic_0035509085_p596761811142"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035509085_p19325271142"><a name="zh-cn_topic_0035509085_p19325271142"></a><a name="zh-cn_topic_0035509085_p19325271142"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035509085_section5636648011439"></a>

无法分配PID给新的业务进程，业务进程不可用。

## 可能原因<a name="zh-cn_topic_0035509085_section2852316511444"></a>

节点同时运行的进程过多，需要扩展“pid\_max“值。 系统环境异常。

## 处理步骤<a name="zh-cn_topic_0035509085_section5453629511452"></a>

1.  扩展pid\_max值。
    1.  打开MRS Manager页面，在实时告警列表中，单击此告警。在“告警详情”区域，获取告警所在主机IP地址。
    2.  登录告警节点。
    3.  执行命令**cat /proc/sys/kernel/pid\_max**，查看系统当前运行的PID最大值“pid\_max“。
    4.  若PID使用率超过阈值，将pid\_max值增大一倍，执行命令：

        **echo** _新pid\_max值_ **\> /proc/sys/kernel/pid\_max**

        例如：

        **echo 65536 \> /proc/sys/kernel/pid\_max**

    5.  等待5分钟，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0035509085_li6558431911107)。


2.  <a name="zh-cn_topic_0035509085_li6558431911107"></a>检查系统环境是否异常。
    1.  联系公有云运维人员，检查操作系统是否存在异常。
        -   是，恢复操作系统故障，执行[2.b](#zh-cn_topic_0035509085_li48344862111230)。
        -   否，执行[3](#zh-cn_topic_0035509085_li6127286143922)。

    2.  <a name="zh-cn_topic_0035509085_li48344862111230"></a>等待5分钟，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0035509085_li6127286143922)。


3.  <a name="zh-cn_topic_0035509085_li6127286143922"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## **参考信息**<a name="zh-cn_topic_0035509085_section13081136172452"></a>

无。

