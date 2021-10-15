# ALM-16002 Hive SQL执行成功率低于阈值<a name="ALM-16002"></a>

## 告警解释<a name="section31005689"></a>

系统每30秒周期性检测执行的HQL成功百分比，HQL成功百分比由一个周期内Hive执行成功的HQL数/Hive执行HQL总数计算得到。该指标可通过“集群 \>  _待操作的集群__名称_  \> 服务 \> Hive \> 实例 \>  _具体的HiveServer__实例_”查看。执行的HQL成功百分比指标默认提供一个阈值范围（90%），当检测到百分比指标低于阈值范围产生该告警。在该告警的定位信息可查看产生该告警的主机名，该主机IP也是HiveServer节点IP。

用户可通过“运维 \> 告警 \> 阈值设置 \>  _待操作集群的名称_  \> Hive \> 执行成功的HQL百分比”修改阈值。

当系统在一个检测周期检测到该指标高于阈值的110%时，恢复告警。

## 告警属性<a name="section10615745"></a>

<a name="table62443390"></a>
<table><thead align="left"><tr id="row47404881"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p14590147"><a name="p14590147"></a><a name="p14590147"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p40951245"><a name="p40951245"></a><a name="p40951245"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p28716568"><a name="p28716568"></a><a name="p28716568"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row44340684"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p34825615"><a name="p34825615"></a><a name="p34825615"></a>16002</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p2302604"><a name="p2302604"></a><a name="p2302604"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p52293225"><a name="p52293225"></a><a name="p52293225"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section28432848"></a>

<a name="table7892814"></a>
<table><thead align="left"><tr id="row58862058"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p3097425"><a name="p3097425"></a><a name="p3097425"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p49564835"><a name="p49564835"></a><a name="p49564835"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1351672642518"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row55328714"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19852726"><a name="p19852726"></a><a name="p19852726"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row44456811"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p26020088"><a name="p26020088"></a><a name="p26020088"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row32854202"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p2748986"><a name="p2748986"></a><a name="p2748986"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row24740882"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p57854422"><a name="p57854422"></a><a name="p57854422"></a>Trigger condition</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p55696635"><a name="p55696635"></a><a name="p55696635"></a>系统当前指标取值满足自定义的告警设置条件。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section54569046"></a>

系统执行业务能力过低，无法正常响应客户请求。

## 可能原因<a name="section21359372"></a>

-   HQL命令语法错误。
-   执行Hive on HBase任务时HBase服务异常。
-   执行Hive on Spark任务时Spark服务异常。
-   依赖的基础服务HDFS、Yarn、ZooKeeper等异常。

## 处理步骤<a name="section58016628"></a>

**检查HQL命令是否符合语法。**

1.  在FusionInsight Manager界面选择“运维 \> 告警”，查看告警详情，获取产生告警的节点信息。
2.  使用Hive客户端连接到产生该告警的HiveServer节点，查询Apache提供的HQL语法规范，确认输入的命令是否正确。详情请参见[https://cwiki.apache.org/confluence/display/hive/languagemanual](https://cwiki.apache.org/confluence/display/hive/languagemanual)。

    -   是，执行[4](#li4043319016335)。
    -   否，执行[3](#li6702105116335)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若想查看执行错误语句的用户，可下载产生该告警的HiveServer节点的HiveServerAudit日志，下载的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟。打开日志文件查找“Result=FAIL”关键字筛选执行错误语句的日志信息，再根据日志信息中的“UserName”查看执行错误语句的用户。

3.  <a name="li6702105116335"></a>输入正确的HQL语句，观察命令是否正确执行。
    -   是，执行[12](#li3329996516335)。
    -   否，执行[4](#li4043319016335)。


**检查HBase服务是否异常。**

1.  <a name="li4043319016335"></a>与执行HQL命令的用户确认是否执行的是Hive on HBase任务。
    -   是，执行[5](#li6664467016335)。
    -   否，执行[8](#li1510454616335)。

2.  <a name="li6664467016335"></a>在FusionInsight Manager界面选择“集群 \>  _待操作集群的名称_  \> 服务”，在服务列表查看HBase服务状态是否正常。
    -   是，执行[8](#li1510454616335)。
    -   否，执行[6](#li6293111916335)。

3.  <a name="li6293111916335"></a>选择“运维 \> 告警”，查看告警界面的HBase相关告警，参照对应告警帮助进行处理。
4.  输入正确的HQL语句，观察命令是否正确执行。
    -   是，执行[12](#li3329996516335)。
    -   否，执行[8](#li1510454616335)。


**检查HDFS、Yarn、ZooKeeper等是否正常。**

1.  <a name="li1510454616335"></a>在FusionInsight Manager首页，选择“集群 \>  _待操作集群的名称_  \> 服务”。
2.  在服务列表查看HDFS、Yarn、ZooKeeper等服务是否正常。
    -   是，执行[12](#li3329996516335)。
    -   否，执行[10](#li743051416335)。

3.  <a name="li743051416335"></a>查看告警界面的相关告警，参照对应告警帮助进行处理。
4.  输入正确的HQL语句，观察命令是否正确执行。
    -   是，执行[12](#li3329996516335)。
    -   否，执行[13](#li1083758416645)。

5.  <a name="li3329996516335"></a>等待一分钟，查看本告警是否清除。
    -   是，处理结束。
    -   否，执行[13](#li1083758416645)。


**收集故障信息。**

1.  <a name="li1083758416645"></a>在FusionInsight Manager首页，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的如下节点信息。
    -   Mapreduce
    -   Hive

3.  单击右上角的![](figures/zh-cn_image_0263895589.png)设置日志收集的“开始时间”和“结束时间”，分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section52387605"></a>

无。

