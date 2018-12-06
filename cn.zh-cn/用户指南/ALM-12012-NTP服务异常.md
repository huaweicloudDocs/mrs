# ALM-12012 NTP服务异常<a name="ZH-CN_TOPIC_0093195028"></a>

## 告警解释<a name="zh-cn_topic_0035461638_section43607363172441"></a>

当节点NTP服务无法与主OMS节点NTP服务正常同步时间时产生该告警。

当节点NTP服务与主OMS节点NTP服务正常同步时间时恢复该告警。

## 告警属性<a name="zh-cn_topic_0035461638_section1266102017250"></a>

<a name="zh-cn_topic_0035461638_table602057071263"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035461638_row102559131263"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035461638_p343074211263"><a name="zh-cn_topic_0035461638_p343074211263"></a><a name="zh-cn_topic_0035461638_p343074211263"></a><strong id="zh-cn_topic_0035461638_b575573101263"><a name="zh-cn_topic_0035461638_b575573101263"></a><a name="zh-cn_topic_0035461638_b575573101263"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035461638_p105814441263"><a name="zh-cn_topic_0035461638_p105814441263"></a><a name="zh-cn_topic_0035461638_p105814441263"></a><strong id="zh-cn_topic_0035461638_b52863871263"><a name="zh-cn_topic_0035461638_b52863871263"></a><a name="zh-cn_topic_0035461638_b52863871263"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035461638_p214780531263"><a name="zh-cn_topic_0035461638_p214780531263"></a><a name="zh-cn_topic_0035461638_p214780531263"></a><strong id="zh-cn_topic_0035461638_b487076501263"><a name="zh-cn_topic_0035461638_b487076501263"></a><a name="zh-cn_topic_0035461638_b487076501263"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035461638_row551545991263"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035461638_p646357441263"><a name="zh-cn_topic_0035461638_p646357441263"></a><a name="zh-cn_topic_0035461638_p646357441263"></a>12012</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035461638_p298423611263"><a name="zh-cn_topic_0035461638_p298423611263"></a><a name="zh-cn_topic_0035461638_p298423611263"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035461638_p433034491263"><a name="zh-cn_topic_0035461638_p433034491263"></a><a name="zh-cn_topic_0035461638_p433034491263"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035461638_section3372054217259"></a>

<a name="zh-cn_topic_0035461638_table91987361263"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035461638_row189395241263"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035461638_p668658261263"><a name="zh-cn_topic_0035461638_p668658261263"></a><a name="zh-cn_topic_0035461638_p668658261263"></a><strong id="zh-cn_topic_0035461638_b377013241263"><a name="zh-cn_topic_0035461638_b377013241263"></a><a name="zh-cn_topic_0035461638_b377013241263"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035461638_p146874361263"><a name="zh-cn_topic_0035461638_p146874361263"></a><a name="zh-cn_topic_0035461638_p146874361263"></a><strong id="zh-cn_topic_0035461638_b323493561263"><a name="zh-cn_topic_0035461638_b323493561263"></a><a name="zh-cn_topic_0035461638_b323493561263"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035461638_row219579991263"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461638_p356185261263"><a name="zh-cn_topic_0035461638_p356185261263"></a><a name="zh-cn_topic_0035461638_p356185261263"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461638_p549782411263"><a name="zh-cn_topic_0035461638_p549782411263"></a><a name="zh-cn_topic_0035461638_p549782411263"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035461638_row85896551263"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461638_p662404731263"><a name="zh-cn_topic_0035461638_p662404731263"></a><a name="zh-cn_topic_0035461638_p662404731263"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461638_p365850281263"><a name="zh-cn_topic_0035461638_p365850281263"></a><a name="zh-cn_topic_0035461638_p365850281263"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035461638_row647122371263"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035461638_p89268291263"><a name="zh-cn_topic_0035461638_p89268291263"></a><a name="zh-cn_topic_0035461638_p89268291263"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035461638_p367579931263"><a name="zh-cn_topic_0035461638_p367579931263"></a><a name="zh-cn_topic_0035461638_p367579931263"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035461638_section43557444172517"></a>

该节点的时间与集群其它节点的时间不同步，可能会导致该节点上的某些MRS应用无法正常运行。

## 可能原因<a name="zh-cn_topic_0035461638_section11916493172522"></a>

-   该节点的NTP服务无法正常启动。
-   该节点与主OMS节点NTP服务不能正常同步时间。
-   该节点NTP认证的key值与主OMS节点NTP服务的key值不一致。
-   该节点与主OMS节点NTP服务时间偏差太大。

## 处理步骤<a name="zh-cn_topic_0035461638_section25927826172547"></a>

1.  检查该节点的NTP服务是否正常启动。
    1.  检查ntpd进程是否运行在告警节点上。登录告警节点，执行**sudo su - root**切换用户。执行以下命令，检查命令是否输出ntpd进程的信息。

        **ps -ef | grep ntpd | grep -v grep**

        -   是，执行[2.a](#zh-cn_topic_0035461638_li64213271174322)。
        -   否，执行[1.b](#zh-cn_topic_0035461638_li6445073917350)。

    2.  <a name="zh-cn_topic_0035461638_li6445073917350"></a>执行**service ntp start**启动NTP服务。
    3.  10分钟后，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0035461638_li64213271174322)。


2.  检查该节点与主OMS节点NTP服务是否正常同步时间。
    1.  <a name="zh-cn_topic_0035461638_li64213271174322"></a>查看NTP告警的“附加信息”是否描述与主OMS节点NTP服务无法同步时间。

        是，执行[2.b](#zh-cn_topic_0035461638_li14178567173544)。

        否，执行[3](#zh-cn_topic_0035461638_li65673991173316)。

    2.  <a name="zh-cn_topic_0035461638_li14178567173544"></a>排查与主OMS节点NTP服务的同步是否有问题。

        登录告警节点执行**sudo su - root**切换用户，执行**ntpq -np**命令。

        如果显示结果的主OMS节点NTP服务IP地址前有“\*”号，表示同步正常，如下：

        ```
        remote refid st t when poll reach delay offset jitter
        ==============================================================================
        *10.10.10.162 .LOCL. 1 u 1 16 377 0.270 -1.562 0.014
        ```

        如果显示结果的主OMS节点NTP服务IP前无“\*”号，且“refid”项内容为“.INIT.”，表示同步不正常。

        ```
        remote refid st t when poll reach delay offset jitter
        ==============================================================================
        10.10.10.162 .INIT. 1 u 1 16 377 0.270 -1.562 0.014
        ```

        -   是，执行[2.c](#zh-cn_topic_0035461638_li25713785173557)。
        -   否，执行[3](#zh-cn_topic_0035461638_li65673991173316)。

    3.  <a name="zh-cn_topic_0035461638_li25713785173557"></a>处理对应问题，问题解决后等待10分钟，检查该告警是否恢复。

        NTP不能正常同步，通常与系统防火墙有关：如果能关闭防火墙，建议尝试关闭防火墙后查看问题能否解决；如果不能关闭防火墙，请检查防火墙配置策略，确保**UDP 123**端口未禁用（具体遵循各系统下防火墙配置策略）。

        -   是，处理完毕。
        -   否，执行[3](#zh-cn_topic_0035461638_li65673991173316)。


3.  <a name="zh-cn_topic_0035461638_li65673991173316"></a>检查该节点NTP认证的key值与主OMS节点NTP服务的key值是否相同。

    执行**cat** **/etc/ntp.keys**查看key值索引号为1的认证码是否与主OMS节点NTP服务的值相同。

    -   是，执行[4.a](#zh-cn_topic_0035461638_li50308011174636)。
    -   否，执行[5](#zh-cn_topic_0035461638_li37670922173038)。

4.  检查该节点与主OMS节点NTP服务时间偏差是否太大。
    1.  <a name="zh-cn_topic_0035461638_li50308011174636"></a>NTP告警的“附加信息”是否描述时间偏差（time offset）太大。
        -   是，执行[4.b](#zh-cn_topic_0035461638_li25272675173633)。
        -   否，执行[5](#zh-cn_topic_0035461638_li37670922173038)。

    2.  <a name="zh-cn_topic_0035461638_li25272675173633"></a>在“主机管理”页面，勾选告警节点的主机，选择“更多 \> 停止所有角色”停止告警节点的所有服务。

        如果告警节点时间比主OMS节点NTP服务时间慢，校正告警节点的系统时间。校正告警节点的系统时间后，选择“更多 \> 启动所有角色”启动告警节点的服务。

        如果告警节点时间比主OMS节点NTP服务时间快，等待相应时间差，校正告警节点的系统时间。校正完成后，选择“更多 \> 启动所有角色”启动告警节点的服务。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果不做相应等待，可能造成数据丢失风险。  

    3.  10分钟后，检查该告警是否恢复。
        -   是，处理完毕。
        -   否，执行[5](#zh-cn_topic_0035461638_li37670922173038)。


5.  <a name="zh-cn_topic_0035461638_li37670922173038"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系公有云运维人员，并发送已收集的故障日志信息。


## **参考信息**<a name="zh-cn_topic_0035461638_section13081136172452"></a>

无。

