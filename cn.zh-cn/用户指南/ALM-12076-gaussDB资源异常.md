# ALM-12076 gaussDB资源异常<a name="ALM-12076"></a>

## 告警解释<a name="section52675926"></a>

HA软件每10秒周期性检测Manager的数据库。当HA软件连续3次检测到数据库异常时，产生该告警。

当HA检测到数据库正常后，告警恢复。

## 告警属性<a name="section4321287"></a>

<a name="table57422478"></a>
<table><thead align="left"><tr id="row44493712"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p47220900"><a name="p47220900"></a><a name="p47220900"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p66796549"><a name="p66796549"></a><a name="p66796549"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p41811354"><a name="p41811354"></a><a name="p41811354"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row31276491"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p50367874"><a name="p50367874"></a><a name="p50367874"></a>12076</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p53265956"><a name="p53265956"></a><a name="p53265956"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p19575195"><a name="p19575195"></a><a name="p19575195"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section38891589"></a>

<a name="table1090459143316"></a>
<table><thead align="left"><tr id="row190429173313"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p129062911339"><a name="p129062911339"></a><a name="p129062911339"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10906093332"><a name="p10906093332"></a><a name="p10906093332"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row175286306352"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17935380415"><a name="p17935380415"></a><a name="p17935380415"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群或系统名称。</p>
</td>
</tr>
<tr id="row18907109203311"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p99095916333"><a name="p99095916333"></a><a name="p99095916333"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p4909159173310"><a name="p4909159173310"></a><a name="p4909159173310"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row4910691332"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39101953320"><a name="p39101953320"></a><a name="p39101953320"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p5911189173310"><a name="p5911189173310"></a><a name="p5911189173310"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row59118923315"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p0912169123319"><a name="p0912169123319"></a><a name="p0912169123319"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p169131916332"><a name="p169131916332"></a><a name="p169131916332"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section14479984"></a>

如果数据库异常，所有核心业务和相关业务进程，例如告警和监控功能，都会受影响。

## 可能原因<a name="section63210993"></a>

数据库异常。

## 处理步骤<a name="section370414815215"></a>

**检查主备管理节点的数据库状态。**

1.  以**root**用户分别登录主备管理节点，用户密码为安装前用户自定义，请咨询系统管理员，执行**su - ommdba**命令切换到**ommdba**用户，执行**gs\_ctl query**命令。查看回显是否显示以下信息。管理节点的主备状态及对应IP地址可在FusionInsight Manager主机管理界面查看。

    主管理节点的回显：

    ```
     Ha state: 
            LOCAL_ROLE                    : Primary 
            STATIC_CONNECTIONS            : 1 
            DB_STATE                      : Normal 
            DETAIL_INFORMATION            : user/password invalid 
     Senders info: 
            No information 
     Receiver info: 
            No information     
    ```

    备管理节点的回显：

    ```
     Ha state: 
            LOCAL_ROLE                    : Standby 
            STATIC_CONNECTIONS            : 1 
            DB_STATE                      : Normal 
            DETAIL_INFORMATION            : user/password invalid 
     Senders info: 
            No information 
     Receiver info: 
            No information
    ```

    -   是，执行[3](#li5028276516216)。
    -   否，执行[2](#li4327401616216)。

2.  <a name="li4327401616216"></a>联系网络管理员查看是否为网络故障，并修复故障。
    -   是，执行[3](#li5028276516216)。
    -   否，执行[5](#li954639716248)。

3.  <a name="li5028276516216"></a>等待5分钟，查看告警列表中，该告警是否已清除。
    -   是，处理完毕。
    -   否，执行[4](#li321964899423)。

4.  <a name="li321964899423"></a>分别登录主备管理节点，执行**su - omm**命令切换到**omm，**用户进入“$\{BIGDATA\_HOME\}/om-server/om/sbin/”目录，并执行**status-oms.sh**脚本检查主备Manager的floatip资源和gaussDB资源是否如下图所示的状态：

    ![](figures/zh-cn_image_0263895772.jpg)

    -   是，在告警列表中找到该告警，手工清除该告警。
    -   否，执行[5](#li954639716248)。


**收集故障信息。**

1.  <a name="li954639716248"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选“OmmServer”，单击“确定”。
3.  单击右上角的![](figures/zh-cn_image_0263895737.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section19816769"></a>

无。

