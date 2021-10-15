# ALM-43001 Spark服务不可用<a name="alm_43001"></a>

## 告警解释<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section43920869"></a>

系统每60秒周期性检测Spark服务状态，当检测到Spark服务不可用时产生该告警。

Spark服务恢复时，告警清除。

## 告警属性<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section59743502"></a>

<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_table64843092"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row10409628"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p37873528"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p37873528"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p37873528"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p47856888"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p47856888"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p47856888"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p51202692"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p51202692"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p51202692"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row53777413"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p61003235"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p61003235"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p61003235"></a>43001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p42315013"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p42315013"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p42315013"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p4964052"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p4964052"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p4964052"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section820607"></a>

<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_table66543927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row61284534"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p65100236"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p65100236"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p65100236"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p38627770"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p38627770"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p38627770"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row41841705"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p33734977"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p33734977"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p33734977"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p48178601"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p48178601"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p48178601"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row30954226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p24264406"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p24264406"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p24264406"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p19259870"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p19259870"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p19259870"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_row39121107"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p14693133"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p14693133"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p14693133"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p49293152"><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p49293152"></a><a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_p49293152"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section7385465"></a>

用户提交的Spark任务执行失败。

## 可能原因<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section66469189"></a>

-   KrbServer服务异常。
-   LdapServer服务异常。
-   ZooKeeper服务异常。
-   HDFS服务故障。
-   Yarn服务故障。
-   对应的Hive服务故障。

## 处理步骤<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section61351797"></a>

1.  检查Spark依赖的服务是否有服务不可用告警。
    1.  登录MRS集群详情页面，选择“告警管理”。
    2.  在告警列表中，查看是否存在以下告警：
        1.  ALM-25500 KrbServer服务不可用
        2.  ALM-25000 LdapServer服务不可用
        3.  ALM-13000 ZooKeeper服务不可用
        4.  ALM-14000 HDFS服务不可用
        5.  ALM-18000 Yarn服务不可用
        6.  ALM-16004 Hive服务不可用

        -   是，执行[1.c](#zh-cn_topic_0191813893_li1257801171836)
        -   否，执行[2](#zh-cn_topic_0191813893_li572522141314)

    3.  <a name="zh-cn_topic_0191813893_li1257801171836"></a>根据对应服务不可用告警帮助文档处理对应告警。

        告警全部恢复后，等待几分钟，检查本告警是否恢复。

        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813893_li572522141314)。

2.  <a name="zh-cn_topic_0191813893_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813893_zh-cn_topic_0087039425_section15295265"></a>

无。

