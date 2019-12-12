# ALM-23001 Loader服务不可用<a name="ZH-CN_TOPIC_0191883133"></a>

## 告警解释<a name="zh-cn_topic_0191813961_section19665522175625"></a>

系统每60秒周期性检测Loader服务的可用性。当Loader服务不可用时产生该告警。当Loader服务恢复时，告警恢复。

## 告警属性<a name="zh-cn_topic_0191813961_section42254989175625"></a>

<a name="zh-cn_topic_0191813961_table102091175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813961_row31905194175625"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813961_p34183898175625"><a name="zh-cn_topic_0191813961_p34183898175625"></a><a name="zh-cn_topic_0191813961_p34183898175625"></a><strong id="zh-cn_topic_0191813961_b39219631175625"><a name="zh-cn_topic_0191813961_b39219631175625"></a><a name="zh-cn_topic_0191813961_b39219631175625"></a>告警ID</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813961_p22673543175625"><a name="zh-cn_topic_0191813961_p22673543175625"></a><a name="zh-cn_topic_0191813961_p22673543175625"></a><strong id="zh-cn_topic_0191813961_b2735300175625"><a name="zh-cn_topic_0191813961_b2735300175625"></a><a name="zh-cn_topic_0191813961_b2735300175625"></a>告警级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813961_p20232782175625"><a name="zh-cn_topic_0191813961_p20232782175625"></a><a name="zh-cn_topic_0191813961_p20232782175625"></a><strong id="zh-cn_topic_0191813961_b47877317175625"><a name="zh-cn_topic_0191813961_b47877317175625"></a><a name="zh-cn_topic_0191813961_b47877317175625"></a>可自动清除</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813961_row52857467175625"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813961_p63628609163045"><a name="zh-cn_topic_0191813961_p63628609163045"></a><a name="zh-cn_topic_0191813961_p63628609163045"></a>23001</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813961_p53643687163045"><a name="zh-cn_topic_0191813961_p53643687163045"></a><a name="zh-cn_topic_0191813961_p53643687163045"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813961_p50171427163045"><a name="zh-cn_topic_0191813961_p50171427163045"></a><a name="zh-cn_topic_0191813961_p50171427163045"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813961_section27218191175625"></a>

<a name="zh-cn_topic_0191813961_table57189892175625"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813961_row20832688175625"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813961_p9726186175625"><a name="zh-cn_topic_0191813961_p9726186175625"></a><a name="zh-cn_topic_0191813961_p9726186175625"></a><strong id="zh-cn_topic_0191813961_b20426813175625"><a name="zh-cn_topic_0191813961_b20426813175625"></a><a name="zh-cn_topic_0191813961_b20426813175625"></a>参数名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813961_p43959148175625"><a name="zh-cn_topic_0191813961_p43959148175625"></a><a name="zh-cn_topic_0191813961_p43959148175625"></a><strong id="zh-cn_topic_0191813961_b60088019175625"><a name="zh-cn_topic_0191813961_b60088019175625"></a><a name="zh-cn_topic_0191813961_b60088019175625"></a>参数含义</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813961_row35291346175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813961_p2931319695830"><a name="zh-cn_topic_0191813961_p2931319695830"></a><a name="zh-cn_topic_0191813961_p2931319695830"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813961_p2555869495830"><a name="zh-cn_topic_0191813961_p2555869495830"></a><a name="zh-cn_topic_0191813961_p2555869495830"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813961_row54265439175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813961_p4313287295830"><a name="zh-cn_topic_0191813961_p4313287295830"></a><a name="zh-cn_topic_0191813961_p4313287295830"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813961_p410176895830"><a name="zh-cn_topic_0191813961_p410176895830"></a><a name="zh-cn_topic_0191813961_p410176895830"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813961_row5894265175625"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813961_p3739937095830"><a name="zh-cn_topic_0191813961_p3739937095830"></a><a name="zh-cn_topic_0191813961_p3739937095830"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813961_p4332232595830"><a name="zh-cn_topic_0191813961_p4332232595830"></a><a name="zh-cn_topic_0191813961_p4332232595830"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813961_section23922301175625"></a>

如果Loader服务不可用，数据加载，导入，转换的功能也不可用。

## 可能原因<a name="zh-cn_topic_0191813961_section58162349175625"></a>

-   Loader服务依赖的内部服务异常。
    -   ZooKeeper服务异常。
    -   HDFS服务异常。
    -   DBService服务异常。
    -   Yarn服务异常。
    -   Mapreduce服务异常。

-   环境故障：网络异常，Loader服务无法与其依赖的内部服务通信，无法提供服务。
-   软件故障：Loader服务无法正常运行。

## 处理步骤<a name="zh-cn_topic_0191813961_section320384891008"></a>

1.  检查ZooKeeper服务状态。
    1.  登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  选择“ZooKeeper”查看ZooKeeper的健康状态是否正常。
        -   是，执行[1.d](#zh-cn_topic_0191813961_li173182016530)。
        -   否，执行[1.c](#zh-cn_topic_0191813961_li4731152065314)。

    3.  <a name="zh-cn_topic_0191813961_li4731152065314"></a>单击“更多 \> 重启服务”重新启动ZooKeeper服务实例。重启完成后在告警列表中，查看“ALM-23001 Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[1.d](#zh-cn_topic_0191813961_li173182016530)。

    4.  <a name="zh-cn_topic_0191813961_li173182016530"></a>在告警列表中，查看是否有“ALM-12007 进程故障”告警产生。
        -   是，执行[1.e](#zh-cn_topic_0191813961_li11731152014534)。
        -   否，执行[2.a](#zh-cn_topic_0191813961_li103551920123512)。

    5.  <a name="zh-cn_topic_0191813961_li11731152014534"></a>在“ALM-12007 进程故障”的“告警详情”区域，查看定位信息的“ServiceName”是否为“ZooKeeper”。
        -   是，执行[1.f](#zh-cn_topic_0191813961_li167320209539)。
        -   否，执行[2.a](#zh-cn_topic_0191813961_li103551920123512)。

    6.  <a name="zh-cn_topic_0191813961_li167320209539"></a>参考“ALM-12007  进程故障”的处理步骤处理该故障。
    7.  在告警列表中，查看“ALM-23001  Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0191813961_li103551920123512)。

2.  检查HDFS服务状态。
    1.  <a name="zh-cn_topic_0191813961_li103551920123512"></a>登录MRS集群详情页面，选择“告警管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“告警管理”。  

    2.  在告警列表中，查看是否有“ALM-14000 HDFS服务不可用”告警产生。
        -   是，执行[2.c](#zh-cn_topic_0191813961_li167011853195320)。
        -   否，执行[3.a](#zh-cn_topic_0191813961_li1554455818353)。

    3.  <a name="zh-cn_topic_0191813961_li167011853195320"></a>参考“ALM-14000  HDFS服务不可用”的处理步骤处理该故障。
    4.  在告警列表中，查看“ALM-23001  Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3.a](#zh-cn_topic_0191813961_li1554455818353)。

3.  检查DBService服务状态。
    1.  <a name="zh-cn_topic_0191813961_li1554455818353"></a>登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  选择“DBService”查看DBService的健康状态是否正常。
        -   是，执行[3.a](#zh-cn_topic_0191813961_li1554455818353)。
        -   否，执行[3.c](#zh-cn_topic_0191813961_li122981864542)。

    3.  <a name="zh-cn_topic_0191813961_li122981864542"></a>单击“更多 \> 重启服务”重新启动DBService服务实例。重启完成后在告警列表中，查看“ALM-23001 Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[4.a](#zh-cn_topic_0191813961_li14598145163614)。

4.  检查MapReduce服务状态。
    1.  <a name="zh-cn_topic_0191813961_li14598145163614"></a>登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  选择“Mapreduce”查看Mapreduce的健康状态是否正常。
        -   是，执行[5.a](#zh-cn_topic_0191813961_li984194223716)。
        -   否，执行[4.c](#zh-cn_topic_0191813961_li191227237549)。

    3.  <a name="zh-cn_topic_0191813961_li191227237549"></a>单击“更多  \> 重启服务”重新启动Mapreduce服务。重启完成后在告警列表中，查看“ALM-23001 Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[5.a](#zh-cn_topic_0191813961_li984194223716)。

5.  检查Yarn服务状态。
    1.  <a name="zh-cn_topic_0191813961_li984194223716"></a>登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  选择“Yarn”查看Yarn的健康状态是否正常。
        -   是，执行[5.d](#zh-cn_topic_0191813961_li11673173775413)。
        -   否，执行[5.c](#zh-cn_topic_0191813961_li126731375547)。

    3.  <a name="zh-cn_topic_0191813961_li126731375547"></a>单击“更多 \> 重启服务”重新启动Yarn服务实例。重启完成后在告警列表中，查看“ALM-23001 Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[5.d](#zh-cn_topic_0191813961_li11673173775413)。

    4.  <a name="zh-cn_topic_0191813961_li11673173775413"></a>在MRS Manager的告警列表中，查看是否有“ALM-18000 Yarn服务不可用”告警产生。
        -   是，执行[5.e](#zh-cn_topic_0191813961_li6673837155415)。
        -   否，执行[6.a](#zh-cn_topic_0191813961_li13825217113813)。

    5.  <a name="zh-cn_topic_0191813961_li6673837155415"></a>参考“ALM-18000 Yarn服务不可用”的处理步骤处理该故障。
    6.  在告警列表中，查看“ALM-23001  Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[6.a](#zh-cn_topic_0191813961_li13825217113813)。

6.  检查Loader和依赖组件之间的网络连接。
    1.  <a name="zh-cn_topic_0191813961_li13825217113813"></a>登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  单击“Loader”。
    3.  单击“实例”，显示Sqoop实例列表。
    4.  <a name="zh-cn_topic_0191813961_li2928194985415"></a>记录所有Sqoop实例的“管理IP”。
    5.  登录[6.d](#zh-cn_topic_0191813961_li2928194985415)获取的IP地址所在的主机，执行以下命令切换用户。

        **sudo su - root**

        **su - omm**

    6.  执行**ping**命令，查看Sqoop实例所在主机和依赖组件所在主机的网络连接是否正常。（依赖组件包括ZooKeeper、DBService、HDFS、Mapreduce和Yarn等，获取依赖组件所在主机的IP地址的方式和获取Sqoop实例的IP地址的方式相同。）
        -   是，执行[7](#zh-cn_topic_0191813961_li572522141314)。
        -   否，执行[6.g](#zh-cn_topic_0191813961_li10928124925412)。

    7.  <a name="zh-cn_topic_0191813961_li10928124925412"></a>联系网络管理员恢复网络。
    8.  在告警列表中，查看“ALM-23001  Loader服务不可用”告警是否清除。
        -   是，处理完毕。
        -   否，执行[7](#zh-cn_topic_0191813961_li572522141314)。

7.  <a name="zh-cn_topic_0191813961_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


