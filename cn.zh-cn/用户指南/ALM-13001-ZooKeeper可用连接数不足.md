# ALM-13001 ZooKeeper可用连接数不足<a name="ZH-CN_TOPIC_0191883088"></a>

## 告警解释<a name="zh-cn_topic_0191813882_section54545236"></a>

系统每30秒周期性检测ZooKeeper服务连接数状态，当检测到ZooKeeper实例连接数超出阈值（最大连接数的百分之八十）时产生该告警。

连接数小于阈值时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813882_section21145081"></a>

<a name="zh-cn_topic_0191813882_table11533784"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813882_row3757979"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813882_p35960896"><a name="zh-cn_topic_0191813882_p35960896"></a><a name="zh-cn_topic_0191813882_p35960896"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813882_p27151449"><a name="zh-cn_topic_0191813882_p27151449"></a><a name="zh-cn_topic_0191813882_p27151449"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813882_p51783759"><a name="zh-cn_topic_0191813882_p51783759"></a><a name="zh-cn_topic_0191813882_p51783759"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813882_row33734921"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813882_p48174063"><a name="zh-cn_topic_0191813882_p48174063"></a><a name="zh-cn_topic_0191813882_p48174063"></a>13001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813882_p9785067"><a name="zh-cn_topic_0191813882_p9785067"></a><a name="zh-cn_topic_0191813882_p9785067"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813882_p54392930"><a name="zh-cn_topic_0191813882_p54392930"></a><a name="zh-cn_topic_0191813882_p54392930"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813882_section56088004"></a>

<a name="zh-cn_topic_0191813882_table43751230"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813882_row43605354"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813882_p42372785"><a name="zh-cn_topic_0191813882_p42372785"></a><a name="zh-cn_topic_0191813882_p42372785"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813882_p9643552"><a name="zh-cn_topic_0191813882_p9643552"></a><a name="zh-cn_topic_0191813882_p9643552"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813882_row42930272"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813882_p54800025"><a name="zh-cn_topic_0191813882_p54800025"></a><a name="zh-cn_topic_0191813882_p54800025"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813882_p9617010"><a name="zh-cn_topic_0191813882_p9617010"></a><a name="zh-cn_topic_0191813882_p9617010"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813882_row19444226"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813882_p31478446"><a name="zh-cn_topic_0191813882_p31478446"></a><a name="zh-cn_topic_0191813882_p31478446"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813882_p66726223"><a name="zh-cn_topic_0191813882_p66726223"></a><a name="zh-cn_topic_0191813882_p66726223"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813882_row63665103"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813882_p56599738"><a name="zh-cn_topic_0191813882_p56599738"></a><a name="zh-cn_topic_0191813882_p56599738"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813882_p21176078"><a name="zh-cn_topic_0191813882_p21176078"></a><a name="zh-cn_topic_0191813882_p21176078"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813882_row56366974"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813882_p2322177"><a name="zh-cn_topic_0191813882_p2322177"></a><a name="zh-cn_topic_0191813882_p2322177"></a>Trigger Condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813882_p53878657"><a name="zh-cn_topic_0191813882_p53878657"></a><a name="zh-cn_topic_0191813882_p53878657"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813882_section35029990"></a>

ZooKeeper可用连接数不足，当连接率超过百分之百时无法处理外部连接。

## 可能原因<a name="zh-cn_topic_0191813882_section46834456"></a>

该节点ZooKeeper连接量过大，超过阈值。某些连接进程存在连接泄露，或配置的最大连接数不符合实际使用场景。

## 处理步骤<a name="zh-cn_topic_0191813882_section18856923"></a>

1.  检查连接状态。
    1.  在MRS集群详情页，单击“告警管理 \> 13001连接数不足 \> 定位信息”。查看告警上报的节点IP地址。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面查看告警信息。  

    2.  获取ZooKeeper进程pid。登录到告警上报的节点，执行命令：**pgrep -f proc\_zookeeper**。
    3.  是否正常获取pid。
        -   是，执行[1.d](#zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb2)。
        -   否，执行[2](#zh-cn_topic_0191813882_li572522141314)。

    4.  <a name="zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb2"></a>获取所有与当前ZooKeeper实例连接的IP及连接数量，取连接数最多的前十个进行检查。根据获取到的pid值，执行命令**lsof -i|grep $pid | awk '\{print $9\}' | cut -d : -f 2 | cut -d \\\> -f 2 | awk '\{a\[$1\]++\} END \{for\(i in a\)\{print i,a\[i\] | "sort -r -g -k 2"\}\}' | head -10**。（$pid为上一步获取的pid值）
    5.  获取节点IP与连接数是否成功。
        -   是，执行[1.f](#zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb4)。
        -   否，执行[2](#zh-cn_topic_0191813882_li572522141314)。

    6.  <a name="zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb4"></a>获取连接进程的端口号。根据获取到的pid与IP值，执行命令**lsof -i|grep $pid | awk '\{print $9\}'|cut -d \\\> -f 2 |grep $IP| cut -d : -f 2**。（$pid与$IP为上一步获取的pid值与IP值）
    7.  获取端口号port成功。
        -   是，执行[1.h](#zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb5)。
        -   否，执行[2](#zh-cn_topic_0191813882_li572522141314)。

    8.  <a name="zh-cn_topic_0191813882_cn_58_42_000001_2_mmccppss_stepb5"></a>获取连接进程的进程号。依次登录到各IP，根据获取到的port号，执行命令**lsof -i|grep $port**。（$port为上一步获取端口号）
    9.  获取进程号成功。
        -   是，执行[1.j](#zh-cn_topic_0191813882_stepb6)。
        -   否，执行[2](#zh-cn_topic_0191813882_li572522141314)。

    10. <a name="zh-cn_topic_0191813882_stepb6"></a>根据获取到的进程号，查看进程是否存在连接泄露。
        -   是，执行[1.k](#zh-cn_topic_0191813882_stepb7)。
        -   否，执行[1.l](#zh-cn_topic_0191813882_stepb8)。

    11. <a name="zh-cn_topic_0191813882_stepb7"></a>将存在连接泄露的进程关掉，观察界面上告警是否消除？
        -   是，处理完毕。
        -   否，执行[1.l](#zh-cn_topic_0191813882_stepb8)。

    12. <a name="zh-cn_topic_0191813882_stepb8"></a>在MRS集群详情页面，单击“组件管理 \> ZooKeeper \> 服务配置 \> 全部配置 \> quorumpeer \> Performance”中，将“maxCnxns”调整到20000或更多。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 1.8.10及之前版本，请打开MRS Manager页面，单击“服务管理 \> ZooKeeper \> 服务配置 \> 全部配置 \> quorumpeer \> Performance”中，将“maxCnxns”调整到20000或更多。  

    13. 界面上告警是否消除？
        -   是，处理完毕。
        -   否，执行[2](#zh-cn_topic_0191813882_li572522141314)。

2.  <a name="zh-cn_topic_0191813882_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813882_section35494585"></a>

无。

