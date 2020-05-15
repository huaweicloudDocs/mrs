# 开源组件Web站点<a name="ZH-CN_TOPIC_0173177999"></a>

## 场景介绍<a name="s87b80e92026344d98747153e293947c8"></a>

MRS集群默认在集群的Master节点或Core节点创建并托管了不同组件的Web站点，用户可以通过这些Web站点查看组件相关信息。

访问开源组件Web站点步骤：

1.  配置访问方式。

    MRS提供如下三种访问开源组件Web站点的方式：

    -   [通过弹性公网IP访问](通过弹性公网IP访问.md)：推荐使用该方式，为集群绑定弹性公网IP，简便易操作。MRS 1.8.0及之后版本支持该方式。
    -   [通过Windows弹性云服务器访问](通过Windows弹性云服务器访问.md)：需要创建单独的ECS并进行相关配置。MRS 1.8.0之前版本的安全集群和MRS 1.6.3以后MRS 1.8.0之前版本的普通集群请使用该方式，MRS 1.6.3及之前版本的普通集群请参考[表1](#td1aa324b6c0543c786768b6ea4e7d46d)中的站点地址访问。
    -   [创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md)：当用户和MRS集群处于不同的网络中时可以使用该方式访问。

2.  访问站点。请参考[表1](#td1aa324b6c0543c786768b6ea4e7d46d)的地址进行访问。

## Web站点一览<a name="sd893f53bb0b2400a8fe79f43dd2b7cf8"></a>

**表 1**  开源组件Web站点地址

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
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="uf15e28119bfe4881bbe0febf9b3d09d6"></a><a name="uf15e28119bfe4881bbe0febf9b3d09d6"></a><ul id="uf15e28119bfe4881bbe0febf9b3d09d6"><li>MRS 1.8.0以前版本<p id="ad035fe9c9b8b4c43b0670bde4d490171"><a name="ad035fe9c9b8b4c43b0670bde4d490171"></a><a name="ad035fe9c9b8b4c43b0670bde4d490171"></a>https://MRS Manager浮动IP地址:28443/web</p>
<div class="note" id="n65beb4e10cfe4ab3a4c8c99a3389216b"><a name="n65beb4e10cfe4ab3a4c8c99a3389216b"></a><a name="n65beb4e10cfe4ab3a4c8c99a3389216b"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a6e8b298acb6942fcb63718be4ef730c1"><a name="a6e8b298acb6942fcb63718be4ef730c1"></a><a name="a6e8b298acb6942fcb63718be4ef730c1"></a>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示MRS Manager浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到MRS Manager的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</p>
</div></div>
</li><li>MRS 1.8.0及以后版本<p id="a19b35fbaf07f462b872d69c6a58e6735"><a name="a19b35fbaf07f462b872d69c6a58e6735"></a><a name="a19b35fbaf07f462b872d69c6a58e6735"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
</li></ul>
<p id="p156152394554"><a name="p156152394554"></a><a name="p156152394554"></a>具体请参见<a href="访问MRS-Manager.md">访问MRS Manager</a>和<a href="访问支持Kerberos认证的Manager.md">访问支持Kerberos认证的Manager</a>。</p>
</td>
</tr>
<tr id="rfc423b5208b84039a912108b70f0785d"><td class="cellrowborder" rowspan="8" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="ae3054eb5a86148deb2cd2063f17d0e07"><a name="ae3054eb5a86148deb2cd2063f17d0e07"></a><a name="ae3054eb5a86148deb2cd2063f17d0e07"></a>分析集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="afbe8a71099a5480f90a8bf1297a12856"><a name="afbe8a71099a5480f90a8bf1297a12856"></a><a name="afbe8a71099a5480f90a8bf1297a12856"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="u9235a479e9104ea7b375d8833f33ab09"></a><a name="u9235a479e9104ea7b375d8833f33ab09"></a><ul id="u9235a479e9104ea7b375d8833f33ab09"><li>MRS 1.6.3及以前版本<a name="ul642397524"></a><a name="ul642397524"></a><ul id="ul642397524"><li>普通集群：http://主NameNode角色实例IP地址:25002/dfshealth.html#tab-overview</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul19696183519525"></a><a name="ul19696183519525"></a><ul id="ul19696183519525"><li>普通集群：http://主NameNode角色实例IP地址:9870/dfshealth.html#tab-overview</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</li></ul>
</td>
</tr>
<tr id="r01de7ca4bb9642a3817209870b0762b5"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a802ff6cab91747a89e26953d1e595539"><a name="a802ff6cab91747a89e26953d1e595539"></a><a name="a802ff6cab91747a89e26953d1e595539"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ua04812c4d267429491a27a0cf10a2c62"></a><a name="ua04812c4d267429491a27a0cf10a2c62"></a><ul id="ua04812c4d267429491a27a0cf10a2c62"><li>MRS 1.6.3及以前版本<a name="ul1656113116119"></a><a name="ul1656113116119"></a><ul id="ul1656113116119"><li>普通集群：https://主HMaster角色实例IP地址:21301/master-status</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul16574319115"></a><a name="ul16574319115"></a><ul id="ul16574319115"><li>普通集群：https://主HMaster角色实例IP地址:16010/master-status</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</li></ul>
</td>
</tr>
<tr id="rf5240842e4854c17939c0d80e22b1e0c"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a134175d45fa947d5a1d03377ed220d24"><a name="a134175d45fa947d5a1d03377ed220d24"></a><a name="a134175d45fa947d5a1d03377ed220d24"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul14263811165"></a><a name="ul14263811165"></a><ul id="ul14263811165"><li>MRS 1.6.3及以前版本<a name="ul826331115619"></a><a name="ul826331115619"></a><ul id="ul826331115619"><li>普通集群：http://JobHistoryServer角色实例IP地址:26012/jobhistory</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul12263201118615"></a><a name="ul12263201118615"></a><ul id="ul12263201118615"><li>普通集群：http://JobHistoryServer角色实例IP地址:19888/jobhistory</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</li></ul>
</td>
</tr>
<tr id="r5429dea56b3d4c8aa477f670cc57a4cf"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p310642615137"><a name="zh-cn_topic_0069869151_p310642615137"></a><a name="zh-cn_topic_0069869151_p310642615137"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul7432736989"></a><a name="ul7432736989"></a><ul id="ul7432736989"><li>MRS 1.6.3及以前版本<a name="ul1143243616814"></a><a name="ul1143243616814"></a><ul id="ul1143243616814"><li>普通集群：http://主ResourceManager角色实例IP地址:26000/cluster</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul543220362088"></a><a name="ul543220362088"></a><ul id="ul543220362088"><li>普通集群：http://主ResourceManager角色实例IP地址:8088/cluster</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</li></ul>
</td>
</tr>
<tr id="re1bee16009da47d988e676110d4ba404"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="aa6b8f78d0aea4948a60847545bc2b0a8"><a name="aa6b8f78d0aea4948a60847545bc2b0a8"></a><a name="aa6b8f78d0aea4948a60847545bc2b0a8"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul3779105416108"></a><a name="ul3779105416108"></a><ul id="ul3779105416108"><li>MRS 1.6.3及以前版本<a name="ul4779654121015"></a><a name="ul4779654121015"></a><ul id="ul4779654121015"><li>普通集群：http://JobHistory角色实例IP地址:22500/</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul1177945411014"></a><a name="ul1177945411014"></a><ul id="ul1177945411014"><li>普通集群：http://JobHistory角色实例IP地址:18080/</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</li></ul>
</td>
</tr>
<tr id="r9087bd4a1daa410fafe9a86b94388513"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="ad53b3df8b35e4119b60b37bef93145c0"><a name="ad53b3df8b35e4119b60b37bef93145c0"></a><a name="ad53b3df8b35e4119b60b37bef93145c0"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul1632101441810"></a><a name="ul1632101441810"></a><ul id="ul1632101441810"><li>MRS 1.6.3及以前版本<a name="ul0321014161810"></a><a name="ul0321014161810"></a><ul id="ul0321014161810"><li>普通集群：https://Hue浮动IP地址:21200</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</li></ul>
</li><li>MRS 1.6.3以后MRS 1.8.0之前的版本<a name="ul133814121816"></a><a name="ul133814121816"></a><ul id="ul133814121816"><li>普通集群：https://Hue浮动IP地址:8888</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</li></ul>
<p id="zh-cn_topic_0069869151_p498289163210"><a name="zh-cn_topic_0069869151_p498289163210"></a><a name="zh-cn_topic_0069869151_p498289163210"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
<div class="note" id="nffc072ceb1a240378e47235e0819cc1f"><a name="nffc072ceb1a240378e47235e0819cc1f"></a><a name="nffc072ceb1a240378e47235e0819cc1f"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0069869151_p155357479426"><a name="zh-cn_topic_0069869151_p155357479426"></a><a name="zh-cn_topic_0069869151_p155357479426"></a>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:FI_HUE”表示为Hue的浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到Hue的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</p>
</div></div>
</td>
</tr>
<tr id="r2c9d95a87d484a29826d50ea722c02a3"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p185194943416"><a name="zh-cn_topic_0069869151_p185194943416"></a><a name="zh-cn_topic_0069869151_p185194943416"></a>Tez</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p688419422118"><a name="p688419422118"></a><a name="p688419422118"></a>在集群详情页选择“组件管理 &gt; Tez &gt; Tez WebUI &gt; TezUI”</p>
</td>
</tr>
<tr id="rb7bb6a04880a4f0daee8e6f9ae2deab4"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="ab90e7ff032d045328076b668a35f060e"><a name="ab90e7ff032d045328076b668a35f060e"></a><a name="ab90e7ff032d045328076b668a35f060e"></a>Presto</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul19817734142118"></a><a name="ul19817734142118"></a><ul id="ul19817734142118"><li>MRS 2.0.1之前版本：在MRS Manager页面选择“服务管理 &gt; Presto &gt; Presto WebUI &gt; Coordinator (主)”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Presto &gt; Presto WebUI &gt; Coordinator (主)”</li></ul>
</td>
</tr>
<tr id="r8242d5f17e6949adae9bed8621205302"><td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a164e2ca3efc349be8d27c26ff85def36"><a name="a164e2ca3efc349be8d27c26ff85def36"></a><a name="a164e2ca3efc349be8d27c26ff85def36"></a>流处理集群</p>
<p id="affd6e45a65e84087b00fe2fade665b29"><a name="affd6e45a65e84087b00fe2fade665b29"></a><a name="affd6e45a65e84087b00fe2fade665b29"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p170958315137"><a name="zh-cn_topic_0069869151_p170958315137"></a><a name="zh-cn_topic_0069869151_p170958315137"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="ua62d150c12e44f1092d0c7908c0a0921"></a><a name="ua62d150c12e44f1092d0c7908c0a0921"></a><ul id="ua62d150c12e44f1092d0c7908c0a0921"><li>MRS 1.8.0之前的版本<a name="ul161285718241"></a><a name="ul161285718241"></a><ul id="ul161285718241"><li>普通集群：http://任一UI角色实例IP地址:29280/index.html</li><li>安全集群：在MRS Manager页面选择“服务管理 &gt; Storm &gt; Storm WebUI &gt; UI”</li></ul>
</li><li>MRS 1.8.x版本：在MRS Manager页面选择“服务管理 &gt; Storm &gt; Storm WebUI &gt; UI”</li><li>MRS 2.0.1及以后版本：在集群详情页选择“组件管理 &gt; Storm &gt; Storm WebUI &gt; UI”</li></ul>
</td>
</tr>
<tr id="r59360952085048d1ba1420e43c9201e3"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p102254291554"><a name="zh-cn_topic_0069869151_p102254291554"></a><a name="zh-cn_topic_0069869151_p102254291554"></a>KafkaManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0069869151_p174984581558"><a name="zh-cn_topic_0069869151_p174984581558"></a><a name="zh-cn_topic_0069869151_p174984581558"></a>在MRS Manager页面选择“服务管理 &gt; KafkaManager &gt; KafkaManager WebUI &gt; KafkaManager”</p>
</td>
</tr>
</tbody>
</table>

