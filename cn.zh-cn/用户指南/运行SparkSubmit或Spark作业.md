# 运行SparkSubmit或Spark作业<a name="mrs_01_0524"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在MRS集群页面如何提交一个新的Spark作业。

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
5.  单击“添加“，进入“添加作业“页面。
6.  配置作业信息。

    -   “作业类型“选择“SparkSubmit“，请参考[表1](#tf38a01bf69f34c29a25317555fc32b92)配置SparkSubmit作业其他参数信息。

    **表 1**  作业配置信息

    <a name="tf38a01bf69f34c29a25317555fc32b92"></a>
    <table><thead align="left"><tr id="rfd2a08fd0ba94517ba01e4ded7454cac"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="af11d9c3dce6c499d8eec0a138b99d392"><a name="af11d9c3dce6c499d8eec0a138b99d392"></a><a name="af11d9c3dce6c499d8eec0a138b99d392"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="ab83f3f06c8cc46369dd5073ae93c3b97"><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row6545171962212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1254517199222"><a name="p1254517199222"></a><a name="p1254517199222"></a>作业名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p18545319122216"><a name="p18545319122216"></a><a name="p18545319122216"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <div class="note" id="note163999410228"><a name="note163999410228"></a><a name="note163999410228"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173264852_p123692397276"><a name="zh-cn_topic_0173264852_p123692397276"></a><a name="zh-cn_topic_0173264852_p123692397276"></a>建议不同的作业设置不同的名称。</p>
    </div></div>
    </td>
    </tr>
    <tr id="rbd79ceb2feb141ff9cb37ffde9e08ed7"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a4e9842e891a449118c2e3811caa071d9"><a name="a4e9842e891a449118c2e3811caa071d9"></a><a name="a4e9842e891a449118c2e3811caa071d9"></a>执行程序路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p3846103721718"><a name="p3846103721718"></a><a name="p3846103721718"></a>待执行程序包地址，需要满足如下要求：</p>
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="zh-cn_topic_0173264852_ul193701439132718"></a><a name="zh-cn_topic_0173264852_ul193701439132718"></a><ul id="zh-cn_topic_0173264852_ul193701439132718"><li>OBS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue206061837142219"><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a><a name="zh-cn_topic_0173264852_parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。（MRS 1.9.2及之后版本支持。）</li><li>HDFS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue73701139162714"><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a><a name="zh-cn_topic_0173264852_parmvalue73701139162714"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
    </li><li>SparkScript和HiveScript需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue037073911277"><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a><a name="zh-cn_topic_0173264852_parmvalue037073911277"></a>“.sql”</span>结尾，MapReduce需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue3370173972716"><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a><a name="zh-cn_topic_0173264852_parmvalue3370173972716"></a>“.jar”</span>结尾，Flink和SparkSubmit需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue0370123910279"><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a><a name="zh-cn_topic_0173264852_parmvalue0370123910279"></a>“.jar”</span>或<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue6370739122720"><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a><a name="zh-cn_topic_0173264852_parmvalue6370739122720"></a>“.py”</span>结尾。sql、jar、py不区分大小写。</li></ul>
    </td>
    </tr>
    <tr id="row17824727141"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p482420210144"><a name="p482420210144"></a><a name="p482420210144"></a>运行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1652632614145"><a name="p1652632614145"></a><a name="p1652632614145"></a>可选参数，为本次执行的作业配置相关优化参数（例如线程、内存、CPU核数等），用于优化资源使用效率，提升作业的执行性能。</p>
    <p id="p625412599416"><a name="p625412599416"></a><a name="p625412599416"></a>常用运行程序参数如<a href="#table4154959181519">表2</a>。</p>
    </td>
    </tr>
    <tr id="r7dcde55c00da4bc88afb2b022bce0abd"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a61afb54329564e458086d7622bda3b89"><a name="a61afb54329564e458086d7622bda3b89"></a><a name="a61afb54329564e458086d7622bda3b89"></a>执行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="ad6f1110b8e38456193949182f7a05980"><a name="ad6f1110b8e38456193949182f7a05980"></a><a name="ad6f1110b8e38456193949182f7a05980"></a>可选参数，程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。多个参数间使用空格隔开。</p>
    <p id="a6c44712b37c74651afe354f3cbf9e02f"><a name="a6c44712b37c74651afe354f3cbf9e02f"></a><a name="a6c44712b37c74651afe354f3cbf9e02f"></a>最多为150000字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
    <div class="caution" id="note2762142185515"><a name="note2762142185515"></a><a name="note2762142185515"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><p id="p27628212551"><a name="p27628212551"></a><a name="p27628212551"></a>若输入带有敏感信息（如登录密码）的参数可能在作业详情展示和日志打印中存在暴露的风险，请谨慎操作。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row7582163653214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1527715406327"><a name="p1527715406327"></a><a name="p1527715406327"></a>服务配置参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p0595819249"><a name="p0595819249"></a><a name="p0595819249"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
    <p id="p1793619348256"><a name="p1793619348256"></a><a name="p1793619348256"></a>如需添加多个参数，请单击右侧<a name="zh-cn_topic_0173264852_image137133942711"></a><a name="zh-cn_topic_0173264852_image137133942711"></a><span><img id="zh-cn_topic_0173264852_image137133942711" src="figures/icon_mrs_addtask.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue163711139122718"><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a>“删除”</span>。</p>
    <p id="p23951959184515"><a name="p23951959184515"></a><a name="p23951959184515"></a>常用服务配置参数如<a href="#table14155459121519">表3</a>。</p>
    <div class="note" id="note6245194795816"><a name="note6245194795816"></a><a name="note6245194795816"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p724624755813"><a name="p724624755813"></a><a name="p724624755813"></a>如需运行长时作业如SparkStreaming等，且需要访问OBS, 需要通过“服务配置参数”传入访问OBS的AK/SK。</p>
    </div></div>
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

    <a name="table4154959181519"></a>
    <table><thead align="left"><tr id="row615255918159"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p015218595151"><a name="p015218595151"></a><a name="p015218595151"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.2"><p id="p141521459201514"><a name="p141521459201514"></a><a name="p141521459201514"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.3"><p id="p15152859131519"><a name="p15152859131519"></a><a name="p15152859131519"></a>取值样例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row915255981519"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p015275913158"><a name="p015275913158"></a><a name="p015275913158"></a>--conf</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p101521859171519"><a name="p101521859171519"></a><a name="p101521859171519"></a>添加任务配置项。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p415215913151"><a name="p415215913151"></a><a name="p415215913151"></a>spark.executor.memory=2G</p>
    </td>
    </tr>
    <tr id="row8152859121519"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p5152559131510"><a name="p5152559131510"></a><a name="p5152559131510"></a>--driver-memory</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p10152145919159"><a name="p10152145919159"></a><a name="p10152145919159"></a>设置driver的运行内存。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p9152135914157"><a name="p9152135914157"></a><a name="p9152135914157"></a>2G</p>
    </td>
    </tr>
    <tr id="row31531559101514"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p615375911519"><a name="p615375911519"></a><a name="p615375911519"></a>--num-executors</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1715345911511"><a name="p1715345911511"></a><a name="p1715345911511"></a>设置executor启动数量。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1815325971514"><a name="p1815325971514"></a><a name="p1815325971514"></a>5</p>
    </td>
    </tr>
    <tr id="row111542059161510"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p015310596154"><a name="p015310596154"></a><a name="p015310596154"></a>--executor-cores</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p415375971512"><a name="p415375971512"></a><a name="p415375971512"></a>设置executor核数。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p31541559141519"><a name="p31541559141519"></a><a name="p31541559141519"></a>2</p>
    </td>
    </tr>
    <tr id="row915455911155"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p181541959191514"><a name="p181541959191514"></a><a name="p181541959191514"></a>--class</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p3154155914158"><a name="p3154155914158"></a><a name="p3154155914158"></a>设置任务的主类。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1715417593151"><a name="p1715417593151"></a><a name="p1715417593151"></a>org.apache.spark.examples.SparkPi</p>
    </td>
    </tr>
    <tr id="row7154105981515"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p16154195919152"><a name="p16154195919152"></a><a name="p16154195919152"></a>--files</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1515495931510"><a name="p1515495931510"></a><a name="p1515495931510"></a>上传文件给任务，可以是自己定义的配置文件或者某些数据文件。来源可以是OBS或者HDFS。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p6154959201515"><a name="p6154959201515"></a><a name="p6154959201515"></a>-</p>
    </td>
    </tr>
    <tr id="row13154145901514"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p4154185919151"><a name="p4154185919151"></a><a name="p4154185919151"></a>--jars</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p4154145920154"><a name="p4154145920154"></a><a name="p4154145920154"></a>上传任务额外依赖包，用于给任务添加任务的外部依赖包。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1115418595155"><a name="p1115418595155"></a><a name="p1115418595155"></a>-</p>
    </td>
    </tr>
    <tr id="row4154195918155"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p7154559171513"><a name="p7154559171513"></a><a name="p7154559171513"></a>--executor-memory</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p7154859131520"><a name="p7154859131520"></a><a name="p7154859131520"></a>设置executor内存。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p815414594156"><a name="p815414594156"></a><a name="p815414594156"></a>2G</p>
    </td>
    </tr>
    <tr id="row16421532171114"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p166434328112"><a name="p166434328112"></a><a name="p166434328112"></a>--conf spark-yarn.maxAppAttempts</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p12643133215113"><a name="p12643133215113"></a><a name="p12643133215113"></a>控制AM的重试次数。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p196439328116"><a name="p196439328116"></a><a name="p196439328116"></a>设置为0时，不允许重试；设置为1时，允许重试一次。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  服务配置参数

    <a name="table14155459121519"></a>
    <table><thead align="left"><tr id="row1815525911153"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p315518599153"><a name="p315518599153"></a><a name="p315518599153"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.2"><p id="p2155859111520"><a name="p2155859111520"></a><a name="p2155859111520"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.3"><p id="p015515917154"><a name="p015515917154"></a><a name="p015515917154"></a>取值样例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row111558592152"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p815516594159"><a name="p815516594159"></a><a name="p815516594159"></a>fs.obs.access.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p115535931510"><a name="p115535931510"></a><a name="p115535931510"></a>访问OBS的密钥ID。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p4155185919152"><a name="p4155185919152"></a><a name="p4155185919152"></a>-</p>
    </td>
    </tr>
    <tr id="row615515916157"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p715555901517"><a name="p715555901517"></a><a name="p715555901517"></a>fs.obs.secret.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p11155195910151"><a name="p11155195910151"></a><a name="p11155195910151"></a>访问OBS与密钥ID对应的密钥。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1515575919156"><a name="p1515575919156"></a><a name="p1515575919156"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section12299175615451"></a>

MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。

1.  参考[创建用户](创建用户.md)页面，创建一个用于提交作业的用户。

    本示例创建一个用户开发场景使用的机机用户，并分配了正确的用户组（hadoop、supergroup）、主组（supergroup）和角色权限（System\_administrator、default）。

2.  <a name="li37101911105"></a>在MRS Manager页面选择“系统设置 \> 用户管理“，在新增用户的操作列单击“更多 \> 下载认证凭据“。
3.  将与作业相关的jar包上传到集群中，本示例使用Spark自带的样例jar包，位置在$SPARK\_HOME/examples/jars/下。
4.  上传[2](#li37101911105)创建的用户认证凭据到集群的/opt/目录下，并执行如下命令解压

    tar –xvf MRSTest \_xxxxxx\_keytab.tar

    您将会得到user.keytab和krb5.conf两个文件。

5.  在对集群操作之前首先需要执行：

    **source /opt/Bigdata/client/bigdata\_env**

    **cd $SPARK\_HOME**

6.  提交spark作业，使用的命令如下：

    **./bin/spark-submit --master yarn --deploy-mode client --conf spark.yarn.principal=MRSTest --conf spark.yarn.keytab=/opt/user.keytab --class org.apache.spark.examples.SparkPi examples/jars/spark-examples\_2.11-2.3.2-mrs-2.0.jar 10**

    参数解释：

    1.  yarn的计算能力，指定使用client模式提交该作业。
    2.  Spark作业的配置项，这里是传入了认证文件和用户名。
    3.  spark.yarn.principal 第一步创建的用户
    4.  spark.yarn.keytab 认证使用的keytab文件
    5.  xx.jar 作业的使用的jar。


