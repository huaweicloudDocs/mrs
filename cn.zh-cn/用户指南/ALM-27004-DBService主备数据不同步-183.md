# ALM-27004 DBService主备数据不同步<a name="ALM-27004"></a>

## 告警解释<a name="section37190527"></a>

DBService主备数据不同步，每10秒检查一次主备数据同步状态，如果连续6次查不到同步状态，或者同步状态不正常，产生告警。

当同步状态正常，告警恢复。

## 告警属性<a name="section66279288"></a>

<a name="table29540708"></a>
<table><thead align="left"><tr id="row31592057"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p8819847"><a name="p8819847"></a><a name="p8819847"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p43318981"><a name="p43318981"></a><a name="p43318981"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p19176539"><a name="p19176539"></a><a name="p19176539"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row9795826"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p55264433"><a name="p55264433"></a><a name="p55264433"></a>27004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p47234113"><a name="p47234113"></a><a name="p47234113"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p757962"><a name="p757962"></a><a name="p757962"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section59642687"></a>

<a name="table61394931"></a>
<table><thead align="left"><tr id="row21339512"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p50778950"><a name="p50778950"></a><a name="p50778950"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p19454296"><a name="p19454296"></a><a name="p19454296"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5810182811216"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row32294167"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19348922"><a name="p19348922"></a><a name="p19348922"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row39922572"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p6100455"><a name="p6100455"></a><a name="p6100455"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row54904100"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p52528460"><a name="p52528460"></a><a name="p52528460"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row2994092"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41194884"><a name="p41194884"></a><a name="p41194884"></a>Local DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p48451284"><a name="p48451284"></a><a name="p48451284"></a>本地DBService HA名称。</p>
</td>
</tr>
<tr id="row33408377"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p21724017"><a name="p21724017"></a><a name="p21724017"></a>Peer DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p14814966"><a name="p14814966"></a><a name="p14814966"></a>对端DBService HA名称。</p>
</td>
</tr>
<tr id="row66225832"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p62692203"><a name="p62692203"></a><a name="p62692203"></a>SYNC_PERCENT</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p44903662"><a name="p44903662"></a><a name="p44903662"></a>同步百分比。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section67022140"></a>

主备DBServer数据不同步，如果此时主实例异常，则会出现数据丢失或者数据异常的情况。

## 可能原因<a name="section66328352"></a>

-   主备节点网络不稳定。
-   备DBService异常。
-   备节点磁盘空间满。

## 处理步骤<a name="section60084260"></a>

**检查主备节点网络是否正常。**

1.  在FusionInsight Manager页面，选择“运维 \> 告警 \> 告警”，在告警列表中单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，查看该告警的DBService备节点IP地址。
2.  以**root**用户登录主DBService节点，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行**ping **_备DBService__心跳IP__地址_命令检查备DBService节点是否可达。
    -   是，执行[6](#li49080712143446)。
    -   否，执行[4](#li40736781143446)。

4.  <a name="li40736781143446"></a>联系网络管理员查看是否为网络故障。
    -   是，执行[5](#li10547988143446)。
    -   否，执行[6](#li49080712143446)。

5.  <a name="li10547988143446"></a>修复网络故障，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#li49080712143446)。


**检查备DBService状态是否正常**

1.  <a name="li49080712143446"></a>以**root**用户登录备DBService节点。
2.  执行**su - omm**命令切换到**omm**用户。
3.  进入“$\{DBSERVER\_HOME\}/sbin”目录，然后执行命令** ./status-dbserver.sh **检查备DBService的gaussDB资源状态是否正常，查看回显中，“ResName”为“gaussDB”的一行，是否显示如下信息：

    例如：

    ```
    10_10_10_231 gaussDB Standby_normal Normal Active_standby
    ```

    -   是，执行[9](#li34334253143446)。
    -   否，执行[16](#li3592590143446)。


**检查备节点磁盘是否已满。**

1.  <a name="li34334253143446"></a>以**root**用户登录备DBService节点。
2.  执行命令**su - omm**切换到**omm**用户。
3.  进入“$\{DBSERVER\_HOME\}”目录，执行以下命令获取DBservice的数据目录。

    **cd $\{DBSERVER\_HOME\}**

    **source .dbservice\_profile**

    **echo $\{DBSERVICE\_DATA\_DIR\}**

4.  执行**df -h**命令，查看系统磁盘分区的使用信息。
5.  查看DBservice数据目录空间是否已满。
    -   是，执行[14](#li12947086143446)。
    -   否，执行[16](#li3592590143446)。

6.  <a name="li12947086143446"></a>对节点磁盘进行扩容。
7.  磁盘扩容后，等待2分钟检查告警是否清除。
    -   是，操作结束。
    -   否，执行[16](#li3592590143446)。


**收集故障信息。**

1.  <a name="li3592590143446"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“DBService”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895392.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section3887433"></a>

无。

