# 数据迁移到MRS前信息收集<a name="mrs_01_0609"></a>

由于离线大数据搬迁有一定的灵活性，迁移前需要掌握现有集群的详细信息，能够更好的进行迁移决策。

## 业务信息调研<a name="section422555713347"></a>

1.  大数据平台及业务的架构图。
2.  大数据平台和业务的数据流图（包括：峰值和均值流量），识别平台数据接入源。大数据平台数据流入方式（实时数据上报、批量数据抽取），分析平台数据流向。数据在平台内各个组件间的流向。比如使用什么组件采集数据，采集完数据后数据如何流向下一层组件，使用什么组件存储数据，数据处理过程中的工作流等。
3.  业务作业类型：hive sql, spark sql,  spark python等，是否需要使用MRS的第三方包，参考[MRS应用开发样例](https://support.huaweicloud.com/devg3-mrs/mrs_07_010000.html)。
4.  调度系统：需要考虑调度系统对接MRS集群。
5.  迁移后，业务割接允许中断时长，识别平台业务优先级。识别在迁移过程中不能中断的业务，可短时中断的业务，整体业务迁移可接受的迁移时长，梳理业务迁移顺序。
6.  客户端部署要求，参考[集群外节点使用MRS客户端前提条件](安装客户端（3-x之前版本）.md#section3219221104310)。
7.  业务执行时间段和高峰时间段。
8.  大数据集群的数量和大数据集群功能划分，分析平台业务模型。各个集群或各个组件分别负责什么业务，处理什么类型的数据。比如实时/离线数据分别使用什么组件处理，数据格式类型，压缩算法等。

## 集群基本信息收集<a name="section142971440143919"></a>

**表 1**  集群基本信息

<a name="table593719941012"></a>
<table><thead align="left"><tr id="row19938199191014"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p29381915105"><a name="p29381915105"></a><a name="p29381915105"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.2"><p id="p39381499109"><a name="p39381499109"></a><a name="p39381499109"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p174651059154011"><a name="p174651059154011"></a><a name="p174651059154011"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row15938119151010"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p493812961011"><a name="p493812961011"></a><a name="p493812961011"></a>集群名称</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p10938139141018"><a name="p10938139141018"></a><a name="p10938139141018"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p104652059124012"><a name="p104652059124012"></a><a name="p104652059124012"></a>-</p>
</td>
</tr>
<tr id="row11938395102"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p29381495107"><a name="p29381495107"></a><a name="p29381495107"></a>集群版本</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p199382095108"><a name="p199382095108"></a><a name="p199382095108"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1046513592402"><a name="p1046513592402"></a><a name="p1046513592402"></a>MRS、CDM、FI等集群的版本。</p>
</td>
</tr>
<tr id="row15938193101"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p09051111124318"><a name="p09051111124318"></a><a name="p09051111124318"></a>节点数及规格</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p290521119433"><a name="p290521119433"></a><a name="p290521119433"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p690561124317"><a name="p690561124317"></a><a name="p690561124317"></a>必填项，调研现有集群节点数和节点规格。</p>
<p id="p199051311194317"><a name="p199051311194317"></a><a name="p199051311194317"></a>如果集群硬件异构，请填写多种规格和对应节点数。请参见<a href="#table31651551561">表2</a></p>
<p id="p19058112438"><a name="p19058112438"></a><a name="p19058112438"></a>例如：</p>
<p id="p49051611124312"><a name="p49051611124312"></a><a name="p49051611124312"></a>2台 32U64G机器部署NameNode + ResourceManager</p>
<p id="p1905151112435"><a name="p1905151112435"></a><a name="p1905151112435"></a>2台 32U64G机器部署Hiveserver</p>
<p id="p2090518112431"><a name="p2090518112431"></a><a name="p2090518112431"></a>20台 16U32G 机器部署DataNode和NodeManager</p>
</td>
</tr>
<tr id="row7938992108"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p39057112433"><a name="p39057112433"></a><a name="p39057112433"></a>是否开启Kerberos认证</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p29056111438"><a name="p29056111438"></a><a name="p29056111438"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p690591111439"><a name="p690591111439"></a><a name="p690591111439"></a>必填项： 是或否</p>
</td>
</tr>
<tr id="row1093829141011"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p119056114437"><a name="p119056114437"></a><a name="p119056114437"></a>权限控制及说明</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p19905131134315"><a name="p19905131134315"></a><a name="p19905131134315"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p139051611174317"><a name="p139051611174317"></a><a name="p139051611174317"></a>必填项，调研各个开启ACL权限控制的组件和配置。</p>
<p id="p129365384511"><a name="p129365384511"></a><a name="p129365384511"></a>涉及： Yarn 、Hive、 Impala、 HBase组件。</p>
<p id="p3905161134319"><a name="p3905161134319"></a><a name="p3905161134319"></a>使用ranger、sentry或组件开源的权限能力进行权限控制。</p>
</td>
</tr>
<tr id="row593912915104"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p10905131194318"><a name="p10905131194318"></a><a name="p10905131194318"></a>所在region/AZ</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p18905151194311"><a name="p18905151194311"></a><a name="p18905151194311"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p11906111119434"><a name="p11906111119434"></a><a name="p11906111119434"></a>云上资源填写项</p>
</td>
</tr>
<tr id="row193919911012"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1690681134318"><a name="p1690681134318"></a><a name="p1690681134318"></a>虚拟私有云</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p199060112433"><a name="p199060112433"></a><a name="p199060112433"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p15906611174315"><a name="p15906611174315"></a><a name="p15906611174315"></a>云上资源填写项</p>
</td>
</tr>
<tr id="row138601901431"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p49061311104317"><a name="p49061311104317"></a><a name="p49061311104317"></a>子网</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p8906141154317"><a name="p8906141154317"></a><a name="p8906141154317"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p89061411144316"><a name="p89061411144316"></a><a name="p89061411144316"></a>云上资源填写项</p>
</td>
</tr>
<tr id="row16513164312"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p190618113430"><a name="p190618113430"></a><a name="p190618113430"></a>安全组</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.2 "><p id="p79061711104318"><a name="p79061711104318"></a><a name="p79061711104318"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p19906171113434"><a name="p19906171113434"></a><a name="p19906171113434"></a>云上资源填写项</p>
</td>
</tr>
</tbody>
</table>

**表 2**  硬件信息调研表

<a name="table31651551561"></a>
<table><tbody><tr id="row1117014558568"><td class="cellrowborder" valign="top"><p id="p18878114313582"><a name="p18878114313582"></a><a name="p18878114313582"></a>节点组</p>
</td>
<td class="cellrowborder" valign="top"><p id="p78781143205812"><a name="p78781143205812"></a><a name="p78781143205812"></a>CPU和内存信息</p>
</td>
<td class="cellrowborder" colspan="2" valign="top"><p id="p86908335599"><a name="p86908335599"></a><a name="p86908335599"></a>磁盘和网络（按节点组统计）</p>
</td>
<td class="cellrowborder" colspan="3" valign="top"><p id="p34981044105919"><a name="p34981044105919"></a><a name="p34981044105919"></a>HDFS</p>
</td>
<td class="cellrowborder" colspan="2" valign="top"><p id="p17726572000"><a name="p17726572000"></a><a name="p17726572000"></a>Yarn</p>
</td>
</tr>
<tr id="row12170455185613"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p198191449211"><a name="p198191449211"></a><a name="p198191449211"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p481812441426"><a name="p481812441426"></a><a name="p481812441426"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1878143155815"><a name="p1878143155815"></a><a name="p1878143155815"></a>磁盘信息（数据盘大小，磁盘IO，当前磁盘使用率和IO情况）</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p2087810433589"><a name="p2087810433589"></a><a name="p2087810433589"></a>网络（网卡带宽大小，网络读写速度和峰值）</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p19879843105812"><a name="p19879843105812"></a><a name="p19879843105812"></a>NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p587914319588"><a name="p587914319588"></a><a name="p587914319588"></a>DadtaNode</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p20879143135813"><a name="p20879143135813"></a><a name="p20879143135813"></a>JouralNode</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p4879194317589"><a name="p4879194317589"></a><a name="p4879194317589"></a>NodeManager</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p108791443195814"><a name="p108791443195814"></a><a name="p108791443195814"></a>ResourceManager</p>
</td>
</tr>
<tr id="row267604025819"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p287984318583"><a name="p287984318583"></a><a name="p287984318583"></a>master1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p11879043195811"><a name="p11879043195811"></a><a name="p11879043195811"></a>(16U64G)</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p15879164315587"><a name="p15879164315587"></a><a name="p15879164315587"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p7879164315587"><a name="p7879164315587"></a><a name="p7879164315587"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p14879204395818"><a name="p14879204395818"></a><a name="p14879204395818"></a>1</p>
</td>
</tr>
<tr id="row12963104075812"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p178791043135816"><a name="p178791043135816"></a><a name="p178791043135816"></a>master2</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p13879144335814"><a name="p13879144335814"></a><a name="p13879144335814"></a>(16U64G)</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1787964315582"><a name="p1787964315582"></a><a name="p1787964315582"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p19879143105819"><a name="p19879143105819"></a><a name="p19879143105819"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1880154365814"><a name="p1880154365814"></a><a name="p1880154365814"></a>1</p>
</td>
</tr>
<tr id="row1032454116583"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p15880114375812"><a name="p15880114375812"></a><a name="p15880114375812"></a>master3</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p58803434589"><a name="p58803434589"></a><a name="p58803434589"></a>(16U64G)</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p16880143105820"><a name="p16880143105820"></a><a name="p16880143105820"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
</tr>
<tr id="row766034116589"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p2880243175819"><a name="p2880243175819"></a><a name="p2880243175819"></a>Core-group1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p78801443105812"><a name="p78801443105812"></a><a name="p78801443105812"></a>(32U128G)*数量</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p88811243205813"><a name="p88811243205813"></a><a name="p88811243205813"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1881843195813"><a name="p1881843195813"></a><a name="p1881843195813"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
</tr>
<tr id="row11171105545620"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p0883154345813"><a name="p0883154345813"></a><a name="p0883154345813"></a>Core-group1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p28831343125814"><a name="p28831343125814"></a><a name="p28831343125814"></a>(32U129G)</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
</tr>
<tr id="row1417145545613"><td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1688417439582"><a name="p1688417439582"></a><a name="p1688417439582"></a>Core-group1</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%"><p id="p1288413439584"><a name="p1288413439584"></a><a name="p1288413439584"></a>(32U130G)</p>
</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
<td class="cellrowborder" valign="top" width="11.111111111111112%">&nbsp;&nbsp;</td>
</tr>
</tbody>
</table>

## 大数据组件信息<a name="section11219161824516"></a>

使用的大数据组件信息和规划的新版本大数据集群版本信息比较，主要识别版本差异可能对迁移过程的影响，以及对迁移后业务兼容性的影响。

**表 3**  大数据组件信息

<a name="table131134714511"></a>
<table><thead align="left"><tr id="row1621747114511"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p32164717457"><a name="p32164717457"></a><a name="p32164717457"></a>大数据组件</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p12264754511"><a name="p12264754511"></a><a name="p12264754511"></a>源端集群版本</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p103372044164616"><a name="p103372044164616"></a><a name="p103372044164616"></a>目的端集群版本</p>
<p id="p3212473459"><a name="p3212473459"></a><a name="p3212473459"></a>（以MRS 1.9.2为例）</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p2749161454615"><a name="p2749161454615"></a><a name="p2749161454615"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row7294724516"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p182154704511"><a name="p182154704511"></a><a name="p182154704511"></a>HDFS/OBS（或其他文件存储系统）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p11217472458"><a name="p11217472458"></a><a name="p11217472458"></a>Hadoop 2.8.3</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p225471457"><a name="p225471457"></a><a name="p225471457"></a>Hadoop 2.8.3</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p574941420462"><a name="p574941420462"></a><a name="p574941420462"></a>-</p>
</td>
</tr>
<tr id="row12218477452"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p62847134512"><a name="p62847134512"></a><a name="p62847134512"></a>Hive</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p22747154514"><a name="p22747154514"></a><a name="p22747154514"></a>1.2.1</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p621847204512"><a name="p621847204512"></a><a name="p621847204512"></a>2.3.3</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p574991434617"><a name="p574991434617"></a><a name="p574991434617"></a>存储元数据的数据库：mysql</p>
</td>
</tr>
<tr id="row1284794519"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p32104712457"><a name="p32104712457"></a><a name="p32104712457"></a>HBase</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p112144734518"><a name="p112144734518"></a><a name="p112144734518"></a>1.3.1</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p192134711452"><a name="p192134711452"></a><a name="p192134711452"></a>1.3.1</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p157491014154618"><a name="p157491014154618"></a><a name="p157491014154618"></a>-</p>
</td>
</tr>
<tr id="row16220476457"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p625478453"><a name="p625478453"></a><a name="p625478453"></a>Spark</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p14213478456"><a name="p14213478456"></a><a name="p14213478456"></a>2.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1021347184511"><a name="p1021347184511"></a><a name="p1021347184511"></a>2.2.2</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p4749161415468"><a name="p4749161415468"></a><a name="p4749161415468"></a>-</p>
</td>
</tr>
<tr id="row6586556184718"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p785215094813"><a name="p785215094813"></a><a name="p785215094813"></a>Kafka</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p1485220124819"><a name="p1485220124819"></a><a name="p1485220124819"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p185240134818"><a name="p185240134818"></a><a name="p185240134818"></a>1.1.0</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1585290134816"><a name="p1585290134816"></a><a name="p1585290134816"></a>-</p>
</td>
</tr>
<tr id="row2086815617475"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p10852110124811"><a name="p10852110124811"></a><a name="p10852110124811"></a>Oozie</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p118526017489"><a name="p118526017489"></a><a name="p118526017489"></a>2.x</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p98520017484"><a name="p98520017484"></a><a name="p98520017484"></a>自建</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p08521102484"><a name="p08521102484"></a><a name="p08521102484"></a>-</p>
</td>
</tr>
<tr id="row1918205714474"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p168522064818"><a name="p168522064818"></a><a name="p168522064818"></a>mysql</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p1585290154819"><a name="p1585290154819"></a><a name="p1585290154819"></a>5.7.1</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p2852204486"><a name="p2852204486"></a><a name="p2852204486"></a>RDS</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p11852180184811"><a name="p11852180184811"></a><a name="p11852180184811"></a>-</p>
</td>
</tr>
<tr id="row1424295764717"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1585215094820"><a name="p1585215094820"></a><a name="p1585215094820"></a>Flink</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p885280154814"><a name="p885280154814"></a><a name="p885280154814"></a>1.7</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p128528094819"><a name="p128528094819"></a><a name="p128528094819"></a>1.7</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p19852808486"><a name="p19852808486"></a><a name="p19852808486"></a>-</p>
</td>
</tr>
<tr id="row12374710454"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p13144710458"><a name="p13144710458"></a><a name="p13144710458"></a>...</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p17319470456"><a name="p17319470456"></a><a name="p17319470456"></a>...</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p183154714455"><a name="p183154714455"></a><a name="p183154714455"></a>...</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1674951418461"><a name="p1674951418461"></a><a name="p1674951418461"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 待迁移的存量数据及数据量统计<a name="section199961033124914"></a>

如果使用HDFS作为文件存储系统，可以使用\` hadoop fs -du -h /user/test\`命令统计路径下的文件大小。

**表 4**  现有数据量统计

<a name="table1892112264255"></a>
<table><thead align="left"><tr id="row20919182610251"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p2920141214266"><a name="p2920141214266"></a><a name="p2920141214266"></a>大数据组件</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p14920181212616"><a name="p14920181212616"></a><a name="p14920181212616"></a>待迁移数据的路径</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p8920131242615"><a name="p8920131242615"></a><a name="p8920131242615"></a>数据量大小</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p39206128261"><a name="p39206128261"></a><a name="p39206128261"></a>文件个数或表个数</p>
</th>
</tr>
</thead>
<tbody><tr id="row17919202602512"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p11601436102618"><a name="p11601436102618"></a><a name="p11601436102618"></a>HDFS/OBS（或其他文件存储系统）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p156011363267"><a name="p156011363267"></a><a name="p156011363267"></a>/user/helloworld</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p660183617262"><a name="p660183617262"></a><a name="p660183617262"></a>xx</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p18601143616264"><a name="p18601143616264"></a><a name="p18601143616264"></a>总共：xxxx个文件</p>
<p id="p1560143618267"><a name="p1560143618267"></a><a name="p1560143618267"></a>小于2M的文件数量：xxx个</p>
</td>
</tr>
<tr id="row5920162672520"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p760103662619"><a name="p760103662619"></a><a name="p760103662619"></a>Hive</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p560111366269"><a name="p560111366269"></a><a name="p560111366269"></a>/user/hive/warehouse/</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p4601153610260"><a name="p4601153610260"></a><a name="p4601153610260"></a>xx</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1760123652617"><a name="p1760123652617"></a><a name="p1760123652617"></a>表个数：xxx</p>
</td>
</tr>
<tr id="row139201026102519"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1460163619269"><a name="p1460163619269"></a><a name="p1460163619269"></a>HBase</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p76021536152617"><a name="p76021536152617"></a><a name="p76021536152617"></a>/hbase</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p18602143682617"><a name="p18602143682617"></a><a name="p18602143682617"></a>xx</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p12602183611268"><a name="p12602183611268"></a><a name="p12602183611268"></a>表个数：xx</p>
<p id="p2060253682618"><a name="p2060253682618"></a><a name="p2060253682618"></a>Region个数：xx</p>
</td>
</tr>
</tbody>
</table>

## 每天新增数据量统计<a name="section1174882612504"></a>

每天新增数据量主要评估数据增长速度（可以按天/小时等周期维度）。在第一次全量迁移数据后，后续可以定期搬迁老集群新增数据，直到业务完成最终割接。

**表 5**  新增数据量统计

<a name="table06823170318"></a>
<table><thead align="left"><tr id="row168112171733"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p868113171733"><a name="p868113171733"></a><a name="p868113171733"></a>大数据组件</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p10681201720313"><a name="p10681201720313"></a><a name="p10681201720313"></a>待迁移的数据路径</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p186811171535"><a name="p186811171535"></a><a name="p186811171535"></a>新增数据量大小</p>
</th>
</tr>
</thead>
<tbody><tr id="row06817171313"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1868111176318"><a name="p1868111176318"></a><a name="p1868111176318"></a>HDFS/OBS（或其他文件存储系统）</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p56818174310"><a name="p56818174310"></a><a name="p56818174310"></a>/user/helloworld</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p66811417135"><a name="p66811417135"></a><a name="p66811417135"></a>xx</p>
</td>
</tr>
<tr id="row1368221718319"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1068110171436"><a name="p1068110171436"></a><a name="p1068110171436"></a>Hive</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p268113171732"><a name="p268113171732"></a><a name="p268113171732"></a>/user/hive/warehouse/</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p768120171331"><a name="p768120171331"></a><a name="p768120171331"></a>xx</p>
</td>
</tr>
<tr id="row3682717636"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p968231713313"><a name="p968231713313"></a><a name="p968231713313"></a>HBase</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p14682217639"><a name="p14682217639"></a><a name="p14682217639"></a>/hbase</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p196821617736"><a name="p196821617736"></a><a name="p196821617736"></a>xx</p>
</td>
</tr>
</tbody>
</table>

## 网络出口带宽能力<a name="section37121818195118"></a>

-   迁移数据可以使用的最大网络带宽和专线带宽（是否可调）
-   迁移数据作业每天可以运行的时间段

## 流式Kafka集群信息收集<a name="section102543292527"></a>

**表 6**  流式Kafka集群信息

<a name="table1749924812522"></a>
<table><thead align="left"><tr id="row5714134817526"><th class="cellrowborder" valign="top" width="49.919999999999995%" id="mcps1.2.3.1.1"><p id="p7714114825218"><a name="p7714114825218"></a><a name="p7714114825218"></a>收集信息项</p>
</th>
<th class="cellrowborder" valign="top" width="50.080000000000005%" id="mcps1.2.3.1.2"><p id="p1871464812526"><a name="p1871464812526"></a><a name="p1871464812526"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1471424813523"><td class="cellrowborder" valign="top" width="49.919999999999995%" headers="mcps1.2.3.1.1 "><p id="p0714144812527"><a name="p0714144812527"></a><a name="p0714144812527"></a>kafka的topics数量和名称</p>
</td>
<td class="cellrowborder" valign="top" width="50.080000000000005%" headers="mcps1.2.3.1.2 "><p id="p8714134865219"><a name="p8714134865219"></a><a name="p8714134865219"></a>-</p>
</td>
</tr>
<tr id="row127147483527"><td class="cellrowborder" valign="top" width="49.919999999999995%" headers="mcps1.2.3.1.1 "><p id="p167141448155218"><a name="p167141448155218"></a><a name="p167141448155218"></a>kafka的本地数据暂存时间，如果每个topic配置不一样，按topic粒度收集</p>
</td>
<td class="cellrowborder" valign="top" width="50.080000000000005%" headers="mcps1.2.3.1.2 "><p id="p3714848165218"><a name="p3714848165218"></a><a name="p3714848165218"></a>-</p>
</td>
</tr>
<tr id="row37141148125218"><td class="cellrowborder" valign="top" width="49.919999999999995%" headers="mcps1.2.3.1.1 "><p id="p171474865212"><a name="p171474865212"></a><a name="p171474865212"></a>每个topic的副本数和partition数量。（默认为2，副本数越多数据越可靠，也会消耗磁盘空间），如果每个topic配置不一样，按topic粒度收集</p>
</td>
<td class="cellrowborder" valign="top" width="50.080000000000005%" headers="mcps1.2.3.1.2 "><p id="p117141548115211"><a name="p117141548115211"></a><a name="p117141548115211"></a>-</p>
</td>
</tr>
<tr id="row157149484522"><td class="cellrowborder" valign="top" width="49.919999999999995%" headers="mcps1.2.3.1.1 "><p id="p171474816524"><a name="p171474816524"></a><a name="p171474816524"></a>Kafka生产和消费的流量大小，细化到topic级别</p>
</td>
<td class="cellrowborder" valign="top" width="50.080000000000005%" headers="mcps1.2.3.1.2 "><p id="p13714648165217"><a name="p13714648165217"></a><a name="p13714648165217"></a>-</p>
</td>
</tr>
<tr id="row271474814523"><td class="cellrowborder" valign="top" width="49.919999999999995%" headers="mcps1.2.3.1.1 "><p id="p16714548205210"><a name="p16714548205210"></a><a name="p16714548205210"></a>kafka客户端ACK配置acks</p>
</td>
<td class="cellrowborder" valign="top" width="50.080000000000005%" headers="mcps1.2.3.1.2 "><p id="p14715748165219"><a name="p14715748165219"></a><a name="p14715748165219"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 数据迁移模型样例<a name="section85577110554"></a>

-   一个离线分析平台的客户业务系统框图，由spark streaming消费kafka数据存入HDFS上，HDFS上进行小文件合并后由Hive load加载到Hive表中，运营可以通过presto进行hive数据查询。

    **图 1**  源集群业务图<a name="fig29177371314"></a>  
    ![](figures/源集群业务图.png "源集群业务图")

-   针对大数据离线平台包括HDFS和Hive数据需要迁移，Kafka、 spark streaming、HDFS、Hive、presto的业务程序要在目的端集群上部署。

    **图 2**  迁移示意图<a name="fig5927155012141"></a>  
    ![](figures/迁移示意图.png "迁移示意图")


