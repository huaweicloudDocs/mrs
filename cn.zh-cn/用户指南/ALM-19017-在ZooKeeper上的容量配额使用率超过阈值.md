# ALM-19017 在ZooKeeper上的容量配额使用率超过阈值<a name="ALM-19017"></a>

## 告警解释<a name="section49280276"></a>

系统每120秒周期性检测HBase服务的ZNode使用情况，当检测到HBase服务的ZNode容量使用率超出告警的阈值（默认75%）时产生该告警。

当ZNode的容量使用率小于告警的阈值时，告警恢复。

>![](public_sys-resources/icon-note.gif) **说明：** 
>若集群启用了多实例功能且安装了多个HBase服务，请根据“定位信息”的“服务名”值来确定具体产生告警的HBase服务。例如“定位信息”中显示服务名=HBase-1，处理步骤中的操作对象也应由HBase调整为HBase-1。

## 告警属性<a name="section40869308"></a>

<a name="table2694484"></a>
<table><thead align="left"><tr id="row57848198"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p55192461"><a name="p55192461"></a><a name="p55192461"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p41404348"><a name="p41404348"></a><a name="p41404348"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p65417916"><a name="p65417916"></a><a name="p65417916"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row64359861"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p45766222"><a name="p45766222"></a><a name="p45766222"></a>19017</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p16076463"><a name="p16076463"></a><a name="p16076463"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p27125121"><a name="p27125121"></a><a name="p27125121"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section32279454"></a>

<a name="table49651179"></a>
<table><thead align="left"><tr id="row461818"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p37407293"><a name="p37407293"></a><a name="p37407293"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p10091901"><a name="p10091901"></a><a name="p10091901"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1975212412175"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row12137633"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p43900087"><a name="p43900087"></a><a name="p43900087"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row59556464"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p37226997"><a name="p37226997"></a><a name="p37226997"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p42160567"><a name="p42160567"></a><a name="p42160567"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row43900785"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p1810620"><a name="p1810620"></a><a name="p1810620"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row1767911615433"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p057114210356"><a name="p057114210356"></a><a name="p057114210356"></a>Threshold</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p124623918333"><a name="p124623918333"></a><a name="p124623918333"></a>产生告警的阈值。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section22079637"></a>

产生该告警表示HBase服务的ZNode的容量使用率已经超过规定的阈值，如果不及时处理，可能会导致问题级别升级为紧急，影响数据写入。

## 可能原因<a name="section64499009"></a>

-   HBase配置了容灾并且容灾存在数据同步失败或者同步速度慢；
-   HBase集群存在大量的WAL文件在进行split。

## 处理步骤<a name="section375714160309"></a>

**检查ZNode容量配置和使用量**

1.  在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，选中“告警ID”为“19017”的告警，查看“附加信息”中的阈值。
2.  以**root**用户登录HBase客户端，用户密码为安装前用户自定义，请咨询系统管理员。执行以下命令进入客户端安装目录：

    **cd** _客户端安装目录_

    然后执行以下命令设置环境变量：

    **source bigdata\_env**

    如果集群采用安全版本，要执行以下命令进行安全认证：

    **kinit hbase**

    按提示输入密码（向管理员获取密码）。

3.  执行**hbase zkcli**命令进入ZooKeeper客户端，然后执行命令**listquota /hbase**查看对应HBase服务的ZNode容量配额，其中命令中的ZNode根目录为对应HBase服务的参数“zookeeper.znode.parent”所指定。下图标注所示即为当前HBase服务根ZNode的容量配置。

    ![](figures/zh-cn_image_0263895783.png)

4.  执行命令**getusage /hbase/splitWAL**查看该ZNode的容量使用情况，查看返回结果的“**Data size**”跟ZNode容量配额的比值是否接近告警的阈值。
    -   是，执行[5](#li6339011093624)。
    -   否，执行[6](#li62018222616)。

5.  <a name="li6339011093624"></a>在FusionInsight Manager首页，查看是否存在“告警ID”为“12007”、“19000”或者“19013”且“定位信息”中的“服务名”为当前HBase服务的告警。
    -   是，单击对应告警右侧的“查看帮助”并按照帮助文档进行处理，执行[8](#li5814142393624)。
    -   否，执行[7](#li17555915687)。

6.  <a name="li62018222616"></a>执行命令**getusage /hbase/replication**查看该ZNode的容量使用情况，查看返回结果的“**Data size**”跟ZNode容量配额的比值是否接近告警的阈值。
    -   是，执行[7](#li17555915687)。
    -   否，执行[9](#li5351076393624)。

7.  <a name="li17555915687"></a>在FusionInsight Manager首页，选择“运维 \> 告警 \> 告警”，查看是否存在“告警ID”为“19006”并且“定位信息”中的“服务名”为当前HBase服务的告警。
    -   是，单击对应告警右侧的“查看帮助”并按照帮助文档进行处理，执行[8](#li5814142393624)。
    -   否，执行[9](#li5351076393624)。

8.  <a name="li5814142393624"></a>观察界面告警是否清除。
    -   是，处理完毕。
    -   否，执行[9](#li5351076393624)。


**收集故障信息**

1.  <a name="li5351076393624"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“HBase”。
3.  单击右上角的![](figures/zh-cn_image_0263895513.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后10分钟，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section57037220"></a>

无。

