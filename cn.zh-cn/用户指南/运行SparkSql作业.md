# 运行SparkSql作业<a name="mrs_01_0526"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在MRS集群页面如何提交一个新的SparkSql作业。SparkSQL作业用于查询和分析数据，包括SQL语句和Script脚本两种形式，如果SQL语句涉及敏感信息，请使用Spark Script提交。

## 前提条件<a name="section2335951116026"></a>

用户已经将运行作业所需的程序包和数据文件上传至OBS系统或HDFS中。

## 通过界面提交作业<a name="section75299125395"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  若集群开启Kerberos认证时执行该步骤，若集群未开启Kerberos认证，请无需执行该步骤。

    在“概览“页签的基本信息区域，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步，具体介绍请参考[IAM用户同步MRS](IAM用户同步MRS.md)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   当IAM用户的用户组的所属策略从MRS ReadOnlyAccess向MRS CommonOperations、MRS FullAccess、MRS Administrator变化时，由于集群节点的SSSD（System Security Services Daemon）缓存刷新需要时间，因此同步完成后，请等待5分钟，等待新修改策略生效之后，再进行提交作业。否则，会出现提交作业失败的情况。
    >-   当IAM用户的用户组的所属策略从MRS CommonOperations、MRS FullAccess、MRS Administrator向MRS ReadOnlyAccess变化时，由于集群节点的SSSD缓存刷新需要时间，因此同步完成后，请等待5分钟，新修改策略才能生效。

4.  单击“作业管理“，进入“作业管理“页签。
5.  请单击“添加“，进入添加作业页面，“作业类型“选择“SparkSql“，作业参考[表1](#table063345817183)配置SparkSql作业信息。

    **表 1**  作业配置信息

    <a name="table063345817183"></a>
    <table><thead align="left"><tr id="row3627105831812"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p13627558111812"><a name="p13627558111812"></a><a name="p13627558111812"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p762712581187"><a name="p762712581187"></a><a name="p762712581187"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row17631185817185"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p0630115810185"><a name="p0630115810185"></a><a name="p0630115810185"></a>作业名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p18545319122216"><a name="p18545319122216"></a><a name="p18545319122216"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <div class="note" id="note163999410228"><a name="note163999410228"></a><a name="note163999410228"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173264852_p123692397276"><a name="zh-cn_topic_0173264852_p123692397276"></a><a name="zh-cn_topic_0173264852_p123692397276"></a>建议不同的作业设置不同的名称。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row1863110583186"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p463112581183"><a name="p463112581183"></a><a name="p463112581183"></a>SQL类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1663165801816"><a name="p1663165801816"></a><a name="p1663165801816"></a>SQL查询语句提交类型。</p>
    <a name="ul1563155810180"></a><a name="ul1563155810180"></a><ul id="ul1563155810180"><li>SQL</li><li>Script</li></ul>
    </td>
    </tr>
    <tr id="row66312586181"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p863175841817"><a name="p863175841817"></a><a name="p863175841817"></a>SQL语句</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5631175841817"><a name="p5631175841817"></a><a name="p5631175841817"></a><span class="parmname" id="zh-cn_topic_0173264854_parmname1481912464617"><a name="zh-cn_topic_0173264854_parmname1481912464617"></a><a name="zh-cn_topic_0173264854_parmname1481912464617"></a>“SQL类型”</span>参数为<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue17647183144620"><a name="zh-cn_topic_0173264854_parmvalue17647183144620"></a><a name="zh-cn_topic_0173264854_parmvalue17647183144620"></a>“SQL”</span>时参数有效，请输入待运行的SQL语句，然后单击<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue10920547498"><a name="zh-cn_topic_0173264854_parmvalue10920547498"></a><a name="zh-cn_topic_0173264854_parmvalue10920547498"></a>“检查”</span>来检查SQL语句的正确性，确保输入语句正确。如果同时需要提交多条语句并执行，使用<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue48418579172755"><a name="zh-cn_topic_0173264854_parmvalue48418579172755"></a><a name="zh-cn_topic_0173264854_parmvalue48418579172755"></a>“;”</span>分隔不同语句。</p>
    </td>
    </tr>
    <tr id="row1063255814180"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p7631105820185"><a name="p7631105820185"></a><a name="p7631105820185"></a>SQL文件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p3632115815183"><a name="p3632115815183"></a><a name="p3632115815183"></a><span class="parmname" id="zh-cn_topic_0173264854_parmname112719181471"><a name="zh-cn_topic_0173264854_parmname112719181471"></a><a name="zh-cn_topic_0173264854_parmname112719181471"></a>“SQL类型”</span>参数为<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue12296102615473"><a name="zh-cn_topic_0173264854_parmvalue12296102615473"></a><a name="zh-cn_topic_0173264854_parmvalue12296102615473"></a>“Script”</span>时参数有效，待执行SQL文件的路径，需要满足以下要求。</p>
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="zh-cn_topic_0173264852_ul193701439132718"></a><a name="zh-cn_topic_0173264852_ul193701439132718"></a><ul id="zh-cn_topic_0173264852_ul193701439132718"><li>OBS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue206061837142219"><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。</li><li>HDFS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue73701139162714"><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
    </li><li>SparkScript和HiveScript需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue037073911277"><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a>“.sql”</span>结尾，MapReduce需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue3370173972716"><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a>“.jar”</span>结尾，Flink和SparkSubmit需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue0370123910279"><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a>“.jar”</span>或<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue6370739122720"><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a>“.py”</span>结尾。sql、jar、py不区分大小写。</li></ul>
    <div class="note" id="note120382412284"><a name="note120382412284"></a><a name="note120382412284"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173264854_p86295129218"><a name="zh-cn_topic_0173264854_p86295129218"></a><a name="zh-cn_topic_0173264854_p86295129218"></a>存储在OBS上的文件路径支持以<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue662931215216"><a name="zh-cn_topic_0173264854_parmvalue662931215216"></a><a name="zh-cn_topic_0173264854_parmvalue662931215216"></a>“obs://”</span>开头格式。如需使用该格式提交作业，访问OBS需要配置对应权限。</p>
    <a name="zh-cn_topic_0173264854_ul11997202215231"></a><a name="zh-cn_topic_0173264854_ul11997202215231"></a><ul id="zh-cn_topic_0173264854_ul11997202215231"><li>创建集群时开启“OBS权限控制”功能时，可直接使用<span class="parmvalue" id="zh-cn_topic_0173264854_parmvalue3657151711249"><a name="zh-cn_topic_0173264854_parmvalue3657151711249"></a><a name="zh-cn_topic_0173264854_parmvalue3657151711249"></a>“obs://”</span>路径，无需单独配置。</li><li>创建集群时未开启或不支持“OBS权限控制”功能时，请参考<a href="配置存算分离集群（委托方式）.md">访问OBS</a>页面进行配置。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row76331558111810"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p12633105851810"><a name="p12633105851810"></a><a name="p12633105851810"></a>运行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p136331358111815"><a name="p136331358111815"></a><a name="p136331358111815"></a>可选参数，为本次执行的作业配置相关优化参数（例如线程、内存、CPU核数等），用于优化资源使用效率，提升作业的执行性能。</p>
    <p id="p4666184610502"><a name="p4666184610502"></a><a name="p4666184610502"></a>常用运行程序参数如<a href="#table15713101071912">表2</a>。</p>
    </td>
    </tr>
    <tr id="row1633145861818"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p18633758131811"><a name="p18633758131811"></a><a name="p18633758131811"></a>服务配置参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p0595819249"><a name="p0595819249"></a><a name="p0595819249"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
    <p id="p1793619348256"><a name="p1793619348256"></a><a name="p1793619348256"></a>如需添加多个参数，请单击右侧<a name="zh-cn_topic_0173264852_image137133942711"></a><a name="zh-cn_topic_0173264852_image137133942711"></a><span><img id="zh-cn_topic_0173264852_image137133942711" src="figures/icon_mrs_addtask.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue163711139122718"><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a>“删除”</span>。</p>
    <p id="p11915985013"><a name="p11915985013"></a><a name="p11915985013"></a>常用服务配置参数如<a href="#table1583911183234">表3</a>。</p>
    </td>
    </tr>
    <tr id="row16633145871815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p136331582189"><a name="p136331582189"></a><a name="p136331582189"></a>命令参考</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p204063412410"><a name="p204063412410"></a><a name="p204063412410"></a>用于展示提交作业时提交到后台执行的命令。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  运行程序参数

    <a name="table15713101071912"></a>
    <table><thead align="left"><tr id="row107146107192"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p1971415109199"><a name="p1971415109199"></a><a name="p1971415109199"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.2"><p id="p1771471011192"><a name="p1771471011192"></a><a name="p1771471011192"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.3"><p id="p4766194061910"><a name="p4766194061910"></a><a name="p4766194061910"></a>取值样例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row071415102199"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p143151156125113"><a name="p143151156125113"></a><a name="p143151156125113"></a>--conf</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1431517568512"><a name="p1431517568512"></a><a name="p1431517568512"></a>添加任务配置项</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p2315256125113"><a name="p2315256125113"></a><a name="p2315256125113"></a>spark.executor.memory=2G</p>
    </td>
    </tr>
    <tr id="row17236418124712"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p16315135645110"><a name="p16315135645110"></a><a name="p16315135645110"></a>--driver-memory</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p631575612516"><a name="p631575612516"></a><a name="p631575612516"></a>设置driver的运行内存</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p43156564511"><a name="p43156564511"></a><a name="p43156564511"></a>2G</p>
    </td>
    </tr>
    <tr id="row138876189476"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1631565611516"><a name="p1631565611516"></a><a name="p1631565611516"></a>--num-executors</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1131510563510"><a name="p1131510563510"></a><a name="p1131510563510"></a>设置executor启动数量</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p631510561516"><a name="p631510561516"></a><a name="p631510561516"></a>5</p>
    </td>
    </tr>
    <tr id="row15865111913472"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1531510564515"><a name="p1531510564515"></a><a name="p1531510564515"></a>--executor-cores</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1931525614519"><a name="p1931525614519"></a><a name="p1931525614519"></a>设置executor核数</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1331535625119"><a name="p1331535625119"></a><a name="p1331535625119"></a>2</p>
    </td>
    </tr>
    <tr id="row168661320164718"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13315205616513"><a name="p13315205616513"></a><a name="p13315205616513"></a>--jars</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1331516563510"><a name="p1331516563510"></a><a name="p1331516563510"></a>上传任务额外依赖包，用于给任务添加任务的外部依赖包</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p19315145665111"><a name="p19315145665111"></a><a name="p19315145665111"></a>-</p>
    </td>
    </tr>
    <tr id="row1399721154719"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p20315105610514"><a name="p20315105610514"></a><a name="p20315105610514"></a>--executor-memory</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p6316195655118"><a name="p6316195655118"></a><a name="p6316195655118"></a>设置executor内存</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p3316125605112"><a name="p3316125605112"></a><a name="p3316125605112"></a>2G</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  服务配置参数

    <a name="table1583911183234"></a>
    <table><thead align="left"><tr id="row483941832316"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p8646182410235"><a name="p8646182410235"></a><a name="p8646182410235"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.2"><p id="p15646324192315"><a name="p15646324192315"></a><a name="p15646324192315"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.3"><p id="p16646192415238"><a name="p16646192415238"></a><a name="p16646192415238"></a>取值样例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row208401118172317"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p684013184230"><a name="p684013184230"></a><a name="p684013184230"></a>fs.obs.access.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p168405185233"><a name="p168405185233"></a><a name="p168405185233"></a>访问OBS的密钥ID。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1984051812310"><a name="p1984051812310"></a><a name="p1984051812310"></a>-</p>
    </td>
    </tr>
    <tr id="row584061832313"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p118400187237"><a name="p118400187237"></a><a name="p118400187237"></a>fs.obs.secret.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p4840218182314"><a name="p4840218182314"></a><a name="p4840218182314"></a>访问OBS与密钥ID对应的密钥。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p3840181822311"><a name="p3840181822311"></a><a name="p3840181822311"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

6.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section1614174715393"></a>

MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。

1.  参考[创建用户](创建用户.md)页面，创建一个用于提交作业的用户。

    本示例创建一个用户开发场景使用的机机用户，并分配了正确的用户组（hadoop、supergroup）、主组（supergroup）和角色权限（System\_administrator、default）。

2.  <a name="mrs_01_0524_li37101911105"></a>在MRS Manager页面选择“系统 \> 用户“，在新增用户的操作列单击“更多 \> 下载认证凭据“。
3.  登录Spark客户端所在节点，上传[2](#mrs_01_0524_li37101911105)创建的用户认证凭据到集群的“/opt/”目录下，并执行如下命令解压：

    **tar –xvf MRSTest \_xxxxxx\_keytab.tar**

    得到user.keytab和krb5.conf两个文件。

4.  在对集群操作之前首先需要执行：

    **source /opt/Bigdata/client/bigdata\_env**

    **cd $SPARK\_HOME**

5.  打开spark-sql命令行，进入spark-sql命令行后可执行SQL语句，执行命令如下：

    **./bin/spark-sql --conf spark.yarn.principal=MRSTest --conf spark.yarn.keytab=/opt/user.keytab**

    若需要执行SQL文件，需要上传SQL文件（如上传到“/opt/”目录），上传文件后执行命令如下：

    **./bin/spark-sql --conf spark.yarn.principal=MRSTest --conf spark.yarn.keytab=/opt/user.keytab -f /opt/script.sql**


