# 运行MapReduce作业<a name="ZH-CN_TOPIC_0173264852"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节指导您在MRS集群页面如何提交一个新的MapReduce作业。MapReduce作业用于提交jar程序快速并行处理大量数据，是一种分布式数据处理模式和执行环境。

若在集群详情页面不支持“作业管理”和“文件管理”功能，请通过后台功能来提交作业。

## 前提条件<a name="section2335951116026"></a>

用户已经将运行作业所需的程序包和数据文件上传至OBS系统或HDFS中。

## 通过界面提交作业<a name="section75299125395"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  若集群开启Kerberos认证时执行该步骤，若集群未开启Kerberos认证，请无需执行该步骤。

    在“概览“页签的基本信息区域，单击“IAM用户同步“右侧的“点击同步”进行IAM用户同步，具体介绍请参考[IAM用户同步MRS](IAM用户同步MRS.md)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   MRS 1.8.7之前版本或者MRS 2.0.1版本开启Kerberos认证集群不支持“作业管理”功能，请通过后台功能提交作业。  
    >-   当IAM用户的用户组的所属策略从MRS ReadOnlyAccess向MRS CommonOperations、MRS FullAccess、MRS Administrator变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，等待新修改策略生效之后，再进行提交作业。否则，会出现提交作业失败的情况。  
    >-   当IAM用户的用户组的所属策略从MRS CommonOperations、MRS FullAccess、MRS Administrator向MRS ReadOnlyAccess变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，新修改策略才能生效。  

4.  单击“作业管理“，进入“作业管理“页签。
5.  单击“添加“，进入“添加作业“页面。
6.  “作业类型“选择“MapReduce“，并配置其他作业信息。
    -   若集群为MRS 1.8.7、MRS 1.8.10、MRS 1.9.2版本或MRS 2.0.1之后版本，请参考[表1](#table2037463920278)配置MapReduce作业信息。
    -   若集群为MRS 1.8.7之前版本或者MRS 2.0.1版本，请参考[表3](#tf38a01bf69f34c29a25317555fc32b92)配置MapReduce作业信息。

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
        <a name="ul33700396271"></a><a name="ul33700396271"></a><ul id="ul33700396271"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul193701439132718"></a><a name="ul193701439132718"></a><ul id="ul193701439132718"><li>OBS：以<span class="parmvalue" id="parmvalue53701639102718"><a name="parmvalue53701639102718"></a><a name="parmvalue53701639102718"></a>“s3a://”</span>开头。示例：s3a://wordcount/program/xxx.jar</li><li>OBS：以<span class="parmvalue" id="parmvalue206061837142219"><a name="parmvalue206061837142219"></a><a name="parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。（MRS 2.0.5及之后版本版本支持。）</li><li>HDFS：以<span class="parmvalue" id="parmvalue73701139162714"><a name="parmvalue73701139162714"></a><a name="parmvalue73701139162714"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
        </li><li>SparkScript和HiveScript需要以<span class="parmvalue" id="parmvalue037073911277"><a name="parmvalue037073911277"></a><a name="parmvalue037073911277"></a>“.sql”</span>结尾，MapReduce需要以<span class="parmvalue" id="parmvalue3370173972716"><a name="parmvalue3370173972716"></a><a name="parmvalue3370173972716"></a>“.jar”</span>结尾，Flink和SparkSubmit需要以<span class="parmvalue" id="parmvalue0370123910279"><a name="parmvalue0370123910279"></a><a name="parmvalue0370123910279"></a>“.jar”</span>或<span class="parmvalue" id="parmvalue6370739122720"><a name="parmvalue6370739122720"></a><a name="parmvalue6370739122720"></a>“.py”</span>结尾。sql、jar、py不区分大小写。</li></ul>
        </td>
        </tr>
        <tr id="row43711339142713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p33700398274"><a name="p33700398274"></a><a name="p33700398274"></a>执行程序参数</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p237043962711"><a name="p237043962711"></a><a name="p237043962711"></a>可选参数，程序执行的关键参数。多个参数间使用空格隔开。</p>
        <p id="p93716393271"><a name="p93716393271"></a><a name="p93716393271"></a>配置方法：<em id="i134015424211"><a name="i134015424211"></a><a name="i134015424211"></a>程序类名 数据输入路径 数据输出路径</em></p>
        <a name="ul63716398279"></a><a name="ul63716398279"></a><ul id="ul63716398279"><li>程序类名：由用户程序内的函数指定，MRS只负责参数的传入。</li><li>数据输入路径：通过单击HDFS或者OBS选择或者直接手动输入正确路径。</li><li>数据输出路径：输出路径请手动输入一个不存在的目录。</li></ul>
        <p id="p12371113910275"><a name="p12371113910275"></a><a name="p12371113910275"></a>最多为2047字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
        <div class="note" id="note1437118396278"><a name="note1437118396278"></a><a name="note1437118396278"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p13371153962714"><a name="p13371153962714"></a><a name="p13371153962714"></a>用户输入带有敏感信息（如登录密码）的参数时，可通过在参数名前添加“@”的方式，为该参数值加密，以防止敏感信息被明文形式持久化。在MRS管理控制台查看作业信息时，敏感信息显示为“*”。</p>
        <p id="p33712039172711"><a name="p33712039172711"></a><a name="p33712039172711"></a>例如：username=admin @password=admin_123</p>
        </div></div>
        </td>
        </tr>
        <tr id="row203713398279"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p17371939172710"><a name="p17371939172710"></a><a name="p17371939172710"></a>服务配置参数</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p4371163914272"><a name="p4371163914272"></a><a name="p4371163914272"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
        <p id="p15371139132712"><a name="p15371139132712"></a><a name="p15371139132712"></a>如需添加多个参数，请单击右侧<a name="image137133942711"></a><a name="image137133942711"></a><span><img id="image137133942711" src="figures/icon_mrs_addtask.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="parmvalue163711139122718"><a name="parmvalue163711139122718"></a><a name="parmvalue163711139122718"></a>“删除”</span>。</p>
        <p id="p625412599416"><a name="p625412599416"></a><a name="p625412599416"></a>常用服务配置参数如<a href="#table1583911183234">表2</a>。</p>
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

        <a name="table1583911183234"></a>
        <table><thead align="left"><tr id="row483941832316"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p8646182410235"><a name="p8646182410235"></a><a name="p8646182410235"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p15646324192315"><a name="p15646324192315"></a><a name="p15646324192315"></a>参数说明</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p16646192415238"><a name="p16646192415238"></a><a name="p16646192415238"></a>取值样例</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row208401118172317"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p684013184230"><a name="p684013184230"></a><a name="p684013184230"></a>fs.obs.access.key</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p168405185233"><a name="p168405185233"></a><a name="p168405185233"></a>访问OBS的密钥ID。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1984051812310"><a name="p1984051812310"></a><a name="p1984051812310"></a>-</p>
        </td>
        </tr>
        <tr id="row584061832313"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p118400187237"><a name="p118400187237"></a><a name="p118400187237"></a>fs.obs.secret.key</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p4840218182314"><a name="p4840218182314"></a><a name="p4840218182314"></a>访问OBS与密钥ID对应的密钥。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p3840181822311"><a name="p3840181822311"></a><a name="p3840181822311"></a>-</p>
        </td>
        </tr>
        </tbody>
        </table>

        **表 3**  作业配置信息

        <a name="tf38a01bf69f34c29a25317555fc32b92"></a>
        <table><thead align="left"><tr id="rfd2a08fd0ba94517ba01e4ded7454cac"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="af11d9c3dce6c499d8eec0a138b99d392"><a name="af11d9c3dce6c499d8eec0a138b99d392"></a><a name="af11d9c3dce6c499d8eec0a138b99d392"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="ab83f3f06c8cc46369dd5073ae93c3b97"><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a><a name="ab83f3f06c8cc46369dd5073ae93c3b97"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row16309131791918"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1931011715198"><a name="p1931011715198"></a><a name="p1931011715198"></a>作业名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1267051812192"><a name="p1267051812192"></a><a name="p1267051812192"></a>作业名称，只能由字母、数字、中划线和下划线组成，并且长度为1～64个字符。</p>
        <div class="note" id="note067018184197"><a name="note067018184197"></a><a name="note067018184197"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1167017186195"><a name="p1167017186195"></a><a name="p1167017186195"></a>建议不同的作业设置不同的名称。</p>
        </div></div>
        </td>
        </tr>
        <tr id="rbd79ceb2feb141ff9cb37ffde9e08ed7"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a4e9842e891a449118c2e3811caa071d9"><a name="a4e9842e891a449118c2e3811caa071d9"></a><a name="a4e9842e891a449118c2e3811caa071d9"></a>执行程序路径</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p655627719565"><a name="p655627719565"></a><a name="p655627719565"></a>待执行程序包地址，需要满足如下要求：</p>
        <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul56833471484"></a><a name="ul56833471484"></a><ul id="ul56833471484"><li>OBS：以<span class="parmvalue" id="parmvalue15615586113316"><a name="parmvalue15615586113316"></a><a name="parmvalue15615586113316"></a>“s3a://”</span>开头。示例：s3a://wordcount/program/xxx.jar</li><li>HDFS：以<span class="parmvalue" id="parmvalue5002226915745"><a name="parmvalue5002226915745"></a><a name="parmvalue5002226915745"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
        </li><li>Spark Script需要以<span class="parmvalue" id="parmvalue3709601695914"><a name="parmvalue3709601695914"></a><a name="parmvalue3709601695914"></a>“.sql”</span>结尾，MR和Spark需要以<span class="parmvalue" id="parmvalue940908595918"><a name="parmvalue940908595918"></a><a name="parmvalue940908595918"></a>“.jar”</span>结尾。sql、jar不区分大小写。</li></ul>
        </td>
        </tr>
        <tr id="r7dcde55c00da4bc88afb2b022bce0abd"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a61afb54329564e458086d7622bda3b89"><a name="a61afb54329564e458086d7622bda3b89"></a><a name="a61afb54329564e458086d7622bda3b89"></a>执行程序参数</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="ad6f1110b8e38456193949182f7a05980"><a name="ad6f1110b8e38456193949182f7a05980"></a><a name="ad6f1110b8e38456193949182f7a05980"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。多个参数间使用空格隔开。</p>
        <p id="p163988156203"><a name="p163988156203"></a><a name="p163988156203"></a><span>配置方法：包名.类名</span></p>
        <p id="a6c44712b37c74651afe354f3cbf9e02f"><a name="a6c44712b37c74651afe354f3cbf9e02f"></a><a name="a6c44712b37c74651afe354f3cbf9e02f"></a>最多为2047字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
        <div class="note" id="note62371709174814"><a name="note62371709174814"></a><a name="note62371709174814"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p20521095174814"><a name="p20521095174814"></a><a name="p20521095174814"></a>用户输入带有敏感信息（如登录密码）的参数时，可通过在参数名前添加“@”的方式，为该参数值加密，以防止敏感信息被明文形式持久化。在MRS管理控制台查看作业信息时，敏感信息显示为“*”。</p>
        <p id="p1265001117571"><a name="p1265001117571"></a><a name="p1265001117571"></a>例如：username=admin @password=admin_123</p>
        </div></div>
        </td>
        </tr>
        <tr id="r3bdfdc9102e8416492da92bb5912306e"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a93b1caabf748429b887fe55580d1db95"><a name="a93b1caabf748429b887fe55580d1db95"></a><a name="a93b1caabf748429b887fe55580d1db95"></a>数据输入路径</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="a52221b5791d44544af1d6daf2bb57612"><a name="a52221b5791d44544af1d6daf2bb57612"></a><a name="a52221b5791d44544af1d6daf2bb57612"></a>数据输入地址。</p>
        <div class="p" id="p6028322915823"><a name="p6028322915823"></a><a name="p6028322915823"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul1668690715439"></a><a name="ul1668690715439"></a><ul id="ul1668690715439"><li>OBS：以<span class="parmvalue" id="parmvalue1805090015439"><a name="parmvalue1805090015439"></a><a name="parmvalue1805090015439"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue2499739115713"><a name="parmvalue2499739115713"></a><a name="parmvalue2499739115713"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
        </div>
        <p id="a8c411087de5a4952a0a0763536c2fd4a"><a name="a8c411087de5a4952a0a0763536c2fd4a"></a><a name="a8c411087de5a4952a0a0763536c2fd4a"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
        </td>
        </tr>
        <tr id="r26ccf29d38884d09b5b2c445f49e3f0a"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p752552114273"><a name="zh-cn_topic_0012807343_p752552114273"></a><a name="zh-cn_topic_0012807343_p752552114273"></a>输出路径</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="af95377875ef1449db585f0d23bdc5096"><a name="af95377875ef1449db585f0d23bdc5096"></a><a name="af95377875ef1449db585f0d23bdc5096"></a>数据输出地址。</p>
        <div class="note" id="note12918618161337"><a name="note12918618161337"></a><a name="note12918618161337"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul1637410244522"></a><a name="ul1637410244522"></a><ul id="ul1637410244522"><li>配置此参数时，单击<span class="uicontrol" id="uicontrol23741024125214"><a name="uicontrol23741024125214"></a><a name="uicontrol23741024125214"></a>“OBS”</span>或<span class="uicontrol" id="uicontrol17374112412529"><a name="uicontrol17374112412529"></a><a name="uicontrol17374112412529"></a>“HDFS”</span>，并选择文件目录，或者手动输入文件目录，然后单击<span class="uicontrol" id="uicontrol43744241528"><a name="uicontrol43744241528"></a><a name="uicontrol43744241528"></a>“确定”</span>。</li><li>若添加hadoop-mapreduce-examples-x.x.x.jar样例程序或和hadoop-mapreduce-examples-x.x.x.jar类似的程序，请手动输入一个不存在的目录。</li></ul>
        </div></div>
        <div class="p" id="p60582415151053"><a name="p60582415151053"></a><a name="p60582415151053"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul8370831151053"></a><a name="ul8370831151053"></a><ul id="ul8370831151053"><li>OBS：以<span class="parmvalue" id="parmvalue6948719151053"><a name="parmvalue6948719151053"></a><a name="parmvalue6948719151053"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue32451534151053"><a name="parmvalue32451534151053"></a><a name="parmvalue32451534151053"></a>“/user”</span>开头。</li></ul>
        </div>
        <p id="aece1cf44e4734f94b3196ff9e9bf38e8"><a name="aece1cf44e4734f94b3196ff9e9bf38e8"></a><a name="aece1cf44e4734f94b3196ff9e9bf38e8"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
        </td>
        </tr>
        <tr id="rff1753bde96f4e81a0631197ac349003"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0012807343_p287101489174"><a name="zh-cn_topic_0012807343_p287101489174"></a><a name="zh-cn_topic_0012807343_p287101489174"></a>日志路径</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="a2bcc88a179f346448d93d0da091aa47f"><a name="a2bcc88a179f346448d93d0da091aa47f"></a><a name="a2bcc88a179f346448d93d0da091aa47f"></a>作业日志存储地址，该日志信息记录作业运行状态。</p>
        <div class="p" id="p52515849151155"><a name="p52515849151155"></a><a name="p52515849151155"></a>数据可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="ul2880601151155"></a><a name="ul2880601151155"></a><ul id="ul2880601151155"><li>OBS：以<span class="parmvalue" id="parmvalue32002114151155"><a name="parmvalue32002114151155"></a><a name="parmvalue32002114151155"></a>“s3a://”</span>开头。</li><li>HDFS：以<span class="parmvalue" id="parmvalue42765641151155"><a name="parmvalue42765641151155"></a><a name="parmvalue42765641151155"></a>“/user”</span>开头。</li></ul>
        </div>
        <p id="zh-cn_topic_0012807343_p438206609174"><a name="zh-cn_topic_0012807343_p438206609174"></a><a name="zh-cn_topic_0012807343_p438206609174"></a>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，可为空。</p>
        </td>
        </tr>
        </tbody>
        </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section12299175615451"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  在“节点管理”页签中单击某一Master节点名称，进入弹性云服务器管理控制台。
4.  单击页面右上角的“远程登录”。
5.  根据界面提示，输入Master节点的用户名和密码，用户名、密码分别为root和创建集群时设置的密码。
6.  执行如下命令初始化环境变量。

    **source /opt/client/bigdata\_env**

7.  如果当前集群已开启Kerberos认证，执行以下命令认证当前用户。如果当前集群未开启Kerberos认证，则无需执行该步骤。

    **kinit** **_MRS__集群用户_**

    例如,  **kinit admin**

8.  执行如下命令拷贝OBS桶中的程序到集群的Master节点。

    **hadoop fs -Dfs.s3a.access.key=AK -Dfs.s3a.secret.key=SK -copyToLocal source\_path.jar target\_path.jar**

    例如：**hadoop fs -Dfs.s3a.access.key=XXXX -Dfs.s3a.secret.key=XXXX -copyToLocal "s3a://mrs-word/program/hadoop-mapreduce-examples-XXX.jar" "/home/omm/hadoop-mapreduce-examples-XXX.jar"**

    AK/SK可登录OBS控制台，请在集群控制台页面右上角的用户名下拉框中选择“我的凭证 \> 访问密钥”页面获取。

9.  执行如下命令提交wordcount作业，如需从OBS读取或向OBS输出数据，需要增加AK/SK参数。

    **source /opt/client/bigdata\_env;hadoop jar execute\_jar wordcount input\_path output\_path**

    例如：**source /opt/client/bigdata\_env;hadoop jar /home/omm/hadoop-mapreduce-examples-XXX.jar wordcount -Dfs.s3a.access.key=XXXX -Dfs.s3a.secret.key=XXXX "s3a://mrs-word/input/\*" "s3a://mrs-word/output/"**

    input\_path为OBS上存放作业输入文件的路径。output\_path为OBS上存放作业输出文件地址，请设置为一个不存在的目录。


