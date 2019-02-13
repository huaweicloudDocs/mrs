# 开源组件Web站点<a name="ZH-CN_TOPIC_0071958188"></a>

## 场景介绍<a name="zh-cn_topic_0069869151_section22160644144045"></a>

MRS集群默认在集群的Master节点或Core节点创建并托管了不同组件的Web站点，用户可以通过这些Web站点查看组件相关信息。由于安全原因，这些Web站点只能在集群所处的网络中被访问且不在互联网发布，普通用户可以通过在网络中创建一个带图形化界面的ECS来访问站点页面。

如果不希望创建一个单独的ECS，技术专家或开发工程师可以通过SSH隧道的动态端口转发功能，访问Web站点，详细操作请参见[创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md#ZH-CN_TOPIC_0071958189)。

## Web站点一览<a name="zh-cn_topic_0069869151_section11481629144654"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>混合集群的站点地址请根据站点类型参考分析集群和流式集群的的站点地址。  

**表 1**  未启用Kerberos认证的集群

<a name="zh-cn_topic_0069869151_table15477438145833"></a>
<table><thead align="left"><tr id="zh-cn_topic_0069869151_row51642521145833"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0069869151_p66434050145833"><a name="zh-cn_topic_0069869151_p66434050145833"></a><a name="zh-cn_topic_0069869151_p66434050145833"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="31.990000000000002%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0069869151_p12448942145833"><a name="zh-cn_topic_0069869151_p12448942145833"></a><a name="zh-cn_topic_0069869151_p12448942145833"></a>站点类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.010000000000005%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0069869151_p1731407145833"><a name="zh-cn_topic_0069869151_p1731407145833"></a><a name="zh-cn_topic_0069869151_p1731407145833"></a>站点地址</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0069869151_row15582671145833"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p54236858145833"><a name="zh-cn_topic_0069869151_p54236858145833"></a><a name="zh-cn_topic_0069869151_p54236858145833"></a>全部类型</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p31109390145833"><a name="zh-cn_topic_0069869151_p31109390145833"></a><a name="zh-cn_topic_0069869151_p31109390145833"></a>MRS Manager</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0069869151_ul54001052154512"></a><a name="zh-cn_topic_0069869151_ul54001052154512"></a><ul id="zh-cn_topic_0069869151_ul54001052154512"><li>适用于MRS 1.8.0以前版本<p id="zh-cn_topic_0069869151_p21398421135022"><a name="zh-cn_topic_0069869151_p21398421135022"></a><a name="zh-cn_topic_0069869151_p21398421135022"></a>https://MRS Manager浮动IP地址:28443/web</p>
<div class="note" id="zh-cn_topic_0069869151_note61259334174512"><a name="zh-cn_topic_0069869151_note61259334174512"></a><a name="zh-cn_topic_0069869151_note61259334174512"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0069869151_p14463101174512"><a name="zh-cn_topic_0069869151_p14463101174512"></a><a name="zh-cn_topic_0069869151_p14463101174512"></a>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示MRS Manager浮动IP地址，请记录“inet”的实际参数值。</p>
</div></div>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p5463837104617"><a name="zh-cn_topic_0069869151_p5463837104617"></a><a name="zh-cn_topic_0069869151_p5463837104617"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row63058177145833"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p7438721145833"><a name="zh-cn_topic_0069869151_p7438721145833"></a><a name="zh-cn_topic_0069869151_p7438721145833"></a>分析集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p65665509145833"><a name="zh-cn_topic_0069869151_p65665509145833"></a><a name="zh-cn_topic_0069869151_p65665509145833"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0069869151_ul129175913114"></a><a name="zh-cn_topic_0069869151_ul129175913114"></a><ul id="zh-cn_topic_0069869151_ul129175913114"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p770781161214"><a name="zh-cn_topic_0069869151_p770781161214"></a><a name="zh-cn_topic_0069869151_p770781161214"></a>http://主NameNode角色实例IP地址:25002/dfshealth.html#tab-overview</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul136071302616"></a><a name="zh-cn_topic_0069869151_ul136071302616"></a><ul id="zh-cn_topic_0069869151_ul136071302616"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p1067016019184"><a name="zh-cn_topic_0069869151_p1067016019184"></a><a name="zh-cn_topic_0069869151_p1067016019184"></a>http://主NameNode角色实例IP地址:9870/dfshealth.html#tab-overview</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p13726585494"><a name="zh-cn_topic_0069869151_p13726585494"></a><a name="zh-cn_topic_0069869151_p13726585494"></a>选择“服务管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row4021035315137"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p1518535215137"><a name="zh-cn_topic_0069869151_p1518535215137"></a><a name="zh-cn_topic_0069869151_p1518535215137"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul5506250120"></a><a name="zh-cn_topic_0069869151_ul5506250120"></a><ul id="zh-cn_topic_0069869151_ul5506250120"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p11302138161210"><a name="zh-cn_topic_0069869151_p11302138161210"></a><a name="zh-cn_topic_0069869151_p11302138161210"></a>https://主HMaster角色实例IP地址:21301/master-status</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul10483185511615"></a><a name="zh-cn_topic_0069869151_ul10483185511615"></a><ul id="zh-cn_topic_0069869151_ul10483185511615"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p14841389186"><a name="zh-cn_topic_0069869151_p14841389186"></a><a name="zh-cn_topic_0069869151_p14841389186"></a>https://主HMaster角色实例IP地址:16010/master-status</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p228845015496"><a name="zh-cn_topic_0069869151_p228845015496"></a><a name="zh-cn_topic_0069869151_p228845015496"></a>选择“服务管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row218196015137"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p2165523115137"><a name="zh-cn_topic_0069869151_p2165523115137"></a><a name="zh-cn_topic_0069869151_p2165523115137"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul92611191215"></a><a name="zh-cn_topic_0069869151_ul92611191215"></a><ul id="zh-cn_topic_0069869151_ul92611191215"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p10175191417128"><a name="zh-cn_topic_0069869151_p10175191417128"></a><a name="zh-cn_topic_0069869151_p10175191417128"></a>http://JobHistoryServer角色实例IP地址:26012/jobhistory</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul278717418717"></a><a name="zh-cn_topic_0069869151_ul278717418717"></a><ul id="zh-cn_topic_0069869151_ul278717418717"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p1147121719183"><a name="zh-cn_topic_0069869151_p1147121719183"></a><a name="zh-cn_topic_0069869151_p1147121719183"></a>http://JobHistoryServer角色实例IP地址:19888/jobhistory</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p4643141314504"><a name="zh-cn_topic_0069869151_p4643141314504"></a><a name="zh-cn_topic_0069869151_p4643141314504"></a>选择“服务管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row1563977415137"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p310642615137"><a name="zh-cn_topic_0069869151_p310642615137"></a><a name="zh-cn_topic_0069869151_p310642615137"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul5844191714129"></a><a name="zh-cn_topic_0069869151_ul5844191714129"></a><ul id="zh-cn_topic_0069869151_ul5844191714129"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p16907519171218"><a name="zh-cn_topic_0069869151_p16907519171218"></a><a name="zh-cn_topic_0069869151_p16907519171218"></a>http://主ResourceManager角色实例IP地址:26000/cluster</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul1691913319818"></a><a name="zh-cn_topic_0069869151_ul1691913319818"></a><ul id="zh-cn_topic_0069869151_ul1691913319818"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p66016269183"><a name="zh-cn_topic_0069869151_p66016269183"></a><a name="zh-cn_topic_0069869151_p66016269183"></a>http://主ResourceManager角色实例IP地址:8088/cluster</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p14584155216505"><a name="zh-cn_topic_0069869151_p14584155216505"></a><a name="zh-cn_topic_0069869151_p14584155216505"></a>选择“服务管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row2724320415137"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p3175929015137"><a name="zh-cn_topic_0069869151_p3175929015137"></a><a name="zh-cn_topic_0069869151_p3175929015137"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul66509078232947"></a><a name="zh-cn_topic_0069869151_ul66509078232947"></a><ul id="zh-cn_topic_0069869151_ul66509078232947"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p6547420716718"><a name="zh-cn_topic_0069869151_p6547420716718"></a><a name="zh-cn_topic_0069869151_p6547420716718"></a>http://JobHistory角色实例IP地址:22500/</p>
</li><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p10653155831016"><a name="zh-cn_topic_0069869151_p10653155831016"></a><a name="zh-cn_topic_0069869151_p10653155831016"></a>http://JobHistory角色实例IP地址:18080/</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p1697218181108"><a name="zh-cn_topic_0069869151_p1697218181108"></a><a name="zh-cn_topic_0069869151_p1697218181108"></a>选择“服务管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row2356032515137"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p2758346615137"><a name="zh-cn_topic_0069869151_p2758346615137"></a><a name="zh-cn_topic_0069869151_p2758346615137"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul7737102661710"></a><a name="zh-cn_topic_0069869151_ul7737102661710"></a><ul id="zh-cn_topic_0069869151_ul7737102661710"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p167901358178"><a name="zh-cn_topic_0069869151_p167901358178"></a><a name="zh-cn_topic_0069869151_p167901358178"></a>https://Hue浮动IP地址:21200</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul1823534721714"></a><a name="zh-cn_topic_0069869151_ul1823534721714"></a><ul id="zh-cn_topic_0069869151_ul1823534721714"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p140483513132"><a name="zh-cn_topic_0069869151_p140483513132"></a><a name="zh-cn_topic_0069869151_p140483513132"></a>https://Hue浮动IP地址:8888</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p9893154914012"><a name="zh-cn_topic_0069869151_p9893154914012"></a><a name="zh-cn_topic_0069869151_p9893154914012"></a>选择“服务管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</p>
</li></ul>
<p id="zh-cn_topic_0069869151_p498289163210"><a name="zh-cn_topic_0069869151_p498289163210"></a><a name="zh-cn_topic_0069869151_p498289163210"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
<div class="note" id="zh-cn_topic_0069869151_note12531395145934"><a name="zh-cn_topic_0069869151_note12531395145934"></a><a name="zh-cn_topic_0069869151_note12531395145934"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0069869151_ul123719115328"></a><a name="zh-cn_topic_0069869151_ul123719115328"></a><ul id="zh-cn_topic_0069869151_ul123719115328"><li>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:FI_HUE”表示为Hue的浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到Hue的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</li></ul>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row2475311015137"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p5884492515137"><a name="zh-cn_topic_0069869151_p5884492515137"></a><a name="zh-cn_topic_0069869151_p5884492515137"></a>流处理集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p170958315137"><a name="zh-cn_topic_0069869151_p170958315137"></a><a name="zh-cn_topic_0069869151_p170958315137"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0069869151_ul1890834616"></a><a name="zh-cn_topic_0069869151_ul1890834616"></a><ul id="zh-cn_topic_0069869151_ul1890834616"><li>适用于MRS 1.8.0以前版本<p id="zh-cn_topic_0069869151_p425855015137"><a name="zh-cn_topic_0069869151_p425855015137"></a><a name="zh-cn_topic_0069869151_p425855015137"></a>http://任一UI角色实例IP地址:29280/index.html</p>
</li></ul>
<a name="zh-cn_topic_0069869151_ul1090514149112"></a><a name="zh-cn_topic_0069869151_ul1090514149112"></a><ul id="zh-cn_topic_0069869151_ul1090514149112"><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p44851318815"><a name="zh-cn_topic_0069869151_p44851318815"></a><a name="zh-cn_topic_0069869151_p44851318815"></a>选择“服务管理 &gt; Storm &gt; Storm WebUI &gt; UI”</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 2**  启用Kerberos认证的集群

<a name="zh-cn_topic_0069869151_table3700702815927"></a>
<table><thead align="left"><tr id="zh-cn_topic_0069869151_row1415862915927"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0069869151_p599826715927"><a name="zh-cn_topic_0069869151_p599826715927"></a><a name="zh-cn_topic_0069869151_p599826715927"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="31.990000000000002%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0069869151_p1609761815927"><a name="zh-cn_topic_0069869151_p1609761815927"></a><a name="zh-cn_topic_0069869151_p1609761815927"></a>站点类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.010000000000005%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0069869151_p2883867315927"><a name="zh-cn_topic_0069869151_p2883867315927"></a><a name="zh-cn_topic_0069869151_p2883867315927"></a>站点地址</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0069869151_row5423120115927"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p3065117815927"><a name="zh-cn_topic_0069869151_p3065117815927"></a><a name="zh-cn_topic_0069869151_p3065117815927"></a>全部类型</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p6682632315927"><a name="zh-cn_topic_0069869151_p6682632315927"></a><a name="zh-cn_topic_0069869151_p6682632315927"></a>MRS Manager</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0069869151_ul6872172263118"></a><a name="zh-cn_topic_0069869151_ul6872172263118"></a><ul id="zh-cn_topic_0069869151_ul6872172263118"><li>适用于MRS 1.8.0以前版本<p id="zh-cn_topic_0069869151_p4422304415927"><a name="zh-cn_topic_0069869151_p4422304415927"></a><a name="zh-cn_topic_0069869151_p4422304415927"></a>https://MRS Manager浮动IP地址:28443/web</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p1377110423213"><a name="zh-cn_topic_0069869151_p1377110423213"></a><a name="zh-cn_topic_0069869151_p1377110423213"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row6246307915927"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p2634466415927"><a name="zh-cn_topic_0069869151_p2634466415927"></a><a name="zh-cn_topic_0069869151_p2634466415927"></a>分析集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p5354307815927"><a name="zh-cn_topic_0069869151_p5354307815927"></a><a name="zh-cn_topic_0069869151_p5354307815927"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0069869151_p2799592151026"><a name="zh-cn_topic_0069869151_p2799592151026"></a><a name="zh-cn_topic_0069869151_p2799592151026"></a>选择“服务管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row4265433515927"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p3244907415927"><a name="zh-cn_topic_0069869151_p3244907415927"></a><a name="zh-cn_topic_0069869151_p3244907415927"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p38932029151026"><a name="zh-cn_topic_0069869151_p38932029151026"></a><a name="zh-cn_topic_0069869151_p38932029151026"></a>选择“服务管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row3305551415927"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p6025095815927"><a name="zh-cn_topic_0069869151_p6025095815927"></a><a name="zh-cn_topic_0069869151_p6025095815927"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p45896025151026"><a name="zh-cn_topic_0069869151_p45896025151026"></a><a name="zh-cn_topic_0069869151_p45896025151026"></a>选择“服务管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row3375162315927"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p4952694915927"><a name="zh-cn_topic_0069869151_p4952694915927"></a><a name="zh-cn_topic_0069869151_p4952694915927"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p21015958151026"><a name="zh-cn_topic_0069869151_p21015958151026"></a><a name="zh-cn_topic_0069869151_p21015958151026"></a>选择“服务管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row57770815927"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p4679435015927"><a name="zh-cn_topic_0069869151_p4679435015927"></a><a name="zh-cn_topic_0069869151_p4679435015927"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p7144396151026"><a name="zh-cn_topic_0069869151_p7144396151026"></a><a name="zh-cn_topic_0069869151_p7144396151026"></a>选择“服务管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row2177874015927"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p1924752515927"><a name="zh-cn_topic_0069869151_p1924752515927"></a><a name="zh-cn_topic_0069869151_p1924752515927"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p39878994151027"><a name="zh-cn_topic_0069869151_p39878994151027"></a><a name="zh-cn_topic_0069869151_p39878994151027"></a>选择“服务管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</p>
<p id="zh-cn_topic_0069869151_p38775106163333"><a name="zh-cn_topic_0069869151_p38775106163333"></a><a name="zh-cn_topic_0069869151_p38775106163333"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
</td>
</tr>
<tr id="zh-cn_topic_0069869151_row569352615927"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p5852244715927"><a name="zh-cn_topic_0069869151_p5852244715927"></a><a name="zh-cn_topic_0069869151_p5852244715927"></a>流处理集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p4269776515927"><a name="zh-cn_topic_0069869151_p4269776515927"></a><a name="zh-cn_topic_0069869151_p4269776515927"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0069869151_p57063425151027"><a name="zh-cn_topic_0069869151_p57063425151027"></a><a name="zh-cn_topic_0069869151_p57063425151027"></a>选择“服务管理 &gt; Storm &gt; Storm WebUI &gt; UI”</p>
</td>
</tr>
</tbody>
</table>

