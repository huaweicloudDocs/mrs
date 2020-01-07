# 开源组件Web站点<a name="ZH-CN_TOPIC_0173177999"></a>

## 场景介绍<a name="s87b80e92026344d98747153e293947c8"></a>

MRS集群默认在集群的Master节点或Core节点创建并托管了不同组件的Web站点，用户可以通过这些Web站点查看组件相关信息。由于安全原因，这些Web站点只能在集群所处的网络中被访问且不在互联网发布，普通用户可以通过在网络中创建一个带图形化界面的ECS来访问站点页面。

如果不希望创建一个单独的ECS，技术专家或开发工程师可以通过SSH隧道的动态端口转发功能，访问Web站点，详细操作请参见[创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md)。

## Web站点一览<a name="sd893f53bb0b2400a8fe79f43dd2b7cf8"></a>

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   混合集群的站点地址请根据站点类型参考分析集群和流式集群的的站点地址。  
>-   针对MRS 2.0.1及之前版本的集群，下表中站点地址列中的“组件管理”请替换为MRS Manager中的“服务管理”。例如HDFS NameNode的站点地址，请登录MRS Manager后选择“服务管理 \> HDFS \> NameNode WebUI \> NameNode \(主\)”。  

**表 1**  未启用Kerberos认证的集群

<a name="td1aa324b6c0543c786768b6ea4e7d46d"></a>
<table><thead align="left"><tr id="rbea165195734431890e52e4e6d6a90d4"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="afbf60354db99473a83d51bf9abbd2d0e"><a name="afbf60354db99473a83d51bf9abbd2d0e"></a><a name="afbf60354db99473a83d51bf9abbd2d0e"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="31.990000000000002%" id="mcps1.2.4.1.2"><p id="a059c5470392a42f29bba65d8b825dac4"><a name="a059c5470392a42f29bba65d8b825dac4"></a><a name="a059c5470392a42f29bba65d8b825dac4"></a>站点类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.010000000000005%" id="mcps1.2.4.1.3"><p id="ad1d1d5e6395e4432a31f68aa1ccacc01"><a name="ad1d1d5e6395e4432a31f68aa1ccacc01"></a><a name="ad1d1d5e6395e4432a31f68aa1ccacc01"></a>站点地址</p>
</th>
</tr>
</thead>
<tbody><tr id="r1e972b9ecd7f4f6784b3ef7ab66ae3d5"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a7cd308f17a9442fb8058bc2bdce47809"><a name="a7cd308f17a9442fb8058bc2bdce47809"></a><a name="a7cd308f17a9442fb8058bc2bdce47809"></a>全部类型</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="ae9d560a575184e6b86cc7617dea71b18"><a name="ae9d560a575184e6b86cc7617dea71b18"></a><a name="ae9d560a575184e6b86cc7617dea71b18"></a>MRS Manager</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="uf15e28119bfe4881bbe0febf9b3d09d6"></a><a name="uf15e28119bfe4881bbe0febf9b3d09d6"></a><ul id="uf15e28119bfe4881bbe0febf9b3d09d6"><li>适用于MRS 1.8.0以前版本<p id="ad035fe9c9b8b4c43b0670bde4d490171"><a name="ad035fe9c9b8b4c43b0670bde4d490171"></a><a name="ad035fe9c9b8b4c43b0670bde4d490171"></a>https://MRS Manager浮动IP地址:28443/web</p>
<div class="note" id="n65beb4e10cfe4ab3a4c8c99a3389216b"><a name="n65beb4e10cfe4ab3a4c8c99a3389216b"></a><a name="n65beb4e10cfe4ab3a4c8c99a3389216b"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a6e8b298acb6942fcb63718be4ef730c1"><a name="a6e8b298acb6942fcb63718be4ef730c1"></a><a name="a6e8b298acb6942fcb63718be4ef730c1"></a>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示MRS Manager浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到MRS Manager的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</p>
</div></div>
</li><li>适用于MRS 1.8.0及以后版本<p id="a19b35fbaf07f462b872d69c6a58e6735"><a name="a19b35fbaf07f462b872d69c6a58e6735"></a><a name="a19b35fbaf07f462b872d69c6a58e6735"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
</li></ul>
<p id="p156152394554"><a name="p156152394554"></a><a name="p156152394554"></a>具体请参见<a href="访问MRS-Manager.md">访问MRS Manager</a>和<a href="访问支持Kerberos认证的Manager.md">访问支持Kerberos认证的Manager</a>。</p>
</td>
</tr>
<tr id="rfc423b5208b84039a912108b70f0785d"><td class="cellrowborder" rowspan="8" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="ae3054eb5a86148deb2cd2063f17d0e07"><a name="ae3054eb5a86148deb2cd2063f17d0e07"></a><a name="ae3054eb5a86148deb2cd2063f17d0e07"></a>分析集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="afbe8a71099a5480f90a8bf1297a12856"><a name="afbe8a71099a5480f90a8bf1297a12856"></a><a name="afbe8a71099a5480f90a8bf1297a12856"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="u684bd16a83ee4dfd9d9fee43c117010c"></a><a name="u684bd16a83ee4dfd9d9fee43c117010c"></a><ul id="u684bd16a83ee4dfd9d9fee43c117010c"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p770781161214"><a name="zh-cn_topic_0069869151_p770781161214"></a><a name="zh-cn_topic_0069869151_p770781161214"></a>http://主NameNode角色实例IP地址:25002/dfshealth.html#tab-overview</p>
</li></ul>
<a name="u9235a479e9104ea7b375d8833f33ab09"></a><a name="u9235a479e9104ea7b375d8833f33ab09"></a><ul id="u9235a479e9104ea7b375d8833f33ab09"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="a3358ca3029a74b1b8860286cacf62a34"><a name="a3358ca3029a74b1b8860286cacf62a34"></a><a name="a3358ca3029a74b1b8860286cacf62a34"></a>http://主NameNode角色实例IP地址:9870/dfshealth.html#tab-overview</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p13726585494"><a name="zh-cn_topic_0069869151_p13726585494"></a><a name="zh-cn_topic_0069869151_p13726585494"></a>选择“<span id="ph33551213182411"><a name="ph33551213182411"></a><a name="ph33551213182411"></a>组件</span>管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</p>
</li></ul>
</td>
</tr>
<tr id="r01de7ca4bb9642a3817209870b0762b5"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a802ff6cab91747a89e26953d1e595539"><a name="a802ff6cab91747a89e26953d1e595539"></a><a name="a802ff6cab91747a89e26953d1e595539"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul5506250120"></a><a name="zh-cn_topic_0069869151_ul5506250120"></a><ul id="zh-cn_topic_0069869151_ul5506250120"><li>适用于MRS 1.6.3及以前版本<p id="a6a5e056c78014dd689b5a60b794e1313"><a name="a6a5e056c78014dd689b5a60b794e1313"></a><a name="a6a5e056c78014dd689b5a60b794e1313"></a>https://主HMaster角色实例IP地址:21301/master-status</p>
</li></ul>
<a name="ua04812c4d267429491a27a0cf10a2c62"></a><a name="ua04812c4d267429491a27a0cf10a2c62"></a><ul id="ua04812c4d267429491a27a0cf10a2c62"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p14841389186"><a name="zh-cn_topic_0069869151_p14841389186"></a><a name="zh-cn_topic_0069869151_p14841389186"></a>https://主HMaster角色实例IP地址:16010/master-status</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p228845015496"><a name="zh-cn_topic_0069869151_p228845015496"></a><a name="zh-cn_topic_0069869151_p228845015496"></a>选择“<span id="ph18120142120247"><a name="ph18120142120247"></a><a name="ph18120142120247"></a>组件</span>管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</p>
</li></ul>
</td>
</tr>
<tr id="rf5240842e4854c17939c0d80e22b1e0c"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a134175d45fa947d5a1d03377ed220d24"><a name="a134175d45fa947d5a1d03377ed220d24"></a><a name="a134175d45fa947d5a1d03377ed220d24"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="zh-cn_topic_0069869151_ul92611191215"></a><a name="zh-cn_topic_0069869151_ul92611191215"></a><ul id="zh-cn_topic_0069869151_ul92611191215"><li>适用于MRS 1.6.3及以前版本<p id="ab786a009d7be4102b25d4d40c1a5f90c"><a name="ab786a009d7be4102b25d4d40c1a5f90c"></a><a name="ab786a009d7be4102b25d4d40c1a5f90c"></a>http://JobHistoryServer角色实例IP地址:26012/jobhistory</p>
</li></ul>
<a name="uf72250d593f2412db3e07ff901a16329"></a><a name="uf72250d593f2412db3e07ff901a16329"></a><ul id="uf72250d593f2412db3e07ff901a16329"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="a16427f91244f4c16b209a2591f0dd82e"><a name="a16427f91244f4c16b209a2591f0dd82e"></a><a name="a16427f91244f4c16b209a2591f0dd82e"></a>http://JobHistoryServer角色实例IP地址:19888/jobhistory</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="a5996c81c0e2446bc8a47dbe3e5950c1a"><a name="a5996c81c0e2446bc8a47dbe3e5950c1a"></a><a name="a5996c81c0e2446bc8a47dbe3e5950c1a"></a>选择“<span id="ph173311727142411"><a name="ph173311727142411"></a><a name="ph173311727142411"></a>组件</span>管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</p>
</li></ul>
</td>
</tr>
<tr id="r5429dea56b3d4c8aa477f670cc57a4cf"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p310642615137"><a name="zh-cn_topic_0069869151_p310642615137"></a><a name="zh-cn_topic_0069869151_p310642615137"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="u07420d5d10a143a9869aa1fd7d81bb26"></a><a name="u07420d5d10a143a9869aa1fd7d81bb26"></a><ul id="u07420d5d10a143a9869aa1fd7d81bb26"><li>适用于MRS 1.6.3及以前版本<p id="a6db331ce256f48b195649af059a06bf2"><a name="a6db331ce256f48b195649af059a06bf2"></a><a name="a6db331ce256f48b195649af059a06bf2"></a>http://主ResourceManager角色实例IP地址:26000/cluster</p>
</li></ul>
<a name="u20c6daa9eaa549f5bbd5ae6821d084eb"></a><a name="u20c6daa9eaa549f5bbd5ae6821d084eb"></a><ul id="u20c6daa9eaa549f5bbd5ae6821d084eb"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p66016269183"><a name="zh-cn_topic_0069869151_p66016269183"></a><a name="zh-cn_topic_0069869151_p66016269183"></a>http://主ResourceManager角色实例IP地址:8088/cluster</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="aa65921f0b53042c9adc6897bc1f16978"><a name="aa65921f0b53042c9adc6897bc1f16978"></a><a name="aa65921f0b53042c9adc6897bc1f16978"></a>选择“<span id="ph13498163262412"><a name="ph13498163262412"></a><a name="ph13498163262412"></a>组件</span>管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</p>
</li></ul>
</td>
</tr>
<tr id="re1bee16009da47d988e676110d4ba404"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="aa6b8f78d0aea4948a60847545bc2b0a8"><a name="aa6b8f78d0aea4948a60847545bc2b0a8"></a><a name="aa6b8f78d0aea4948a60847545bc2b0a8"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="u87f39fc935294c7fba3a69f66f240c8c"></a><a name="u87f39fc935294c7fba3a69f66f240c8c"></a><ul id="u87f39fc935294c7fba3a69f66f240c8c"><li>适用于MRS 1.6.3及以前版本<p id="a9966848166af44c7a8b6ca0ad2e178f3"><a name="a9966848166af44c7a8b6ca0ad2e178f3"></a><a name="a9966848166af44c7a8b6ca0ad2e178f3"></a>http://JobHistory角色实例IP地址:22500/</p>
</li><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="adc2bb798462948ca8fd8588fd04d05f2"><a name="adc2bb798462948ca8fd8588fd04d05f2"></a><a name="adc2bb798462948ca8fd8588fd04d05f2"></a>http://JobHistory角色实例IP地址:18080/</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="af17a0fd35cb54b61bb34e09648aeda0a"><a name="af17a0fd35cb54b61bb34e09648aeda0a"></a><a name="af17a0fd35cb54b61bb34e09648aeda0a"></a>选择“<span id="ph321293542417"><a name="ph321293542417"></a><a name="ph321293542417"></a>组件</span>管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</p>
</li></ul>
</td>
</tr>
<tr id="r9087bd4a1daa410fafe9a86b94388513"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="ad53b3df8b35e4119b60b37bef93145c0"><a name="ad53b3df8b35e4119b60b37bef93145c0"></a><a name="ad53b3df8b35e4119b60b37bef93145c0"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="uc2364706b8984e0096a96f163e434cf7"></a><a name="uc2364706b8984e0096a96f163e434cf7"></a><ul id="uc2364706b8984e0096a96f163e434cf7"><li>适用于MRS 1.6.3及以前版本<p id="zh-cn_topic_0069869151_p167901358178"><a name="zh-cn_topic_0069869151_p167901358178"></a><a name="zh-cn_topic_0069869151_p167901358178"></a>https://Hue浮动IP地址:21200</p>
</li></ul>
<a name="u8e44e09e69824645b6095965dbb9a9ee"></a><a name="u8e44e09e69824645b6095965dbb9a9ee"></a><ul id="u8e44e09e69824645b6095965dbb9a9ee"><li>适用于MRS 1.6.3以后MRS 1.8.0之前的版本<p id="zh-cn_topic_0069869151_p140483513132"><a name="zh-cn_topic_0069869151_p140483513132"></a><a name="zh-cn_topic_0069869151_p140483513132"></a>https://Hue浮动IP地址:8888</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="a505c04b37939435eb84c4f0a0eba8654"><a name="a505c04b37939435eb84c4f0a0eba8654"></a><a name="a505c04b37939435eb84c4f0a0eba8654"></a>选择“<span id="ph95391240122411"><a name="ph95391240122411"></a><a name="ph95391240122411"></a>组件</span>管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</p>
</li></ul>
<p id="zh-cn_topic_0069869151_p498289163210"><a name="zh-cn_topic_0069869151_p498289163210"></a><a name="zh-cn_topic_0069869151_p498289163210"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
<div class="note" id="nffc072ceb1a240378e47235e0819cc1f"><a name="nffc072ceb1a240378e47235e0819cc1f"></a><a name="nffc072ceb1a240378e47235e0819cc1f"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0069869151_p155357479426"><a name="zh-cn_topic_0069869151_p155357479426"></a><a name="zh-cn_topic_0069869151_p155357479426"></a>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:FI_HUE”表示为Hue的浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到Hue的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</p>
</div></div>
</td>
</tr>
<tr id="r2c9d95a87d484a29826d50ea722c02a3"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p185194943416"><a name="zh-cn_topic_0069869151_p185194943416"></a><a name="zh-cn_topic_0069869151_p185194943416"></a>Tez</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a5473962e9f82410fb37abaeafbd593d2"><a name="a5473962e9f82410fb37abaeafbd593d2"></a><a name="a5473962e9f82410fb37abaeafbd593d2"></a>选择“<span id="ph202211465247"><a name="ph202211465247"></a><a name="ph202211465247"></a>组件</span>管理 &gt; Tez &gt; Tez WebUI &gt; TezUI”</p>
</td>
</tr>
<tr id="rb7bb6a04880a4f0daee8e6f9ae2deab4"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="ab90e7ff032d045328076b668a35f060e"><a name="ab90e7ff032d045328076b668a35f060e"></a><a name="ab90e7ff032d045328076b668a35f060e"></a>Presto</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="ab8ebca6e2bba4291ac862a85892fddb5"><a name="ab8ebca6e2bba4291ac862a85892fddb5"></a><a name="ab8ebca6e2bba4291ac862a85892fddb5"></a>选择“<span id="ph43110493244"><a name="ph43110493244"></a><a name="ph43110493244"></a>组件</span>管理 &gt; Presto &gt; Presto WebUI &gt; Coordinator (主)”</p>
</td>
</tr>
<tr id="r8242d5f17e6949adae9bed8621205302"><td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a164e2ca3efc349be8d27c26ff85def36"><a name="a164e2ca3efc349be8d27c26ff85def36"></a><a name="a164e2ca3efc349be8d27c26ff85def36"></a>流处理集群</p>
<p id="affd6e45a65e84087b00fe2fade665b29"><a name="affd6e45a65e84087b00fe2fade665b29"></a><a name="affd6e45a65e84087b00fe2fade665b29"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p170958315137"><a name="zh-cn_topic_0069869151_p170958315137"></a><a name="zh-cn_topic_0069869151_p170958315137"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0069869151_ul1890834616"></a><a name="zh-cn_topic_0069869151_ul1890834616"></a><ul id="zh-cn_topic_0069869151_ul1890834616"><li>适用于MRS 1.8.0以前版本<p id="zh-cn_topic_0069869151_p425855015137"><a name="zh-cn_topic_0069869151_p425855015137"></a><a name="zh-cn_topic_0069869151_p425855015137"></a>http://任一UI角色实例IP地址:29280/index.html</p>
</li></ul>
<a name="ua62d150c12e44f1092d0c7908c0a0921"></a><a name="ua62d150c12e44f1092d0c7908c0a0921"></a><ul id="ua62d150c12e44f1092d0c7908c0a0921"><li>适用于MRS 1.8.0及以后版本<p id="zh-cn_topic_0069869151_p44851318815"><a name="zh-cn_topic_0069869151_p44851318815"></a><a name="zh-cn_topic_0069869151_p44851318815"></a>选择“<span id="ph967345362413"><a name="ph967345362413"></a><a name="ph967345362413"></a>组件</span>管理 &gt; Storm &gt; Storm WebUI &gt; UI”</p>
</li></ul>
</td>
</tr>
<tr id="r59360952085048d1ba1420e43c9201e3"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p102254291554"><a name="zh-cn_topic_0069869151_p102254291554"></a><a name="zh-cn_topic_0069869151_p102254291554"></a>KafkaManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p174984581558"><a name="zh-cn_topic_0069869151_p174984581558"></a><a name="zh-cn_topic_0069869151_p174984581558"></a>选择“<span id="ph9552135618240"><a name="ph9552135618240"></a><a name="ph9552135618240"></a>组件</span>管理 &gt; KafkaManager &gt; KafkaManager WebUI &gt; KafkaManager”</p>
</td>
</tr>
</tbody>
</table>

**表 2**  启用Kerberos认证的集群

<a name="t0cd25eca33ce49e7a9663eb4d6e911f0"></a>
<table><thead align="left"><tr id="rdd50b7ce973f48bc92dbbed622a0d6f0"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0069869151_p599826715927"><a name="zh-cn_topic_0069869151_p599826715927"></a><a name="zh-cn_topic_0069869151_p599826715927"></a>集群类型</p>
</th>
<th class="cellrowborder" valign="top" width="31.990000000000002%" id="mcps1.2.4.1.2"><p id="a553008fabcc74d95807aa2766d314252"><a name="a553008fabcc74d95807aa2766d314252"></a><a name="a553008fabcc74d95807aa2766d314252"></a>站点类型</p>
</th>
<th class="cellrowborder" valign="top" width="48.010000000000005%" id="mcps1.2.4.1.3"><p id="a75c50c645471433496edaaeea793df29"><a name="a75c50c645471433496edaaeea793df29"></a><a name="a75c50c645471433496edaaeea793df29"></a>站点地址</p>
</th>
</tr>
</thead>
<tbody><tr id="r8f1502e284464ae3bcd517c843cf7fa7"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a6c5df37e43f54c92b477ffae14a5ce80"><a name="a6c5df37e43f54c92b477ffae14a5ce80"></a><a name="a6c5df37e43f54c92b477ffae14a5ce80"></a>全部类型</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="a628ec3225ee1482887b8008f6f7fdefb"><a name="a628ec3225ee1482887b8008f6f7fdefb"></a><a name="a628ec3225ee1482887b8008f6f7fdefb"></a>MRS Manager</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="ue04b57bdddc046d4844efabd8f1fea6a"></a><a name="ue04b57bdddc046d4844efabd8f1fea6a"></a><ul id="ue04b57bdddc046d4844efabd8f1fea6a"><li>适用于MRS 1.8.0以前版本<p id="a1a7e441704b643ba90115ebad4e19242"><a name="a1a7e441704b643ba90115ebad4e19242"></a><a name="a1a7e441704b643ba90115ebad4e19242"></a>https://MRS Manager浮动IP地址:28443/web</p>
</li><li>适用于MRS 1.8.0及以后版本<p id="a37ccd0159687490c9d3412d4ee7625ef"><a name="a37ccd0159687490c9d3412d4ee7625ef"></a><a name="a37ccd0159687490c9d3412d4ee7625ef"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
</li></ul>
<p id="p4870113310566"><a name="p4870113310566"></a><a name="p4870113310566"></a>具体请参见<a href="访问MRS-Manager.md">访问MRS Manager</a>和<a href="访问支持Kerberos认证的Manager.md">访问支持Kerberos认证的Manager</a>。</p>
</td>
</tr>
<tr id="r0d4fe89f88484262b0f657cbbbb3f7ac"><td class="cellrowborder" rowspan="8" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a6b620d70a4384cefbe80825bf4037e61"><a name="a6b620d70a4384cefbe80825bf4037e61"></a><a name="a6b620d70a4384cefbe80825bf4037e61"></a>分析集群</p>
<p id="p549171313577"><a name="p549171313577"></a><a name="p549171313577"></a></p>
<p id="p236701316571"><a name="p236701316571"></a><a name="p236701316571"></a></p>
<p id="p1571112131579"><a name="p1571112131579"></a><a name="p1571112131579"></a></p>
<p id="p6682171405712"><a name="p6682171405712"></a><a name="p6682171405712"></a></p>
<p id="p5121315105720"><a name="p5121315105720"></a><a name="p5121315105720"></a></p>
<p id="p2356101595712"><a name="p2356101595712"></a><a name="p2356101595712"></a></p>
<p id="p19674715185711"><a name="p19674715185711"></a><a name="p19674715185711"></a></p>
<p id="p129941815175720"><a name="p129941815175720"></a><a name="p129941815175720"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="a6c00be87d78848da987ec881eb6eb142"><a name="a6c00be87d78848da987ec881eb6eb142"></a><a name="a6c00be87d78848da987ec881eb6eb142"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><p id="a694b97ab89504776a0e68b3d09a48bf8"><a name="a694b97ab89504776a0e68b3d09a48bf8"></a><a name="a694b97ab89504776a0e68b3d09a48bf8"></a>选择“<span id="ph1754623253"><a name="ph1754623253"></a><a name="ph1754623253"></a>组件</span>管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</p>
</td>
</tr>
<tr id="r0dc26c0506514e85a16e049327a199af"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a55abb760b1314bcfa969b626237c1c1a"><a name="a55abb760b1314bcfa969b626237c1c1a"></a><a name="a55abb760b1314bcfa969b626237c1c1a"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a91a0e09f9ecd44bc84ae3d95841b8d17"><a name="a91a0e09f9ecd44bc84ae3d95841b8d17"></a><a name="a91a0e09f9ecd44bc84ae3d95841b8d17"></a>选择“<span id="ph1641124192511"><a name="ph1641124192511"></a><a name="ph1641124192511"></a>组件</span>管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</p>
</td>
</tr>
<tr id="r88fbe93f51c048a7ba6e02d09ce222ad"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a1ab02c26ba294b598077bd87061ab64f"><a name="a1ab02c26ba294b598077bd87061ab64f"></a><a name="a1ab02c26ba294b598077bd87061ab64f"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a3d63e60c2e75470fb637fd93b615e06d"><a name="a3d63e60c2e75470fb637fd93b615e06d"></a><a name="a3d63e60c2e75470fb637fd93b615e06d"></a>选择“<span id="ph71290732510"><a name="ph71290732510"></a><a name="ph71290732510"></a>组件</span>管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</p>
</td>
</tr>
<tr id="r7d392cae19fd45eaa6099f0c55466d1c"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a6d317e827cf84c6fb05cbf054915330d"><a name="a6d317e827cf84c6fb05cbf054915330d"></a><a name="a6d317e827cf84c6fb05cbf054915330d"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a1f2611241be045df83d0feb9da440594"><a name="a1f2611241be045df83d0feb9da440594"></a><a name="a1f2611241be045df83d0feb9da440594"></a>选择“<span id="ph1652579152519"><a name="ph1652579152519"></a><a name="ph1652579152519"></a>组件</span>管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</p>
</td>
</tr>
<tr id="r0a1d030a635e4df891cf6cacbab2f464"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="aa661938e32a2492c97f562c64eacc66f"><a name="aa661938e32a2492c97f562c64eacc66f"></a><a name="aa661938e32a2492c97f562c64eacc66f"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a4354fd6c86ce4f11bac727a2bd0ea002"><a name="a4354fd6c86ce4f11bac727a2bd0ea002"></a><a name="a4354fd6c86ce4f11bac727a2bd0ea002"></a>选择“<span id="ph14618811132513"><a name="ph14618811132513"></a><a name="ph14618811132513"></a>组件</span>管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</p>
</td>
</tr>
<tr id="r47bac5fa08a24e79bc63ca0555fc1882"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="adcc763bbe1bd4663840aa3008da29b09"><a name="adcc763bbe1bd4663840aa3008da29b09"></a><a name="adcc763bbe1bd4663840aa3008da29b09"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="abffaadc717794ede9834d3f472294f93"><a name="abffaadc717794ede9834d3f472294f93"></a><a name="abffaadc717794ede9834d3f472294f93"></a>选择“<span id="ph1439791416253"><a name="ph1439791416253"></a><a name="ph1439791416253"></a>组件</span>管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</p>
<p id="a2d5be2b5ac084eb79ce0ee543ef25b3a"><a name="a2d5be2b5ac084eb79ce0ee543ef25b3a"></a><a name="a2d5be2b5ac084eb79ce0ee543ef25b3a"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
</td>
</tr>
<tr id="ra8e6ef4fbd474cc79c0fac2f3572ad30"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p131653193364"><a name="zh-cn_topic_0069869151_p131653193364"></a><a name="zh-cn_topic_0069869151_p131653193364"></a>Tez</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="a5a45f8ed1eb247d3b07713ffaa5c9bad"><a name="a5a45f8ed1eb247d3b07713ffaa5c9bad"></a><a name="a5a45f8ed1eb247d3b07713ffaa5c9bad"></a>选择“<span id="ph15975717192513"><a name="ph15975717192513"></a><a name="ph15975717192513"></a>组件</span>管理 &gt; Tez &gt; Tez WebUI &gt; TezUI”</p>
</td>
</tr>
<tr id="rb73e4340671b458eb0d2516c847591f6"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a0e5639f9af7e445d84c3207d2df68140"><a name="a0e5639f9af7e445d84c3207d2df68140"></a><a name="a0e5639f9af7e445d84c3207d2df68140"></a>Presto</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p28001345837"><a name="zh-cn_topic_0069869151_p28001345837"></a><a name="zh-cn_topic_0069869151_p28001345837"></a>选择“<span id="ph1125414214254"><a name="ph1125414214254"></a><a name="ph1125414214254"></a>组件</span>管理 &gt; Presto &gt; Presto WebUI &gt; Coordinator (主)”</p>
</td>
</tr>
<tr id="ra3d6594a180a486380f31b0d18d04d1f"><td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a36340b5b5ba34f148032ec657abbe8a5"><a name="a36340b5b5ba34f148032ec657abbe8a5"></a><a name="a36340b5b5ba34f148032ec657abbe8a5"></a>流处理集群</p>
<p id="zh-cn_topic_0069869151_p290222914319"><a name="zh-cn_topic_0069869151_p290222914319"></a><a name="zh-cn_topic_0069869151_p290222914319"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="ae53c1928cb4549399ec212a715fb2e84"><a name="ae53c1928cb4549399ec212a715fb2e84"></a><a name="ae53c1928cb4549399ec212a715fb2e84"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><p id="a46c8bab6afbd4c2a9c6ee60b52eb2b9e"><a name="a46c8bab6afbd4c2a9c6ee60b52eb2b9e"></a><a name="a46c8bab6afbd4c2a9c6ee60b52eb2b9e"></a>选择“<span id="ph9568132332510"><a name="ph9568132332510"></a><a name="ph9568132332510"></a>组件</span>管理 &gt; Storm &gt; Storm WebUI &gt; UI”</p>
</td>
</tr>
<tr id="rd4c61ec2397243a6b89017947ea4786d"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="ad625cff657f340c3a785c986024027e5"><a name="ad625cff657f340c3a785c986024027e5"></a><a name="ad625cff657f340c3a785c986024027e5"></a>KafkaManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p161247311330"><a name="zh-cn_topic_0069869151_p161247311330"></a><a name="zh-cn_topic_0069869151_p161247311330"></a>选择“<span id="ph1841652616250"><a name="ph1841652616250"></a><a name="ph1841652616250"></a>组件</span>管理 &gt; KafkaManager &gt; KafkaManager WebUI &gt; KafkaManager”</p>
</td>
</tr>
</tbody>
</table>

