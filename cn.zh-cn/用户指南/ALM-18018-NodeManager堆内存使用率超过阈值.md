# ALM-18018 NodeManager堆内存使用率超过阈值<a name="ALM-18018"></a>

## 告警解释<a name="section13447226"></a>

系统每30秒周期性检测Yarn服务堆内存使用状态，当检测到NodeManager实例堆内存使用率超出阈值（最大内存的95%）时产生该告警。

堆内存使用率小于阈值时，告警恢复。

## 告警属性<a name="section53916176"></a>

<a name="table33817547"></a>
<table><thead align="left"><tr id="row8931076"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p52328576"><a name="p52328576"></a><a name="p52328576"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p10756297"><a name="p10756297"></a><a name="p10756297"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65953734"><a name="p65953734"></a><a name="p65953734"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row40652256"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p4498430"><a name="p4498430"></a><a name="p4498430"></a>18018</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p28828553"><a name="p28828553"></a><a name="p28828553"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p53411432"><a name="p53411432"></a><a name="p53411432"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section15483537"></a>

<a name="table31358724"></a>
<table><thead align="left"><tr id="row33518103"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p30611809"><a name="p30611809"></a><a name="p30611809"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p63637484"><a name="p63637484"></a><a name="p63637484"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row914216115195"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row54362592"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56463136"><a name="p56463136"></a><a name="p56463136"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row38406179"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p56266616"><a name="p56266616"></a><a name="p56266616"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row36637496"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p61773077"><a name="p61773077"></a><a name="p61773077"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row19086789"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p2526039"><a name="p2526039"></a><a name="p2526039"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p3282622"><a name="p3282622"></a><a name="p3282622"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section5134112"></a>

NodeManager堆内存使用率过高，会影响Yarn任务提交和运行的性能，甚至可能会造成内存溢出导致Yarn服务崩溃。

## 可能原因<a name="section46207013"></a>

该节点NodeManager实例堆内存使用率过大，或配置的堆内存不合理，导致使用率超过阈值。

## 处理步骤<a name="section13209937"></a>

**检查堆内存使用率。**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警 \> ALM-18018 NodeManager堆内存使用率超过阈值 \> 定位信息”。查看告警上报的实例的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 实例 \> NodeManager（对应上报告警实例IP地址）”，单击图表区域右上角的下拉菜单，选择“定制 \> 资源”，勾选“NodeManager内存使用率”。查看堆内存使用情况。

    **图 1**  定制NodeManager内存使用率<a name="fig267352845611"></a>  
    ![](figures/定制NodeManager内存使用率-89.png "定制NodeManager内存使用率-89")

3.  查看NodeManager使用的堆内存是否已达到NodeManager设定的最大堆内存的95%\(默认阈值\)。
    -   是，执行[4](#li6413071185459)。
    -   否，执行[6](#li4749473185459)。

4.  <a name="li6413071185459"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Yarn \> 配置 \> 全部配置 \> NodeManager \> 系统”。将“GC\_OPTS”参数的值根据实际情况调大。保存配置，并重启NodeManager实例。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >集群中的NodeManager实例数量和NodeManager内存大小的对应关系参考如下：
    >-   集群中的NodeManager实例数据达到100，NodeManager实例的JVM参数建议配置为：-Xms2G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到200，NodeManager实例的JVM参数建议配置为：-Xms4G -Xmx4G -XX:NewSize=512M -XX:MaxNewSize=1G
    >-   集群中的NodeManager实例数据达到500以上，NodeManager实例的JVM参数建议配置为：-Xms8G -Xmx8G -XX:NewSize=1G -XX:MaxNewSize=2G

5.  观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li4749473185459)。


**收集故障信息。**

1.  <a name="li4749473185459"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   NodeAgent
    -   Yarn

3.  单击右上角的![](figures/zh-cn_image_0263895445.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section51780573"></a>

无。

