# ALM-12010 Manager主备节点间心跳中断<a name="ALM-12010"></a>

## 告警解释<a name="section61793540"></a>

当主Manager节点在7秒内没有收到备Manager节点的心跳信号时，产生该告警。

当主Manager节点收到备Manager节点的心跳信号后，告警恢复。

## 告警属性<a name="section19270953"></a>

<a name="table65740923"></a>
<table><thead align="left"><tr id="row10790349"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p1603095"><a name="p1603095"></a><a name="p1603095"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p62741861"><a name="p62741861"></a><a name="p62741861"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p48925984"><a name="p48925984"></a><a name="p48925984"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row3581743"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p21685755"><a name="p21685755"></a><a name="p21685755"></a>12010</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p11715691"><a name="p11715691"></a><a name="p11715691"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p9446887"><a name="p9446887"></a><a name="p9446887"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section39220857"></a>

<a name="table27000408"></a>
<table><thead align="left"><tr id="row41867263"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35805106"><a name="p35805106"></a><a name="p35805106"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p14532511"><a name="p14532511"></a><a name="p14532511"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row106581110164210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row36282732"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p53220161"><a name="p53220161"></a><a name="p53220161"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p15865799"><a name="p15865799"></a><a name="p15865799"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row8574468"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23443285"><a name="p23443285"></a><a name="p23443285"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19857964"><a name="p19857964"></a><a name="p19857964"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row44503948"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p48050020"><a name="p48050020"></a><a name="p48050020"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p66846388"><a name="p66846388"></a><a name="p66846388"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section17443395"></a>

如果主Manager进程异常，主备倒换无法进行，影响业务。

## 可能原因<a name="section22772834"></a>

-   主备Manager节点间链路异常。
-   节点名配置错误。
-   防火墙禁用端口。

## 处理步骤<a name="section3628918"></a>

**检查主备Manager服务器间的网络是否正常。**

1.  在FusionInsight Manager页面，选择“运维 \> 告警 \> 告警”，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，查看该告警的备Manager服务器（即Peer Manager）IP地址。
2.  以**root**用户登录主Manager服务器，用户密码为安装前用户自定义，请咨询系统管理员。管理节点的主备状态及对应IP地址可在FusionInsight Manager主机管理界面查看。
3.  执行**ping **_备Manager__心跳IP__地址_命令检查备Manager服务器是否可达。
    -   是，执行[6](#li689014735016)。
    -   否，执行[4](#li15540104812493)。

4.  <a name="li15540104812493"></a>联系网络管理员查看是否为网络故障。
    -   是，执行[5](#li1354284813492)。
    -   否，执行[6](#li689014735016)。

5.  <a name="li1354284813492"></a>修复网络故障，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#li689014735016)。


**检查节点名配置是否正确**。

1.  <a name="li689014735016"></a>进入软件安装目录。

    **cd /opt**

2.  查找主备节点的配置文件目录。

    **find -name hacom\_local.xml**

3.  进入workspace目录。

    **cd $\{BIGDATA\_HOME\}/om-server/OMS/workspace0/ha/local/hacom/conf/**

4.  使用**vim**命令打开hacom\_local.xml，查看local、peer节点配置是否正确，local配置主节点，peer配置备节点。
    -   是，执行[12](#li20248142255015)。
    -   否，执行[10](#li1789118717500)。

5.  <a name="li1789118717500"></a>修改hacom\_local.xml中主备节点的配置，修改完成后，按**Esc**回到命令模式，输入命令**:wq**保存退出。
6.  查看此告警信息是否自动清除。
    -   是，处理完毕。
    -   否，执行[12](#li20248142255015)。


**检查是否防火墙禁用端口。**

1.  <a name="li20248142255015"></a>执行命令**lsof -i :20012**查询主备节点的心跳端口是否打开，有查询结果说明端口已经开放，否则说明端口被防火墙禁用。
    -   是，执行[13](#li82481522105012)。
    -   否，执行[16](#li17435598171317)。

2.  <a name="li82481522105012"></a>执行命令**iptables -P INPUT ACCEPT**，防止与服务器断开。
3.  清除防火墙。

    **iptables -F**

4.  查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[16](#li17435598171317)。


**收集故障信息。**

1.  <a name="li17435598171317"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选如下节点信息，单击“确定”。
    -   OmmServer
    -   Controller
    -   NodeAgent

3.  单击右上角的![](figures/zh-cn_image_0263895607.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section32660264"></a>

无。

