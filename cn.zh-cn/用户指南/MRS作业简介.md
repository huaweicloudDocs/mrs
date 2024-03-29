# MRS作业简介<a name="mrs_01_0051"></a>

MRS作业是MRS为用户提供的程序执行平台，用于处理和分析用户数据。作业创建完成后，所有的作业列表信息展示在“作业管理“页面中，您可以查看所有的作业列表，也可以创建和管理作业。若集群详情页面不支持“作业管理“页签，请通过后台方式提交作业。

MRS集群处理的数据源来源于OBS或HDFS，HDFS是Hadoop分布式文件系统（Hadoop Distributed File System），OBS即对象存储服务，是一个基于对象的海量存储服务，为客户提供海量、安全、高可靠、低成本的数据存储能力。MRS可以直接处理OBS中的数据，客户可以基于管理控制台Web界面和OBS客户端对数据进行浏览、管理和使用，同时可以通过REST API接口方式单独或集成到业务程序进行管理和访问数据。

用户创建作业前需要将本地数据上传至OBS系统，MRS使用OBS中的数据进行计算分析。当然MRS也支持将OBS中的数据导入至HDFS中，使用HDFS中的数据进行计算分析。数据完成处理和分析后，您可以将数据存储在HDFS中，也可以将集群中的数据导出至OBS系统。需要注意，HDFS和OBS也支持存储压缩格式的数据，目前支持存储bz2、gz压缩格式的数据。

## 作业分类<a name="section992317541770"></a>

目前MRS集群支持创建和管理如下几种类型的作业。如果处于“运行中“状态的集群创建作业失败，请查看集群管理页面中相关组件健康情况。操作方法，请参见[查看和定制集群监控指标](查看和定制集群监控指标.md)。

-   MapReduce：提供快速并行处理大量数据的能力，是一种分布式数据处理模式和执行环境。MRS当前支持提交MapReduce Jar程序。
-   Spark：基于内存进行计算的分布式计算框架，MRS当前支持提交SparkSubmit、Spark Script和Spark SQL作业。
    -   SparkSubmit：支持提交Spark Jar和Spark python程序，执行Spark application，计算和处理用户数据。
    -   SparkScript：支持提交SparkScript脚本，批量执行Spark SQL语句。
    -   Spark SQL：运用Spark提供的类似SQL的Spark SQL语言，实时查询和分析用户数据。

-   Hive：建立在Hadoop基础上的开源的数据仓库。MRS当前支持提交HiveScript脚本，和执行Hive SQL语句。
-   Flink：提供一个分布式大数据处理引擎，可对有限数据流和无限数据流进行有状态计算。

## 作业列表<a name="section841709416292"></a>

作业列表默认按时间顺序排列，时间最近的作业显示在最前端。各类作业列表参数说明如[表 1](#table38822211162654)所示。

**表 1**  作业列表参数

<a name="table38822211162654"></a>
<table><thead align="left"><tr id="row34098764162654"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p27719311162654"><a name="p27719311162654"></a><a name="p27719311162654"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p30671727162654"><a name="p30671727162654"></a><a name="p30671727162654"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row42885145165327"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17166527165340"><a name="p17166527165340"></a><a name="p17166527165340"></a>作业名称/ID</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p48311417165340"><a name="p48311417165340"></a><a name="p48311417165340"></a>作业的名称，新增作业时配置。</p>
<p id="p193709282188"><a name="p193709282188"></a><a name="p193709282188"></a>ID是作业的唯一标识，作业新增后系统自动赋值。</p>
</td>
</tr>
<tr id="row108151404302"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p981654003013"><a name="p981654003013"></a><a name="p981654003013"></a>用户名称</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p158161940163017"><a name="p158161940163017"></a><a name="p158161940163017"></a>提交作业的用户名称。</p>
</td>
</tr>
<tr id="row6153362791419"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1816792591419"><a name="p1816792591419"></a><a name="p1816792591419"></a>作业类型</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p27601125115453"><a name="p27601125115453"></a><a name="p27601125115453"></a>支持的作业类型：</p>
<a name="ul47083539115453"></a><a name="ul47083539115453"></a><ul id="ul47083539115453"><li>Distcp：导入、导出数据</li><li>MapReduce</li><li>Spark</li><li>SparkSubmit</li><li>SparkScript</li><li>Spark SQL</li><li>Hive SQL</li><li>HiveScript</li><li>Flink</li></ul>
<div class="note" id="note1880140112120"><a name="note1880140112120"></a><a name="note1880140112120"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul18242201511307"></a><a name="ul18242201511307"></a><ul id="ul18242201511307"><li>在<span class="wintitle" id="wintitle1879134052114"><a name="wintitle1879134052114"></a><a name="wintitle1879134052114"></a>“文件管理”</span>页面进行文件的导入导出操作后，您可以在<span class="wintitle" id="wintitle9880184012110"><a name="wintitle9880184012110"></a><a name="wintitle9880184012110"></a>“作业管理”</span>页面查看Distcp作业。</li><li>只有创建集群时选择了Spark、Hive和Flink组件，并且集群处于运行中，才能新增Spark、Hive和Flink类型的作业。</li></ul>
</div></div>
</td>
</tr>
<tr id="row44482813113250"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p46338114113250"><a name="p46338114113250"></a><a name="p46338114113250"></a>状态</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p62399739113250"><a name="p62399739113250"></a><a name="p62399739113250"></a>显示作业的状态。</p>
<a name="ul805096292920"></a><a name="ul805096292920"></a><ul id="ul805096292920"><li>已提交</li><li>已接受</li><li>运行中</li><li>已完成</li><li>已终止</li><li>异常</li></ul>
</td>
</tr>
<tr id="row494107911332"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p6468315011332"><a name="p6468315011332"></a><a name="p6468315011332"></a>执行结果</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p484376011332"><a name="p484376011332"></a><a name="p484376011332"></a>显示作业执行完成的结果。</p>
<a name="ul6488394795222"></a><a name="ul6488394795222"></a><ul id="ul6488394795222"><li>未定：正在执行的作业。</li><li>成功：执行成功的作业。</li><li>终止：执行中被手动终止的作业。</li><li>失败：执行失败的作业。</li></ul>
<div class="note" id="note23001598114642"><a name="note23001598114642"></a><a name="note23001598114642"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p5687796114642"><a name="p5687796114642"></a><a name="p5687796114642"></a>作业执行成功或失败后都不能再次执行，只能新增作业，配置作业参数后重新提交作业。</p>
</div></div>
</td>
</tr>
<tr id="row53867856113313"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1220239113313"><a name="p1220239113313"></a><a name="p1220239113313"></a>作业提交时间</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p31730530113313"><a name="p31730530113313"></a><a name="p31730530113313"></a>记录作业提交的开始时间。</p>
</td>
</tr>
<tr id="row5549133644919"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1954943614918"><a name="p1954943614918"></a><a name="p1954943614918"></a>作业结束时间</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p454933613497"><a name="p454933613497"></a><a name="p454933613497"></a>记录作业执行完成或手工停止的时间。</p>
</td>
</tr>
<tr id="row45051218102033"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p25270067102033"><a name="p25270067102033"></a><a name="p25270067102033"></a>操作</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><a name="ul50349227102458"></a><a name="ul50349227102458"></a><ul id="ul50349227102458"><li>查看日志：单击<span class="uicontrol" id="uicontrol1265814913131"><a name="uicontrol1265814913131"></a><a name="uicontrol1265814913131"></a>“查看日志”</span>，查看运行中的作业执行的实时日志信息。操作方法，请参见<a href="查看作业配置信息和日志.md">查看作业配置信息和日志</a>。</li><li>查看详情：单击<span class="uicontrol" id="uicontrol58686534131324"><a name="uicontrol58686534131324"></a><a name="uicontrol58686534131324"></a>“查看详情”</span>，查看作业的详细配置信息。操作方法，请参见<a href="查看作业配置信息和日志.md">查看作业配置信息和日志</a>。</li><li>更多<a name="ul6838970152917"></a><a name="ul6838970152917"></a><ul id="ul6838970152917"><li>停止：单击<span class="uicontrol" id="uicontrol11788451131346"><a name="uicontrol11788451131346"></a><a name="uicontrol11788451131346"></a>“停止”</span>，停止正在运行的作业。操作方法，请参见<a href="停止作业.md">停止作业</a>。</li><li>删除：单击<span class="uicontrol" id="uicontrol284949131443"><a name="uicontrol284949131443"></a><a name="uicontrol284949131443"></a>“删除”</span>，删除一个作业。操作方法，请参见<a href="删除作业.md">删除作业</a>。</li><li>结果：单击<span class="uicontrol" id="uicontrol1457111916416"><a name="uicontrol1457111916416"></a><a name="uicontrol1457111916416"></a>“结果”</span>，查看SparkSql和SparkScript类型的<span class="parmname" id="parmname18831926184314"><a name="parmname18831926184314"></a><a name="parmname18831926184314"></a>“状态”</span>为<span class="parmvalue" id="parmvalue119844289434"><a name="parmvalue119844289434"></a><a name="parmvalue119844289434"></a>“已完成”</span>且<span class="parmname" id="parmname379519325436"><a name="parmname379519325436"></a><a name="parmname379519325436"></a>“执行结果”</span>为<span class="parmvalue" id="parmvalue15955535134312"><a name="parmvalue15955535134312"></a><a name="parmvalue15955535134312"></a>“成功”</span>的作业执行结果。</li></ul>
<div class="note" id="note22656211102524"><a name="note22656211102524"></a><a name="note22656211102524"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul21412974111314"></a><a name="ul21412974111314"></a><ul id="ul21412974111314"><li>Spark SQL作业不支持停止。</li><li>作业删除后不可恢复，请谨慎操作。</li><li>当选择保留作业日志到OBS或HDFS时，系统在作业执行结束后，将日志压缩并存储到对应路径。因此，此类作业运行结束后，作业状态仍然为“运行中”，需等日志存储成功后，状态变更为“已完成”。日志存储花费时间依赖于日志大小，需要数分钟以上。</li></ul>
</div></div>
</li></ul>
</td>
</tr>
</tbody>
</table>

**表 2**  按钮说明

<a name="table3011042510139"></a>
<table><thead align="left"><tr id="row708755810139"><th class="cellrowborder" valign="top" width="26.68%" id="mcps1.2.3.1.1"><p id="p6655665410139"><a name="p6655665410139"></a><a name="p6655665410139"></a>按钮</p>
</th>
<th class="cellrowborder" valign="top" width="73.32%" id="mcps1.2.3.1.2"><p id="p2237991710139"><a name="p2237991710139"></a><a name="p2237991710139"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row7481172093319"><td class="cellrowborder" valign="top" width="26.68%" headers="mcps1.2.3.1.1 "><p id="p87221353171918"><a name="p87221353171918"></a><a name="p87221353171918"></a><a name="image87091653131919"></a><a name="image87091653131919"></a><span><img id="image87091653131919" src="figures/icon_mrs_selectdate.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="73.32%" headers="mcps1.2.3.1.2 "><p id="p154811720123319"><a name="p154811720123319"></a><a name="p154811720123319"></a>选择提交作业的时间区间，筛选在对应时间区间内提交的作业。</p>
</td>
</tr>
<tr id="row9266410139"><td class="cellrowborder" valign="top" width="26.68%" headers="mcps1.2.3.1.1 "><p id="p750586110139"><a name="p750586110139"></a><a name="p750586110139"></a><a name="image16983222163520"></a><a name="image16983222163520"></a><span><img id="image16983222163520" src="figures/zh-cn_image_0275521910.png" width="131.67000000000002" height="20.206690000000002"></span></p>
</td>
<td class="cellrowborder" valign="top" width="73.32%" headers="mcps1.2.3.1.2 "><p id="p5344702710412"><a name="p5344702710412"></a><a name="p5344702710412"></a>在下拉框中选择作业执行结果，筛选作业。</p>
<a name="ul1294383513519"></a><a name="ul1294383513519"></a><ul id="ul1294383513519"><li>全部：表示筛选所有的作业。</li><li>成功：表示筛选执行成功的作业。</li><li>未定：表示筛选正在执行的作业。</li><li>终止：表示筛选被手动终止的作业。</li><li>失败：表示筛选执行失败的作业。</li></ul>
</td>
</tr>
<tr id="row11185183511"><td class="cellrowborder" valign="top" width="26.68%" headers="mcps1.2.3.1.1 "><p id="p1899110116226"><a name="p1899110116226"></a><a name="p1899110116226"></a><a name="image582717413612"></a><a name="image582717413612"></a><span><img id="image582717413612" src="figures/zh-cn_image_0275522465.png" width="131.67000000000002" height="20.40885"></span></p>
</td>
<td class="cellrowborder" valign="top" width="73.32%" headers="mcps1.2.3.1.2 "><p id="p6780114713464"><a name="p6780114713464"></a><a name="p6780114713464"></a>在下拉框中选择作业类型，筛选作业。</p>
<a name="ul4111131216471"></a><a name="ul4111131216471"></a><ul id="ul4111131216471"><li>全部作业类型</li><li>MapReduce</li><li>HiveScript</li><li>Distcp</li><li>SparkScript</li><li>Spark SQL</li><li>Hive SQL</li><li>SparkSubmit</li><li>Flink</li></ul>
</td>
</tr>
<tr id="row3595494810139"><td class="cellrowborder" valign="top" width="26.68%" headers="mcps1.2.3.1.1 "><p id="p2666966910139"><a name="p2666966910139"></a><a name="p2666966910139"></a><a name="image201211322162010"></a><a name="image201211322162010"></a><span><img id="image201211322162010" src="figures/zh-cn_image_0000001212012177.png" width="131.67000000000002" height="27.431250000000002"></span></p>
</td>
<td class="cellrowborder" valign="top" width="73.32%" headers="mcps1.2.3.1.2 "><p id="p1275954610139"><a name="p1275954610139"></a><a name="p1275954610139"></a>在搜索框中根据搜索条件输入对应内容，单击<a name="image4788301327"></a><a name="image4788301327"></a><span><img id="image4788301327" src="figures/icon_mrs_search_L.png"></span>，搜索作业。</p>
<a name="ul796318101915"></a><a name="ul796318101915"></a><ul id="ul796318101915"><li>作业名称</li><li>作业ID</li><li>用户名称</li><li>队列名称</li></ul>
</td>
</tr>
<tr id="row4772705110139"><td class="cellrowborder" valign="top" width="26.68%" headers="mcps1.2.3.1.1 "><p id="p4068596210139"><a name="p4068596210139"></a><a name="p4068596210139"></a><a name="image11700151203317"></a><a name="image11700151203317"></a><span><img id="image11700151203317" src="figures/icon_mrs_fresh_R.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="73.32%" headers="mcps1.2.3.1.2 "><p id="p722865810139"><a name="p722865810139"></a><a name="p722865810139"></a>单击<a name="image572954511337"></a><a name="image572954511337"></a><span><img id="image572954511337" src="figures/icon_mrs_fresh_R.png"></span>，手动刷新作业列表。</p>
</td>
</tr>
</tbody>
</table>

## 作业执行权限说明<a name="section18211416173919"></a>

对于开启Kerberos认证的安全集群，用户在MRS界面提交作业时，要先执行IAM用户同步操作，同步完成后会在MRS系统中产生同IAM用户名的用户。IAM同步用户是否有提交作业权限，取决于IAM同步时，用户所绑定的IAM策略，提交作业策略请参考[IAM用户同步MRS说明](IAM用户同步MRS说明.md)章节中[表1](IAM用户同步MRS说明.md#table3878619101919)。

用户提交作业，如果涉及到具体组件的资源使用，如HDFS的目录访问、Hive表的访问等相关组件的权限时，需由admin（Manager管理员）用户进行授权，给提交作业用户赋予相关组件权限。具体操作如下：

1.  使用admin用户登录Manager。
2.  参考[创建角色](创建角色-154.md)内容，增加用户具体需要的组件权限的角色。
3.  参考[相关任务](创建用户组-155.md#s855da92cb75446818be082dff6e197f1)修改提交作业用户所属的用户组，将新增的组件角色加入到该用户组中。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >用户所在用户组绑定的组件角色修改后，权限生效需要一定时间，请耐心等待。


