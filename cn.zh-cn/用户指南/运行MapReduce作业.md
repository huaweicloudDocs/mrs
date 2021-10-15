# 运行MapReduce作业<a name="mrs_01_0052"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节指导您在MRS集群页面如何提交一个新的MapReduce作业。MapReduce作业用于提交jar程序快速并行处理大量数据，是一种分布式数据处理模式和执行环境。

若在集群详情页面不支持“作业管理”和“文件管理”功能，请通过后台功能来提交作业。

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
6.  “作业类型“选择“MapReduce“，并配置其他作业信息。

    ![](figures/添加Mapreduce.png)

    -   请参考[表1](#table2037463920278)配置MapReduce作业信息。

    **表 1**  作业配置信息

    <a name="table2037463920278"></a>
    <table><thead align="left"><tr id="row8368193916278"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p83681839192713"><a name="p83681839192713"></a><a name="p83681839192713"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p18368639102711"><a name="p18368639102711"></a><a name="p18368639102711"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row6369739112710"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p203691739132714"><a name="p203691739132714"></a><a name="p203691739132714"></a>作业名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1936983952719"><a name="p1936983952719"></a><a name="p1936983952719"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
    <div class="note" id="note1736953911274"><a name="note1736953911274"></a><a name="note1736953911274"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p123692397276"><a name="p123692397276"></a><a name="p123692397276"></a>建议不同的作业设置不同的名称。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row1837003922716"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p237013952717"><a name="p237013952717"></a><a name="p237013952717"></a>执行程序路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p137013972712"><a name="p137013972712"></a><a name="p137013972712"></a>待执行程序包地址，需要满足如下要求：</p>
    <a name="ul33700396271"></a><a name="ul33700396271"></a><ul id="ul33700396271"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul193701439132718"></a><a name="ul193701439132718"></a><ul id="ul193701439132718"><li>OBS：以<span class="parmvalue" id="parmvalue206061837142219"><a name="parmvalue206061837142219"></a><a name="parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。</li><li>HDFS：以<span class="parmvalue" id="parmvalue73701139162714"><a name="parmvalue73701139162714"></a><a name="parmvalue73701139162714"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
    </li><li>SparkScript和HiveScript需要以<span class="parmvalue" id="parmvalue037073911277"><a name="parmvalue037073911277"></a><a name="parmvalue037073911277"></a>“.sql”</span>结尾，MapReduce需要以<span class="parmvalue" id="parmvalue3370173972716"><a name="parmvalue3370173972716"></a><a name="parmvalue3370173972716"></a>“.jar”</span>结尾，Flink和SparkSubmit需要以<span class="parmvalue" id="parmvalue0370123910279"><a name="parmvalue0370123910279"></a><a name="parmvalue0370123910279"></a>“.jar”</span>或<span class="parmvalue" id="parmvalue6370739122720"><a name="parmvalue6370739122720"></a><a name="parmvalue6370739122720"></a>“.py”</span>结尾。sql、jar、py不区分大小写。</li></ul>
    </td>
    </tr>
    <tr id="row43711339142713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p33700398274"><a name="p33700398274"></a><a name="p33700398274"></a>执行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p237043962711"><a name="p237043962711"></a><a name="p237043962711"></a>可选参数，程序执行的关键参数。多个参数间使用空格隔开。</p>
    <p id="p93716393271"><a name="p93716393271"></a><a name="p93716393271"></a>配置方法：<em id="i134015424211"><a name="i134015424211"></a><a name="i134015424211"></a>程序类名 数据输入路径 数据输出路径</em></p>
    <a name="ul63716398279"></a><a name="ul63716398279"></a><ul id="ul63716398279"><li>程序类名：由用户程序内的函数指定，MRS只负责参数的传入。</li><li>数据输入路径：通过单击<span class="uicontrol" id="uicontrol180016615619"><a name="uicontrol180016615619"></a><a name="uicontrol180016615619"></a>“HDFS”</span>或者<span class="uicontrol" id="uicontrol1414081112568"><a name="uicontrol1414081112568"></a><a name="uicontrol1414081112568"></a>“OBS”</span>选择或者直接手动输入正确路径。</li><li>数据输出路径：输出路径请手动输入一个不存在的目录。<p id="p12371113910275"><a name="p12371113910275"></a><a name="p12371113910275"></a>最多为150000字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
    <div class="caution" id="note2762142185515"><a name="note2762142185515"></a><a name="note2762142185515"></a><span class="cautiontitle"> 注意： </span><div class="cautionbody"><p id="p27628212551"><a name="p27628212551"></a><a name="p27628212551"></a>若输入带有敏感信息（如登录密码）的参数可能在作业详情展示和日志打印中存在暴露的风险，请谨慎操作。</p>
    </div></div>
    </li></ul>
    </td>
    </tr>
    <tr id="row203713398279"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17371939172710"><a name="p17371939172710"></a><a name="p17371939172710"></a>服务配置参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p4371163914272"><a name="p4371163914272"></a><a name="p4371163914272"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
    <p id="p15371139132712"><a name="p15371139132712"></a><a name="p15371139132712"></a>如需添加多个参数，请单击右侧<a name="image137133942711"></a><a name="image137133942711"></a><span><img id="image137133942711" src="figures/icon_mrs_addtask.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="parmvalue163711139122718"><a name="parmvalue163711139122718"></a><a name="parmvalue163711139122718"></a>“删除”</span>。</p>
    <p id="p625412599416"><a name="p625412599416"></a><a name="p625412599416"></a>常用服务配置参数如<a href="#table12538926589">表2</a>。</p>
    </td>
    </tr>
    <tr id="row9373839142712"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p12373339132716"><a name="p12373339132716"></a><a name="p12373339132716"></a>命令参考</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p7373193992711"><a name="p7373193992711"></a><a name="p7373193992711"></a>用于展示提交作业时提交到后台执行的命令。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  服务配置参数

    <a name="table12538926589"></a>
    <table><thead align="left"><tr id="row95371726284"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="p1453610267810"><a name="p1453610267810"></a><a name="p1453610267810"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.2"><p id="p85361261681"><a name="p85361261681"></a><a name="p85361261681"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.3"><p id="p1536142616818"><a name="p1536142616818"></a><a name="p1536142616818"></a>取值样例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row115378261381"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p145377262818"><a name="p145377262818"></a><a name="p145377262818"></a>fs.obs.access.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p115370264818"><a name="p115370264818"></a><a name="p115370264818"></a>访问OBS的密钥ID。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1053710261482"><a name="p1053710261482"></a><a name="p1053710261482"></a>-</p>
    </td>
    </tr>
    <tr id="row16537926882"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p165376262087"><a name="p165376262087"></a><a name="p165376262087"></a>fs.obs.secret.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1553712261188"><a name="p1553712261188"></a><a name="p1553712261188"></a>访问OBS与密钥ID对应的密钥。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1253718261385"><a name="p1253718261385"></a><a name="p1253718261385"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section12299175615451"></a>

MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  在“节点管理”页签中单击某一Master节点名称，进入弹性云服务器管理控制台。
4.  单击页面右上角的“远程登录”。
5.  根据界面提示，输入Master节点的用户名和密码，用户名、密码分别为root和创建集群时设置的密码。
6.  执行如下命令初始化环境变量。

    **source /opt/Bigdata/client/bigdata\_env**

7.  如果当前集群已开启Kerberos认证，执行以下命令认证当前用户。如果当前集群未开启Kerberos认证，则无需执行该步骤。

    **kinit** **_MRS__集群用户_**

    例如,  **kinit admin**

8.  执行如下命令拷贝OBS文件系统中的程序到集群的Master节点。

    **hadoop fs -Dfs.obs.access.key=AK -Dfs.obs.secret.key=SK -copyToLocal source\_path.jar target\_path.jar**

    例如：**hadoop fs -Dfs.obs.access.key=XXXX -Dfs.obs.secret.key=XXXX -copyToLocal "obs://mrs-word/program/hadoop-mapreduce-examples-XXX.jar" "/home/omm/hadoop-mapreduce-examples-XXX.jar"**

    AK/SK可登录OBS控制台，请在集群控制台页面右上角的用户名下拉框中选择“我的凭证 \> 访问密钥”页面获取。

9.  执行如下命令提交wordcount作业，如需从OBS读取或向OBS输出数据，需要增加AK/SK参数。

    **source /opt/Bigdata/client/bigdata\_env;hadoop jar execute\_jar wordcount input\_path output\_path**

    例如：**source /opt/Bigdata/client/bigdata\_env;hadoop jar /home/omm/hadoop-mapreduce-examples-XXX.jar wordcount -Dfs.obs.access.key=XXXX -Dfs.obs.secret.key=XXXX "obs://mrs-word/input/\*" "obs://mrs-word/output/"**

    input\_path为OBS上存放作业输入文件的路径。output\_path为OBS上存放作业输出文件地址，请设置为一个不存在的目录。


