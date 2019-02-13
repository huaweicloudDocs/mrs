# ALM-28001 Spark服务不可用<a name="ZH-CN_TOPIC_0093195074"></a>

## 告警解释<a name="zh-cn_topic_0035998748_section6492062019553"></a>

系统每30秒周期性检测Spark服务状态，当检测到Spark服务不可用时产生该告警。

Spark服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0035998748_section40216543195528"></a>

<a name="zh-cn_topic_0035998748_table743650619568"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998748_row37225951195612"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998748_p62512036195612"><a name="zh-cn_topic_0035998748_p62512036195612"></a><a name="zh-cn_topic_0035998748_p62512036195612"></a><strong id="zh-cn_topic_0035998748_b57424273195642"><a name="zh-cn_topic_0035998748_b57424273195642"></a><a name="zh-cn_topic_0035998748_b57424273195642"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998748_p30310170195612"><a name="zh-cn_topic_0035998748_p30310170195612"></a><a name="zh-cn_topic_0035998748_p30310170195612"></a><strong id="zh-cn_topic_0035998748_b20854518195642"><a name="zh-cn_topic_0035998748_b20854518195642"></a><a name="zh-cn_topic_0035998748_b20854518195642"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998748_p39204712195612"><a name="zh-cn_topic_0035998748_p39204712195612"></a><a name="zh-cn_topic_0035998748_p39204712195612"></a><strong id="zh-cn_topic_0035998748_b11494412195642"><a name="zh-cn_topic_0035998748_b11494412195642"></a><a name="zh-cn_topic_0035998748_b11494412195642"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998748_row2335960319568"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998748_p1307965419568"><a name="zh-cn_topic_0035998748_p1307965419568"></a><a name="zh-cn_topic_0035998748_p1307965419568"></a>28001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998748_p5281909119568"><a name="zh-cn_topic_0035998748_p5281909119568"></a><a name="zh-cn_topic_0035998748_p5281909119568"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998748_p5048796819568"><a name="zh-cn_topic_0035998748_p5048796819568"></a><a name="zh-cn_topic_0035998748_p5048796819568"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998748_section41923046195725"></a>

<a name="zh-cn_topic_0035998748_table53044787"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998748_row2530563"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998748_p3649016"><a name="zh-cn_topic_0035998748_p3649016"></a><a name="zh-cn_topic_0035998748_p3649016"></a><strong id="zh-cn_topic_0035998748_b1586586195722"><a name="zh-cn_topic_0035998748_b1586586195722"></a><a name="zh-cn_topic_0035998748_b1586586195722"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998748_p27134857"><a name="zh-cn_topic_0035998748_p27134857"></a><a name="zh-cn_topic_0035998748_p27134857"></a><strong id="zh-cn_topic_0035998748_b61404618195722"><a name="zh-cn_topic_0035998748_b61404618195722"></a><a name="zh-cn_topic_0035998748_b61404618195722"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998748_row50439840"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998748_p59095202"><a name="zh-cn_topic_0035998748_p59095202"></a><a name="zh-cn_topic_0035998748_p59095202"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998748_p21982073"><a name="zh-cn_topic_0035998748_p21982073"></a><a name="zh-cn_topic_0035998748_p21982073"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998748_row63620936"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998748_p53022201"><a name="zh-cn_topic_0035998748_p53022201"></a><a name="zh-cn_topic_0035998748_p53022201"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998748_p66939890"><a name="zh-cn_topic_0035998748_p66939890"></a><a name="zh-cn_topic_0035998748_p66939890"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998748_row65588106"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998748_p11036355"><a name="zh-cn_topic_0035998748_p11036355"></a><a name="zh-cn_topic_0035998748_p11036355"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998748_p21529561"><a name="zh-cn_topic_0035998748_p21529561"></a><a name="zh-cn_topic_0035998748_p21529561"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998748_section29721847195729"></a>

用户提交的Spark任务执行失败。

## 可能原因<a name="zh-cn_topic_0035998748_section29064590195733"></a>

-   KrbServer服务异常。
-   LdapServer服务异常。
-   ZooKeeper服务异常。
-   HDFS服务故障。
-   Yarn服务故障。
-   对应的Hive服务故障。

## 处理步骤<a name="zh-cn_topic_0035998748_section35286881195746"></a>

1.  检查Spark依赖的服务是否有服务不可用告警。
    1.  在MRS Manager首页，单击“告警管理”。
    2.  在告警列表中，查看是否存在以下告警：
        1.  ALM-25500 KrbServer服务不可用
        2.  ALM-25000 LdapServer服务不可用
        3.  ALM-13000 ZooKeeper服务不可用
        4.  ALM-14000 HDFS服务不可用
        5.  ALM-18000 Yarn服务不可用
        6.  ALM-16004 Hive服务不可用

        -   是，执行[1.c](#zh-cn_topic_0035998748_li645282320039)。
        -   否，执行[2](#zh-cn_topic_0035998748_li368425714576)。

    3.  <a name="zh-cn_topic_0035998748_li645282320039"></a>根据对应服务不可用告警帮助提供的故障处理对应告警。

        告警全部恢复后，等待几分钟，检查本告警是否恢复。

        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0035998748_li368425714576)。


2.  <a name="zh-cn_topic_0035998748_li368425714576"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035998748_section30321530195513"></a>

无。

