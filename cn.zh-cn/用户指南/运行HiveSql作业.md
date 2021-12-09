# 运行HiveSql作业<a name="mrs_01_0525"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在MRS集群页面如何提交一个新的HiveSql作业。HiveSql作业用于提交SQL语句和SQL脚本文件查询和分析数据，包括SQL语句和Script脚本两种形式，如果SQL语句涉及敏感信息，请使用Script提交。

## 前提条件<a name="section2335951116026"></a>

用户已经将运行作业所需的程序包和数据文件上传至OBS系统或HDFS中。

## 通过界面提交作业<a name="section75299125395"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  若集群开启Kerberos认证时执行该步骤，若集群未开启Kerberos认证，请无需执行该步骤。

    在“概览“页签的基本信息区域，单击“IAM用户同步“右侧的“同步”进行IAM用户同步，具体介绍请参考[IAM用户同步MRS说明](IAM用户同步MRS说明.md)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   当IAM用户的用户组的所属策略从MRS ReadOnlyAccess向MRS CommonOperations、MRS FullAccess、MRS Administrator变化时，由于集群节点的SSSD（System Security Services Daemon）缓存刷新需要时间，因此同步完成后，请等待5分钟，等待新修改策略生效之后，再进行提交作业。否则，会出现提交作业失败的情况。
    >-   当IAM用户的用户组的所属策略从MRS CommonOperations、MRS FullAccess、MRS Administrator向MRS ReadOnlyAccess变化时，由于集群节点的SSSD缓存刷新需要时间，因此同步完成后，请等待5分钟，新修改策略才能生效。

4.  单击“作业管理“，进入“作业管理“页签。
5.  单击“添加“，进入“添加作业“页面。
6.  配置作业信息。“作业类型“选择“HiveSql“并参考[表1](#tf38a01bf69f34c29a25317555fc32b92)配置HiveSql作业信息。

    **表 1**  作业配置信息

    <a name="tf38a01bf69f34c29a25317555fc32b92"></a>
    <table><thead align="left"><tr id="rfd2a08fd0ba94517ba01e4ded7454cac"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="af11d9c3dce6c499d8eec0a138b99d392"><a name="af11d9c3dce6c499d8eec0a138b99d392"></a><a name="af11d9c3dce6c499d8eec0a138b99d392"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="ab83f3f06c8cc46369dd5073ae93c3b97"><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r683b3168dd8341798f260d75ab24909c"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="ad2841a7eecfd48b6bc3e616a68292c71"><a name="ad2841a7eecfd48b6bc3e616a68292c71"></a><a name="ad2841a7eecfd48b6bc3e616a68292c71"></a>作业名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p18545319122216"><a name="p18545319122216"></a><a name="p18545319122216"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <div class="note" id="note163999410228"><a name="note163999410228"></a><a name="note163999410228"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173264852_p123692397276"><a name="zh-cn_topic_0173264852_p123692397276"></a><a name="zh-cn_topic_0173264852_p123692397276"></a>建议不同的作业设置不同的名称。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row196696374412"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1867063114410"><a name="p1867063114410"></a><a name="p1867063114410"></a>SQL类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p06701364418"><a name="p06701364418"></a><a name="p06701364418"></a>SQL查询语句提交类型。</p>
    <a name="ul2672431204511"></a><a name="ul2672431204511"></a><ul id="ul2672431204511"><li>SQL</li><li>Script</li></ul>
    </td>
    </tr>
    <tr id="row146350174618"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1863208460"><a name="p1863208460"></a><a name="p1863208460"></a>SQL语句</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p36370194614"><a name="p36370194614"></a><a name="p36370194614"></a><span class="parmname" id="parmname1481912464617"><a name="parmname1481912464617"></a><a name="parmname1481912464617"></a>“SQL类型”</span>参数为<span class="parmvalue" id="parmvalue17647183144620"><a name="parmvalue17647183144620"></a><a name="parmvalue17647183144620"></a>“SQL”</span>时参数有效，请输入待运行的SQL语句，然后单击<span class="parmvalue" id="parmvalue10920547498"><a name="parmvalue10920547498"></a><a name="parmvalue10920547498"></a>“检查”</span>来检查SQL语句的正确性，确保输入语句正确。如果同时需要提交多条语句并执行，使用<span class="parmvalue" id="parmvalue48418579172755"><a name="parmvalue48418579172755"></a><a name="parmvalue48418579172755"></a>“;”</span>分隔不同语句。</p>
    </td>
    </tr>
    <tr id="rbd79ceb2feb141ff9cb37ffde9e08ed7"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a4e9842e891a449118c2e3811caa071d9"><a name="a4e9842e891a449118c2e3811caa071d9"></a><a name="a4e9842e891a449118c2e3811caa071d9"></a>SQL文件</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p11270101864711"><a name="p11270101864711"></a><a name="p11270101864711"></a><span class="parmname" id="parmname112719181471"><a name="parmname112719181471"></a><a name="parmname112719181471"></a>“SQL类型”</span>参数为<span class="parmvalue" id="parmvalue12296102615473"><a name="parmvalue12296102615473"></a><a name="parmvalue12296102615473"></a>“Script”</span>时参数有效，待执行SQL文件的路径，需要满足以下要求。</p>
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="zh-cn_topic_0173264852_ul193701439132718"></a><a name="zh-cn_topic_0173264852_ul193701439132718"></a><ul id="zh-cn_topic_0173264852_ul193701439132718"><li>OBS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue206061837142219"><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。</li><li>HDFS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue73701139162714"><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a>“/user”</span>开头。数据导入HDFS请参考<a href="导入导出数据.md#section6302178417377">导入数据</a>。</li></ul>
    </li><li>SparkScript和HiveScript需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue037073911277"><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a>“.sql”</span>结尾，MapReduce需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue3370173972716"><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a>“.jar”</span>结尾，Flink和SparkSubmit需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue0370123910279"><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a>“.jar”</span>或<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue6370739122720"><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a>“.py”</span>结尾。sql、jar、py不区分大小写。</li></ul>
    <div class="note" id="note37771150161214"><a name="note37771150161214"></a><a name="note37771150161214"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p86295129218"><a name="p86295129218"></a><a name="p86295129218"></a>存储在OBS上的文件路径支持以<span class="parmvalue" id="parmvalue662931215216"><a name="parmvalue662931215216"></a><a name="parmvalue662931215216"></a>“obs://”</span>开头格式。如需使用该格式提交作业，访问OBS需要配置对应权限。</p>
    <a name="ul11997202215231"></a><a name="ul11997202215231"></a><ul id="ul11997202215231"><li>创建集群时开启“OBS权限控制”功能时，可直接使用<span class="parmvalue" id="parmvalue3657151711249"><a name="parmvalue3657151711249"></a><a name="parmvalue3657151711249"></a>“obs://”</span>路径，无需单独配置。</li><li>创建集群时未开启或不支持“OBS权限控制”功能时，请参考<a href="配置存算分离集群（委托方式）.md">访问OBS</a>页面进行配置。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row2042974731712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17430134791713"><a name="p17430134791713"></a><a name="p17430134791713"></a>运行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1652632614145"><a name="p1652632614145"></a><a name="p1652632614145"></a>可选参数，为本次执行的作业配置相关优化参数（例如线程、内存、CPU核数等），用于优化资源使用效率，提升作业的执行性能。</p>
    <p id="p843010472175"><a name="p843010472175"></a><a name="p843010472175"></a>常用运行参数如<a href="#table15713101071912">表2</a>。</p>
    </td>
    </tr>
    <tr id="row7582163653214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1527715406327"><a name="p1527715406327"></a><a name="p1527715406327"></a>服务配置参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p0595819249"><a name="p0595819249"></a><a name="p0595819249"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
    <p id="p1793619348256"><a name="p1793619348256"></a><a name="p1793619348256"></a>如需添加多个参数，请单击右侧<a name="zh-cn_topic_0173264852_image137133942711"></a><a name="zh-cn_topic_0173264852_image137133942711"></a><span><img id="zh-cn_topic_0173264852_image137133942711" src="figures/icon_mrs_addtask.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue163711139122718"><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a>“删除”</span>。</p>
    <p id="p15928153419235"><a name="p15928153419235"></a><a name="p15928153419235"></a>常用服务配置参数如<a href="#table1583911183234">表3</a>。</p>
    </td>
    </tr>
    <tr id="row17661172893316"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p10661142818337"><a name="p10661142818337"></a><a name="p10661142818337"></a>命令参考</p>
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
    <tbody><tr id="row071415102199"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p18714171051910"><a name="p18714171051910"></a><a name="p18714171051910"></a>--hiveconf</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p137141210181912"><a name="p137141210181912"></a><a name="p137141210181912"></a>设置Hive服务相关配置，例如设置执行引擎为MR。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1471451001912"><a name="p1471451001912"></a><a name="p1471451001912"></a>设置执行引擎为MR：--hiveconf "hive.execution.engine=mr"</p>
    </td>
    </tr>
    <tr id="row1714710161916"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p171411041910"><a name="p171411041910"></a><a name="p171411041910"></a>--hivevar</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p15714101031911"><a name="p15714101031911"></a><a name="p15714101031911"></a>设置用户自定义变量，例如设置变量id。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1171411041912"><a name="p1171411041912"></a><a name="p1171411041912"></a>设置变量id：--hivevar id="123" select * from test where id = ${hivevar:id};</p>
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
    <tr id="row18401818182311"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p108401818182314"><a name="p108401818182314"></a><a name="p108401818182314"></a>hive.execution.engine</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1184051822316"><a name="p1184051822316"></a><a name="p1184051822316"></a>选择执行作业的引擎。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><a name="ul175211595383"></a><a name="ul175211595383"></a><ul id="ul175211595383"><li>mr</li><li>tez</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section112982186391"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  在“节点管理”页签中单击某一Master节点名称，进入弹性云服务器管理控制台。
4.  单击页面右上角的“远程登录”。
5.  根据界面提示，输入Master节点的用户名和密码，用户名、密码分别为root和创建集群时设置的密码。
6.  执行如下命令初始化环境变量。

    **source /opt/BigData/client/bigdata\_env**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。
    >-   若安装了Hive多实例，在使用客户端连接具体Hive实例时，请执行以下命令加载具体实例的环境变量，否则请跳过此步骤。例如，加载Hive2实例变量：
    >    **source  **/opt/BigData/client/**Hive2/component\_env**

7.  如果当前集群已开启Kerberos认证，执行以下命令认证当前用户。如果当前集群未开启Kerberos认证\(普通模式），则无需执行该步骤。

    **kinit** _MRS__集群用户_  \(用户需要有hive组）

8.  执行beeline连接hiveserver，运行任务。

    **beeline**

    普通模式，则执行以下命令，如果不指定组件业务用户，则会以当前操作系统用户连接hiveserver。

    **beeline -n**_组件业务用户_

    **beeline -f**  sql文件（执行文件里的sql）


