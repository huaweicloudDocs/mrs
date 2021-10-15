# ALM-13001 ZooKeeper可用连接数不足<a name="ALM-13001"></a>

## 告警解释<a name="section66880084"></a>

系统每60秒周期性检测ZooKeeper服务连接数状态，当检测到ZooKeeper实例连接数超出阈值（最大连接数的80%）时产生该告警。

平滑次数为1，ZooKeeper可用连接数小于或等于阈值时，告警恢复；平滑次数大于1，ZooKeeper可用连接数小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section65049850"></a>

<a name="table56775870"></a>
<table><thead align="left"><tr id="row7891871"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p35261838"><a name="p35261838"></a><a name="p35261838"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p37636625"><a name="p37636625"></a><a name="p37636625"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p28667793"><a name="p28667793"></a><a name="p28667793"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row40389877"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p50354598"><a name="p50354598"></a><a name="p50354598"></a>13001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p52190603"><a name="p52190603"></a><a name="p52190603"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p66689292"><a name="p66689292"></a><a name="p66689292"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section48577742"></a>

<a name="table33123603"></a>
<table><thead align="left"><tr id="row27794227"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p36739924"><a name="p36739924"></a><a name="p36739924"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p23143869"><a name="p23143869"></a><a name="p23143869"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5210193243314"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p864542418105"><a name="p864542418105"></a><a name="p864542418105"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row62714135"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p22999997"><a name="p22999997"></a><a name="p22999997"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row5673382"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p44750504"><a name="p44750504"></a><a name="p44750504"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row101352"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p60996347"><a name="p60996347"></a><a name="p60996347"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row12096212"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p40269121"><a name="p40269121"></a><a name="p40269121"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p40573387"><a name="p40573387"></a><a name="p40573387"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section34546497"></a>

ZooKeeper可用连接数不足，当连接率超过100%时无法处理外部连接。

## 可能原因<a name="section42483020"></a>

该节点ZooKeeper连接量过大，超过阈值。某些连接进程存在连接泄露，或配置的最大连接数不符合实际使用场景。

## 处理步骤<a name="section46802864"></a>

**检查连接状态。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，单击告警“ZooKeeper可用连接数不足”所在行的下拉菜单，在定位信息中确认告警上报的主机名所在的节点IP地址。
2.  获取ZooKeeper进程pid。以**root**用户登录到告警上报的节点，用户密码为安装前用户自定义，请咨询系统管理员，执行命令：**pgrep -f proc\_zookeeper**。
3.  是否正常获取pid。
    -   是，执行[4](#li4771552716024)。
    -   否，执行[15](#li3558651916024)。

4.  <a name="li4771552716024"></a>获取所有与当前ZooKeeper实例连接的IP及连接数量，取连接数最多的前十个进行检查。根据获取到的pid值，执行命令**lsof -i|grep **_$pid_** | awk '\{print $9\}' | cut -d : -f 2 | cut -d \\\> -f 2 | awk '\{a\[$1\]++\} END \{for\(i in a\)\{print i,a\[i\] | "sort -r -g -k 2"\}\}' | head -10 **。（$pid为上一步获取的pid值）
5.  获取节点IP与连接数是否成功。
    -   是，执行[6](#li3591731816024)。
    -   否，执行[15](#li3558651916024)。

6.  <a name="li3591731816024"></a>获取连接进程的端口号。根据获取到的pid与IP值，执行命令**lsof -i|grep **_$pid_** | awk '\{print $9\}'|cut -d \\\> -f 2 |grep **_$IP_**| cut -d : -f 2 **。（$pid与$IP为上一步获取的pid值与IP值）
7.  获取端口号port成功。
    -   是，执行[8](#li5425953216024)。
    -   否，执行[15](#li3558651916024)。

8.  <a name="li5425953216024"></a>获取连接进程的进程号。依次登录到各IP，根据获取到的port号，执行命令**lsof -i|grep **_$port_。（$port为上一步获取端口号）
9.  获取进程号成功。
    -   是，执行[10](#li6614378116024)。
    -   否，执行[15](#li3558651916024)。

10. <a name="li6614378116024"></a>根据获取到的进程号，查看进程是否存在连接泄露。
    -   是，执行[11](#li5540288416024)。
    -   否，执行[12](#li2886390916024)。

11. <a name="li5540288416024"></a>将存在连接泄露的进程关掉，观察界面上告警是否消除。
    -   是，处理完毕。
    -   否，执行[12](#li2886390916024)。

12. <a name="li2886390916024"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> 配置 \> 全部配置 \> quorumpeer \> 性能”中，将“maxCnxns”的值根据实际情况调大。

    **图 1**  maxCnxns<a name="fig16445154511377"></a>  
    ![](figures/maxCnxns.png "maxCnxns")

13. 保存配置，并重启ZooKeeper服务。
14. 界面上告警是否消除。
    -   是，处理完毕。
    -   否，执行[15](#li3558651916024)。


**收集故障信息。**

1.  <a name="li3558651916024"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“ZooKeeper”。
3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section18572599"></a>

无。

