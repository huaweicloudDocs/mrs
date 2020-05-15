# ALM-27004 DBService主备数据不同步<a name="ZH-CN_TOPIC_0191883117"></a>

## 告警解释<a name="zh-cn_topic_0191813894_section51489795"></a>

DBService主备数据不同步，每10秒检查一次主备数据同步状态，如果连续6次查不到同步状态，或者同步状态不正常，产生告警。

当同步状态正常，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813894_section60754972"></a>

<a name="zh-cn_topic_0191813894_table15697576"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813894_row32894845"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813894_p47236811"><a name="zh-cn_topic_0191813894_p47236811"></a><a name="zh-cn_topic_0191813894_p47236811"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813894_p976457"><a name="zh-cn_topic_0191813894_p976457"></a><a name="zh-cn_topic_0191813894_p976457"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813894_p11984159"><a name="zh-cn_topic_0191813894_p11984159"></a><a name="zh-cn_topic_0191813894_p11984159"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813894_row31192822"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813894_p43590645"><a name="zh-cn_topic_0191813894_p43590645"></a><a name="zh-cn_topic_0191813894_p43590645"></a>27004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813894_p41181381"><a name="zh-cn_topic_0191813894_p41181381"></a><a name="zh-cn_topic_0191813894_p41181381"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813894_p47357582"><a name="zh-cn_topic_0191813894_p47357582"></a><a name="zh-cn_topic_0191813894_p47357582"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813894_section9923843"></a>

<a name="zh-cn_topic_0191813894_table10758903"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813894_row49957660"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813894_p20038698"><a name="zh-cn_topic_0191813894_p20038698"></a><a name="zh-cn_topic_0191813894_p20038698"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813894_p12521852"><a name="zh-cn_topic_0191813894_p12521852"></a><a name="zh-cn_topic_0191813894_p12521852"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813894_row7637115"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p14626574"><a name="zh-cn_topic_0191813894_p14626574"></a><a name="zh-cn_topic_0191813894_p14626574"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p43901854"><a name="zh-cn_topic_0191813894_p43901854"></a><a name="zh-cn_topic_0191813894_p43901854"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813894_row59572368"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p60632485"><a name="zh-cn_topic_0191813894_p60632485"></a><a name="zh-cn_topic_0191813894_p60632485"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p12284267"><a name="zh-cn_topic_0191813894_p12284267"></a><a name="zh-cn_topic_0191813894_p12284267"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813894_row43449544"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p29752153"><a name="zh-cn_topic_0191813894_p29752153"></a><a name="zh-cn_topic_0191813894_p29752153"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p61114224"><a name="zh-cn_topic_0191813894_p61114224"></a><a name="zh-cn_topic_0191813894_p61114224"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813894_row13157104"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p59092488"><a name="zh-cn_topic_0191813894_p59092488"></a><a name="zh-cn_topic_0191813894_p59092488"></a>Local DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p21762200"><a name="zh-cn_topic_0191813894_p21762200"></a><a name="zh-cn_topic_0191813894_p21762200"></a>本地DBService HA名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813894_row61642077"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p26952341"><a name="zh-cn_topic_0191813894_p26952341"></a><a name="zh-cn_topic_0191813894_p26952341"></a>Peer DBService HA Name</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p35656026"><a name="zh-cn_topic_0191813894_p35656026"></a><a name="zh-cn_topic_0191813894_p35656026"></a>对端DBService HA名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813894_row52468780"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813894_p22112815"><a name="zh-cn_topic_0191813894_p22112815"></a><a name="zh-cn_topic_0191813894_p22112815"></a>SYNC_PERSENT</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813894_p46307570"><a name="zh-cn_topic_0191813894_p46307570"></a><a name="zh-cn_topic_0191813894_p46307570"></a>同步百分比。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813894_section22205728"></a>

主备DBServer数据不同步，如果此时主实例异常，则会出现数据丢失或者数据异常的情况。

## 可能原因<a name="zh-cn_topic_0191813894_section65633828"></a>

-   主备节点网络不稳定。
-   备DBService异常。
-   备节点磁盘空间满。

## 处理步骤<a name="zh-cn_topic_0191813894_section53833544"></a>

1.  检查主备节点网络是否正常。
    1.  登录MRS集群详情页面，选择“告警管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请登录MRS Manager页面，选择“告警管理”。  

    2.  在告警列表中单击此告警所在行，在告警详情中查看该告警的DBService备节点IP地址。
    3.  登录主DBService节点。
    4.  执行**ping** _备DBService__心跳IP__地址_命令检查备DBService节点是否可达。
        -   是，执行[2.a](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step6)。
        -   否，执行[1.e](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step2)。

    5.  <a name="zh-cn_topic_0191813894_alm-27002_3_mmccppss_step2"></a>联系运维人员查看是否为网络故障。
        -   是，执行[1.f](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_s4)。
        -   否，执行[2.a](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step6)。

    6.  <a name="zh-cn_topic_0191813894_alm-27002_3_mmccppss_s4"></a>修复网络故障，查看告警列表中，该告警是否已清除。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step6)。

2.  检查备DBService状态是否正常
    1.  <a name="zh-cn_topic_0191813894_alm-27002_3_mmccppss_step6"></a>登录备DBService节点。
    2.  执行以下命令切换用户：

        **sudo su - root**

        **su - omm**

    3.  进入“$\{DBSERVER\_HOME\}/sbin”目录，然后执行命令**./status-dbserver.sh**  检查备DBService的gaussDB资源状态是否正常，查看回显中，“ResName”为“gaussDB”的一行，是否显示如下信息：

        例如：

        ```
        10_10_10_231 gaussDB Standby_normal Normal Active_standby
        ```

        -   是，执行[3.a](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step9)。
        -   否，执行[4](#zh-cn_topic_0191813894_li572522141314)。

3.  检查备节点磁盘是否已满。
    1.  <a name="zh-cn_topic_0191813894_alm-27002_3_mmccppss_step9"></a>登录备DBService节点。
    2.  执行以下命令切换用户：

        **sudo su - root**

        **su - omm**

    3.  进入“$\{DBSERVER\_HOME\}”目录，执行以下命令获取DBservice的数据目录。

        **cd $\{DBSERVER\_HOME\}**

        **source .dbservice\_profile**

        **echo $\{DBSERVICE\_DATA\_DIR\}**

    4.  执行**df -h**命令，查看系统磁盘分区的使用信息。
    5.  查看DBservice数据目录空间是否已满。
        -   是，执行[3.f](#zh-cn_topic_0191813894_alm-27002_3_mmccppss_step14)。
        -   否，执行[4](#zh-cn_topic_0191813894_li572522141314)。

    6.  <a name="zh-cn_topic_0191813894_alm-27002_3_mmccppss_step14"></a>扩容升级。
    7.  磁盘扩容后，等待2分钟检查告警是否清除。
        -   是，操作结束。
        -   否，执行[4](#zh-cn_topic_0191813894_li572522141314)。

4.  <a name="zh-cn_topic_0191813894_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813894_section14739853"></a>

无。

