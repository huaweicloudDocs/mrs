# ALM-12039 GaussDB主备数据不同步<a name="ZH-CN_TOPIC_0093195041"></a>

## 告警解释<a name="zh-cn_topic_0035546889_section96088172812"></a>

GaussDB主备数据不同步，系统每10秒检查一次主备数据同步状态，如果连续6次查不到同步状态，或者同步状态异常，产生告警。

当主备数据同步状态正常，告警恢复。

## 告警属性<a name="zh-cn_topic_0035546889_section45216965172823"></a>

<a name="zh-cn_topic_0035546889_table52588499172753"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035546889_row64390706172753"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035546889_p48264674172753"><a name="zh-cn_topic_0035546889_p48264674172753"></a><a name="zh-cn_topic_0035546889_p48264674172753"></a><strong id="zh-cn_topic_0035546889_b31728887172753"><a name="zh-cn_topic_0035546889_b31728887172753"></a><a name="zh-cn_topic_0035546889_b31728887172753"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035546889_p19903055172753"><a name="zh-cn_topic_0035546889_p19903055172753"></a><a name="zh-cn_topic_0035546889_p19903055172753"></a><strong id="zh-cn_topic_0035546889_b44909772172753"><a name="zh-cn_topic_0035546889_b44909772172753"></a><a name="zh-cn_topic_0035546889_b44909772172753"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035546889_p13812950172753"><a name="zh-cn_topic_0035546889_p13812950172753"></a><a name="zh-cn_topic_0035546889_p13812950172753"></a><strong id="zh-cn_topic_0035546889_b57207693172753"><a name="zh-cn_topic_0035546889_b57207693172753"></a><a name="zh-cn_topic_0035546889_b57207693172753"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035546889_row45107193172753"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035546889_p29803996172753"><a name="zh-cn_topic_0035546889_p29803996172753"></a><a name="zh-cn_topic_0035546889_p29803996172753"></a>12039</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035546889_p65313447172753"><a name="zh-cn_topic_0035546889_p65313447172753"></a><a name="zh-cn_topic_0035546889_p65313447172753"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035546889_p55897859172753"><a name="zh-cn_topic_0035546889_p55897859172753"></a><a name="zh-cn_topic_0035546889_p55897859172753"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035546889_section7154496172832"></a>

<a name="zh-cn_topic_0035546889_table14459094172753"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035546889_row36118200172753"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035546889_p39893054172753"><a name="zh-cn_topic_0035546889_p39893054172753"></a><a name="zh-cn_topic_0035546889_p39893054172753"></a><strong id="zh-cn_topic_0035546889_b23493170172753"><a name="zh-cn_topic_0035546889_b23493170172753"></a><a name="zh-cn_topic_0035546889_b23493170172753"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035546889_p23898608172753"><a name="zh-cn_topic_0035546889_p23898608172753"></a><a name="zh-cn_topic_0035546889_p23898608172753"></a><strong id="zh-cn_topic_0035546889_b13760884172753"><a name="zh-cn_topic_0035546889_b13760884172753"></a><a name="zh-cn_topic_0035546889_b13760884172753"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035546889_row56739099172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p32464282172753"><a name="zh-cn_topic_0035546889_p32464282172753"></a><a name="zh-cn_topic_0035546889_p32464282172753"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p12361174172753"><a name="zh-cn_topic_0035546889_p12361174172753"></a><a name="zh-cn_topic_0035546889_p12361174172753"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035546889_row44141702172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p18708071172753"><a name="zh-cn_topic_0035546889_p18708071172753"></a><a name="zh-cn_topic_0035546889_p18708071172753"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p38958777172753"><a name="zh-cn_topic_0035546889_p38958777172753"></a><a name="zh-cn_topic_0035546889_p38958777172753"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035546889_row15084675172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p13899201172753"><a name="zh-cn_topic_0035546889_p13899201172753"></a><a name="zh-cn_topic_0035546889_p13899201172753"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p52093507172753"><a name="zh-cn_topic_0035546889_p52093507172753"></a><a name="zh-cn_topic_0035546889_p52093507172753"></a>产生告警的主机节点信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035546889_row66188386172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p59659013172753"><a name="zh-cn_topic_0035546889_p59659013172753"></a><a name="zh-cn_topic_0035546889_p59659013172753"></a>Local GaussDB HA IP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p541922172753"><a name="zh-cn_topic_0035546889_p541922172753"></a><a name="zh-cn_topic_0035546889_p541922172753"></a>本地GaussDB HA IP地址。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035546889_row4877301172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p59517081172753"><a name="zh-cn_topic_0035546889_p59517081172753"></a><a name="zh-cn_topic_0035546889_p59517081172753"></a>Peer GaussDB HA IP</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p56154250172753"><a name="zh-cn_topic_0035546889_p56154250172753"></a><a name="zh-cn_topic_0035546889_p56154250172753"></a>对端GaussDB HA IP地址。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035546889_row35626202172753"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035546889_p41256172753"><a name="zh-cn_topic_0035546889_p41256172753"></a><a name="zh-cn_topic_0035546889_p41256172753"></a>SYNC_PERSENT</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035546889_p3341815172753"><a name="zh-cn_topic_0035546889_p3341815172753"></a><a name="zh-cn_topic_0035546889_p3341815172753"></a>同步百分比。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035546889_section34300035172843"></a>

主备GaussDB数据不同步，如果此时主实例异常，会出现数据丢失或者数据异常的情况。

## 可能原因<a name="zh-cn_topic_0035546889_section64509769172847"></a>

-   主备节点网络不稳定。
-   备GaussDB异常。
-   备节点磁盘空间满。

## 处理步骤<a name="zh-cn_topic_0035546889_section33200607172858"></a>

1.  登录MRS Manager，单击“告警管理”，在告警列表中单击此告警所在行，在告警详情中查看该告警的GaussDB备节点IP地址。
2.  登录主管理节点。
3.  执行以下命令检查备GaussDB节点是否可达。

    **ping** _备GaussDB心跳IP地址_

    是，执行[6](#zh-cn_topic_0035546889_li39909275144355)。

    否，执行[4](#zh-cn_topic_0035546889_li1095691144355)。

4.  <a name="zh-cn_topic_0035546889_li1095691144355"></a>联系公有云运维人员查看是否为网络故障。
    -   是，执行[5](#zh-cn_topic_0035546889_li8186264144355)。
    -   否，执行[6](#zh-cn_topic_0035546889_li39909275144355)。

5.  <a name="zh-cn_topic_0035546889_li8186264144355"></a>修复网络故障，然后查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[6](#zh-cn_topic_0035546889_li39909275144355)。

6.  <a name="zh-cn_topic_0035546889_li39909275144355"></a>登录备GaussDB节点。
7.  执行以下命令切换用户：

    **sudo su - root**

    **su - omm**

8.  切换到“$\{BIGDATA\_HOME\}/om-0.0.1/sbin/”目录。

    执行以下命令检查备gaussDB资源状态是否正常

    **sh status-oms.sh**

    查看回显中，“ResName”为“gaussDB”的一行，是否显示如下信息，例如：

    ```
    10_10_10_231 gaussDB Standby_normal Normal Active_standby
    ```

    -   是，执行[9](#zh-cn_topic_0035546889_li58535127144355)。
    -   否，执行[15](#zh-cn_topic_0035546889_li34763607144355)。


1.  <a name="zh-cn_topic_0035546889_li58535127144355"></a>登录备GaussDB节点。
2.  执行以下命令切换用户：

    **sudo su - root**

    **su - omm**

3.  执行**echo $\{BIGDATA\_DATA\_HOME\}/dbdata\_om**命令获取GaussDB的数据目录。
4.  执行**df -h**命令，查看系统磁盘分区的使用信息。
5.  查看GaussDB数据目录挂载磁盘是否剩余空间不足。
    -   是，执行[14](#zh-cn_topic_0035546889_li31581498144355)。
    -   否，执行[15](#zh-cn_topic_0035546889_li34763607144355)。

6.  <a name="zh-cn_topic_0035546889_li31581498144355"></a>联系公有云运维人员进行扩容磁盘。扩容后，等待2分钟检查告警是否清除。
    -   是，操作结束。
    -   否，执行[15](#zh-cn_topic_0035546889_li34763607144355)。

7.  <a name="zh-cn_topic_0035546889_li34763607144355"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035546889_section5597720165321"></a>

无。

