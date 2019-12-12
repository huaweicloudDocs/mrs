# ALM-16002 Hive SQL执行成功率低于阈值<a name="ZH-CN_TOPIC_0191883104"></a>

## 告警解释<a name="zh-cn_topic_0191813927_section22593558"></a>

系统每30秒周期性检测执行的HiveQL成功百分比，HiveQL成功百分比由一个周期内Hive执行成功的HiveQL数/Hive执行HiveQL总数计算得到。该指标可在Hive服务监控界面查看。执行的HiveQL成功百分比指标默认提供一个阈值范围（90%），当检测到百分比指标低于阈值范围产生该告警。在该告警的定位信息可查看产生该告警的主机名，该主机IP也是HiveServer节点IP。

当系统在一个检测周期检测到该指标高于阈值时，恢复告警。

## 告警属性<a name="zh-cn_topic_0191813927_section2015430"></a>

<a name="zh-cn_topic_0191813927_table9994955"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813927_row62312200"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0191813927_p14123440"><a name="zh-cn_topic_0191813927_p14123440"></a><a name="zh-cn_topic_0191813927_p14123440"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0191813927_p3148005"><a name="zh-cn_topic_0191813927_p3148005"></a><a name="zh-cn_topic_0191813927_p3148005"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0191813927_p53661838"><a name="zh-cn_topic_0191813927_p53661838"></a><a name="zh-cn_topic_0191813927_p53661838"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813927_row51641620"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0191813927_p22221662"><a name="zh-cn_topic_0191813927_p22221662"></a><a name="zh-cn_topic_0191813927_p22221662"></a>16002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0191813927_p55124180"><a name="zh-cn_topic_0191813927_p55124180"></a><a name="zh-cn_topic_0191813927_p55124180"></a>严重</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0191813927_p35873632"><a name="zh-cn_topic_0191813927_p35873632"></a><a name="zh-cn_topic_0191813927_p35873632"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0191813927_section18138873"></a>

<a name="zh-cn_topic_0191813927_table20083047"></a>
<table><thead align="left"><tr id="zh-cn_topic_0191813927_row3150961"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0191813927_p53901255"><a name="zh-cn_topic_0191813927_p53901255"></a><a name="zh-cn_topic_0191813927_p53901255"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0191813927_p3925534"><a name="zh-cn_topic_0191813927_p3925534"></a><a name="zh-cn_topic_0191813927_p3925534"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0191813927_row49532829"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813927_p52736237"><a name="zh-cn_topic_0191813927_p52736237"></a><a name="zh-cn_topic_0191813927_p52736237"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813927_p43776822"><a name="zh-cn_topic_0191813927_p43776822"></a><a name="zh-cn_topic_0191813927_p43776822"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813927_row58447079"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813927_p36592919"><a name="zh-cn_topic_0191813927_p36592919"></a><a name="zh-cn_topic_0191813927_p36592919"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813927_p11236435"><a name="zh-cn_topic_0191813927_p11236435"></a><a name="zh-cn_topic_0191813927_p11236435"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813927_row34019058"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813927_p4080300"><a name="zh-cn_topic_0191813927_p4080300"></a><a name="zh-cn_topic_0191813927_p4080300"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813927_p62068903"><a name="zh-cn_topic_0191813927_p62068903"></a><a name="zh-cn_topic_0191813927_p62068903"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0191813927_row21749220"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0191813927_p16856419"><a name="zh-cn_topic_0191813927_p16856419"></a><a name="zh-cn_topic_0191813927_p16856419"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0191813927_p23192694"><a name="zh-cn_topic_0191813927_p23192694"></a><a name="zh-cn_topic_0191813927_p23192694"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0191813927_section29032137"></a>

系统执行业务能力过低，无法正常响应客户请求。

## 可能原因<a name="zh-cn_topic_0191813927_section59962646"></a>

-   HiveQL命令语法错误
-   执行Hive on HBase任务时HBase服务异常
-   依赖的基础服务HDFS、Yarn、ZooKeeper等异常

## 处理步骤<a name="zh-cn_topic_0191813927_section2792905"></a>

1.  检查HiveQL命令是否符合语法。
    1.  使用Hive客户端连接到产生该告警的HiveServer节点，查询Apache提供的HiveQL语法规范，确认输入的命令是否正确。详情请参见[https://cwiki.apache.org/confluence/display/hive/languagemanual](https://cwiki.apache.org/confluence/display/hive/languagemanual)。

        -   是，执行[2.a](#zh-cn_topic_0191813927_step11)。
        -   否，执行[1.b](#zh-cn_topic_0191813927_aalm-16002_mmccppss_step2)。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >若想查看执行错误语句的用户，可下载产生该告警的HiveServer节点的HiveServerAudit日志，下载的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟。打开日志文件查找“Result=FAIL”关键字筛选执行错误语句的日志信息，再根据日志信息中的“UserName”查看执行错误语句的用户。  

    2.  <a name="zh-cn_topic_0191813927_aalm-16002_mmccppss_step2"></a>输入正确的HiveQL语句，观察命令是否正确执行。
        -   是，执行[4.e](#zh-cn_topic_0191813927_step_6)。
        -   否，执行[2.a](#zh-cn_topic_0191813927_step11)。

2.  检查HBase服务是否异常。
    1.  <a name="zh-cn_topic_0191813927_step11"></a>检查是否执行Hive on HBase任务。
        -   是，执行[2.b](#zh-cn_topic_0191813927_aalm-16002_mmccppss_step12)。
        -   否，执行[3.a](ALM-16002-Hive-SQL执行成功率低于阈值.md#zh-cn_topic_0191813927_step22)。

    2.  <a name="zh-cn_topic_0191813927_aalm-16002_mmccppss_step12"></a>在服务列表查看HBase服务是否正常。
        -   是，执行[3.a](ALM-16002-Hive-SQL执行成功率低于阈值.md#zh-cn_topic_0191813927_step22)。
        -   否，执行[2.c](#zh-cn_topic_0191813927_aalm-16002_mmccppss_step_15)。

    3.  <a name="zh-cn_topic_0191813927_aalm-16002_mmccppss_step_15"></a>查看告警界面的相关告警，参照对应告警帮助进行处理。
    4.  输入正确的HiveQL语句，观察命令是否正确执行。
        -   是，执行[4.e](#zh-cn_topic_0191813927_step_6)。
        -   否，执行[3.a](ALM-16002-Hive-SQL执行成功率低于阈值.md#zh-cn_topic_0191813927_step22)。

3.  检查Spark服务是否异常。
    1.  在服务列表查看Spark服务是否正常。
        -   是，执行[4.a](#zh-cn_topic_0191813927_li51692872)。
        -   否，执行[3.b](#zh-cn_topic_0191813927_step_25)。

    2.  <a name="zh-cn_topic_0191813927_step_25"></a>查看告警界面的相关告警，参照对应告警帮助进行处理。
    3.  输入正确的HiveQL语句，观察命令是否正确执行。
        -   是，执行[4.e](#zh-cn_topic_0191813927_step_6)。
        -   否，执行[4.a](#zh-cn_topic_0191813927_li51692872)。

4.  检查HDFS、Yarn、ZooKeeper等是否正常。
    1.  <a name="zh-cn_topic_0191813927_li51692872"></a>登录MRS集群详情页面，选择“组件管理”。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >针对MRS 2.0.1及之前版本，请登录MRS Manager页面，选择“服务管理”。  

    2.  在服务列表查看HDFS、Yarn、ZooKeeper等服务是否正常。
        -   是，执行[4.e](#zh-cn_topic_0191813927_step_6)。
        -   否，执行[4.c](#zh-cn_topic_0191813927_aalm-16002_mmccppss_step_5)。

    3.  <a name="zh-cn_topic_0191813927_aalm-16002_mmccppss_step_5"></a>查看告警界面的相关告警，参照对应告警帮助进行处理。
    4.  输入正确的HiveQL语句，观察命令是否正确执行。
        -   是，执行[4.e](#zh-cn_topic_0191813927_step_6)。
        -   否，执行[5](#zh-cn_topic_0191813927_li572522141314)。

    5.  <a name="zh-cn_topic_0191813927_step_6"></a>等待一分钟，查看本告警是否清除。
        -   是，处理结束。
        -   否，执行[5](#zh-cn_topic_0191813927_li572522141314)。

5.  <a name="zh-cn_topic_0191813927_li572522141314"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0191813927_section25136147"></a>

无。

