# ALM-13000 ZooKeeper服务不可用<a name="ZH-CN_TOPIC_0174499343"></a>

## 告警解释<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section30661937"></a>

系统每30秒周期性检测ZooKeeper服务状态，当检测到ZooKeeper服务不可用时产生该告警。

ZooKeeper服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section7521977"></a>

<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_table11808928"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row63404869"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p35520730"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p35520730"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p35520730"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p58606859"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p58606859"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p58606859"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p49535170"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p49535170"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p49535170"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row52925796"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59131099"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59131099"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59131099"></a>13000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p24889743"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p24889743"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p24889743"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p2803303"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p2803303"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p2803303"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section588929"></a>

<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_table25741004"></a>
<table><thead align="left"><tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row31903028"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p34008447"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p34008447"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p34008447"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p3220827"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p3220827"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p3220827"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row59560431"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59665636"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59665636"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p59665636"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p1078370"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p1078370"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p1078370"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row9705331"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p47934352"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p47934352"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p47934352"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p57477322"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p57477322"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p57477322"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_row47533853"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p25036876"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p25036876"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p25036876"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p14721100"><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p14721100"></a><a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_p14721100"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section5300362"></a>

ZooKeeper无法为上层组件提供协调服务，依赖ZooKeeper的组件可能无法正常运行。

## 可能原因<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section47703261"></a>

-   ZooKeeper实例状态异常。
-   磁盘容量不足。
-   网络故障。
-   ZooKeeper节点上安装了DNS。

## 处理步骤<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section26676172"></a>

**检查ZooKeeper服务实例状态。**

1.  在MRS Manager首页，单击“服务管理 \> ZooKeeper \> quorumpeer”。
2.  查看ZooKeeper各实例是否正常。
    -   是，执行[6](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li40423354145525)。
    -   否，执行[3](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li43049911145525)。

3.  <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li43049911145525"></a>选中健康状态不为良好的实例，单击“更多 \> 重启实例”。
4.  查看实例重启后健康状态是否为良好。
    -   是，执行[5](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li64143807145525)。
    -   否，执行[19](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229)。

5.  <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li64143807145525"></a>在“告警管理”页签，查看该告警是否恢复。

    -   是，处理完毕。
    -   否，执行[6](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li40423354145525)。

    **检查磁盘状态。**

6.  <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li40423354145525"></a>在MRS Manager首页，单击“服务管理 \> ZooKeeper \> quorumpeer”查看ZooKeeper实例所在的各节点主机信息。
7.  在MRS Manager首页，单击“主机管理”。
8.  在“磁盘使用率”列，检查ZooKeeper实例所在的各节点磁盘空间是否不足（使用率超过百分之80）。
    -   是，执行[9](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li66786352145525)。
    -   否，执行[11](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li835031145525)。

9.  <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li66786352145525"></a>参考[ALM-12017 磁盘容量不足](ALM-12017-磁盘容量不足-13.md#ZH-CN_TOPIC_0174499330)进行处理，对磁盘进行扩容。
10. 在“告警管理”页签，查看该告警是否恢复。

    -   是，处理完毕。
    -   否，执行[11](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li835031145525)。

    **检查网络状态。**

11. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li835031145525"></a>在ZooKeeper实例所在Linux节点使用**ping**命令，看能否**ping**通其他ZooKeeper实例所在节点的主机名。
    -   是，执行[15](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li53340623145525)。
    -   否，执行[12](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li7515284145525)。

12. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li7515284145525"></a>修改“/etc/hosts”中的IP信息，添加主机名与IP地址的对应关系。
13. 再次执行**ping**命令，查看能否在该ZooKeeper实例节点**ping**通其他ZooKeeper实例节点的主机名。
    -   是，执行[14](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li15395686145525)。
    -   否，执行[19](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229)。

14. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li15395686145525"></a>在“告警管理”页签，查看该告警是否恢复。

    -   是，处理完毕。
    -   否，执行[15](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li53340623145525)。

    **检查DNS。**

15. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li53340623145525"></a>查看ZooKeeper实例所在节点上是否安装DNS。在ZooKeeper实例所在Linux节点使用命令cat /etc/resolv.conf，看该文件是否为空。
    -   是，执行[16](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li54403854145525)。
    -   否，执行[19](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229)。

16. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li54403854145525"></a>运行命令**service named status**查看DNS是否启动。
    -   是，执行[17](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li44636076145525)。
    -   否，执行[19](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229)。

17. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li44636076145525"></a>运行命令**service named stop**将DNS服务停掉，如果出现“Shutting down name server BIND waiting for named to shut down \(28s\)”如下结果，即说明DNS服务停止成功。然后将“/etc/resolv.conf”文件的内容（若不为空）全部注释。
18. 在“告警管理”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[19](#zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229)。

19. <a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_li36159542145229"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0093195043_zh-cn_topic_0035998717_section38758958"></a>

无。

