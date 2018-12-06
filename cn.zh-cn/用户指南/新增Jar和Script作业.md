# 新增Jar和Script作业<a name="ZH-CN_TOPIC_0012808240"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在MRS集群页面如何提交一个新的作业。

## 前提条件<a name="section2335951116026"></a>

已操作完成如下信息：

MRS集群处理的数据源来源于OBS或HDFS，HDFS是Hadoop分布式文件系统（Hadoop Distributed File System），OBS即对象存储服务，是一个基于对象的海量存储服务，为客户提供海量、安全、高可靠、低成本的数据存储能力。MRS可以直接处理OBS中的数据，客户可以基于管理控制台Web界面和OBS客户端对数据进行浏览、管理和使用，同时可以通过REST API接口方式单独或集成到业务程序进行管理和访问数据。

用户创建作业前需要将本地数据上传至OBS系统，MRS使用OBS中的数据进行计算分析。当然MRS也支持将OBS中的数据导入至HDFS中，使用HDFS中的数据进行计算分析。数据完成处理和分析后，您可以将数据存储在HDFS中，也可以将集群中的数据导出至OBS系统。需要注意，HDFS和OBS也支持存储压缩格式的数据，目前支持存储bz2、gz压缩格式的数据。

## 操作步骤<a name="zh-cn_topic_0012807343_section56570152103954"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名，进入集群信息页面。
3.  单击“作业管理“，进入“作业管理“页签。
4.  在“作业“页签中单击“添加“，进入“添加作业“页面。

    此处MapReduce仅为示例，请根据业务类型，选择不同的作业类型。

5.  参考[表 1](#zh-cn_topic_0012807343_table2007281095546)配置作业信息。

    **表 1**  作业配置信息

    <a name="zh-cn_topic_0012807343_table2007281095546"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0012807343_row2385663595546"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0012807343_p5333928795546"><a name="zh-cn_topic_0012807343_p5333928795546"></a><a name="zh-cn_topic_0012807343_p5333928795546"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0012807343_p2551498795546"><a name="zh-cn_topic_0012807343_p2551498795546"></a><a name="zh-cn_topic_0012807343_p2551498795546"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0012807343_row5344809695546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p3432854295546"><a name="zh-cn_topic_0012807343_p3432854295546"></a><a name="zh-cn_topic_0012807343_p3432854295546"></a>作业类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p19187781102343"><a name="zh-cn_topic_0012807343_p19187781102343"></a><a name="zh-cn_topic_0012807343_p19187781102343"></a>支持的作业类型，请根据业务类型选择：</p>
    <a name="zh-cn_topic_0012807343_ul16035663102539"></a><a name="zh-cn_topic_0012807343_ul16035663102539"></a><ul id="zh-cn_topic_0012807343_ul16035663102539"><li>MapReduce</li><li>Spark</li><li>Spark Script</li><li>Hive Script<div class="note" id="note6412416195513"><a name="note6412416195513"></a><a name="note6412416195513"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1413716175517"><a name="p1413716175517"></a><a name="p1413716175517"></a>只有创建集群时选择了Spark和Hive组件，并且集群处于运行中，才能新增Spark和Hive类型的作业。Spark Script作业只支持运行Spark SQL程序，Spark支持运行Spark Core、Spark SQL程序。</p>
    </div></div>
    </li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row6100983695546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p4284970295546"><a name="zh-cn_topic_0012807343_p4284970295546"></a><a name="zh-cn_topic_0012807343_p4284970295546"></a>作业名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p4725704311292"><a name="zh-cn_topic_0012807343_p4725704311292"></a><a name="zh-cn_topic_0012807343_p4725704311292"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <div class="note" id="zh-cn_topic_0012807343_note2266020411292"><a name="zh-cn_topic_0012807343_note2266020411292"></a><a name="zh-cn_topic_0012807343_note2266020411292"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0012807343_p261524611292"><a name="zh-cn_topic_0012807343_p261524611292"></a><a name="zh-cn_topic_0012807343_p261524611292"></a>建议不同的作业设置不同的名称。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row2657626495546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p4239557514273"><a name="zh-cn_topic_0012807343_p4239557514273"></a><a name="zh-cn_topic_0012807343_p4239557514273"></a>执行程序路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p655627719565"><a name="p655627719565"></a><a name="p655627719565"></a>执行程序Jar包地址，需要满足如下要求：</p>
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul56833471484"></a><a name="ul56833471484"></a><ul id="ul56833471484"><li>OBS：以<span class="parmvalue" id="parmvalue15615586113316"><a name="parmvalue15615586113316"></a><a name="parmvalue15615586113316"></a>“s3a://”</span>开头。示例：s3a://wordcount/program/hadoop-mapreduce-examples-2.7.x.jar</li><li>HDFS：以<span class="parmvalue" id="parmvalue5002226915745"><a name="parmvalue5002226915745"></a><a name="parmvalue5002226915745"></a>“/user”</span>开头。</li></ul>
    </li><li>Spark Script需要以<span class="parmvalue" id="parmvalue3709601695914"><a name="parmvalue3709601695914"></a><a name="parmvalue3709601695914"></a>“.sql”</span>结尾，MR和Spark需要以<span class="parmvalue" id="parmvalue940908595918"><a name="parmvalue940908595918"></a><a name="parmvalue940908595918"></a>“.jar”</span>结尾。sql、jar不区分大小写。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row2817879495546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p5436557014273"><a name="zh-cn_topic_0012807343_p5436557014273"></a><a name="zh-cn_topic_0012807343_p5436557014273"></a>执行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p33862476113321"><a name="zh-cn_topic_0012807343_p33862476113321"></a><a name="zh-cn_topic_0012807343_p33862476113321"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。多个参数间使用空格隔开。</p>
    <p id="p163988156203"><a name="p163988156203"></a><a name="p163988156203"></a><span>配置方法：包名.类名</span></p>
    <p id="zh-cn_topic_0012807343_p4153501114273"><a name="zh-cn_topic_0012807343_p4153501114273"></a><a name="zh-cn_topic_0012807343_p4153501114273"></a>最多为2047字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
    <div class="note" id="note62371709174814"><a name="note62371709174814"></a><a name="note62371709174814"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p20521095174814"><a name="p20521095174814"></a><a name="p20521095174814"></a>用户输入带有敏感信息（如登录密码）的参数时，可通过在参数名前添加“@”的方式，为该参数值加密，以防止敏感信息被明文形式持久化。在MRS管理控制台查看作业信息时，敏感信息显示为“*”。</p>
    <p id="p1265001117571"><a name="p1265001117571"></a><a name="p1265001117571"></a>例如：username=admin @password=admin_123</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row1057507495546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p4034582114273"><a name="zh-cn_topic_0012807343_p4034582114273"></a><a name="zh-cn_topic_0012807343_p4034582114273"></a>数据输入路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p58342063113324"><a name="zh-cn_topic_0012807343_p58342063113324"></a><a name="zh-cn_topic_0012807343_p58342063113324"></a>数据输入地址</p>
    <div class="p" id="p6028322915823"><a name="p6028322915823"></a><a name="p6028322915823"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul1668690715439"></a><a name="ul1668690715439"></a><ul id="ul1668690715439"><li>OBS：以<span class="parmvalue" id="parmvalue1805090015439"><a name="parmvalue1805090015439"></a><a name="parmvalue1805090015439"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue2499739115713"><a name="parmvalue2499739115713"></a><a name="parmvalue2499739115713"></a>“/user”</span>开头。</li></ul>
    </div>
    <p id="zh-cn_topic_0012807343_p1842153414273"><a name="zh-cn_topic_0012807343_p1842153414273"></a><a name="zh-cn_topic_0012807343_p1842153414273"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row6353631095546"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p752552114273"><a name="zh-cn_topic_0012807343_p752552114273"></a><a name="zh-cn_topic_0012807343_p752552114273"></a>输出路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p58879755113122"><a name="zh-cn_topic_0012807343_p58879755113122"></a><a name="zh-cn_topic_0012807343_p58879755113122"></a>数据输出地址</p>
    <div class="note" id="note12918618161337"><a name="note12918618161337"></a><a name="note12918618161337"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1637410244522"></a><a name="ul1637410244522"></a><ul id="ul1637410244522"><li>配置此参数时，选择<span class="uicontrol" id="uicontrol23741024125214"><a name="uicontrol23741024125214"></a><a name="uicontrol23741024125214"></a>“OBS”</span>或<span class="uicontrol" id="uicontrol17374112412529"><a name="uicontrol17374112412529"></a><a name="uicontrol17374112412529"></a>“HDFS”</span>，单击<span class="uicontrol" id="uicontrol173741724145216"><a name="uicontrol173741724145216"></a><a name="uicontrol173741724145216"></a>“浏览”</span>并选择文件目录，或者手动输入文件目录，然后单击<span class="uicontrol" id="uicontrol43744241528"><a name="uicontrol43744241528"></a><a name="uicontrol43744241528"></a>“确定”</span>。</li><li>若添加hadoop-mapreduce-examples-x.x.x.jar样例程序或和hadoop-mapreduce-examples-x.x.x.jar类似的程序，请手动输入一个不存在的目录。</li></ul>
    </div></div>
    <div class="p" id="p60582415151053"><a name="p60582415151053"></a><a name="p60582415151053"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul8370831151053"></a><a name="ul8370831151053"></a><ul id="ul8370831151053"><li>OBS：以<span class="parmvalue" id="parmvalue6948719151053"><a name="parmvalue6948719151053"></a><a name="parmvalue6948719151053"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue32451534151053"><a name="parmvalue32451534151053"></a><a name="parmvalue32451534151053"></a>“/user”</span>开头。</li></ul>
    </div>
    <p id="zh-cn_topic_0012807343_p40777300113122"><a name="zh-cn_topic_0012807343_p40777300113122"></a><a name="zh-cn_topic_0012807343_p40777300113122"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0012807343_row459221939174"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p287101489174"><a name="zh-cn_topic_0012807343_p287101489174"></a><a name="zh-cn_topic_0012807343_p287101489174"></a>日志路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0012807343_p27632339113252"><a name="zh-cn_topic_0012807343_p27632339113252"></a><a name="zh-cn_topic_0012807343_p27632339113252"></a>作业日志存储地址，该日志信息记录作业运行状态。</p>
    <div class="p" id="p52515849151155"><a name="p52515849151155"></a><a name="p52515849151155"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul2880601151155"></a><a name="ul2880601151155"></a><ul id="ul2880601151155"><li>OBS：以<span class="parmvalue" id="parmvalue32002114151155"><a name="parmvalue32002114151155"></a><a name="parmvalue32002114151155"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue42765641151155"><a name="parmvalue42765641151155"></a><a name="parmvalue42765641151155"></a>“/user”</span>开头。</li></ul>
    </div>
    <p id="zh-cn_topic_0012807343_p438206609174"><a name="zh-cn_topic_0012807343_p438206609174"></a><a name="zh-cn_topic_0012807343_p438206609174"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   OBS路径支持“s3a://“，默认使用“s3a://“。  
    >-   OBS路径不支持KMS加密的文件或程序。  
    >-   OBS和HDFS的全路径长度小于等于1023字符。  

6.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >默认每个集群最多支持运行中的作业数量为10。  


