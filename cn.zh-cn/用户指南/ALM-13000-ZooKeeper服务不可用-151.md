# ALM-13000 ZooKeeper服务不可用<a name="ALM-13000"></a>

## 告警解释<a name="section59446631"></a>

系统每60秒周期性检测ZooKeeper服务状态，当检测到ZooKeeper服务不可用时产生该告警。

ZooKeeper服务恢复时，告警清除。

## 告警属性<a name="section65257632"></a>

<a name="table62499017"></a>
<table><thead align="left"><tr id="row14656770"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p46347704"><a name="p46347704"></a><a name="p46347704"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p63176580"><a name="p63176580"></a><a name="p63176580"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p17029323"><a name="p17029323"></a><a name="p17029323"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row37197943"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p60243440"><a name="p60243440"></a><a name="p60243440"></a>13000</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p47880477"><a name="p47880477"></a><a name="p47880477"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p53113447"><a name="p53113447"></a><a name="p53113447"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section50447784"></a>

<a name="table7221941"></a>
<table><thead align="left"><tr id="row38703738"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p47995043"><a name="p47995043"></a><a name="p47995043"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p62393236"><a name="p62393236"></a><a name="p62393236"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row12600839183317"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14765121319101"><a name="p14765121319101"></a><a name="p14765121319101"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row20687350"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p1376621317100"><a name="p1376621317100"></a><a name="p1376621317100"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p35582507"><a name="p35582507"></a><a name="p35582507"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row51807112"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p15766121315107"><a name="p15766121315107"></a><a name="p15766121315107"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p70810"><a name="p70810"></a><a name="p70810"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row637295"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2076651312109"><a name="p2076651312109"></a><a name="p2076651312109"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p20545297"><a name="p20545297"></a><a name="p20545297"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section51376879"></a>

ZooKeeper无法为上层组件提供协调服务，依赖ZooKeeper的组件可能无法正常运行。

## 可能原因<a name="section59738735"></a>

-   ZooKeeper节点上安装了DNS。
-   网络故障。
-   KrbServer服务异常。
-   ZooKeeper实例状态异常。
-   磁盘容量不足。

## 处理步骤<a name="section777703"></a>

**检查DNS。**

1.  查看ZooKeeper实例所在节点上是否安装DNS。在ZooKeeper实例所在Linux节点使用命令**cat /etc/resolv.conf**，看该文件是否为空。
    -   是，执行[2](#li204081120144218)。
    -   否，执行[3](#li17424152094215)。

2.  <a name="li204081120144218"></a>运行命令**service named status**查看DNS是否启动。
    -   是，执行[3](#li17424152094215)。
    -   否，执行[5](#li15706103911426)。

3.  <a name="li17424152094215"></a>运行命令**service named stop**将DNS服务停掉，如果出现“Shutting down name server BIND waiting for named to shut down \(28s\)”结果，即说明DNS服务停止成功。然后将“/etc/resolv.conf”文件的内容（若不为空）全部注释。
4.  在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[5](#li15706103911426)。


**检查网络状态。**

1.  <a name="li15706103911426"></a>在ZooKeeper实例所在Linux节点使用**ping**命令，看能否**ping**通其他ZooKeeper实例所在节点的主机名。
    -   是，执行[9](#li16060469154840)。
    -   否，执行[6](#li147221739104213)。

2.  <a name="li147221739104213"></a>修改“/etc/hosts”中的IP信息，添加主机名与IP地址的对应关系。
3.  再次执行**ping**命令，查看能否在该ZooKeeper实例节点**ping**通其他ZooKeeper实例节点的主机名。
    -   是，执行[8](#li167371739134213)。
    -   否，执行[23](#li2967530154840)。

4.  <a name="li167371739134213"></a>在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[9](#li16060469154840)。


**检查KrbServer服务状态（普通模式集群跳过此步骤）**。

1.  <a name="li16060469154840"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务”。
2.  查看KrbServer服务是否正常。
    -   是，执行[13](#li22204821154840)。
    -   否，执行[11](#li35657112154840)。

3.  <a name="li35657112154840"></a>参考“ALM-25500 KrbServer服务不可用”进行处理，查看KrbServer服务是否能够恢复。
    -   是，执行[12](#li54662985154840)。
    -   否，执行[23](#li2967530154840)。

4.  <a name="li54662985154840"></a>在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[13](#li22204821154840)。


**检查ZooKeeper服务实例状态。**

1.  <a name="li22204821154840"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> quorumpeer”。
2.  查看ZooKeeper各实例是否正常。
    -   是，执行[18](#li55150024154840)。
    -   否，执行[15](#li30324396154840)。

3.  <a name="li30324396154840"></a>选中运行状态不为良好的实例，选择“更多 \> 重启实例”。
4.  查看实例重启后运行状态是否为良好。
    -   是，执行[17](#li50867023154840)。
    -   否，执行[18](#li55150024154840)。

5.  <a name="li50867023154840"></a>在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li55150024154840)。


**检查磁盘状态。**

1.  <a name="li55150024154840"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> ZooKeeper \> quorumpeer”查看ZooKeeper实例所在的各节点主机信息。
2.  在FusionInsight Manager首页，单击“主机”。
3.  在“磁盘”列，检查ZooKeeper实例所在的各节点数据磁盘空间是否不足（使用率超过百分之80）。
    -   是，执行[21](#li29424080154840)。
    -   否，执行[23](#li2967530154840)。

4.  <a name="li29424080154840"></a>参考“ALM-12017 磁盘容量不足”进行处理，对磁盘进行扩容。
5.  在“运维 \> 告警 \> 告警”页签，查看该告警是否恢复。
    -   是，处理完毕。
    -   否，执行[23](#li2967530154840)。


**收集故障信息。**

1.  <a name="li2967530154840"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。（普通模式集群不需要下载KrbServer日志。）
    -   ZooKeeper
    -   KrbServer

3.  单击右上角的![](figures/zh-cn_image_0263895382.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section6999329"></a>

无。

