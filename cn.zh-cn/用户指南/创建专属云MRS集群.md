# 创建专属云MRS集群<a name="ZH-CN_TOPIC_0136952563"></a>

本章节为您介绍如何在您的专属资源上创建一个MRS集群。

-   如果您希望MRS服务运行在隔离的专属区域，请您先申请专属计算集群，再创建专属云MRS集群。

    了解和申请专属计算集群，请参见《专属计算集群用户指南》。


-   如果您希望MRS服务拥有独享的存储设备，请您在开通专属计算集群后申请专属企业存储，再创建专属云MRS集群。

    了解和申请专属企业存储，请参见《专属企业存储用户指南》。


## 操作步骤<a name="section875182920158"></a>

1.  登录MRS管理控制台。
2.  单击“购买集群“，进入“购买集群“页面。
3.  参考下列表格配置集群基本信息。

    **表 1**  配置集群基本信息

    <a name="table1749818782212"></a>
    <table><thead align="left"><tr id="row155139722215"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p351817712228"><a name="p351817712228"></a><a name="p351817712228"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p1452218712228"><a name="p1452218712228"></a><a name="p1452218712228"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row552827172217"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p253247122220"><a name="p253247122220"></a><a name="p253247122220"></a>计费模式</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p632912539262"><a name="p632912539262"></a><a name="p632912539262"></a>当前仅支持<span class="parmvalue" id="parmvalue10361847192714"><a name="parmvalue10361847192714"></a><a name="parmvalue10361847192714"></a>“包年/包月”</span>模式。</p>
    </td>
    </tr>
    <tr id="row3552197162214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1855717102216"><a name="p1855717102216"></a><a name="p1855717102216"></a>当前区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p205608722217"><a name="p205608722217"></a><a name="p205608722217"></a>选择已申请的支持专属云的区域。</p>
    </td>
    </tr>
    <tr id="row356810713229"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p115737713229"><a name="p115737713229"></a><a name="p115737713229"></a>可用分区</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p057918792216"><a name="p057918792216"></a><a name="p057918792216"></a>可用区域是使用独立电源和网络资源的物理区域。通过内部网络互联，再以物理方式进行隔离，提高了应用程序的可用性。建议您在不同的可用区域下创建集群。</p>
    </td>
    </tr>
    <tr id="row136252079225"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1632137202218"><a name="p1632137202218"></a><a name="p1632137202218"></a>集群名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p2063816718226"><a name="p2063816718226"></a><a name="p2063816718226"></a>集群名称，集群名称不允许相同。</p>
    <p id="p864015712219"><a name="p864015712219"></a><a name="p864015712219"></a>只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <p id="p17643576224"><a name="p17643576224"></a><a name="p17643576224"></a>默认名称为mrs_xxxx，xxxx为字母和数字的四位随机组合数，系统自动组合。</p>
    </td>
    </tr>
    <tr id="row16491571227"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p2065916742212"><a name="p2065916742212"></a><a name="p2065916742212"></a>集群版本</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p11302191119226"><a name="p11302191119226"></a><a name="p11302191119226"></a>目前支持MRS 1.5.1、MRS 1.6.3、MRS 1.7.2、MRS 1.8.0、MRS 1.8.1版本。默认值为当前最新版本。</p>
    </td>
    </tr>
    <tr id="row1668817713222"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17692775227"><a name="p17692775227"></a><a name="p17692775227"></a>Kerberos认证</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1269712712218"><a name="p1269712712218"></a><a name="p1269712712218"></a>登录MRS Manager管理页面时是否启用Kerberos认证。</p>
    <a name="ul137018762216"></a><a name="ul137018762216"></a><ul id="ul137018762216"><li><a name="image5710479227"></a><a name="image5710479227"></a><span><img id="image5710479227" src="figures/zh-cn_image_0137085670.png"></span>：<span class="parmname" id="parmname1772018732216"><a name="parmname1772018732216"></a><a name="parmname1772018732216"></a>“Kerberos认证”</span>关闭时，用户可使用MRS集群的所有功能。建议单用户场景下使用。不启用Kerberos认证时的安全配置建议请参见<a href="集群（未启用Kerberos认证）安全配置建议.md">集群（未启用Kerberos认证）安全配置建议</a>。</li><li><a name="image19730117162210"></a><a name="image19730117162210"></a><span><img id="image19730117162210" src="figures/zh-cn_image_0137085678.png"></span>：<span class="parmname" id="parmname074211710221"><a name="parmname074211710221"></a><a name="parmname074211710221"></a>“Kerberos认证”</span>开启时，普通用户无权限使用MRS集群的<span class="menucascade" id="menucascade074411762214"><a name="menucascade074411762214"></a><a name="menucascade074411762214"></a>“<span class="uicontrol" id="uicontrol157485711225"><a name="uicontrol157485711225"></a><a name="uicontrol157485711225"></a>文件管理</span>”</span>和<span class="menucascade" id="menucascade575047182215"><a name="menucascade575047182215"></a><a name="menucascade575047182215"></a>“<span class="uicontrol" id="uicontrol2753167192211"><a name="uicontrol2753167192211"></a><a name="uicontrol2753167192211"></a>作业管理</span>”</span>功能，并且无法查看Hadoop、Spark的作业记录以及集群资源使用情况。如果需要使用集群更多功能，需要找MRS Manager的管理员分配权限。建议在多用户场景下使用。</li></ul>
    <p id="p19756107142214"><a name="p19756107142214"></a><a name="p19756107142214"></a>通过单击<a name="image07588742211"></a><a name="image07588742211"></a><span><img id="image07588742211" src="figures/zh-cn_image_0137085706.png"></span>或<a name="image157696710228"></a><a name="image157696710228"></a><span><img id="image157696710228" src="figures/zh-cn_image_0137085716.png"></span>来关闭或开启Kerberos认证。</p>
    <p id="p4781471227"><a name="p4781471227"></a><a name="p4781471227"></a>用户在创建了支持Kerberos认证的MRS集群之后，可以使用MRS Manager管理运行中的集群。具体操作请参见<a href="访问支持Kerberos认证的Manager.md">访问支持Kerberos认证的Manager</a>。</p>
    </td>
    </tr>
    <tr id="row19806376224"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1881047102211"><a name="p1881047102211"></a><a name="p1881047102211"></a>用户名</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p78163717228"><a name="p78163717228"></a><a name="p78163717228"></a>MRS Manager管理员用户，目前默认为<strong id="b118184702216"><a name="b118184702216"></a><a name="b118184702216"></a>admin</strong>用户。</p>
    <p id="p61862320212"><a name="p61862320212"></a><a name="p61862320212"></a>对于MRS 1.8.0之前的版本，仅当<span class="parmname" id="parmname419813262118"><a name="parmname419813262118"></a><a name="parmname419813262118"></a>“Kerberos认证”</span>配置为<span class="parmvalue" id="parmvalue22131832142117"><a name="parmvalue22131832142117"></a><a name="parmvalue22131832142117"></a>“开启”</span>：<a name="image11232163292115"></a><a name="image11232163292115"></a><span><img id="image11232163292115" src="figures/zh-cn_image_0137085740.png"></span>时需要配置此参数。</p>
    </td>
    </tr>
    <tr id="row484207132213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1584714718227"><a name="p1584714718227"></a><a name="p1584714718227"></a>密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1685312718220"><a name="p1685312718220"></a><a name="p1685312718220"></a>配置MRS Manager管理员用户的密码。</p>
    <p id="p78555710227"><a name="p78555710227"></a><a name="p78555710227"></a>需要满足：</p>
    <a name="ul1485917132213"></a><a name="ul1485917132213"></a><ul id="ul1485917132213"><li>密码长度应在8～32个字符之间</li><li>必须包含如下5种中至少3种字符的组合<a name="ul88721278226"></a><a name="ul88721278226"></a><ul id="ul88721278226"><li>至少一个小写字母</li><li>至少一个大写字母</li><li>至少一个数字</li><li>至少一个特殊字符：`~!@#$%^&amp;*()-_=+\|[{}];:'",&lt;.&gt;/?</li><li>空格</li></ul>
    </li><li>不能和用户名一样</li><li>不能和用户名的倒写一样</li></ul>
    <p id="p891310772213"><a name="p891310772213"></a><a name="p891310772213"></a>安全程度：颜色条红、橙、绿分别表示密码安全强度弱、中、强。</p>
    <p id="p458928172711"><a name="p458928172711"></a><a name="p458928172711"></a>对于MRS 1.8.0之前的版本，仅当<span class="parmname" id="parmname14601828132712"><a name="parmname14601828132712"></a><a name="parmname14601828132712"></a>“Kerberos认证”</span>配置为<span class="parmvalue" id="parmvalue364328122711"><a name="parmvalue364328122711"></a><a name="parmvalue364328122711"></a>“开启”</span>：<a name="image4686281277"></a><a name="image4686281277"></a><span><img id="image4686281277" src="figures/zh-cn_image_0137085732.png"></span>时需要配置此参数。</p>
    </td>
    </tr>
    <tr id="row1093615716229"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p694219719224"><a name="p694219719224"></a><a name="p694219719224"></a>确认密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p149481718222"><a name="p149481718222"></a><a name="p149481718222"></a>再次输入MRS Manager管理员用户的密码。</p>
    <p id="p3746431152719"><a name="p3746431152719"></a><a name="p3746431152719"></a>对于MRS 1.8.0之前的版本，仅当<span class="parmname" id="parmname9749931142714"><a name="parmname9749931142714"></a><a name="parmname9749931142714"></a>“Kerberos认证”</span>配置为<span class="parmvalue" id="parmvalue6752203122715"><a name="parmvalue6752203122715"></a><a name="parmvalue6752203122715"></a>“开启”</span>：<a name="image16754031202716"></a><a name="image16754031202716"></a><span><img id="image16754031202716" src="figures/zh-cn_image_0137085724.png"></span>时需要配置此参数。</p>
    </td>
    </tr>
    <tr id="row179721370221"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p197518710224"><a name="p197518710224"></a><a name="p197518710224"></a>集群类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><div class="p" id="p2415053122615"><a name="p2415053122615"></a><a name="p2415053122615"></a>提供两种集群类型：<a name="ul1415135362617"></a><a name="ul1415135362617"></a><ul id="ul1415135362617"><li>分析集群：用来做离线数据分析，提供的是Hadoop体系的组件。</li><li>流式集群：用来做流处理任务，提供的是流式处理组件。</li></ul>
    </div>
    <div class="note" id="note3116811229"><a name="note3116811229"></a><a name="note3116811229"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p18311892216"><a name="p18311892216"></a><a name="p18311892216"></a>MRS流式集群不支持<span class="parmname" id="parmname116148122214"><a name="parmname116148122214"></a><a name="parmname116148122214"></a>“作业管理”</span>和<span class="parmname" id="parmname1510108152218"><a name="parmname1510108152218"></a><a name="parmname1510108152218"></a>“文件管理”</span>功能<sub id="sub162001738173"><a name="sub162001738173"></a><a name="sub162001738173"></a>。</sub></p>
    </div></div>
    </td>
    </tr>
    <tr id="row17162816227"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p18240812214"><a name="p18240812214"></a><a name="p18240812214"></a>组件选择</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p530128172211"><a name="p530128172211"></a><a name="p530128172211"></a>MRS配套的组件如下：</p>
    <div class="p" id="p642514534268"><a name="p642514534268"></a><a name="p642514534268"></a>分析集群组件<a name="ul1933148102219"></a><a name="ul1933148102219"></a><ul id="ul1933148102219"><li>Hadoop：分布式系统基础架构</li><li>Spark：内存分布式系统框架</li><li>Hive：建立在Hadoop上的数据仓库框架</li><li>HBase：分布式列数据库</li><li>Hue：提供Hadoop UI能力，让用户通过浏览器分析处理Hadoop集群数据</li><li>Loader：基于开源sqoop 1.99.7开发，专为Apache Hadoop和结构化数据库（如关系型数据库）设计的高效传输大量数据的工具。<p id="p1987178152216"><a name="p1987178152216"></a><a name="p1987178152216"></a>Hadoop为必选组件，且Spark与Hive组件需要配套使用。请根据业务选择搭配组件。</p>
    </li></ul>
    </div>
    <div class="p" id="p19440175332611"><a name="p19440175332611"></a><a name="p19440175332611"></a>流式集群组件<a name="ul3892814225"></a><a name="ul3892814225"></a><ul id="ul3892814225"><li>Kafka：提供分布式消息订阅的系统。</li><li>Storm：提供分布式实时计算的系统。</li><li>Flume：提供分布式、高可用、高可靠的海量日志采集、聚合和传输系统。</li></ul>
    </div>
    </td>
    </tr>
    <tr id="row8114286224"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p41213832219"><a name="p41213832219"></a><a name="p41213832219"></a>虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p612712819226"><a name="p612712819226"></a><a name="p612712819226"></a>VPC即虚拟私有云，是通过逻辑方式进行网络隔离，提供安全、隔离的网络环境。</p>
    <p id="p7131782226"><a name="p7131782226"></a><a name="p7131782226"></a>选择需要创建集群的VPC，单击<span class="uicontrol" id="uicontrol131334811224"><a name="uicontrol131334811224"></a><a name="uicontrol131334811224"></a>“查看虚拟私有云”</span>进入VPC服务查看已创建的VPC名称和ID。如果没有VPC，需要创建一个新的VPC。</p>
    </td>
    </tr>
    <tr id="row11358812215"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1313988182210"><a name="p1313988182210"></a><a name="p1313988182210"></a>子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p171459811223"><a name="p171459811223"></a><a name="p171459811223"></a>通过子网提供与其他网络隔离的、可以独享的网络资源，以提高网络安全。</p>
    <p id="p1214915819223"><a name="p1214915819223"></a><a name="p1214915819223"></a>选择需要创建集群的子网，可进入VPC服务查看VPC下已创建的子网名称和ID。若VPC下未创建子网，请单击<span class="uicontrol" id="uicontrol191521488223"><a name="uicontrol191521488223"></a><a name="uicontrol191521488223"></a>“创建子网”</span>进行创建。</p>
    <div class="notice" id="note1315616819227"><a name="note1315616819227"></a><a name="note1315616819227"></a><span class="noticetitle"> 注意： </span><div class="noticebody"><p id="p7159489228"><a name="p7159489228"></a><a name="p7159489228"></a>请勿将子网和网络ACL关联。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row816610814221"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p417415882210"><a name="p417415882210"></a><a name="p417415882210"></a>安全组</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5180168102214"><a name="p5180168102214"></a><a name="p5180168102214"></a>安全组是一组对弹性云服务器的访问规则的集合，为同一个VPC内具有相同安全保护需求并相互信任的弹性云服务器提供访问策略。</p>
    <p id="p171821489227"><a name="p171821489227"></a><a name="p171821489227"></a>用户创建集群时，可自动创建安全组，也可选择下拉框中已有的安全组。</p>
    </td>
    </tr>
    <tr id="row946703113359"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p12467163110352"><a name="p12467163110352"></a><a name="p12467163110352"></a>弹性公网IP</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p21911274314"><a name="p21911274314"></a><a name="p21911274314"></a>通过将弹性公网IP与MRS集群绑定，实现使用弹性公网IP访问MRS Manager的目的。</p>
    <p id="p19997852143711"><a name="p19997852143711"></a><a name="p19997852143711"></a>用户创建集群时，可选择下拉框中已有的弹性公网IP进行绑定。若下拉框中没有可选的弹性公网IP，可以单击<span class="parmname" id="parmname14739128123819"><a name="parmname14739128123819"></a><a name="parmname14739128123819"></a>“管理弹性公网IP”</span>进入弹性公网IP服务进行购买。</p>
    <div class="note" id="note69611412419"><a name="note69611412419"></a><a name="note69611412419"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1531291915418"></a><a name="ul1531291915418"></a><ul id="ul1531291915418"><li>该参数仅在MRS 1.8.0及以后版本有效。</li><li>弹性公网IP必须和集群在同一区域。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row824141010403"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p13257109407"><a name="p13257109407"></a><a name="p13257109407"></a>磁盘</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p3719192864111"><a name="p3719192864111"></a><a name="p3719192864111"></a><span>根据磁盘使用的存储资源是否独享，磁盘划分为“云硬盘”、“专属分布式存储”。</span></p>
    <a name="ul9721162864116"></a><a name="ul9721162864116"></a><ul id="ul9721162864116"><li>云硬盘：提供规格丰富、安全可靠、可弹性扩展的硬盘资源，满足不同性能要求的业务场景。<p id="p57214285411"><a name="p57214285411"></a><a name="p57214285411"></a>如果未申请独享的存储池，请选择“云硬盘”，创建的磁盘使用公共存储资源。</p>
    </li><li>专属分布式存储：为用户提供独享的存储资源，通过数据冗余和缓存加速等多项技术，提供高可用性和持久性，以及稳定的低时延性能。<p id="p372152817417"><a name="p372152817417"></a><a name="p372152817417"></a>如果您在专属分布式存储服务页面申请了存储池，可以选择“专属分布式存储”，在已申请的存储池中创建磁盘。</p>
    </li></ul>
    </td>
    </tr>
    <tr id="row518519822212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p31894813221"><a name="p31894813221"></a><a name="p31894813221"></a>集群高可用</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p819598102214"><a name="p819598102214"></a><a name="p819598102214"></a>是否开启集群高可用，默认开启。</p>
    <p id="p1919818817220"><a name="p1919818817220"></a><a name="p1919818817220"></a>启用高可用特性时，所有组件的管理进程将会部署在两个master节点上，实现双机热备，防止单机故障，提高可靠性。当关闭高可用特性时，所有组件的管理进程只会部署在一个master节点上，当某个组件的进程出现异常时，该组件将无法提供服务。</p>
    <a name="ul820119872211"></a><a name="ul820119872211"></a><ul id="ul820119872211"><li><a name="image521008182220"></a><a name="image521008182220"></a><span><img id="image521008182220" src="figures/zh-cn_image_0137085748.png"></span>：<span class="parmname" id="parmname1922268162213"><a name="parmname1922268162213"></a><a name="parmname1922268162213"></a>“集群高可用”</span>关闭时，Master节点实例数量固定为1个，Core节点实例数量默认为3个，最小可调整为1个。</li><li><a name="image1423118822215"></a><a name="image1423118822215"></a><span><img id="image1423118822215" src="figures/zh-cn_image_0137085756.png"></span>：<span class="parmname" id="parmname42431486228"><a name="parmname42431486228"></a><a name="parmname42431486228"></a>“集群高可用”</span>开启时，Master节点实例数量固定为2个，Core节点实例数量默认为3个，最小可调整为1个。</li></ul>
    <p id="p16247684221"><a name="p16247684221"></a><a name="p16247684221"></a>通过单击<a name="image1724912815223"></a><a name="image1724912815223"></a><span><img id="image1724912815223" src="figures/zh-cn_image_0137085764.png"></span>或<a name="image102632815223"></a><a name="image102632815223"></a><span><img id="image102632815223" src="figures/zh-cn_image_0137085772.png"></span>来关闭或开启集群高可用。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  集群节点信息

    <a name="table827713892213"></a>
    <table><thead align="left"><tr id="row329038122217"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p3297584226"><a name="p3297584226"></a><a name="p3297584226"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p183028842219"><a name="p183028842219"></a><a name="p183028842219"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row330718812224"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p73130852219"><a name="p73130852219"></a><a name="p73130852219"></a>类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p93202832215"><a name="p93202832215"></a><a name="p93202832215"></a>MRS提供节点类型：</p>
    <a name="ul832115818229"></a><a name="ul832115818229"></a><ul id="ul832115818229"><li>Master：指集群Master节点，负责管理集群，协调将集群可执行文件分配到Core节点。此外，还会跟踪每个作业的执行状态，监控DataNode的运行状况。</li><li>Core：指集群Core节点，处理数据并在HDFS中存储过程数据。</li><li>Task：指集群Task节点，主要用于计算，不存放持久数据。主要安装Yarn、Storm组件。Task节点为可选节点，数目可以是零。（MRS 1.6.0及以上版本支持。）<p id="p68431394516"><a name="p68431394516"></a><a name="p68431394516"></a>当集群数据量变化不大而集群业务处理能力需求变化比较大，大的业务处理能力只是临时需要，此时选择添加Task节点。</p>
    <a name="ul19776172184513"></a><a name="ul19776172184513"></a><ul id="ul19776172184513"><li>临时业务量增大，如年底报表处理。</li><li>需要在短时间内处理完原来需要处理很久的任务，如一些紧急分析任务。</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="row7533133584813"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p87019484486"><a name="p87019484486"></a><a name="p87019484486"></a>添加Task节点（可选配置）</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p3701164814819"><a name="p3701164814819"></a><a name="p3701164814819"></a>单击“添加Task节点”，配置Task节点信息。</p>
    </td>
    </tr>
    <tr id="row047112564457"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p44711156164517"><a name="p44711156164517"></a><a name="p44711156164517"></a>资源池类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p8471125624513"><a name="p8471125624513"></a><a name="p8471125624513"></a>Master、Core、Task类型节点目前均仅支持<span class="parmvalue" id="parmvalue27324721319"><a name="parmvalue27324721319"></a><a name="parmvalue27324721319"></a>“通用计算型s2”</span>。</p>
    </td>
    </tr>
    <tr id="row1337683228"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p534315842217"><a name="p534315842217"></a><a name="p534315842217"></a>实例规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p197419862211"><a name="p197419862211"></a><a name="p197419862211"></a>选择主节点和核心节点的实例规格。MRS当前支持主机规格的配型由CPU+内存+Disk共同决定。</p>
    <p id="p19346134523019"><a name="p19346134523019"></a><a name="p19346134523019"></a>支持专属云MRS集群的工作区域中支持的实例规格详细说明请参见<a href="MRS所使用的弹性云服务器规格.md">MRS所使用的弹性云服务器规格</a>。</p>
    <div class="note" id="note1648939122217"><a name="note1648939122217"></a><a name="note1648939122217"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul16495199172216"></a><a name="ul16495199172216"></a><ul id="ul16495199172216"><li>节点的实例规格配置越高，数据处理分析能力越强，集群所需费用也越高。</li><li>当Core节点规格选择为HDD磁盘时，MRS无需为数据磁盘付费，但ECS需要为此付费。</li><li>当Core节点规格选择HDD磁盘时，Master节点和Core节点的系统磁盘大小为40GB，或者Master节点的数据磁盘大小为200GB，它们都称为SATA磁盘。</li><li>当Core节点规格选择非HDD磁盘时，Master节点和Core节点的磁盘类型取决于数据磁盘。</li><li>当节点的实例规格选项后标示<span class="parmvalue" id="parmvalue1898312103619"><a name="parmvalue1898312103619"></a><a name="parmvalue1898312103619"></a>“已售罄”</span>时，将无法购买此规格的节点，请选择其他规格节点进行购买。</li><li>Master节点中的4核8GB规格不在SLA售后范围内，仅适用于测试环境，不建议用于生产环境。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row953613911221"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17542129182220"><a name="p17542129182220"></a><a name="p17542129182220"></a>实例数量</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p854715916223"><a name="p854715916223"></a><a name="p854715916223"></a>配置主节点和核心节点的个数。</p>
    <p id="p1555039172214"><a name="p1555039172214"></a><a name="p1555039172214"></a>Master：</p>
    <a name="ul2553129152219"></a><a name="ul2553129152219"></a><ul id="ul2553129152219"><li>开启“集群高可用”时，Master实例数量固定为2个。</li><li>关闭“集群高可用”时，Master实例数量固定为1个。</li></ul>
    <p id="p19566792221"><a name="p19566792221"></a><a name="p19566792221"></a>Core节点至少存在一个，Core节点和Task节点的数量之和不能超过500个。</p>
    <div class="note" id="note7569199112213"><a name="note7569199112213"></a><a name="note7569199112213"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul2057213962214"></a><a name="ul2057213962214"></a><ul id="ul2057213962214"><li>Core节点默认的最大值为500，如果用户需要的Core节点数大于500，可以联系技术支持人员或者调用后台接口修改数据库。</li><li>过小的节点容量会导致您的集群运行缓慢，而过大的节点容量会产生不必要的成本，请根据您要处理的数据对集群节点数量进行调整。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row75851998222"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1159114962210"><a name="p1159114962210"></a><a name="p1159114962210"></a>数据盘</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5596209192218"><a name="p5596209192218"></a><a name="p5596209192218"></a>Core节点数据磁盘存储空间。为增大数据存储容量，创建集群时可同时购买磁盘，有如下应用场景：</p>
    <a name="ul759913912212"></a><a name="ul759913912212"></a><ul id="ul759913912212"><li>数据存储和计算分离，数据存储在OBS中，集群存储成本低，存储量不受限制，并且集群可以随时删除，但计算性能取决于OBS访问性能，相对HDFS有所下降，建议在数据计算不频繁场景下使用。</li><li>数据存储和计算不分离，数据存储在HDFS中，集群成本较高，计算性能高，但存储量受磁盘空间限制，删除集群前需将数据导出保存，建议在数据计算频繁场景下使用。</li></ul>
    <p id="p19612189142210"><a name="p19612189142210"></a><a name="p19612189142210"></a>目前支持SATA、SAS和SSD存储类型：</p>
    <a name="ul661879172212"></a><a name="ul661879172212"></a><ul id="ul661879172212"><li>SATA：普通IO</li><li>SAS：高IO</li><li>SSD：超高IO</li></ul>
    <p id="p863529182218"><a name="p863529182218"></a><a name="p863529182218"></a>取值范围：100GB～32000GB</p>
    <p id="p15440424144816"><a name="p15440424144816"></a><a name="p15440424144816"></a>当<span class="parmname" id="parmname19689438497"><a name="parmname19689438497"></a><a name="parmname19689438497"></a>“磁盘”</span>选择<span class="parmvalue" id="parmvalue126914439491"><a name="parmvalue126914439491"></a><a name="parmvalue126914439491"></a>“专属分布式存储”</span>时，磁盘类型显示格式为：磁盘存储类型 | 专属分布式存储资源池的名称(专属分布式存储资源池的ID)</p>
    <div class="note" id="note76381915224"><a name="note76381915224"></a><a name="note76381915224"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1064010972212"></a><a name="ul1064010972212"></a><ul id="ul1064010972212"><li>创建的节点个数越多，对管理节点（即master节点）的硬盘容量要求越高。为了保证集群能够健康地运行，当创建的节点个数达到300时，建议将Master的硬盘容量配置成600GB以上；当创建的节点个数达到500时，建议将Master的硬盘容量配置成1TB以上。</li><li>Master节点自动为MRS Manager增加数据磁盘存储空间，硬盘类型与Core节点数据磁盘类型相同，但磁盘空间默认为200GB且不支持修改。</li></ul>
    </div></div>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  登录信息

    <a name="table19676791228"></a>
    <table><thead align="left"><tr id="row136895982219"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p669415922211"><a name="p669415922211"></a><a name="p669415922211"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p969917914229"><a name="p969917914229"></a><a name="p969917914229"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2705179132213"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p8524121411549"><a name="p8524121411549"></a><a name="p8524121411549"></a>登录方式</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="ul14774310175416"></a><a name="ul14774310175416"></a><ul id="ul14774310175416"><li>密码<p id="p3326524165517"><a name="p3326524165517"></a><a name="p3326524165517"></a>使用密码方式登录ECS节点。</p>
    <p id="p11372175116563"><a name="p11372175116563"></a><a name="p11372175116563"></a>密码设置约束如下：</p>
    <a name="ol1437295125619"></a><a name="ol1437295125619"></a><ol id="ol1437295125619"><li>字符串类型，可输入的字符串长度为8-26。</li><li>至少包含三种字符组合，如大写字母，小写字母，数字，特殊字符（!@$%^-_=+[{}]:\,./?），但不能包含空格。</li><li>不能与用户名或者倒序用户名相同。</li></ol>
    </li><li>密钥对</li></ul>
    <p id="p1071419914222"><a name="p1071419914222"></a><a name="p1071419914222"></a>使用密钥方式登录集群ECS节点。从下拉框中选择密钥对，如果已获取私钥文件，请勾选“我确认已获取该密钥对中的私钥文件<i><span class="varname" id="varname47183932217"><a name="varname47183932217"></a><a name="varname47183932217"></a>SSHkey-bba1.pem</span></i>，否则无法登录弹性云服务器”。如果没有创建密钥对，请单击<span class="uicontrol" id="uicontrol1572069192218"><a name="uicontrol1572069192218"></a><a name="uicontrol1572069192218"></a>“查看密钥对”</span>创建或导入密钥，然后再获取私钥文件。</p>
    <p id="p17247952213"><a name="p17247952213"></a><a name="p17247952213"></a>密钥对即SSH密钥，包含SSH公钥和私钥。您可以新建一个SSH密钥，并下载私钥用于远程登录身份认证。为保证安全，私钥只能下载一次，请妥善保管。</p>
    <p id="p1672620914229"><a name="p1672620914229"></a><a name="p1672620914229"></a>您可以通过以下两种方式中的任意一种使用SSH密钥。</p>
    <a name="ol2945123165614"></a><a name="ol2945123165614"></a><ol id="ol2945123165614"><li>创建SSH密钥：创建SSH密钥，同时会创建公钥和私钥，公钥保存在ECS系统中，私钥保存在用户本机。当登录弹性云服务器时，使用公钥和私钥进行鉴权。</li><li>导入SSH密钥：当用户已有公钥和私钥，可以选择将公钥导入系统。当登录弹性云服务器时，使用公钥和私钥进行鉴权。</li></ol>
    </td>
    </tr>
    </tbody>
    </table>

    **表 4**  日志管理信息

    <a name="table7747179132220"></a>
    <table><thead align="left"><tr id="row1976289122220"><th class="cellrowborder" valign="top" width="19.919999999999998%" id="mcps1.2.3.1.1"><p id="p3767159112213"><a name="p3767159112213"></a><a name="p3767159112213"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80.08%" id="mcps1.2.3.1.2"><p id="p7773179122213"><a name="p7773179122213"></a><a name="p7773179122213"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row87800932217"><td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.3.1.1 "><p id="p078518972217"><a name="p078518972217"></a><a name="p078518972217"></a>日志记录</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.08%" headers="mcps1.2.3.1.2 "><p id="p1779779152220"><a name="p1779779152220"></a><a name="p1779779152220"></a>租户是否开启日志收集功能。</p>
    <a name="ul1800129202215"></a><a name="ul1800129202215"></a><ul id="ul1800129202215"><li><a name="image880910952211"></a><a name="image880910952211"></a><span><img id="image880910952211" src="figures/zh-cn_image_0137085782.png"></span> ：开启</li><li><a name="image148270913229"></a><a name="image148270913229"></a><span><img id="image148270913229" src="figures/zh-cn_image_0137085790.png"></span>：关闭</li></ul>
    <p id="p1883809112219"><a name="p1883809112219"></a><a name="p1883809112219"></a>通过单击<a name="image18841593221"></a><a name="image18841593221"></a><span><img id="image18841593221" src="figures/zh-cn_image_0137085798.png"></span>或<a name="image7851994222"></a><a name="image7851994222"></a><span><img id="image7851994222" src="figures/zh-cn_image_0137085806.png"></span>来关闭或开启日志收集功能。</p>
    <p id="p5376142122719"><a name="p5376142122719"></a><a name="p5376142122719"></a>说明：该参数仅在MRS 1.7.2之前版本有效。</p>
    </td>
    </tr>
    <tr id="row9861149162210"><td class="cellrowborder" valign="top" width="19.919999999999998%" headers="mcps1.2.3.1.1 "><p id="p18677912217"><a name="p18677912217"></a><a name="p18677912217"></a>OBS桶</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.08%" headers="mcps1.2.3.1.2 "><p id="p2877992225"><a name="p2877992225"></a><a name="p2877992225"></a>日志收集后存放的路径。</p>
    <p id="p1288029122218"><a name="p1288029122218"></a><a name="p1288029122218"></a>例如s3a://mrs-log-a3859af76b874760969cd24f2640bbb4-northchina</p>
    <p id="p5889189112214"><a name="p5889189112214"></a><a name="p5889189112214"></a>勾选<span class="parmvalue" id="parmvalue889119952219"><a name="parmvalue889119952219"></a><a name="parmvalue889119952219"></a>“我确认OBS桶s3a://mrs-log-a3859af76b874760969cd24f2640bbb4-northchina将被创建，该桶仅用于MRS集群创建失败日志收集。”</span></p>
    <p id="p108944982217"><a name="p108944982217"></a><a name="p108944982217"></a>用户创建了支持日志记录的MRS集群，当集群创建失败时，可以使用OBS服务下载日志来诊断问题。</p>
    <p id="p48974922217"><a name="p48974922217"></a><a name="p48974922217"></a>操作步骤：</p>
    <a name="ol14900791222"></a><a name="ol14900791222"></a><ol id="ol14900791222"><li>登录OBS管理控制台。</li><li>在桶列表中选择<span class="filepath" id="filepath1191479162218"><a name="filepath1191479162218"></a><a name="filepath1191479162218"></a>“mrs-log-&lt;tenant_id&gt;-&lt;region_id&gt;”</span>桶<em id="i291418952213"><a name="i291418952213"></a><a name="i291418952213"></a>，</em>进入<span class="filepath" id="filepath7918994220"><a name="filepath7918994220"></a><a name="filepath7918994220"></a>“/&lt;cluster_id&gt;/install_log”</span>文件夹，下载<span class="filepath" id="filepath2092018942216"><a name="filepath2092018942216"></a><a name="filepath2092018942216"></a>“YYYYMMDDHHMMSS.tar.gz”</span>日志。<p id="p092329192212"><a name="p092329192212"></a><a name="p092329192212"></a>如/mrs-log-a3859af76b874760969cd24f2640bbb4-northchina/65d0a20f-bcb7-4da3-81d3-71fef12d993d/20170818091516.tar.gz。</p>
    </li></ol>
    <p id="p76878535355"><a name="p76878535355"></a><a name="p76878535355"></a>说明：该参数仅在MRS 1.7.2之前版本有效。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 5**  高级配置信息

    <a name="table098211912227"></a>
    <table><thead align="left"><tr id="row39964912225"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p14999990223"><a name="p14999990223"></a><a name="p14999990223"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p1451072215"><a name="p1451072215"></a><a name="p1451072215"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row18121010102211"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1516161015226"><a name="p1516161015226"></a><a name="p1516161015226"></a>现在配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p142241002214"><a name="p142241002214"></a><a name="p142241002214"></a>单击<span class="uicontrol" id="uicontrol122521072215"><a name="uicontrol122521072215"></a><a name="uicontrol122521072215"></a>“现在配置”</span>，呈现添加标签、引导操作。</p>
    <a name="ul265673984011"></a><a name="ul265673984011"></a><ul id="ul265673984011"><li>添加标签具体请参考<a href="管理集群标签.md">管理集群标签</a></li><li>添加引导操作具体请参考<a href="引导操作简介.md">引导操作简介</a></li></ul>
    </td>
    </tr>
    <tr id="row102801019225"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p16331210132219"><a name="p16331210132219"></a><a name="p16331210132219"></a>暂不配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1738121014228"><a name="p1738121014228"></a><a name="p1738121014228"></a>暂不配置任何信息。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 6**  购买时长配置

    <a name="table15934499221"></a>
    <table><thead align="left"><tr id="row19508942216"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p5956209152213"><a name="p5956209152213"></a><a name="p5956209152213"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p169619910227"><a name="p169619910227"></a><a name="p169619910227"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row11967992228"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1497159122212"><a name="p1497159122212"></a><a name="p1497159122212"></a>购买时长</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5978119112210"><a name="p5978119112210"></a><a name="p5978119112210"></a>包年/包月模式下购买集群的时长。最短时长为1个月，最长时长为9个月。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  集群配置完成后，单击右下角“立即购买”。
5.  确认集群详情，单击“提交订单“，成功提交集群创建任务。
6.  单击“返回集群列表”，可以查看到集群创建的状态。

    集群创建需要时间，所创集群的初始状态为“启动中”，创建成功后状态更新为“运行中”，请您耐心等待。


