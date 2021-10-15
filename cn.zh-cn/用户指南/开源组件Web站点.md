# 开源组件Web站点<a name="mrs_01_0362"></a>

## 场景介绍<a name="s87b80e92026344d98747153e293947c8"></a>

MRS集群默认在集群的Master节点或Core节点创建并托管了不同组件的Web站点，用户可以通过这些Web站点查看组件相关信息。

访问开源组件Web站点步骤：

1.  配置访问方式。

    MRS提供如下访问开源组件Web站点的方式：

    -   [通过弹性公网IP访问](通过弹性公网IP访问.md)：推荐使用该方式，为集群绑定弹性公网IP，简便易操作。
    -   [通过Windows弹性云服务器访问](通过Windows弹性云服务器访问.md)：需要创建单独的ECS并进行相关配置。
    -   [创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md)：当用户和MRS集群处于不同的网络中时可以使用该方式访问。

2.  访问站点。请参考[表1](#t0cd25eca33ce49e7a9663eb4d6e911f0)的地址进行访问。

## Web站点一览<a name="sd893f53bb0b2400a8fe79f43dd2b7cf8"></a>

**表 1**  开源组件Web站点地址

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
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="ul63581615542"></a><a name="ul63581615542"></a><ul id="ul63581615542"><li>适用于所有版本集群<p id="p03581564547"><a name="p03581564547"></a><a name="p03581564547"></a>https://Manager浮动IP地址:28443/web</p>
<div class="note" id="note1735817614546"><a name="note1735817614546"></a><a name="note1735817614546"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ol11358163544"></a><a name="ol11358163544"></a><ol id="ol11358163544"><li>确保本地机器与MRS集群网络互通。</li><li>远程登录Master2节点，执行“ifconfig”命令，系统回显中“eth0:wsom”表示MRS Manager浮动IP地址，请记录“inet”的实际参数值。如果在Master2节点无法查询到MRS Manager的浮动IP地址，请切换到Master1节点查询并记录。如果只有一个Master节点时，直接在该Master节点查询并记录。</li></ol>
</div></div>
</li><li>MRS 3.x之前版本集群<p id="p1635817695412"><a name="p1635817695412"></a><a name="p1635817695412"></a>https://&lt;弹性公网IP&gt;:9022/mrsmanager?locale=zh-cn</p>
<p id="p11358106185417"><a name="p11358106185417"></a><a name="p11358106185417"></a>具体请参见<a href="访问Manager-2.md">访问Manager</a>。</p>
</li></ul>
<a name="ul5358136185410"></a><a name="ul5358136185410"></a><ul id="ul5358136185410"><li>MRS 3.x及以后版本请参见<a href="访问FusionInsight-Manager（MRS-3-x及之后版本）.md">访问FusionInsight Manager（MRS 3.x及之后版本）</a>。</li></ul>
</td>
</tr>
<tr id="r0d4fe89f88484262b0f657cbbbb3f7ac"><td class="cellrowborder" rowspan="9" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a6b620d70a4384cefbe80825bf4037e61"><a name="a6b620d70a4384cefbe80825bf4037e61"></a><a name="a6b620d70a4384cefbe80825bf4037e61"></a>分析集群</p>
<p id="p549171313577"><a name="p549171313577"></a><a name="p549171313577"></a></p>
<p id="p236701316571"><a name="p236701316571"></a><a name="p236701316571"></a></p>
<p id="p1571112131579"><a name="p1571112131579"></a><a name="p1571112131579"></a></p>
<p id="p6682171405712"><a name="p6682171405712"></a><a name="p6682171405712"></a></p>
<p id="p5121315105720"><a name="p5121315105720"></a><a name="p5121315105720"></a></p>
<p id="p2356101595712"><a name="p2356101595712"></a><a name="p2356101595712"></a></p>
<p id="p19674715185711"><a name="p19674715185711"></a><a name="p19674715185711"></a></p>
<p id="p129941815175720"><a name="p129941815175720"></a><a name="p129941815175720"></a></p>
<p id="p8773141619"><a name="p8773141619"></a><a name="p8773141619"></a></p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="a6c00be87d78848da987ec881eb6eb142"><a name="a6c00be87d78848da987ec881eb6eb142"></a><a name="a6c00be87d78848da987ec881eb6eb142"></a>HDFS NameNode</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="ul17817225563"></a><a name="ul17817225563"></a><ul id="ul17817225563"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (主)”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; HDFS &gt; NameNode WebUI &gt; NameNode (<em id="i1560014241561"><a name="i1560014241561"></a><a name="i1560014241561"></a>主机名称</em>，主)”</li></ul>
</td>
</tr>
<tr id="r0dc26c0506514e85a16e049327a199af"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a55abb760b1314bcfa969b626237c1c1a"><a name="a55abb760b1314bcfa969b626237c1c1a"></a><a name="a55abb760b1314bcfa969b626237c1c1a"></a>HBase HMaster</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul28881437165720"></a><a name="ul28881437165720"></a><ul id="ul28881437165720"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; HBase &gt; HMaster WebUI &gt; HMaster (主)”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; HBase &gt; HMaster WebUI &gt; HMaster (<em id="i12639143912572"><a name="i12639143912572"></a><a name="i12639143912572"></a>主机名称</em>，主)”</li></ul>
</td>
</tr>
<tr id="r88fbe93f51c048a7ba6e02d09ce222ad"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a1ab02c26ba294b598077bd87061ab64f"><a name="a1ab02c26ba294b598077bd87061ab64f"></a><a name="a1ab02c26ba294b598077bd87061ab64f"></a>MapReduce JobHistoryServer</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul142152580577"></a><a name="ul142152580577"></a><ul id="ul142152580577"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Mapreduce &gt; JobHistoryServer WebUI &gt; JobHistoryServer (<em id="i111215175816"><a name="i111215175816"></a><a name="i111215175816"></a>主机名称</em>，主)”</li></ul>
</td>
</tr>
<tr id="r7d392cae19fd45eaa6099f0c55466d1c"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a6d317e827cf84c6fb05cbf054915330d"><a name="a6d317e827cf84c6fb05cbf054915330d"></a><a name="a6d317e827cf84c6fb05cbf054915330d"></a>YARN ResourceManager</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul153413457597"></a><a name="ul153413457597"></a><ul id="ul153413457597"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (主)”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Yarn &gt; ResourceManager WebUI &gt; ResourceManager (<em id="i8605447145915"><a name="i8605447145915"></a><a name="i8605447145915"></a>主机名称</em>，主)”</li></ul>
</td>
</tr>
<tr id="r0a1d030a635e4df891cf6cacbab2f464"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="aa661938e32a2492c97f562c64eacc66f"><a name="aa661938e32a2492c97f562c64eacc66f"></a><a name="aa661938e32a2492c97f562c64eacc66f"></a>Spark JobHistory</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul1747845913593"></a><a name="ul1747845913593"></a><ul id="ul1747845913593"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Spark &gt; Spark WebUI &gt; JobHistory”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Spark2x &gt; Spark2x WebUI &gt; JobHistory2x (<em id="i157031511606"><a name="i157031511606"></a><a name="i157031511606"></a>主机名称</em>)”</li></ul>
</td>
</tr>
<tr id="r47bac5fa08a24e79bc63ca0555fc1882"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="adcc763bbe1bd4663840aa3008da29b09"><a name="adcc763bbe1bd4663840aa3008da29b09"></a><a name="adcc763bbe1bd4663840aa3008da29b09"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul57609126012"></a><a name="ul57609126012"></a><ul id="ul57609126012"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Hue &gt; Hue WebUI &gt; Hue (主)”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Hue &gt; Hue WebUI &gt; Hue (<em id="i11788181510010"><a name="i11788181510010"></a><a name="i11788181510010"></a>主机名称</em>，主)”</li></ul>
<p id="a2d5be2b5ac084eb79ce0ee543ef25b3a"><a name="a2d5be2b5ac084eb79ce0ee543ef25b3a"></a><a name="a2d5be2b5ac084eb79ce0ee543ef25b3a"></a>Loader页面是基于开放源代码Sqoop WebUI的图形化数据迁移管理工具，由Hue WebUI承载。</p>
</td>
</tr>
<tr id="ra8e6ef4fbd474cc79c0fac2f3572ad30"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0069869151_p131653193364"><a name="zh-cn_topic_0069869151_p131653193364"></a><a name="zh-cn_topic_0069869151_p131653193364"></a>Tez</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul104411027101"></a><a name="ul104411027101"></a><ul id="ul104411027101"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Tez &gt; Tez WebUI &gt; TezUI”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Tez &gt; Tez WebUI &gt; TezUI (<em id="i1151915301003"><a name="i1151915301003"></a><a name="i1151915301003"></a>主机名称</em>)”</li></ul>
</td>
</tr>
<tr id="rb73e4340671b458eb0d2516c847591f6"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="a0e5639f9af7e445d84c3207d2df68140"><a name="a0e5639f9af7e445d84c3207d2df68140"></a><a name="a0e5639f9af7e445d84c3207d2df68140"></a>Presto</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul69741411434"></a><a name="ul69741411434"></a><ul id="ul69741411434"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Presto &gt; Presto WebUI &gt; Coordinator (主)”</li><li>在Manager页面选择“集群 &gt; 服务 &gt; Presto &gt; Coordinator WebUI &gt; Coordinator(Coordinator)”</li></ul>
</td>
</tr>
<tr id="row476191411112"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6772142011"><a name="p6772142011"></a><a name="p6772142011"></a>Ranger</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><a name="ul1984624615512"></a><a name="ul1984624615512"></a><ul id="ul1984624615512"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Ranger &gt; Ranger WebUI &gt; RangerAdmin (主)”</li><li>MRS 3.x及以后版本集群，在Manager页面选择“集群 &gt; 服务 &gt; Ranger &gt; Ranger WebUI &gt; RangerAdmin”</li></ul>
</td>
</tr>
<tr id="ra3d6594a180a486380f31b0d18d04d1f"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="a36340b5b5ba34f148032ec657abbe8a5"><a name="a36340b5b5ba34f148032ec657abbe8a5"></a><a name="a36340b5b5ba34f148032ec657abbe8a5"></a>流处理集群</p>
</td>
<td class="cellrowborder" valign="top" width="31.990000000000002%" headers="mcps1.2.4.1.2 "><p id="ae53c1928cb4549399ec212a715fb2e84"><a name="ae53c1928cb4549399ec212a715fb2e84"></a><a name="ae53c1928cb4549399ec212a715fb2e84"></a>Storm</p>
</td>
<td class="cellrowborder" valign="top" width="48.010000000000005%" headers="mcps1.2.4.1.3 "><a name="ul5311755101"></a><a name="ul5311755101"></a><ul id="ul5311755101"><li>MRS 3.x之前版本集群，在集群详情页选择“组件管理 &gt; Storm &gt; Storm WebUI &gt; UI”</li><li>在Manager页面选择“集群 &gt; 服务 &gt; Storm &gt; Storm WebUI &gt; UI (<em id="i148375567013"><a name="i148375567013"></a><a name="i148375567013"></a>主机名称</em>)”</li></ul>
</td>
</tr>
</tbody>
</table>

