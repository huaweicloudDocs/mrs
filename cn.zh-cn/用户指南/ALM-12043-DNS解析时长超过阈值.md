# ALM-12043 DNS解析时长超过阈值<a name="ZH-CN_TOPIC_0191883137"></a>

## 告警解释<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section19482731"></a>

系统每30秒周期性检测DNS解析时长，并把DNS解析时长和阈值（系统默认阈值20000ms）进行比较，当检测到DNS解析时长连续多次（默认值为2）超过阈值时产生该告警。

用户可通过“系统设置 \> 阈值配置 \> 设备 \> 主机 \> 网络状态 \> DNS解析时长 \> DNS解析时长”修改阈值。

平滑次数为1，DNS解析时长小于等于阈值时，告警恢复；平滑次数不为1，DNS解析时长小于等于阈值的90%时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section41126851"></a>

<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_table55839258"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row376394"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p30487925"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p30487925"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p30487925"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p53602865"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p53602865"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p53602865"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p46864805"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p46864805"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p46864805"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row37952890"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p54285272"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p54285272"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p54285272"></a>12043</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p35030886"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p35030886"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p35030886"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p18929484"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p18929484"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p18929484"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section34597344"></a>

<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_table56893235"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row18924856"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56518356"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56518356"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56518356"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p14584084"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p14584084"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p14584084"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row40460128"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56044961"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56044961"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p56044961"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p43348031"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p43348031"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p43348031"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row54587964"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p59548976"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p59548976"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p59548976"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p58737715"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p58737715"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p58737715"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_row58877395"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p4339699"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p4339699"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p4339699"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p15971319"><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p15971319"></a><a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_p15971319"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section42940641"></a>

-   使用Kerberos进行的二次认证较慢。
-   ZooKeeper服务异常。
-   导致节点故障。

## 可能原因<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section50921457"></a>

-   该节点配置了DNS客户端。
-   该节点安装并启动了DNS服务端。

## 处理步骤<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section55639936"></a>

**检查是否配置了DNS客户端。**

1.  登录MRS集群详情页面，选择“告警管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“告警管理”。  

2.  查看该告警的详细信息，查看定位信息中对应的“HostName”字段值，获取该告警产生的主机名。
3.  使用PuTTY工具，以**root**用户登录告警所在节点。
4.  执行**cat /etc/resolv.conf**命令，查看是否安装DNS客户端。

    如果出现了类似如下内容，说明节点安装并启用了DNS客户端服务。

    ```
    namesever 10.2.3.4  
    namesever 10.2.3.4
    ```

    -   是，执行[5](#zh-cn_topic_0191813958_zh-cn_topic_0087039385_li29935381112614)。
    -   否，执行[7](#zh-cn_topic_0191813958_zh-cn_topic_0087039385_li39250560112614)。

5.  <a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_li29935381112614"></a>执行**vi /etc/resolv.conf**命令，将内容全部用“\#”注释，并保存文件。

    ```
    # namesever 10.2.3.4  
    # namesever 10.2.3.4
    ```

6.  等待5分钟，查看告警是否恢复。
    -   是，操作结束。
    -   否，执行[7](#zh-cn_topic_0191813958_zh-cn_topic_0087039385_li39250560112614)。


**检查是否安装并启动了DNS服务端。**

1.  <a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_li39250560112614"></a>执行**service named status**命令，查看节点是否安装DNS服务。

    如果出现以下内容，说明安装并启用了DNS服务。

    ```
    Checking for nameserver BIND  
    version: 9.6-ESV-R7-P4 
    CPUs found: 8 
    worker threads: 8 
    number of zones: 17 
    debug level: 0 
    xfers running: 0 
    xfers deferred: 0 
    soa queries in progress: 0 
    query logging is ON 
    recursive clients: 4/0/1000 
    tcp clients: 0/100 
    server is up and running
    ```

    -   是，执行[8](#zh-cn_topic_0191813958_zh-cn_topic_0087039385_li25178791112614)。
    -   否，执行[10](#zh-cn_topic_0191813958_li572522141314)。

2.  <a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_li25178791112614"></a>执行**service named stop**命令，停止DNS服务。
3.  等待5分钟，查看告警是否恢复。
    -   是，操作结束。
    -   否，执行[10](#zh-cn_topic_0191813958_li572522141314)。

4.  <a name="zh-cn_topic_0191813958_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813958_zh-cn_topic_0087039385_section30997384"></a>

无

