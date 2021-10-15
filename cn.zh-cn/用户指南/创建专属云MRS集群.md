# 创建专属云MRS集群<a name="mrs_01_0911"></a>

本章节为您介绍如何在您的专属资源上创建一个MRS集群。

-   如果您希望MRS服务运行在隔离的专属区域，请您先申请专属计算集群，再创建专属云MRS集群。

    了解和申请专属计算集群，请参见《专属计算集群用户指南》。


-   如果您希望MRS服务拥有独享的存储设备，请您在开通专属计算集群后申请专属企业存储，再创建专属云MRS集群。

    了解和申请专属企业存储，请参见《专属企业存储用户指南》。


## 快速购买专属云MRS集群<a name="section13749157144617"></a>

1.  登录MRS管理控制台。
2.  单击“购买集群“，进入“购买集群“页面。
3.  在购买集群页面，选择“快速购买”页签。
4.  参考下列参数说明配置集群基本信息，参数详细信息请参考[自定义购买集群](自定义购买集群.md)。
    -   区域：默认即可。
    -   计费模式：根据需要选择“按需计费“或“包年/包月“模式。
    -   购买时长：购买集群的时长，最短时长为1个月，最长时长为一年。
    -   集群名称：可以设置为系统默认名称，但为了区分和记忆，建议带上项目拼音缩写或者日期等。
    -   集群版本：默认选择最新版本即可（不同版本集群提供的组件有所不同，请根据需要选择集群版本）。
    -   组件选择：根据需要选择“Hadoop分析集群”、“HBase查询集群”或“Kafka流式集群”。
    -   磁盘类型：默认即可。MRS 3.x版本暂时没有该参数。
    -   集群节点：请根据自身需要选择集群节点规格数量等。
    -   集群高可用：默认即可。MRS 3.x版本暂时没有该参数。
    -   用户名：默认为“root/admin”，root用于远程登录ECS机器，admin用于登录集群管理页面。
    -   密码：设置root用户和admin用户密码。
    -   确认密码：再次输入设置的root用户和admin用户密码。

5.  单击“立即购买”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果您对价格有疑问，可以单击页面左下角“了解计费详情”，根据计费详情来了解产品价格。

6.  单击“返回集群列表”，可以查看到集群创建的状态。

    集群创建需要时间，所创集群的初始状态为“启动中”，创建成功后状态更新为“运行中”，请您耐心等待。


## 自定义购买专属云MRS集群<a name="section875182920158"></a>

1.  登录MRS管理控制台。
2.  单击“购买集群“，进入“购买集群“页面。
3.  在购买集群页面，选择“自定义购买”页签。
4.  参考[自定义购买集群软件配置](#section319610428513)配置集群信息后，单击“下一步”。
5.  参考[自定义购买集群硬件配置](#section1339818162220)配置集群信息后，单击“下一步”。
6.  参考[自定义购买集群高级配置（可选）](#section861294242018)配置集群信息后，单击“立即购买“。

    当集群开启Kerberos认证时，需要确认是否需要开启Kerberos认证，若确认开启请单击“继续”，若无需开启Kerberos认证请单击“返回”关闭Kerberos认证后再创建集群。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果您对价格有疑问，可以单击页面左下角“了解计费详情”，根据计费详情来了解产品价格。

7.  单击“返回集群列表”，可以查看到集群创建的状态。

    集群创建的状态过程请参见[表1](集群列表简介.md#table3950169215120)中的“状态”参数说明。

    集群创建需要时间，所创集群的初始状态为“启动中”，创建成功后状态更新为“运行中”，请您耐心等待。


## 自定义购买集群软件配置<a name="section319610428513"></a>

**表 1**  MRS集群软件配置

<a name="table93258111263"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173525263_row1477942314570"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0173525263_p277952314578"><a name="zh-cn_topic_0173525263_p277952314578"></a><a name="zh-cn_topic_0173525263_p277952314578"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0173525263_p19779182313578"><a name="zh-cn_topic_0173525263_p19779182313578"></a><a name="zh-cn_topic_0173525263_p19779182313578"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173525263_row13287142793915"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1545319287398"><a name="zh-cn_topic_0173525263_p1545319287398"></a><a name="zh-cn_topic_0173525263_p1545319287398"></a>区域</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p14453728143913"><a name="zh-cn_topic_0173525263_p14453728143913"></a><a name="zh-cn_topic_0173525263_p14453728143913"></a>选择<a href="https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0184026189.html" target="_blank" rel="noopener noreferrer">区域</a>。</p>
<p id="zh-cn_topic_0173525263_p174542028183916"><a name="zh-cn_topic_0173525263_p174542028183916"></a><a name="zh-cn_topic_0173525263_p174542028183916"></a>不同区域的云服务产品之间内网互不相通。请就近选择靠近您业务的区域，可减少网络时延，提高访问速度。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row077982319575"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1632137202218"><a name="zh-cn_topic_0173525263_p1632137202218"></a><a name="zh-cn_topic_0173525263_p1632137202218"></a>集群名称</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p2063816718226"><a name="zh-cn_topic_0173525263_p2063816718226"></a><a name="zh-cn_topic_0173525263_p2063816718226"></a>集群名称不允许重复。</p>
<p id="zh-cn_topic_0173525263_p864015712219"><a name="zh-cn_topic_0173525263_p864015712219"></a><a name="zh-cn_topic_0173525263_p864015712219"></a>只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
<p id="zh-cn_topic_0173525263_p17643576224"><a name="zh-cn_topic_0173525263_p17643576224"></a><a name="zh-cn_topic_0173525263_p17643576224"></a>默认名称为mrs_xxxx，xxxx为字母和数字的四位随机组合数，系统自动组合。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row178019237579"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p2065916742212"><a name="zh-cn_topic_0173525263_p2065916742212"></a><a name="zh-cn_topic_0173525263_p2065916742212"></a>集群版本</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p11302191119226"><a name="zh-cn_topic_0173525263_p11302191119226"></a><a name="zh-cn_topic_0173525263_p11302191119226"></a>目前支持MRS 1.9.2、MRS 3.1.0版本。默认值为当前最新版本。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row3780823165720"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p197518710224"><a name="zh-cn_topic_0173525263_p197518710224"></a><a name="zh-cn_topic_0173525263_p197518710224"></a>集群类型</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><div class="p" id="zh-cn_topic_0173525263_p2978676228"><a name="zh-cn_topic_0173525263_p2978676228"></a><a name="zh-cn_topic_0173525263_p2978676228"></a>提供几种集群类型：<a name="zh-cn_topic_0173525263_ul6981207172215"></a><a name="zh-cn_topic_0173525263_ul6981207172215"></a><ul id="zh-cn_topic_0173525263_ul6981207172215"><li>分析集群：用来做离线数据分析，提供的是Hadoop体系的组件。</li><li>流式集群：用来做流处理任务，提供的是流式处理组件。</li><li>混合集群：既可以用来做离线数据分析，也可以用来做流处理任务，提供的是Hadoop体系的组件和流式处理组件。建议同时需要做离线数据分析和流处理任务时使用混合集群。</li><li>自定义：用户可按照业务需求调整集群服务的部署方式，具体请参见<a href="创建自定义拓扑集群.md">创建自定义拓扑集群</a>。（目前仅MRS 3.x版本支持）</li></ul>
</div>
<div class="note" id="zh-cn_topic_0173525263_note3116811229"><a name="zh-cn_topic_0173525263_note3116811229"></a><a name="zh-cn_topic_0173525263_note3116811229"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173525263_p18311892216"><a name="zh-cn_topic_0173525263_p18311892216"></a><a name="zh-cn_topic_0173525263_p18311892216"></a>MRS流式集群不支持<span class="parmname" id="zh-cn_topic_0173525263_parmname116148122214"><a name="zh-cn_topic_0173525263_parmname116148122214"></a><a name="zh-cn_topic_0173525263_parmname116148122214"></a>“作业管理”</span>和<span class="parmname" id="zh-cn_topic_0173525263_parmname1510108152218"><a name="zh-cn_topic_0173525263_parmname1510108152218"></a><a name="zh-cn_topic_0173525263_parmname1510108152218"></a>“文件管理”</span>功能<sub id="zh-cn_topic_0173525263_sub162001738173"><a name="zh-cn_topic_0173525263_sub162001738173"></a><a name="zh-cn_topic_0173525263_sub162001738173"></a>。</sub></p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row19962132916585"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p18240812214"><a name="zh-cn_topic_0173525263_p18240812214"></a><a name="zh-cn_topic_0173525263_p18240812214"></a>组件选择</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p530128172211"><a name="zh-cn_topic_0173525263_p530128172211"></a><a name="zh-cn_topic_0173525263_p530128172211"></a>MRS配套的组件如下，MRS不同版本集群支持的组件版本请参见<a href="https://support.huaweicloud.com/productdesc-mrs/mrs_08_0005.html" target="_blank" rel="noopener noreferrer">MRS组件版本一览表</a>：</p>
<div class="p" id="zh-cn_topic_0173525263_p17754193712915"><a name="zh-cn_topic_0173525263_p17754193712915"></a><a name="zh-cn_topic_0173525263_p17754193712915"></a>分析集群组件<a name="zh-cn_topic_0173525263_ul107601137694"></a><a name="zh-cn_topic_0173525263_ul107601137694"></a><ul id="zh-cn_topic_0173525263_ul107601137694"><li>Presto：开源、分布式SQL查询引擎</li><li>Hadoop：分布式系统基础架构</li><li>Spark：内存分布式系统框架</li><li>Hive：建立在Hadoop上的数据仓库框架</li><li>Opentsdb：可扩展的分布式时间序列数据库，可以存储和服务于大量时间序列数据，而不会丢失粒度。</li><li>HBase：分布式列数据库</li><li>Tez：提供有向无环图的分布式计算框架</li><li>Hue：提供Hadoop UI能力，让用户通过浏览器分析处理Hadoop集群数据</li><li>Loader：基于开源sqoop 1.99.7开发，专为Apache Hadoop和结构化数据库（如关系型数据库）设计的高效传输大量数据的工具。<p id="zh-cn_topic_0173525263_p148558372910"><a name="zh-cn_topic_0173525263_p148558372910"></a><a name="zh-cn_topic_0173525263_p148558372910"></a>Hadoop为必选组件，且Spark与Hive组件需要配套使用。请根据业务选择搭配组件。</p>
</li><li>Flink：分布式大数据处理引擎，可对有限数据流和无限数据流进行有状态计算。</li><li>Alluxio：一个基于内存的分布式存储系统。</li><li>Ranger：一个基于Hadoop平台监控和管理数据安全的框架。（Ranger组件当前不支持开启Kerberos认证。）</li><li>Impala：一种处理大量数据的SQL查询引擎。</li><li>Kudu：一种列存储管理器。</li></ul>
</div>
<div class="p" id="zh-cn_topic_0173525263_p128580371792"><a name="zh-cn_topic_0173525263_p128580371792"></a><a name="zh-cn_topic_0173525263_p128580371792"></a>流式集群组件<a name="zh-cn_topic_0173525263_ul1586213370918"></a><a name="zh-cn_topic_0173525263_ul1586213370918"></a><ul id="zh-cn_topic_0173525263_ul1586213370918"><li>Kafka：提供分布式消息订阅的系统。</li><li>KafkaManager：Kafka集群监控管理工具。</li><li>Storm：提供分布式实时计算的系统。</li><li>Flume：提供分布式、高可用、高可靠的海量日志采集、聚合和传输系统。</li></ul>
</div>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1435212408419"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p09151334184818"><a name="zh-cn_topic_0173525263_p09151334184818"></a><a name="zh-cn_topic_0173525263_p09151334184818"></a>使用外部数据源存储元数据</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p491518342484"><a name="zh-cn_topic_0173525263_p491518342484"></a><a name="zh-cn_topic_0173525263_p491518342484"></a>是否使用外部数据源存储元数据。通过单击<a name="zh-cn_topic_0173525263_image15322271545"></a><a name="zh-cn_topic_0173525263_image15322271545"></a><span><img id="zh-cn_topic_0173525263_image15322271545" src="figures/icon_mrs_disable_hec4.png"></span>开启该功能，当该功能开启时，若集群异常或删除时将不影响元数据，适用于存储计算分离的场景。</p>
<p id="zh-cn_topic_0173525263_p1929716115717"><a name="zh-cn_topic_0173525263_p1929716115717"></a><a name="zh-cn_topic_0173525263_p1929716115717"></a>支持Hive或Ranger组件的集群支持该功能。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row9292195355510"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1729315532557"><a name="zh-cn_topic_0173525263_p1729315532557"></a><a name="zh-cn_topic_0173525263_p1729315532557"></a>组件名</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p34213569566"><a name="zh-cn_topic_0173525263_p34213569566"></a><a name="zh-cn_topic_0173525263_p34213569566"></a>当“使用外部数据源存储元数据”功能开启时，该参数有效。用于表示可以设置外部数据源的组件类型。</p>
<a name="zh-cn_topic_0173525263_ul13894124220567"></a><a name="zh-cn_topic_0173525263_ul13894124220567"></a><ul id="zh-cn_topic_0173525263_ul13894124220567"><li>Hive</li><li>Ranger</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row154493815418"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1321713413482"><a name="zh-cn_topic_0173525263_p1321713413482"></a><a name="zh-cn_topic_0173525263_p1321713413482"></a>数据连接类型</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p93371537165616"><a name="zh-cn_topic_0173525263_p93371537165616"></a><a name="zh-cn_topic_0173525263_p93371537165616"></a>当“使用外部数据源存储元数据”功能开启时，该参数有效。用于表示外部数据源的类型。</p>
<a name="zh-cn_topic_0173525263_ul162477143598"></a><a name="zh-cn_topic_0173525263_ul162477143598"></a><ul id="zh-cn_topic_0173525263_ul162477143598"><li>Hive组件支持的数据连接类型：<a name="zh-cn_topic_0173525263_ul1517911541311"></a><a name="zh-cn_topic_0173525263_ul1517911541311"></a><ul id="zh-cn_topic_0173525263_ul1517911541311"><li>RDS服务PostgreSQL数据库</li><li>RDS服务MySQL数据库</li><li>本地数据库</li></ul>
</li><li>Ranger组件支持的数据连接类型：<a name="zh-cn_topic_0173525263_ul1873931412"></a><a name="zh-cn_topic_0173525263_ul1873931412"></a><ul id="zh-cn_topic_0173525263_ul1873931412"><li>RDS服务MySQL数据库</li><li>本地数据库</li></ul>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row25882361410"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p12108183315483"><a name="zh-cn_topic_0173525263_p12108183315483"></a><a name="zh-cn_topic_0173525263_p12108183315483"></a>数据连接实例</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p3108173364815"><a name="zh-cn_topic_0173525263_p3108173364815"></a><a name="zh-cn_topic_0173525263_p3108173364815"></a>当“数据连接类型”选择“RDS服务PostgreSQL数据库”或“RDS服务MySQL数据库”时，该参数有效。用于表示MRS集群与RDS服务数据库连接的名称，该实例必选先创建才能在此处引用。可单击“创建数据连接”进行创建，具体请参考<a href="配置数据连接.md">配置数据连接</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row2341133015583"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p17692775227"><a name="zh-cn_topic_0173525263_p17692775227"></a><a name="zh-cn_topic_0173525263_p17692775227"></a>Kerberos认证</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p515256154517"><a name="zh-cn_topic_0173525263_p515256154517"></a><a name="zh-cn_topic_0173525263_p515256154517"></a>登录Manager管理页面时是否启用Kerberos认证。</p>
<a name="zh-cn_topic_0173525263_ul137018762216"></a><a name="zh-cn_topic_0173525263_ul137018762216"></a><ul id="zh-cn_topic_0173525263_ul137018762216"><li><a name="zh-cn_topic_0173525263_image141881543400"></a><a name="zh-cn_topic_0173525263_image141881543400"></a><span><img id="zh-cn_topic_0173525263_image141881543400" src="figures/icon_mrs_disable_hec4.png"></span>：<span class="parmname" id="zh-cn_topic_0173525263_parmname1772018732216"><a name="zh-cn_topic_0173525263_parmname1772018732216"></a><a name="zh-cn_topic_0173525263_parmname1772018732216"></a>“Kerberos认证”</span>关闭时，普通用户可使用MRS集群的所有功能。建议单用户场景下使用。不启用Kerberos认证时的安全配置建议请参见<a href="集群（未启用Kerberos认证）安全配置建议.md">集群（未启用Kerberos认证）安全配置建议</a>。</li><li><a name="zh-cn_topic_0173525263_image18280143715110"></a><a name="zh-cn_topic_0173525263_image18280143715110"></a><span><img id="zh-cn_topic_0173525263_image18280143715110" src="figures/icon_mrs_enable_hec4.png"></span>：<span class="parmname" id="zh-cn_topic_0173525263_parmname074211710221"><a name="zh-cn_topic_0173525263_parmname074211710221"></a><a name="zh-cn_topic_0173525263_parmname074211710221"></a>“Kerberos认证”</span>开启时，普通用户无权限使用MRS集群的<span class="menucascade" id="zh-cn_topic_0173525263_menucascade074411762214"><a name="zh-cn_topic_0173525263_menucascade074411762214"></a><a name="zh-cn_topic_0173525263_menucascade074411762214"></a>“<span class="uicontrol" id="zh-cn_topic_0173525263_uicontrol157485711225"><a name="zh-cn_topic_0173525263_uicontrol157485711225"></a><a name="zh-cn_topic_0173525263_uicontrol157485711225"></a>文件管理</span>”</span>和<span class="menucascade" id="zh-cn_topic_0173525263_menucascade575047182215"><a name="zh-cn_topic_0173525263_menucascade575047182215"></a><a name="zh-cn_topic_0173525263_menucascade575047182215"></a>“<span class="uicontrol" id="zh-cn_topic_0173525263_uicontrol2753167192211"><a name="zh-cn_topic_0173525263_uicontrol2753167192211"></a><a name="zh-cn_topic_0173525263_uicontrol2753167192211"></a>作业管理</span>”</span>功能，并且无法查看Hadoop、Spark的作业记录以及集群资源使用情况。如果需要使用集群更多功能，需要找Manager的管理员分配权限。建议在多用户场景下使用。</li></ul>
<p id="zh-cn_topic_0173525263_p19756107142214"><a name="zh-cn_topic_0173525263_p19756107142214"></a><a name="zh-cn_topic_0173525263_p19756107142214"></a>通过单击<a name="zh-cn_topic_0173525263_image713061419317"></a><a name="zh-cn_topic_0173525263_image713061419317"></a><span><img id="zh-cn_topic_0173525263_image713061419317" src="figures/icon_mrs_enable_hec4.png"></span>或<a name="zh-cn_topic_0173525263_image136638518414"></a><a name="zh-cn_topic_0173525263_image136638518414"></a><span><img id="zh-cn_topic_0173525263_image136638518414" src="figures/icon_mrs_disable_hec4.png"></span>来关闭或开启Kerberos认证。</p>
<p id="zh-cn_topic_0173525263_p6182700381"><a name="zh-cn_topic_0173525263_p6182700381"></a><a name="zh-cn_topic_0173525263_p6182700381"></a>当选择Ranger组件时不支持开启Kerberos认证。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row84211237163015"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1881047102211"><a name="zh-cn_topic_0173525263_p1881047102211"></a><a name="zh-cn_topic_0173525263_p1881047102211"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p78163717228"><a name="zh-cn_topic_0173525263_p78163717228"></a><a name="zh-cn_topic_0173525263_p78163717228"></a>Manager管理员用户，目前默认为<strong id="zh-cn_topic_0173525263_b118184702216"><a name="zh-cn_topic_0173525263_b118184702216"></a><a name="zh-cn_topic_0173525263_b118184702216"></a>admin</strong>用户。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row794111372304"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1584714718227"><a name="zh-cn_topic_0173525263_p1584714718227"></a><a name="zh-cn_topic_0173525263_p1584714718227"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p1685312718220"><a name="zh-cn_topic_0173525263_p1685312718220"></a><a name="zh-cn_topic_0173525263_p1685312718220"></a>配置Manager管理员用户的密码。</p>
<p id="zh-cn_topic_0173525263_p78555710227"><a name="zh-cn_topic_0173525263_p78555710227"></a><a name="zh-cn_topic_0173525263_p78555710227"></a>需要满足：</p>
<a name="zh-cn_topic_0173525263_ul1485917132213"></a><a name="zh-cn_topic_0173525263_ul1485917132213"></a><ul id="zh-cn_topic_0173525263_ul1485917132213"><li>密码长度应在8～26个字符之间</li><li>必须包含如下4种字符的组合<a name="zh-cn_topic_0173525263_ul88721278226"></a><a name="zh-cn_topic_0173525263_ul88721278226"></a><ul id="zh-cn_topic_0173525263_ul88721278226"><li>至少一个小写字母</li><li>至少一个大写字母</li><li>至少一个数字</li><li>至少一个特殊字符：~`!?,.:;-_'"(){}[]/&lt;&gt;@#$%^&amp;*+|\=</li></ul>
</li><li>不能和用户名或倒序的用户名相同</li></ul>
<p id="zh-cn_topic_0173525263_p891310772213"><a name="zh-cn_topic_0173525263_p891310772213"></a><a name="zh-cn_topic_0173525263_p891310772213"></a>安全程度：颜色条红、橙、绿分别表示密码安全强度弱、中、强。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row45583386304"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p694219719224"><a name="zh-cn_topic_0173525263_p694219719224"></a><a name="zh-cn_topic_0173525263_p694219719224"></a>确认密码</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p149481718222"><a name="zh-cn_topic_0173525263_p149481718222"></a><a name="zh-cn_topic_0173525263_p149481718222"></a>再次输入Manager管理员用户的密码。</p>
</td>
</tr>
</tbody>
</table>

## 自定义购买集群硬件配置<a name="section1339818162220"></a>

**表 2**  MRS集群计费模式配置

<a name="table3765997814"></a>
<table><thead align="left"><tr id="row11766291688"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="p16766697812"><a name="p16766697812"></a><a name="p16766697812"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="p6766293811"><a name="p6766293811"></a><a name="p6766293811"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row107660916820"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p187661591087"><a name="p187661591087"></a><a name="p187661591087"></a>计费模式</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p10806734161420"><a name="p10806734161420"></a><a name="p10806734161420"></a>当前仅支持<span class="parmvalue" id="parmvalue7806113471417"><a name="parmvalue7806113471417"></a><a name="parmvalue7806113471417"></a>“包年/包月”</span>模式。</p>
</td>
</tr>
<tr id="row776669788"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p476639287"><a name="p476639287"></a><a name="p476639287"></a>购买时长</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p07661293811"><a name="p07661293811"></a><a name="p07661293811"></a>包年/包月模式下该参数有效，表示购买集群的时长。最短时长为1个月，最长时长为1年。</p>
<p id="p1076617911814"><a name="p1076617911814"></a><a name="p1076617911814"></a>如需开通自动续费功能，请勾选“自动续费”，开通后按月购买的集群 自动续费周期为一个月，按年购买的集群自动续费周期为一年。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  MRS集群硬件配置

<a name="table173619576578"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173525263_row10361857105719"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0173525263_p113619573570"><a name="zh-cn_topic_0173525263_p113619573570"></a><a name="zh-cn_topic_0173525263_p113619573570"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0173525263_p436357155717"><a name="zh-cn_topic_0173525263_p436357155717"></a><a name="zh-cn_topic_0173525263_p436357155717"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173525263_row13801315134215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p14821315154219"><a name="zh-cn_topic_0173525263_p14821315154219"></a><a name="zh-cn_topic_0173525263_p14821315154219"></a>可用区</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p18944114418540"><a name="zh-cn_topic_0173525263_p18944114418540"></a><a name="zh-cn_topic_0173525263_p18944114418540"></a>选择集群工作区域下关联的<a href="https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0184026189.html" target="_blank" rel="noopener noreferrer">可用区</a>。</p>
<p id="zh-cn_topic_0173525263_p057918792216"><a name="zh-cn_topic_0173525263_p057918792216"></a><a name="zh-cn_topic_0173525263_p057918792216"></a>可用区是使用独立电源和网络资源的物理区域。通过内部网络互联，再以物理方式进行隔离，提高了应用程序的可用性。建议您在不同的可用区下创建集群。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row28181423104212"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p8818182316428"><a name="zh-cn_topic_0173525263_p8818182316428"></a><a name="zh-cn_topic_0173525263_p8818182316428"></a>虚拟私有云</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p612712819226"><a name="zh-cn_topic_0173525263_p612712819226"></a><a name="zh-cn_topic_0173525263_p612712819226"></a>VPC即虚拟私有云，是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
<p id="zh-cn_topic_0173525263_p7131782226"><a name="zh-cn_topic_0173525263_p7131782226"></a><a name="zh-cn_topic_0173525263_p7131782226"></a>选择需要创建集群的VPC，单击<span class="uicontrol" id="zh-cn_topic_0173525263_uicontrol131334811224"><a name="zh-cn_topic_0173525263_uicontrol131334811224"></a><a name="zh-cn_topic_0173525263_uicontrol131334811224"></a>“查看虚拟私有云”</span>进入VPC服务查看已创建的VPC名称和ID。如果没有VPC，需要创建一个新的VPC。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row971023274215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p9711153212421"><a name="zh-cn_topic_0173525263_p9711153212421"></a><a name="zh-cn_topic_0173525263_p9711153212421"></a>子网</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p171459811223"><a name="zh-cn_topic_0173525263_p171459811223"></a><a name="zh-cn_topic_0173525263_p171459811223"></a>通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。</p>
<p id="zh-cn_topic_0173525263_p1214915819223"><a name="zh-cn_topic_0173525263_p1214915819223"></a><a name="zh-cn_topic_0173525263_p1214915819223"></a>选择需要创建集群的子网，可进入VPC服务控制台查看VPC下已创建的子网名称和ID，若VPC下未创建子网，请在VPC服务控制台单击<span class="uicontrol" id="zh-cn_topic_0173525263_uicontrol191521488223"><a name="zh-cn_topic_0173525263_uicontrol191521488223"></a><a name="zh-cn_topic_0173525263_uicontrol191521488223"></a>“创建子网”</span>进行创建。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1599515321422"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p14995123219425"><a name="zh-cn_topic_0173525263_p14995123219425"></a><a name="zh-cn_topic_0173525263_p14995123219425"></a>安全组</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p5180168102214"><a name="zh-cn_topic_0173525263_p5180168102214"></a><a name="zh-cn_topic_0173525263_p5180168102214"></a>安全组是一组对弹性云服务器的访问规则的集合，为同一个VPC内具有相同安全保护需求并相互信任的弹性云服务器提供访问策略。</p>
<p id="zh-cn_topic_0173525263_p171821489227"><a name="zh-cn_topic_0173525263_p171821489227"></a><a name="zh-cn_topic_0173525263_p171821489227"></a>用户创建集群时，可自动创建安全组，也可选择下拉框中已有的安全组。</p>
<div class="note" id="zh-cn_topic_0173525263_note674462819392"><a name="zh-cn_topic_0173525263_note674462819392"></a><a name="zh-cn_topic_0173525263_note674462819392"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173525263_p13744202815393"><a name="zh-cn_topic_0173525263_p13744202815393"></a><a name="zh-cn_topic_0173525263_p13744202815393"></a>选择用户自己创建的安全组时，请确保入方向规则中有一条全部协议，全部端口，源地址为可信任的IP访问范围的规则，源地址请勿使用0.0.0.0/0，否则会有安全风险。若用户不清楚可信任的IP访问范围，请选择自动创建。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row153131233184215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1431383311429"><a name="zh-cn_topic_0173525263_p1431383311429"></a><a name="zh-cn_topic_0173525263_p1431383311429"></a>弹性公网IP</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p21911274314"><a name="zh-cn_topic_0173525263_p21911274314"></a><a name="zh-cn_topic_0173525263_p21911274314"></a>通过将弹性公网IP与MRS集群绑定，实现使用弹性公网IP访问Manager的目的。</p>
<p id="zh-cn_topic_0173525263_p19997852143711"><a name="zh-cn_topic_0173525263_p19997852143711"></a><a name="zh-cn_topic_0173525263_p19997852143711"></a>用户创建集群时，可选择下拉框中已有的弹性公网IP进行绑定。若下拉框中没有可选的弹性公网IP，可以单击<span class="parmname" id="zh-cn_topic_0173525263_parmname14739128123819"><a name="zh-cn_topic_0173525263_parmname14739128123819"></a><a name="zh-cn_topic_0173525263_parmname14739128123819"></a>“管理弹性公网IP”</span>进入弹性公网IP服务进行购买。</p>
<div class="note" id="zh-cn_topic_0173525263_note69611412419"><a name="zh-cn_topic_0173525263_note69611412419"></a><a name="zh-cn_topic_0173525263_note69611412419"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173525263_p6461193613816"><a name="zh-cn_topic_0173525263_p6461193613816"></a><a name="zh-cn_topic_0173525263_p6461193613816"></a>弹性公网IP必须和集群在同一区域。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1569193334211"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p2569733204215"><a name="zh-cn_topic_0173525263_p2569733204215"></a><a name="zh-cn_topic_0173525263_p2569733204215"></a>企业项目</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p1114434124610"><a name="zh-cn_topic_0173525263_p1114434124610"></a><a name="zh-cn_topic_0173525263_p1114434124610"></a>选择集群所属的企业项目，如需使用企业项目，请先通过“企业管理 &gt; 企业项目管理”服务创建。</p>
<p id="zh-cn_topic_0173525263_p1011543414467"><a name="zh-cn_topic_0173525263_p1011543414467"></a><a name="zh-cn_topic_0173525263_p1011543414467"></a>企业项目所在的企业管理控制台以面向企业资源管理为出发点，帮助企业以公司、部门、项目等分级管理方式实现企业云上的人员、资源、权限、财务的管理。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  集群节点信息

<a name="table1780615244913"></a>
<table><thead align="left"><tr id="row1280625224918"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="p5867164215611"><a name="p5867164215611"></a><a name="p5867164215611"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="p10867642105612"><a name="p10867642105612"></a><a name="p10867642105612"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row932994614912"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p252412414471"><a name="p252412414471"></a><a name="p252412414471"></a>CPU架构</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p11001830115010"><a name="p11001830115010"></a><a name="p11001830115010"></a>MRS提供的CPU架构类型。MRS 3.x版本无该参数。</p>
<a name="ul6902183265018"></a><a name="ul6902183265018"></a><ul id="ul6902183265018"><li>x86计算：x86 CPU架构采用复杂指令集（CISC），CISC指令集的每个小指令可以执行一些较低阶的硬件操作，指令数目多而且复杂，每条指令的长度并不相同。由于指令执行较为复杂所以每条指令花费的时间较长。</li><li>鲲鹏计算：鲲鹏 CPU架构采用精简指令集（RISC），RISC是一种执行较少类型计算机指令的微处理器，它能够以更快的速度执行操作，使计算机的结构更加简单合理地提高运行速度，相对于X86 CPU架构具有更加均衡的性能功耗比。鲲鹏的优势是高密度低功耗，可以提供更高的性价比。</li></ul>
</td>
</tr>
<tr id="row2863132191813"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p85205852019"><a name="p85205852019"></a><a name="p85205852019"></a>磁盘类型</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p155135852013"><a name="p155135852013"></a><a name="p155135852013"></a>根据磁盘使用的存储资源是否独享，磁盘划分为“云硬盘”、“专属分布式存储”。</p>
<a name="ul185658192014"></a><a name="ul185658192014"></a><ul id="ul185658192014"><li>云硬盘：提供规格丰富、安全可靠、可弹性扩展的硬盘资源，满足不同性能要求的业务场景。<p id="p125458192019"><a name="p125458192019"></a><a name="p125458192019"></a>如果未申请独享的存储池，请选择“云硬盘”，创建的磁盘使用公共存储资源。</p>
</li><li>专属分布式存储：为用户提供独享的存储资源，通过数据冗余和缓存加速等多项技术，提供高可用性和持久性，以及稳定的低时延性能。<p id="p2051582207"><a name="p2051582207"></a><a name="p2051582207"></a>如果您在专属分布式存储服务页面申请了存储池，可以选择“专属分布式存储”，在已申请的存储池中创建磁盘。</p>
</li></ul>
</td>
</tr>
<tr id="row180675274914"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p18806145213491"><a name="p18806145213491"></a><a name="p18806145213491"></a>节点类型</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p148141452161618"><a name="p148141452161618"></a><a name="p148141452161618"></a>MRS提供节点类型：</p>
<a name="ul1681485281617"></a><a name="ul1681485281617"></a><ul id="ul1681485281617"><li>Master：指集群Master节点，负责管理集群，协调将集群可执行文件分配到Core节点。此外，还会跟踪每个作业的执行状态，监控DataNode的运行状况。</li><li>Core：指集群Core节点，处理数据并在HDFS中存储过程数据。分析集群将创建分析Core节点，流式集群将创建流式Core节点，混合集群分别创建分析Core和流式Core节点。</li><li>Task：指集群Task节点，主要用于计算，不存放持久数据。主要安装Yarn、Storm组件。Task节点为可选节点，数目可以是零。分析集群将创建分析Task节点，流式集群将创建流式Task节点，混合集群分别创建分析Task和流式Task节点。<div class="p" id="zh-cn_topic_0173525263_p2081455251613"><a name="zh-cn_topic_0173525263_p2081455251613"></a><a name="zh-cn_topic_0173525263_p2081455251613"></a>当集群数据量变化不大而集群业务处理能力需求变化比较大，大的业务处理能力只是临时需要，此时选择添加Task节点。<a name="zh-cn_topic_0173525263_ul1814452121612"></a><a name="zh-cn_topic_0173525263_ul1814452121612"></a><ul id="zh-cn_topic_0173525263_ul1814452121612"><li>临时业务量增大，如年底报表处理。</li><li>需要在短时间内处理完原来需要处理很久的任务，如一些紧急分析任务。</li></ul>
</div>
</li></ul>
</td>
</tr>
<tr id="row138881553164217"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p1288985324219"><a name="p1288985324219"></a><a name="p1288985324219"></a>计费模式</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p38899536425"><a name="p38899536425"></a><a name="p38899536425"></a>MRS集群中节点的计费模式。</p>
<a name="ul332415301471"></a><a name="ul332415301471"></a><ul id="ul332415301471"><li>Master和Core节点的计费模式与集群所选计费模式保持一致。</li><li>Task节点的计费模式固定为“按需计费”，表示即使创建包周期集群，Task节点依然按照按需计费模式进行计费。</li></ul>
</td>
</tr>
<tr id="row118071852124914"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p14807125213494"><a name="p14807125213494"></a><a name="p14807125213494"></a>实例规格</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p89434514180"><a name="p89434514180"></a><a name="p89434514180"></a>选择主节点和核心节点的实例规格。MRS当前支持主机规格的配型由CPU+内存+Disk共同决定。支持的实例规格详细说明请参见<a href="MRS所使用的弹性云服务器规格.md">MRS所使用的弹性云服务器规格</a>。单击<a name="image7943428195217"></a><a name="image7943428195217"></a><span><img id="image7943428195217" src="figures/icon_mrs_edit.png"></span>，配置集群节点的实例规格、系统盘和数据盘参数。</p>
<div class="note" id="note14394174431514"><a name="note14394174431514"></a><a name="note14394174431514"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul16495199172216"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul16495199172216"></a><ul id="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul16495199172216"><li>节点的实例规格配置越高，数据处理分析能力越强，集群所需费用也越高。</li><li>当Core节点规格选择为HDD磁盘时，MRS无需为数据磁盘付费，但ECS需要为此付费。</li><li>当Core节点规格选择非HDD磁盘时，Master节点和Core节点的磁盘类型取决于数据磁盘。</li><li>当节点的实例规格选项后标示<span class="parmvalue" id="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmvalue1898312103619"><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmvalue1898312103619"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmvalue1898312103619"></a>“已售罄”</span>时，将无法购买此规格的节点，请选择其他规格节点进行购买。</li><li>Master节点中的4核8GB规格不在SLA售后范围内，仅适用于测试环境，不建议用于生产环境。</li></ul>
</div></div>
</td>
</tr>
<tr id="row14357194115244"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p183581341142414"><a name="p183581341142414"></a><a name="p183581341142414"></a>系统盘</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p195682473813"><a name="p195682473813"></a><a name="p195682473813"></a>节点系统盘的存储类型和存储空间。</p>
<a name="ul15201239152616"></a><a name="ul15201239152616"></a><ul id="ul15201239152616"><li>存储类型<a name="zh-cn_topic_0173525263_ul187871428277"></a><a name="zh-cn_topic_0173525263_ul187871428277"></a><ul id="zh-cn_topic_0173525263_ul187871428277"><li>SATA：普通IO</li><li>SAS：高IO</li><li>SSD：超高IO</li></ul>
</li><li>存储空间取值范围：40GB～1000GB</li></ul>
</td>
</tr>
<tr id="row782751802211"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p1582851819226"><a name="p1582851819226"></a><a name="p1582851819226"></a>数据盘</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p18396124412152"><a name="p18396124412152"></a><a name="p18396124412152"></a>节点数据磁盘存储空间。为增大数据存储容量，创建集群时可同时添加磁盘，有如下应用场景：</p>
<a name="ul739694413152"></a><a name="ul739694413152"></a><ul id="ul739694413152"><li>数据存储和计算分离，数据存储在OBS中，集群存储成本低，存储量不受限制，并且集群可以随时删除，但计算性能取决于OBS访问性能，相对HDFS有所下降，建议在数据计算不频繁场景下使用。</li><li>数据存储和计算不分离，数据存储在HDFS中，集群成本较高，计算性能高，但存储量受磁盘空间限制，删除集群前需将数据导出保存，建议在数据计算频繁场景下使用。</li></ul>
<p id="p1339618440154"><a name="p1339618440154"></a><a name="p1339618440154"></a>目前支持SATA、SAS和SSD存储类型：</p>
<a name="ul7396644181520"></a><a name="ul7396644181520"></a><ul id="ul7396644181520"><li>SATA：普通IO</li><li>SAS：高IO</li><li>SSD：超高IO</li></ul>
<p id="p17396744121512"><a name="p17396744121512"></a><a name="p17396744121512"></a>取值范围：100GB～32000GB</p>
<div class="note" id="note53961344191515"><a name="note53961344191515"></a><a name="note53961344191515"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173525263_p19550114416519"><a name="zh-cn_topic_0173525263_p19550114416519"></a><a name="zh-cn_topic_0173525263_p19550114416519"></a>创建的节点个数越多，对管理节点（即master节点）的硬盘容量要求越高。为了保证集群能够健康地运行，当创建的节点个数达到300时，建议将master的硬盘容量配置成600GB以上；当创建的节点个数达到500时，建议将master的硬盘容量配置成1TB以上。</p>
</div></div>
</td>
</tr>
<tr id="row1280719521499"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p11807952194917"><a name="p11807952194917"></a><a name="p11807952194917"></a>实例数量</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p1039614412154"><a name="p1039614412154"></a><a name="p1039614412154"></a>配置主节点和核心节点的个数。</p>
<p id="p16396444191517"><a name="p16396444191517"></a><a name="p16396444191517"></a>Master：</p>
<a name="ul15396194412158"></a><a name="ul15396194412158"></a><ul id="ul15396194412158"><li>开启“集群高可用”时，Master实例数量固定为2个。</li><li>关闭“集群高可用”时，Master实例数量固定为1个。</li></ul>
<p id="p173971644111511"><a name="p173971644111511"></a><a name="p173971644111511"></a>Core节点至少存在一个，Core节点和Task节点的数量之和不能超过500个。</p>
<p id="p17515183010423"><a name="p17515183010423"></a><a name="p17515183010423"></a>Task：单击<a name="zh-cn_topic_0173525263_image1259134810450"></a><a name="zh-cn_topic_0173525263_image1259134810450"></a><span><img id="zh-cn_topic_0173525263_image1259134810450" src="figures/icon_mrs_addtask.png"></span>添加Task节点。单击<a name="zh-cn_topic_0173525263_image88921033111413"></a><a name="zh-cn_topic_0173525263_image88921033111413"></a><span><img id="zh-cn_topic_0173525263_image88921033111413" src="figures/icon_mrs_edit.png"></span>修改Task节点额实例规格和磁盘配置。单击<a name="zh-cn_topic_0173525263_image1272544101715"></a><a name="zh-cn_topic_0173525263_image1272544101715"></a><span><img id="zh-cn_topic_0173525263_image1272544101715" src="figures/icon_mrs_deletetask.png"></span>删除已添加的Task节点。</p>
<div class="note" id="note13397144131517"><a name="note13397144131517"></a><a name="note13397144131517"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul2057213962214"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul2057213962214"></a><ul id="zh-cn_topic_0173525263_zh-cn_topic_0173525262_ul2057213962214"><li>Core节点默认的最大值为500，如果用户需要的Core节点数大于500，请申请扩大配额，具体请参考<a href="https://support.huaweicloud.com/usermanual-iaas/zh-cn_topic_0040259342.html" target="_blank" rel="noopener noreferrer">关于配额</a>。</li><li>过小的节点容量会导致您的集群运行缓慢，而过大的节点容量会产生不必要的成本，请根据您要处理的数据对集群节点数量进行调整。</li></ul>
</div></div>
</td>
</tr>
<tr id="row2807752204910"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p8397844101516"><a name="p8397844101516"></a><a name="p8397844101516"></a>集群高可用</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p6397114420152"><a name="p6397114420152"></a><a name="p6397114420152"></a>是否开启集群高可用，默认开启。</p>
<p id="p157151046131616"><a name="p157151046131616"></a><a name="p157151046131616"></a>启用高可用特性时，所有组件的管理进程将会部署在两个master节点上，实现双机热备，防止单机故障，提高可靠性。当关闭高可用特性时，所有组件的管理进程只会部署在一个master节点上，当某个组件的进程出现异常时，该组件将无法提供服务。</p>
<a name="ul173971444121520"></a><a name="ul173971444121520"></a><ul id="ul173971444121520"><li><a name="zh-cn_topic_0173525263_image1790212365"></a><a name="zh-cn_topic_0173525263_image1790212365"></a><span><img id="zh-cn_topic_0173525263_image1790212365" src="figures/icon_mrs_disable_hec4.png"></span>：<span class="parmname" id="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname1922268162213"><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname1922268162213"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname1922268162213"></a>“集群高可用”</span>关闭时，Master节点实例数量固定为1个，Core节点实例数量默认为3个，最小可调整为1个。</li><li><a name="zh-cn_topic_0173525263_image1364824183820"></a><a name="zh-cn_topic_0173525263_image1364824183820"></a><span><img id="zh-cn_topic_0173525263_image1364824183820" src="figures/icon_mrs_enable_hec4.png"></span>：<span class="parmname" id="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname42431486228"><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname42431486228"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0173525262_parmname42431486228"></a>“集群高可用”</span>开启时，Master节点实例数量固定为2个，Core节点实例数量默认为3个，最小可调整为1个。</li></ul>
<p id="p73981441153"><a name="p73981441153"></a><a name="p73981441153"></a>通过单击<a name="zh-cn_topic_0173525263_image1030463013212"></a><a name="zh-cn_topic_0173525263_image1030463013212"></a><span><img id="zh-cn_topic_0173525263_image1030463013212" src="figures/icon_mrs_enable_hec4.png"></span>或<a name="zh-cn_topic_0173525263_image132611510123315"></a><a name="zh-cn_topic_0173525263_image132611510123315"></a><span><img id="zh-cn_topic_0173525263_image132611510123315" src="figures/icon_mrs_disable_hec4.png"></span>来关闭或开启集群高可用。</p>
</td>
</tr>
<tr id="row144051838183219"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p104971055191015"><a name="p104971055191015"></a><a name="p104971055191015"></a>LVM</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p83991244191511"><a name="p83991244191511"></a><a name="p83991244191511"></a>仅当创建流式Core节点时，该参数在流式Core节点有效。单击该参数以开启或关闭磁盘LVM管理。</p>
<p id="p13399184481513"><a name="p13399184481513"></a><a name="p13399184481513"></a>启用逻辑卷管理(LVM)时，会将节点中所有磁盘以逻辑卷的方式挂载，能够更加合理的规划磁盘，避免磁盘不均匀的问题，提升系统的稳定性。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  登录方式

<a name="table493595819197"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173525263_row172357588176"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0173525263_p152163161811"><a name="zh-cn_topic_0173525263_p152163161811"></a><a name="zh-cn_topic_0173525263_p152163161811"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0173525263_p722183101818"><a name="zh-cn_topic_0173525263_p722183101818"></a><a name="zh-cn_topic_0173525263_p722183101818"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173525263_row423519588172"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1023520584174"><a name="zh-cn_topic_0173525263_p1023520584174"></a><a name="zh-cn_topic_0173525263_p1023520584174"></a>登录方式</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><a name="zh-cn_topic_0173525263_ul1060120434182"></a><a name="zh-cn_topic_0173525263_ul1060120434182"></a><ul id="zh-cn_topic_0173525263_ul1060120434182"><li>密码<p id="zh-cn_topic_0173525263_p1611692652019"><a name="zh-cn_topic_0173525263_p1611692652019"></a><a name="zh-cn_topic_0173525263_p1611692652019"></a>使用密码方式登录ECS节点。</p>
<p id="zh-cn_topic_0173525263_p18116126162012"><a name="zh-cn_topic_0173525263_p18116126162012"></a><a name="zh-cn_topic_0173525263_p18116126162012"></a>密码设置约束如下：</p>
<a name="zh-cn_topic_0173525263_ol8116126132011"></a><a name="zh-cn_topic_0173525263_ol8116126132011"></a><ol id="zh-cn_topic_0173525263_ol8116126132011"><li>字符串类型，可输入的字符串长度为8~26。</li><li>至少包含三种字符组合，如大写字母，小写字母，数字，特殊字符（`~!@#$%^&amp;*()-_=+\|[{}];:'",&lt;.&gt;/?）和空格。</li><li>不能与用户名或倒序用户名相同。</li></ol>
</li><li>密钥对<p id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1071419914222"><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1071419914222"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1071419914222"></a>使用密钥方式登录集群ECS节点。从下拉框中选择密钥对，如果已获取私钥文件，请勾选“我确认已获取该密钥对中的私钥文件<i><span class="varname" id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_varname47183932217"><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_varname47183932217"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_varname47183932217"></a>SSHkey-xxx</span></i>，否则无法登录弹性云服务器”。如果没有创建密钥对，请单击<span class="uicontrol" id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_uicontrol1572069192218"><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_uicontrol1572069192218"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_uicontrol1572069192218"></a>“查看密钥对”</span>创建或导入密钥，然后再获取私钥文件。</p>
<p id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p17247952213"><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p17247952213"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p17247952213"></a>密钥对即SSH密钥，包含SSH公钥和私钥。您可以新建一个SSH密钥，并下载私钥用于远程登录身份认证。为保证安全，私钥只能下载一次，请妥善保管。</p>
<p id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1672620914229"><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1672620914229"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_p1672620914229"></a>您可以通过以下两种方式中的任意一种使用SSH密钥。</p>
<a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_ol2945123165614"></a><a name="zh-cn_topic_0173525263_zh-cn_topic_0175446773_ol2945123165614"></a><ol id="zh-cn_topic_0173525263_zh-cn_topic_0175446773_ol2945123165614"><li>创建SSH密钥：创建SSH密钥，同时会创建公钥和私钥，公钥保存在ECS系统中，私钥保存在用户本机。当登录弹性云服务器时，使用公钥和私钥进行鉴权。</li><li>导入SSH密钥：当用户已有公钥和私钥，可以选择将公钥导入系统。当登录弹性云服务器时，使用公钥和私钥进行鉴权。</li></ol>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 自定义购买集群高级配置（可选）<a name="section861294242018"></a>

**表 6**  MRS集群高级配置

<a name="table794042919210"></a>
<table><thead align="left"><tr id="zh-cn_topic_0173525263_row16451659125715"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0173525263_p74511659185713"><a name="zh-cn_topic_0173525263_p74511659185713"></a><a name="zh-cn_topic_0173525263_p74511659185713"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0173525263_p1445195905715"><a name="zh-cn_topic_0173525263_p1445195905715"></a><a name="zh-cn_topic_0173525263_p1445195905715"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0173525263_row1451159125717"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1945285918575"><a name="zh-cn_topic_0173525263_p1945285918575"></a><a name="zh-cn_topic_0173525263_p1945285918575"></a>标签</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p3995171313252"><a name="zh-cn_topic_0173525263_p3995171313252"></a><a name="zh-cn_topic_0173525263_p3995171313252"></a>具体请参考<a href="添加集群标签.md">添加集群标签</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row84521859105718"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p19452185918570"><a name="zh-cn_topic_0173525263_p19452185918570"></a><a name="zh-cn_topic_0173525263_p19452185918570"></a>弹性伸缩</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p9452185965713"><a name="zh-cn_topic_0173525263_p9452185965713"></a><a name="zh-cn_topic_0173525263_p9452185965713"></a>请在“硬件配置”页签指定Task节点的规格，然后参考<a href="创建集群时配置弹性伸缩规则.md">创建集群时配置弹性伸缩规则</a>配置。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row145211599577"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p845225995716"><a name="zh-cn_topic_0173525263_p845225995716"></a><a name="zh-cn_topic_0173525263_p845225995716"></a>引导操作</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p104522595575"><a name="zh-cn_topic_0173525263_p104522595575"></a><a name="zh-cn_topic_0173525263_p104522595575"></a>具体请参考<a href="添加引导操作.md">添加引导操作</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row164071028993"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p24081528694"><a name="zh-cn_topic_0173525263_p24081528694"></a><a name="zh-cn_topic_0173525263_p24081528694"></a>委托</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p740872813913"><a name="zh-cn_topic_0173525263_p740872813913"></a><a name="zh-cn_topic_0173525263_p740872813913"></a>通过绑定委托，您可以将部分资源共享给ECS或BMS云服务来管理，例如通过配置ECS委托可自动获取AK/SK访问OBS，具体请参见<a href="配置存算分离集群（委托方式）.md">配置存算分离集群（委托方式）</a>。</p>
<p id="zh-cn_topic_0173525263_p5919131831716"><a name="zh-cn_topic_0173525263_p5919131831716"></a><a name="zh-cn_topic_0173525263_p5919131831716"></a><strong id="zh-cn_topic_0173525263_b23613919610"><a name="zh-cn_topic_0173525263_b23613919610"></a><a name="zh-cn_topic_0173525263_b23613919610"></a>MRS_ECS_DEFAULT_AGENCY</strong>委托拥有对象存储服务的OBS&nbsp;OperateAccess权限和在集群所在区域拥有CES&nbsp;FullAccess（对开启细粒度策略的用户）、CES Administrator和KMS Administrator权限。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row162561137183217"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p52561537183213"><a name="zh-cn_topic_0173525263_p52561537183213"></a><a name="zh-cn_topic_0173525263_p52561537183213"></a>指标共享</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p4256937103218"><a name="zh-cn_topic_0173525263_p4256937103218"></a><a name="zh-cn_topic_0173525263_p4256937103218"></a>用于采集大数据组件的监控指标，当用户使用集群过程中出现问题时，供华为云支持人员定位问题。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1213044602011"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1784404717208"><a name="zh-cn_topic_0173525263_p1784404717208"></a><a name="zh-cn_topic_0173525263_p1784404717208"></a>OBS权限控制</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p10844147162017"><a name="zh-cn_topic_0173525263_p10844147162017"></a><a name="zh-cn_topic_0173525263_p10844147162017"></a>开启细粒度权限控制的用户可以通过该功能实现不同的MRS用户对OBS文件系统下的不同目录有不同的权限。具体请参见<a href="配置MRS多用户访问OBS细粒度权限.md">配置MRS多用户访问OBS细粒度权限</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row3236230111812"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1079035013513"><a name="zh-cn_topic_0173525263_p1079035013513"></a><a name="zh-cn_topic_0173525263_p1079035013513"></a>数据盘加密</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p16335111473519"><a name="zh-cn_topic_0173525263_p16335111473519"></a><a name="zh-cn_topic_0173525263_p16335111473519"></a>是否对集群挂载的数据盘中的数据进行加密，默认关闭。如需使用该功能，当前用户必须拥有“Security Administrator”和“KMS Administrator”权限。</p>
<p id="zh-cn_topic_0173525263_p229333463718"><a name="zh-cn_topic_0173525263_p229333463718"></a><a name="zh-cn_topic_0173525263_p229333463718"></a>加密数据盘使用的密钥由数据加密服务（DEW，Data Encryption Workshop）中的密钥管理（KMS，Key Management Service）功能提供，无需您自行构建和维护密钥管理基础设施，安全便捷。</p>
<p id="zh-cn_topic_0173525263_p1943193514409"><a name="zh-cn_topic_0173525263_p1943193514409"></a><a name="zh-cn_topic_0173525263_p1943193514409"></a>通过单击<span class="parmname" id="zh-cn_topic_0173525263_parmname1690182792518"><a name="zh-cn_topic_0173525263_parmname1690182792518"></a><a name="zh-cn_topic_0173525263_parmname1690182792518"></a>“数据盘加密”</span>开启或关闭数据盘加密功能，详情请参考<a href="https://support.huaweicloud.com/productdesc-evs/evs_01_0001.html" target="_blank" rel="noopener noreferrer">云硬盘加密</a>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row85391633112311"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p15631405241"><a name="zh-cn_topic_0173525263_p15631405241"></a><a name="zh-cn_topic_0173525263_p15631405241"></a>密钥ID</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p186318042410"><a name="zh-cn_topic_0173525263_p186318042410"></a><a name="zh-cn_topic_0173525263_p186318042410"></a>当<span class="parmname" id="zh-cn_topic_0173525263_parmname156319072417"><a name="zh-cn_topic_0173525263_parmname156319072417"></a><a name="zh-cn_topic_0173525263_parmname156319072417"></a>“数据盘加密”</span>功能开启时，显示该参数。用于显示已选择的密钥名称对应的密钥ID。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1522613275189"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p528502914118"><a name="zh-cn_topic_0173525263_p528502914118"></a><a name="zh-cn_topic_0173525263_p528502914118"></a>密钥名称</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p1828516291416"><a name="zh-cn_topic_0173525263_p1828516291416"></a><a name="zh-cn_topic_0173525263_p1828516291416"></a>当<span class="parmname" id="zh-cn_topic_0173525263_parmname1625014151522"><a name="zh-cn_topic_0173525263_parmname1625014151522"></a><a name="zh-cn_topic_0173525263_parmname1625014151522"></a>“数据盘加密”</span>功能开启时，需要配置该参数。选择用来加密数据盘的密钥名称，默认选择密钥名称为“evs/default”的默认主密钥，在下拉框中可以选择其他用户主密钥。</p>
<p id="zh-cn_topic_0173525263_p1291510961417"><a name="zh-cn_topic_0173525263_p1291510961417"></a><a name="zh-cn_topic_0173525263_p1291510961417"></a>使用用户主密钥加密云硬盘，若对用户主密钥执行禁用、计划删除等操作，将会导致云硬盘不可读写，甚至数据永远无法恢复，请谨慎操作。</p>
<p id="zh-cn_topic_0173525263_p15153141941411"><a name="zh-cn_topic_0173525263_p15153141941411"></a><a name="zh-cn_topic_0173525263_p15153141941411"></a>单击<span class="parmname" id="zh-cn_topic_0173525263_parmname1287017439141"><a name="zh-cn_topic_0173525263_parmname1287017439141"></a><a name="zh-cn_topic_0173525263_parmname1287017439141"></a>“查看密钥列表”</span>，进入密钥管理页面可以创建及管理密钥。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row846175116240"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p84665118243"><a name="zh-cn_topic_0173525263_p84665118243"></a><a name="zh-cn_topic_0173525263_p84665118243"></a>告警</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p10460514249"><a name="zh-cn_topic_0173525263_p10460514249"></a><a name="zh-cn_topic_0173525263_p10460514249"></a>开启告警功能可在集群运行异常或系统故障时，及时通知集群维护人员定位问题。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1493095315248"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p1193085315241"><a name="zh-cn_topic_0173525263_p1193085315241"></a><a name="zh-cn_topic_0173525263_p1193085315241"></a>规则名称</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p1493005362411"><a name="zh-cn_topic_0173525263_p1493005362411"></a><a name="zh-cn_topic_0173525263_p1493005362411"></a>用户自定义发送告警消息的规则名称，只能包含数字、英文字符、中划线和下划线。</p>
</td>
</tr>
<tr id="zh-cn_topic_0173525263_row1225331983811"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0173525263_p4253119183818"><a name="zh-cn_topic_0173525263_p4253119183818"></a><a name="zh-cn_topic_0173525263_p4253119183818"></a>主题名称</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0173525263_p09265368428"><a name="zh-cn_topic_0173525263_p09265368428"></a><a name="zh-cn_topic_0173525263_p09265368428"></a>选择已创建的主题，也可以单击“创建主题”重新创建。新创建的主题请参考<a href="配置消息通知.md#section186691424145018">向主题添加订阅</a>向该主题添加订阅者才能接收发布至主题的消息。</p>
<p id="zh-cn_topic_0173525263_p162531619133816"><a name="zh-cn_topic_0173525263_p162531619133816"></a><a name="zh-cn_topic_0173525263_p162531619133816"></a>主题是发送消息和订阅通知的信道，为发布者和订阅者提供一个可以相互交流的通道。</p>
</td>
</tr>
</tbody>
</table>

