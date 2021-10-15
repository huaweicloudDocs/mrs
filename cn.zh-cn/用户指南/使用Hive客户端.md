# 使用Hive客户端<a name="mrs_01_24189"></a>

## 操作场景<a name="zh-cn_topic_0264265780_s189a552b8b4942fdb075311d135d088e"></a>

该任务指导用户在运维场景或业务场景中使用Hive客户端。

## 前提条件<a name="zh-cn_topic_0264265780_sa6b9ccb3f042427eb19b43be2a0b2132"></a>

-   已安装客户端，例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。
-   各组件业务用户由系统管理员根据业务需要创建。安全模式下，“机机”用户需要下载keytab文件。“人机”用户第一次登录时需修改密码。

## 使用Hive客户端（MRS 3.x之前版本）<a name="zh-cn_topic_0264265780_s2bf83637be514738a9c473ff512bf1e8"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  根据集群认证模式，完成Hive客户端登录。

    -   安全模式，则执行以下命令，完成用户认证并登录Hive客户端。

        **kinit **_组件业务用户_

        **beeline**

    -   普通模式，则执行以下命令，登录Hive客户端，如果不指定组件业务用户，则会以当前操作系统用户登录。

        **beeline -n** _组件业务用户_

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >进行beeline连接后，可以编写并提交HQL语句执行相关任务。如需执行Catalog客户端命令，需要先执行**!q**命令退出beeline环境。

6.  使用以下命令，执行HCatalog的客户端命令。

    **hcat -e **_"cmd"_

    其中_"cmd"_必须为Hive DDL语句，如**hcat -e "show tables"**。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   若要使用HCatalog客户端，必须从“组件管理”页面单击“下载客户端”，下载全部服务的客户端。Beeline客户端不受此限制。
    >-   由于权限模型不兼容，使用HCatalog客户端创建的表，在HiveServer客户端中不能访问，但可以使用WebHCat客户端访问。
    >-   在普通模式下使用HCatalog客户端，系统将以当前登录操作系统用户来执行DDL命令。
    >-   退出beeline客户端时请使用**!q**命令，不要使用“Ctrl + c”。否则会导致连接生成的临时文件无法删除，长期会累积产生大量的垃圾文件。
    >-   在使用beeline客户端时，如果需要在一行中输入多条语句，语句之间以“;“分隔，需要将“entireLineAsCommand“的值设置为“false“。
    >    设置方法：如果未启动beeline，则执行**beeline --entireLineAsCommand=false**命令；如果已启动beeline，则在beeline中执行**!set entireLineAsCommand false**命令。
    >    设置完成后，如果语句中含有不是表示语句结束的“;“，需要进行转义，例如**select concat\_ws\('\\;', collect\_set\(col1\)\) from tbl**。


## 使用Hive客户端（MRS 3.x及之后版本）<a name="zh-cn_topic_0264265780_section363014973119"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。
2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  MRS 3.X支持Hive多实例，若安装了Hive多实例，在使用客户端连接具体Hive实例时，请执行以下命令加载具体实例的环境变量，否则请跳过此步骤。例如，加载Hive2实例变量：

    **source Hive2/component\_env**

6.  根据集群认证模式，完成Hive客户端登录。
    -   安全模式，则执行以下命令，完成用户认证并登录Hive客户端。

        **kinit **_组件业务用户_

        **beeline**

    -   普通模式，则执行以下命令，登录Hive客户端，如果不指定组件业务用户，则会以当前操作系统用户登录。

        **beeline -n** _组件业务用户_

7.  使用以下命令，执行HCatalog的客户端命令。

    **hcat -e **_"cmd"_

    其中_"cmd"_必须为Hive DDL语句，如**hcat -e "show tables"**。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   若要使用HCatalog客户端，必须从服务页面选择“更多 \> 下载客户端”，下载全部服务的客户端。Beeline客户端不受此限制。
    >-   由于权限模型不兼容，使用HCatalog客户端创建的表，在HiveServer客户端中不能访问，但可以使用WebHCat客户端访问。
    >-   在普通模式下使用HCatalog客户端，系统将以当前登录操作系统用户来执行DDL命令。
    >-   退出beeline客户端时请使用**!q**命令，不要使用“Ctrl + C”。否则会导致连接生成的临时文件无法删除，长期会累积产生大量的垃圾文件。
    >-   在使用beeline客户端时，如果需要在一行中输入多条语句，语句之间以“;“分隔，需要将“entireLineAsCommand“的值设置为“false“。
    >    设置方法：如果未启动beeline，则执行**beeline --entireLineAsCommand=false**命令；如果已启动beeline，则在beeline中执行**!set entireLineAsCommand false**命令。
    >    设置完成后，如果语句中含有不是表示语句结束的“;“，需要进行转义，例如**select concat\_ws\('\\;', collect\_set\(col1\)\) from tbl**。


## Hive客户端常用命令<a name="zh-cn_topic_0264265780_section1462718419"></a>

常用的Hive Beeline客户端命令如下表所示。

更多命令可参考[https://cwiki.apache.org/confluence/display/Hive/HiveServer2+Clients\#HiveServer2Clients-BeelineCommands](https://cwiki.apache.org/confluence/display/Hive/HiveServer2+Clients#HiveServer2Clients-BeelineCommands)。

**表 1**  Hive Beeline客户端常用命令

<a name="zh-cn_topic_0264265780_table122538012428"></a>
<table><thead align="left"><tr id="zh-cn_topic_0264265780_row142532012426"><th class="cellrowborder" valign="top" width="34.94%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0264265780_p122532016422"><a name="zh-cn_topic_0264265780_p122532016422"></a><a name="zh-cn_topic_0264265780_p122532016422"></a>命令</p>
</th>
<th class="cellrowborder" valign="top" width="65.06%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0264265780_p162532064218"><a name="zh-cn_topic_0264265780_p162532064218"></a><a name="zh-cn_topic_0264265780_p162532064218"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0264265780_row2021434171115"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p71342032665"><a name="zh-cn_topic_0264265780_p71342032665"></a><a name="zh-cn_topic_0264265780_p71342032665"></a>set &lt;key&gt;=&lt;value&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p19842133413116"><a name="zh-cn_topic_0264265780_p19842133413116"></a><a name="zh-cn_topic_0264265780_p19842133413116"></a>设置特定配置变量（键）的值。</p>
<div class="note" id="zh-cn_topic_0264265780_note2835203419111"><a name="zh-cn_topic_0264265780_note2835203419111"></a><a name="zh-cn_topic_0264265780_note2835203419111"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0264265780_p913842513334"><a name="zh-cn_topic_0264265780_p913842513334"></a><a name="zh-cn_topic_0264265780_p913842513334"></a>若变量名拼错，Beeline不会显示错误。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row1960353171115"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p313417325616"><a name="zh-cn_topic_0264265780_p313417325616"></a><a name="zh-cn_topic_0264265780_p313417325616"></a>set</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p789933320337"><a name="zh-cn_topic_0264265780_p789933320337"></a><a name="zh-cn_topic_0264265780_p789933320337"></a>打印由用户或Hive覆盖的配置变量列表。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row47651428141117"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p813483215614"><a name="zh-cn_topic_0264265780_p813483215614"></a><a name="zh-cn_topic_0264265780_p813483215614"></a>set -v</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p1321154133317"><a name="zh-cn_topic_0264265780_p1321154133317"></a><a name="zh-cn_topic_0264265780_p1321154133317"></a>打印Hadoop和Hive的所有配置变量。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row11871191912314"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p31341132960"><a name="zh-cn_topic_0264265780_p31341132960"></a><a name="zh-cn_topic_0264265780_p31341132960"></a>add FILE[S] &lt;filepath&gt; &lt;filepath&gt;*add JAR[S] &lt;filepath&gt; &lt;filepath&gt;*add ARCHIVE[S] &lt;filepath&gt; &lt;filepath&gt;*</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p17685948163315"><a name="zh-cn_topic_0264265780_p17685948163315"></a><a name="zh-cn_topic_0264265780_p17685948163315"></a>将一个或多个文件、JAR文件或ARCHIVE文件添加至分布式缓存的资源列表中。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row1215814241538"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p1913473212611"><a name="zh-cn_topic_0264265780_p1913473212611"></a><a name="zh-cn_topic_0264265780_p1913473212611"></a>add FILE[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
<p id="zh-cn_topic_0264265780_p111341327612"><a name="zh-cn_topic_0264265780_p111341327612"></a><a name="zh-cn_topic_0264265780_p111341327612"></a>add JAR[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
<p id="zh-cn_topic_0264265780_p15134183219611"><a name="zh-cn_topic_0264265780_p15134183219611"></a><a name="zh-cn_topic_0264265780_p15134183219611"></a>add ARCHIVE[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p5652814103420"><a name="zh-cn_topic_0264265780_p5652814103420"></a><a name="zh-cn_topic_0264265780_p5652814103420"></a>使用“ivy://goup:module:version?query_string”格式的lvy URL，将一个或多个文件、JAR文件或ARCHIVE文件添加至分布式缓存的资源列表中。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row2333428433"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p151351032766"><a name="zh-cn_topic_0264265780_p151351032766"></a><a name="zh-cn_topic_0264265780_p151351032766"></a>list FILE[S]list JAR[S]list ARCHIVE[S]</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p3838194153516"><a name="zh-cn_topic_0264265780_p3838194153516"></a><a name="zh-cn_topic_0264265780_p3838194153516"></a>列出已添加至分布式缓存中的资源。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row78354332312"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p613563211618"><a name="zh-cn_topic_0264265780_p613563211618"></a><a name="zh-cn_topic_0264265780_p613563211618"></a>list FILE[S] &lt;filepath&gt;*list JAR[S] &lt;filepath&gt;*list ARCHIVE[S] &lt;filepath&gt;*</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p2997121114351"><a name="zh-cn_topic_0264265780_p2997121114351"></a><a name="zh-cn_topic_0264265780_p2997121114351"></a>检查给定的资源是否已添加至分布式缓存中。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row167295557319"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p313514321965"><a name="zh-cn_topic_0264265780_p313514321965"></a><a name="zh-cn_topic_0264265780_p313514321965"></a>delete FILE[S] &lt;filepath&gt;*delete JAR[S] &lt;filepath&gt;*delete ARCHIVE[S] &lt;filepath&gt;*</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p16659182119354"><a name="zh-cn_topic_0264265780_p16659182119354"></a><a name="zh-cn_topic_0264265780_p16659182119354"></a>从分布式缓存中删除资源。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row188142041049"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p91351732261"><a name="zh-cn_topic_0264265780_p91351732261"></a><a name="zh-cn_topic_0264265780_p91351732261"></a>delete FILE[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
<p id="zh-cn_topic_0264265780_p5135432261"><a name="zh-cn_topic_0264265780_p5135432261"></a><a name="zh-cn_topic_0264265780_p5135432261"></a>delete JAR[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
<p id="zh-cn_topic_0264265780_p1413510321561"><a name="zh-cn_topic_0264265780_p1413510321561"></a><a name="zh-cn_topic_0264265780_p1413510321561"></a>delete ARCHIVE[S] &lt;ivyurl&gt; &lt;ivyurl&gt;*</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p792102913516"><a name="zh-cn_topic_0264265780_p792102913516"></a><a name="zh-cn_topic_0264265780_p792102913516"></a>从分布式缓存中删除使用&lt;ivyurl&gt;添加的资源。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row76481095413"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p0135193220611"><a name="zh-cn_topic_0264265780_p0135193220611"></a><a name="zh-cn_topic_0264265780_p0135193220611"></a>reload</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p15404113783515"><a name="zh-cn_topic_0264265780_p15404113783515"></a><a name="zh-cn_topic_0264265780_p15404113783515"></a>使HiveServer2发现配置参数指定路径下JAR文件的变更“hive.reloadable.aux.jars.path”（无需重启HiveServer2）。更改操作包括添加、删除或更新JAR文件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row3287141815420"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p191359321863"><a name="zh-cn_topic_0264265780_p191359321863"></a><a name="zh-cn_topic_0264265780_p191359321863"></a>dfs &lt;dfs command&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p1383010912360"><a name="zh-cn_topic_0264265780_p1383010912360"></a><a name="zh-cn_topic_0264265780_p1383010912360"></a>执行dfs命令。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264265780_row74947138419"><td class="cellrowborder" valign="top" width="34.94%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264265780_p813717320611"><a name="zh-cn_topic_0264265780_p813717320611"></a><a name="zh-cn_topic_0264265780_p813717320611"></a>&lt;query string&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="65.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264265780_p14213131616365"><a name="zh-cn_topic_0264265780_p14213131616365"></a><a name="zh-cn_topic_0264265780_p14213131616365"></a>执行Hive查询，并将结果打印到标准输出。</p>
</td>
</tr>
</tbody>
</table>

