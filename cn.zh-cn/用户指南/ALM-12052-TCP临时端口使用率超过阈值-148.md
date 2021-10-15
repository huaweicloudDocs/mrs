# ALM-12052 TCP临时端口使用率超过阈值<a name="ALM-12052"></a>

## 告警解释<a name="section41396267"></a>

系统每30秒周期性检测TCP临时端口使用率，并把实际使用率和阈值（系统默认阈值80%）进行比较，当检测到TCP临时端口使用率连续多次（默认值为5）超过阈值时产生该告警。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> 主机 \> 网络状态 \> TCP临时端口使用率”修改阈值。

平滑次数为1，TCP临时端口使用率小于或等于阈值时，告警恢复；平滑次数大于1，TCP临时端口使用率小于或等于阈值的90%时，告警恢复。

## 告警属性<a name="section37022085"></a>

<a name="table52321376"></a>
<table><thead align="left"><tr id="row39266406"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p26462316"><a name="p26462316"></a><a name="p26462316"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p63072822"><a name="p63072822"></a><a name="p63072822"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p8624940"><a name="p8624940"></a><a name="p8624940"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row27531576"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p15465151"><a name="p15465151"></a><a name="p15465151"></a>12052</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p44717739"><a name="p44717739"></a><a name="p44717739"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p65367140"><a name="p65367140"></a><a name="p65367140"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section64763312"></a>

<a name="table60246993"></a>
<table><thead align="left"><tr id="row16742709"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p13982213"><a name="p13982213"></a><a name="p13982213"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p58817486"><a name="p58817486"></a><a name="p58817486"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row2773114823717"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row66595895"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p25558376"><a name="p25558376"></a><a name="p25558376"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56962570"><a name="p56962570"></a><a name="p56962570"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row42901084"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p52435818"><a name="p52435818"></a><a name="p52435818"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19442876"><a name="p19442876"></a><a name="p19442876"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row40768163"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13886870"><a name="p13886870"></a><a name="p13886870"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p51094723"><a name="p51094723"></a><a name="p51094723"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row57199326"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2633810"><a name="p2633810"></a><a name="p2633810"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p12012051"><a name="p12012051"></a><a name="p12012051"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section45998902"></a>

主机上业务无法发起对外建立连接，业务中断。

## 可能原因<a name="section11336934"></a>

-   临时端口不满足当前业务需求。
-   系统环境异常。

## 处理步骤<a name="section34923547"></a>

**扩大临时端口范围。**

1.  打开FusionInsight Manager页面，在实时告警列表中，单击此告警所在行的![](figures/zh-cn_image_0263895749.png)，获取告警所在主机IP地址。
2.  以**omm**用户登录告警所在主机。
3.  执行**cat /proc/sys/net/ipv4/ip\_local\_port\_range |cut -f 1**命令，获得开始端口值，执行****cat /proc/sys/net/ipv4/ip\_local\_port\_range**  |cut -f 2**命令，获得结束端口值，相减得到临时端口总数，若临时端口总数小于28232，说明操作系统随机端口范围太小，需要联系系统管理员扩大端口范围。
4.  执行命令**ss -ant 2\>/dev/null | grep -v LISTEN | awk 'NR \> 2 \{print $4\}'|cut -d ':' -f 2 | awk '$1 \>"_开始端口值_" \{print $1\}' | sort -u | wc -l**，计算临时端口使用数。
5.  使用公式计算临时端口使用率，临时端口使用率=（临时端口使用数/临时端口总数）\*100，确认临时端口使用率是否超过阈值。
    -   是，执行[7](#li62811777151245)。
    -   否，执行[6](#li5574623151245)。

6.  <a name="li5574623151245"></a>等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[7](#li62811777151245)。


**检查系统环境是否异常。**

1.  <a name="li62811777151245"></a>执行以下命令导入临时文件，并查看“port\_result.txt“文件中高使用率端口。

    **netstat -tnp \> $BIGDATA\_HOME/tmp/port\_result.txt**

    ```
    netstat -tnp 
    
    Active Internet connections (w/o servers)
    
    Proto Recv Send LocalAddress ForeignAddress State PID/ProgramName tcp   0   0 10-120-85-154:45433  10-120-85-154:9866 CLOSE_WAIT 94237/java 
    tcp   0   0 10-120-85-154:45434  10-120-85-154:9866 CLOSE_WAIT 94237/java 
    tcp   0   0 10-120-85-154:45435  10-120-85-154:9866 CLOSE_WAIT 94237/java 
    ...
    ```

2.  执行如下命令，查看占用大量端口的进程。

    **ps -ef |grep **_PID_

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   PID为[7](#li62811777151245)查询出所属端口的进程号。
    >-   可以执行如下命令，收集系统所有进程信息，查看占用大量端口的进程。
    >    **ps -ef \> $BIGDATA\_HOME/tmp/ps\_result.txt**

3.  请系统管理员确认后，清除大量占用端口的进程，等待5分钟，检查该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[10](#li65563174151245)。


**收集故障信息。**

1.  <a name="li65563174151245"></a>在主集群的FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OMS”，单击“确定”。
3.  设置“主机”为告警所在节点和主OMS节点。
4.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后30分钟，单击“下载”。
5.  请联系运维人员，发送已收集的故障日志信息及“ port\_result.txt”和“ ps\_result.txt”文件，并删除环境中残留的两个临时文件。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section45876468"></a>

无。

