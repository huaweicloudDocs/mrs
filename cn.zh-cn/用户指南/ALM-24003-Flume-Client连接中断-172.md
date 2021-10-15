# ALM-24003 Flume Client连接中断<a name="ALM-24003"></a>

## 告警解释<a name="section22611353"></a>

告警模块对Flume Server的连接端口状态进行监控。当Flume Client连接到Flume Server的某个端口，Client端连续3分钟未与Server端连接时，系统产生此告警。

当Flume Server收到Flume Client连接消息，告警恢复。

## 告警属性<a name="section2175586"></a>

<a name="table10055771"></a>
<table><thead align="left"><tr id="row36105076"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p38830026"><a name="p38830026"></a><a name="p38830026"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p58224438"><a name="p58224438"></a><a name="p58224438"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p18559005"><a name="p18559005"></a><a name="p18559005"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row26884457"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p30157442"><a name="p30157442"></a><a name="p30157442"></a>24003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p26833743"><a name="p26833743"></a><a name="p26833743"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p26049593"><a name="p26049593"></a><a name="p26049593"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section19580282"></a>

<a name="table29642279"></a>
<table><thead align="left"><tr id="row13573308"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p25696133"><a name="p25696133"></a><a name="p25696133"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p1011990"><a name="p1011990"></a><a name="p1011990"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1817164191617"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row14862360"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1776739171815"><a name="p1776739171815"></a><a name="p1776739171815"></a>客户端IP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2766733"><a name="p2766733"></a><a name="p2766733"></a>Flume客户端IP地址。</p>
</td>
</tr>
<tr id="row24900602"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p11359565193"><a name="p11359565193"></a><a name="p11359565193"></a>客户端名称</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p29879884"><a name="p29879884"></a><a name="p29879884"></a>Flume客户端的Agent名称。</p>
</td>
</tr>
<tr id="row483505"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p368651311195"><a name="p368651311195"></a><a name="p368651311195"></a>sink名称</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p18162067"><a name="p18162067"></a><a name="p18162067"></a>Flume Agent的sink名称。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section42004817"></a>

产生告警的Flume Client无法与Flume Server端进行通信，Flume Client端的数据无法传输到Flume Server端。

## 可能原因<a name="section42499041"></a>

-   Flume Client端与Flume Server端网络故障。
-   Flume Client端进程故障。
-   Flume Client端配置错误。

## 处理步骤<a name="section46947049"></a>

**检查Flume Client与Flume Server的网络状况。**

1.  以**root**用户登录到告警定位参数中描述的Flume ClientIP所在主机，用户密码为安装前用户自定义，请咨询系统管理员。
2.  执行**ping **_Flume Server IP__地址_命令，检查Flume Client到Flume Server的网络是否正常。
    -   是，执行[3](#li331072891100)。
    -   否，执行[11](#li228207951100)。


**检查Flume Client端进程故障。**

1.  <a name="li331072891100"></a>以**root**用户登录到告警定位参数中描述的Flume ClientIP所在主机。
2.  执行**ps -ef|grep flume |grep client**命令，查看是否存在Flume Client进程。
    -   是，执行[5](#li540399381100)。
    -   否，执行[11](#li228207951100)。


**检查Flume Client端的配置。**

1.  <a name="li540399381100"></a>以**root**用户登录到告警定位参数中描述的Flume ClientIP所在主机。
2.  执行**cd **_Flume客户端__安装目录_**/fusioninsight-flume-1.9.0/conf/**命令，进入Flume的配置目录。
3.  执行**cat properties.properties**命令，查看当前的Flume Client配置文件。
4.  根据Flume Agent的配置说明检查“properties.properties”的配置是否有误。
    -   是，执行[9](#li636773281100)。
    -   否，执行[11](#li228207951100)。

5.  <a name="li636773281100"></a>修改“properties.properties”配置文件。

**查看告警是否已清除。**

1.  查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[11](#li228207951100)。


**收集故障信息。**

1.  <a name="li228207951100"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”框中勾选待操作集群的“Flume”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  使用传输工具，收集Flume Client端“/var/log/Bigdata/flume-client”下的日志。
5.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19870259"></a>

无。

