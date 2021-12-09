# ALM-12039 OMS数据库主备不同步<a name="ALM-12039"></a>

## 告警解释<a name="section53376559"></a>

OMS数据库主备不同步，系统每10秒检查一次主备数据同步状态，如果连续30次查不到同步状态，或者同步状态异常，产生告警。

当主备数据同步状态正常，告警恢复。

## 告警属性<a name="section10626988"></a>

<a name="table34025664"></a>
<table><thead align="left"><tr id="row15521143"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p49253045"><a name="p49253045"></a><a name="p49253045"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p30073675"><a name="p30073675"></a><a name="p30073675"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p20048610"><a name="p20048610"></a><a name="p20048610"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row13324705"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p5559345"><a name="p5559345"></a><a name="p5559345"></a>12039</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p47653818"><a name="p47653818"></a><a name="p47653818"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p34754019"><a name="p34754019"></a><a name="p34754019"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section28534032"></a>

<a name="table63612116"></a>
<table><thead align="left"><tr id="row14526902"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p35828424"><a name="p35828424"></a><a name="p35828424"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p16421255"><a name="p16421255"></a><a name="p16421255"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row5811123323918"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row55053274"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p30130218"><a name="p30130218"></a><a name="p30130218"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p24628574"><a name="p24628574"></a><a name="p24628574"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row20330577"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p36164055"><a name="p36164055"></a><a name="p36164055"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43607349"><a name="p43607349"></a><a name="p43607349"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row56921829"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p47265468"><a name="p47265468"></a><a name="p47265468"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p3297662"><a name="p3297662"></a><a name="p3297662"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55479700"></a>

OMS数据库主备不同步，如果此时主实例异常，会出现数据丢失或者数据异常的情况。

## 可能原因<a name="section29555257"></a>

-   主备节点网络不稳定。
-   备OMS数据库异常。
-   备节点磁盘空间满。

## 处理步骤<a name="section64670729"></a>

**检查主备节点网络是否正常。**

1.  在FusionInsight Manager界面上选择“运维 \> 告警 \> 告警”，在告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，查看该告警的OMS数据库备节点IP地址。
2.  以**root**用户登录主OMS数据库节点，用户密码为安装前用户自定义，请咨询系统管理员。
3.  执行**ping **_备OMS数据库__心跳IP__地址_命令检查备OMS数据库节点是否可达。
    -   是，执行[6](#li4022101310471)。
    -   否，执行[4](#li4974773510471)。

4.  <a name="li4974773510471"></a>联系网络管理员查看是否为网络故障。
    -   是，执行[5](#li4689280710471)。
    -   否，执行[6](#li4022101310471)。

5.  <a name="li4689280710471"></a>修复网络故障，然后查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#li4022101310471)。


**检查备OMS数据库状态是否正常。**

1.  <a name="li4022101310471"></a>以**root**用户登录备OMS数据库节点。
2.  执行**su - omm**命令切换到**omm**用户。
3.  进入“$\{BIGDATA\_HOME\}/om-server/om/sbin/”目录，然后执行**./status-oms.sh**命令检查备OMS数据库资源状态是否正常，查看回显中，“ResName”为“gaussDB”的一行，是否显示如下信息：

    例如：

    ```
    10_10_10_231 gaussDB Standby_normal Normal Active_standby
    ```

    -   是，执行[9](#li5624519510471)。
    -   否，执行[16](#li5774450110471)。


**检查备节点磁盘是否已满。**

1.  <a name="li5624519510471"></a>以**root**用户登录备OMS数据库节点。
2.  执行**su - omm**命令切换到**omm**用户。
3.  执行**echo $\{BIGDATA\_DATA\_HOME\}/dbdata\_om**命令获取OMS数据库的数据目录。
4.  执行**df -h**命令，查看系统磁盘分区的使用信息。
5.  查看OMS数据库数据目录挂载磁盘是否已满。
    -   是，执行[14](#li321832510471)。
    -   否，执行[16](#li5774450110471)。

6.  <a name="li321832510471"></a>进行磁盘扩容。
7.  磁盘扩容后，等待2分钟检查告警是否清除。
    -   是，操作结束。
    -   否，执行[16](#li5774450110471)。


**收集故障信息。**

1.  <a name="li5774450110471"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OmmServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895533.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section45165651"></a>

无。

