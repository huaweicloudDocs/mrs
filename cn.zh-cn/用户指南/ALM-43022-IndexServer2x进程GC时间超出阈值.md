# ALM-43022 IndexServer2x进程GC时间超出阈值<a name="ALM-43022"></a>

## 告警解释<a name="s7c9141d03d6b444d8290c30b631d0cf0"></a>

系统每60秒周期性检测IndexServer2x进程的GC时间，当检测到IndexServer2x进程的GC时间超出阈值（连续3次检测超过12秒）时产生该告警。用户可通过“运维 \>告警 \> 阈值设置 \>  _待操作集群的名称_  \> Spark2x \> GC时间 \> IndexServer2x的总GC时间”修改阈值。当IndexServer2x进程GC时间小于或等于阈值时，告警恢复。

## 告警属性<a name="s376651fb53d8499887f815231786b339"></a>

<a name="t4159bb171b174e059da9bd760207c4d0"></a>
<table><thead align="left"><tr id="r1e339099e2f645ff9056bd119fe381bf"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="a38b80ab58f384df88ab015cc524b7cbb"><a name="a38b80ab58f384df88ab015cc524b7cbb"></a><a name="a38b80ab58f384df88ab015cc524b7cbb"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="a46c53a74faf84ecf9c9af27d6f61eaab"><a name="a46c53a74faf84ecf9c9af27d6f61eaab"></a><a name="a46c53a74faf84ecf9c9af27d6f61eaab"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="a5fb5879d1a934dd39866e315bf6dfe8f"><a name="a5fb5879d1a934dd39866e315bf6dfe8f"></a><a name="a5fb5879d1a934dd39866e315bf6dfe8f"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="r237ab3a8c9504376a9db5fa7a97b148f"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="af28381aaf20e4c4a8f85098ec46a0303"><a name="af28381aaf20e4c4a8f85098ec46a0303"></a><a name="af28381aaf20e4c4a8f85098ec46a0303"></a>43022</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="a6317fab9a9e34459b2a6e2e021edc2a2"><a name="a6317fab9a9e34459b2a6e2e021edc2a2"></a><a name="a6317fab9a9e34459b2a6e2e021edc2a2"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="aa82affe10728446b8a39f58bf556fc8a"><a name="aa82affe10728446b8a39f58bf556fc8a"></a><a name="aa82affe10728446b8a39f58bf556fc8a"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="s41639aabee044d8d960019194e2e6eb6"></a>

<a name="t97c720d80e924869b586cf705bdbb204"></a>
<table><thead align="left"><tr id="rae0af347daa24e06b98b0421fe713051"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a56eccbfb77e74aa68437112aac4782ef"><a name="a56eccbfb77e74aa68437112aac4782ef"></a><a name="a56eccbfb77e74aa68437112aac4782ef"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="aa100738b88d94b3890e8fdde1ca6cf02"><a name="aa100738b88d94b3890e8fdde1ca6cf02"></a><a name="aa100738b88d94b3890e8fdde1ca6cf02"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row46363355123"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="r84a8eeac06ca46ee937631f94bb0eb3c"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p41293795"><a name="p41293795"></a><a name="p41293795"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a3782d19bc5bb49a9b3b129fe8f6a7f37"><a name="a3782d19bc5bb49a9b3b129fe8f6a7f37"></a><a name="a3782d19bc5bb49a9b3b129fe8f6a7f37"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="r6d450898cd1948969635904d31fc0ab5"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p23892775"><a name="p23892775"></a><a name="p23892775"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="abede771415c3492381db5c9910db0bff"><a name="abede771415c3492381db5c9910db0bff"></a><a name="abede771415c3492381db5c9910db0bff"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="r1f75e56643624cf987aadc9f9569929f"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p14847206"><a name="p14847206"></a><a name="p14847206"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a318fdd3afdd84d8295b93803fe7dd9f4"><a name="a318fdd3afdd84d8295b93803fe7dd9f4"></a><a name="a318fdd3afdd84d8295b93803fe7dd9f4"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="r4e888b217e0c4dda911e3e79da8fce66"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="af9afacd827ec415e968655804e8e93e6"><a name="af9afacd827ec415e968655804e8e93e6"></a><a name="af9afacd827ec415e968655804e8e93e6"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="aa568fb5712484a5ca4bbf32224da6b54"><a name="aa568fb5712484a5ca4bbf32224da6b54"></a><a name="aa568fb5712484a5ca4bbf32224da6b54"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="s571b1640392345b59ad2a1ffba139704"></a>

GC时间超出阈值，会影响IndexServer2x进程运行的性能，甚至造成IndexServer2x进程不可用。

## 可能原因<a name="s069a86c403ce485e94e72eba6af1c8d3"></a>

该节点IndexServer2x进程堆内存使用率过大，或配置的堆内存不合理，导致进程GC频繁。

## 处理步骤<a name="section18256634182118"></a>

**检查GC时间**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“ID”为“43022”的告警，查看“定位信息”中的角色名以及确认主机名所在的IP地址。
2.  在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 实例”，单击告警上报的IndexServer2x，进入实例“概览”页面，单击图表区域右上角的下拉菜单，选择“定制 \> IndexServer2x的GC时间”，单击“确定”，查看IndexServer2x进程的GC时间是否大于阈值（默认12秒）。

    -   是，执行[3](#li928810235414)。
    -   否，执行[6](#li728614235411)。

    **图 1**  IndexServer2x的GC时间<a name="fig22503568282"></a>  
    ![](figures/IndexServer2x的GC时间.png "IndexServer2x的GC时间")

3.  <a name="li928810235414"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Spark2x \> 配置”，单击“全部配置”，选择“IndexServer2x \> 默认”，“SPARK\_DRIVER\_MEMORY”参数默认值为4G，可根据如下原则调整：可将“SPARK\_DRIVER\_MEMORY”参数调整为默认值的1.5倍；若参数值调整后，仍偶现告警，可按0.5倍速率调大。若告警次数比较频繁，可以按1倍速率调大。
4.  重启所有的IndexServer2x实例。
5.  等待10分钟，观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[6](#li728614235411)。


**收集故障信息**

1.  <a name="li728614235411"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“Spark2x”。
3.  单击右上角的![](figures/zh-cn_image_0263895754.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="s117ba5042c8047e49828d78387997ff5"></a>

无。

