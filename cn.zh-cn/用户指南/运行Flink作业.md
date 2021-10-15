# 运行Flink作业<a name="mrs_01_0527"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节指导用户在MRS集群页面如何提交一个新的Flink作业。Flink作业用于提交jar程序处理流式数据。

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
6.  “作业类型“选择“Flink“，参考[表 1](#tf38a01bf69f34c29a25317555fc32b92)配置Flink作业信息。

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
    <tr id="rbd79ceb2feb141ff9cb37ffde9e08ed7"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a4e9842e891a449118c2e3811caa071d9"><a name="a4e9842e891a449118c2e3811caa071d9"></a><a name="a4e9842e891a449118c2e3811caa071d9"></a>执行程序路径</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p655627719565"><a name="p655627719565"></a><a name="p655627719565"></a>待执行程序包地址，需要满足如下要求：</p>
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="zh-cn_topic_0173264852_ul56833471484"></a><a name="zh-cn_topic_0173264852_ul56833471484"></a><ul id="zh-cn_topic_0173264852_ul56833471484"><li>OBS：以<span class="parmvalue" id="parmvalue206061837142219"><a name="parmvalue206061837142219"></a><a name="parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。（MRS 3.x及之后版本支持。）</li><li>HDFS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue5002226915745"><a name="zh-cn_topic_0173264852_parmvalue5002226915745"></a><a name="zh-cn_topic_0173264852_parmvalue5002226915745"></a>“/user”</span>开头。数据导入HDFS请参考<a href="管理数据文件.md#section6302178417377">导入数据</a>。</li></ul>
    </li></ul>
    <div class="note" id="note37771150161214"><a name="note37771150161214"></a><a name="note37771150161214"></a><span class="notetitle"> 说明： </span><div class="notebody"><div class="p" id="p56653124212"><a name="p56653124212"></a><a name="p56653124212"></a>若使用<span class="parmvalue" id="parmvalue14232435424"><a name="parmvalue14232435424"></a><a name="parmvalue14232435424"></a>“obs://”</span>开头的OBS路径，请参考如下场景配置访问OBS的对应权限。<a name="ul123943154216"></a><a name="ul123943154216"></a><ul id="ul123943154216"><li>创建集群时开启“OBS权限控制”功能时，可直接使用<span class="parmvalue" id="parmvalue72314344218"><a name="parmvalue72314344218"></a><a name="parmvalue72314344218"></a>“obs://”</span>路径，无需单独配置。</li><li>创建集群时未开启或不支持“OBS权限控制”功能时，请执行如下步骤配置。<a name="ol3543105619436"></a><a name="ol3543105619436"></a><ol id="ol3543105619436"><li>在集群详情页选择“节点管理”并展开节点组。</li><li>单击节点名称，进入云服务器控制台。</li><li>单击“委托”右侧的<a name="image4963141134811"></a><a name="image4963141134811"></a><span><img id="image4963141134811" src="figures/icon_mrs_edit.png"></span>，选择并添加“MRS_ECS_DEFAULT_AGENCY”委托。</li><li>重复以上步骤为集群中的所有节点添加委托。</li></ol>
    </li></ul>
    </div>
    </div></div>
    </td>
    </tr>
    <tr id="row17824727141"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p482420210144"><a name="p482420210144"></a><a name="p482420210144"></a>运行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1652632614145"><a name="p1652632614145"></a><a name="p1652632614145"></a>可选参数，为本次执行的作业配置相关优化参数（例如线程、内存、CPU核数等），用于优化资源使用效率，提升作业的执行性能。</p>
    <p id="p173285722119"><a name="p173285722119"></a><a name="p173285722119"></a>常用运行程序参数如<a href="#table15713101071912">表2</a>。</p>
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
    <p id="p1919755320209"><a name="p1919755320209"></a><a name="p1919755320209"></a>常用服务配置参数如<a href="#table1583911183234">表3</a>。</p>
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
    <tbody><tr id="row071415102199"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p184547371233"><a name="p184547371233"></a><a name="p184547371233"></a>-ytm</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p144333820438"><a name="p144333820438"></a><a name="p144333820438"></a>设置每个TaskManager容器的内存（单位可选, 默认单位：MB）。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1310518539225"><a name="p1310518539225"></a><a name="p1310518539225"></a>1024</p>
    </td>
    </tr>
    <tr id="row17236418124712"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p1945233719231"><a name="p1945233719231"></a><a name="p1945233719231"></a>-yjm</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p154432380434"><a name="p154432380434"></a><a name="p154432380434"></a>设置JobManager容器内存（单位可选，默认单位：MB）。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1710665352213"><a name="p1710665352213"></a><a name="p1710665352213"></a>1024</p>
    </td>
    </tr>
    <tr id="row138876189476"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p8448143716231"><a name="p8448143716231"></a><a name="p8448143716231"></a>-yn</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p141061253112211"><a name="p141061253112211"></a><a name="p141061253112211"></a>设置分配给应用程序的Yarn容器的数量，该值与TaskManager数量相同。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1710619532220"><a name="p1710619532220"></a><a name="p1710619532220"></a>2</p>
    </td>
    </tr>
    <tr id="row15865111913472"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p3440103792318"><a name="p3440103792318"></a><a name="p3440103792318"></a>-ys</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p1210675332211"><a name="p1210675332211"></a><a name="p1210675332211"></a>设置TaskManager的核数。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p71065539223"><a name="p71065539223"></a><a name="p71065539223"></a>2</p>
    </td>
    </tr>
    <tr id="row168661320164718"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p13437237152314"><a name="p13437237152314"></a><a name="p13437237152314"></a>-ynm</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p87211046134315"><a name="p87211046134315"></a><a name="p87211046134315"></a>自定义Yarn上应用程序名称。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p1610615534221"><a name="p1610615534221"></a><a name="p1610615534221"></a>test</p>
    </td>
    </tr>
    <tr id="row1399721154719"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p184341737172312"><a name="p184341737172312"></a><a name="p184341737172312"></a>-c</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p37216461432"><a name="p37216461432"></a><a name="p37216461432"></a>设置程序入口点的类（如“main”或“getPlan(）”方法）。该参数仅在JAR文件未指定其清单的类时需要。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p710814535227"><a name="p710814535227"></a><a name="p710814535227"></a>com.bigdata.mrs.test</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >针对MRS 3.x及之后版本，运行程序参数不支持“-yn”。

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
    <tr id="row11876153883020"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="p118400187237"><a name="p118400187237"></a><a name="p118400187237"></a>fs.obs.secret.key</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.2 "><p id="p4840218182314"><a name="p4840218182314"></a><a name="p4840218182314"></a>访问OBS与密钥ID对应的密钥。</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.3 "><p id="p3840181822311"><a name="p3840181822311"></a><a name="p3840181822311"></a>-</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


## 通过后台提交作业<a name="section12299175615451"></a>

MRS 3.x及之后版本客户端默认安装路径为“/opt/Bigdata/client”，MRS 3.x之前版本为“/opt/client”。具体以实际为准。

1.  登录MRS客户端。
2.  执行如下命令初始化环境变量。

    **source /opt/Bigdata/client/bigdata\_env**

3.  若集群开启Kerberos认证，需要执行以下步骤，若集群未开启Kerberos认证请跳过该步骤。
    1.  准备一个提交Flink作业的用户。
        -   MRS 3.x之前版本，具体请参考[准备开发用户](https://support.huaweicloud.com/devg-mrs/mrs_06_0389.html)。
        -   MRS 3.x及之后版本，具体请参考[准备开发用户](https://support.huaweicloud.com/devg3-mrs/mrs_07_020002.html)。

    2.  使用新创建的用户登录Manager页面。
        -   MRS 3.x之前版本，登录集群的Manager界面，选择“系统设置 \> 用户管理”，在已增加用户所在行的“操作”列，选择“更多 \> 下载认证凭据”。
        -   MRS 3.x及之后版本，登录集群的Manager界面，选择“系统 \> 权限 \> 用户”，在已增加用户所在行的“操作”列，选择“更多 \> 下载认证凭据”。

    3.  将下载的认证凭据压缩包解压缩，并将得到的user.keytab文件拷贝到客户端节点中，例如客户端节点的“/opt/Bigdata/client/Flink/flink/conf“目录下。如果是在集群外节点安装的客户端，需要将得到的krb5.conf文件拷贝到该节点的“/etc/”目录下。
    4.  MRS 3.x及之后版本，安全模式下需要将客户端安装节点的业务IP以及Manager的浮动ip追加到“/opt/Bigdata/client/Flink/flink/conf/flink-conf.yaml”文件中的“jobmanager.web.allow-access-address”配置项中，ip之间使用英文逗号分隔。
    5.  配置安全认证，在“/opt/Bigdata/client/Flink/flink/conf/flink-conf.yaml”配置文件中的对应配置添加keytab路径以及用户名。

        security.kerberos.login.keytab: <_user.keytab文件路径_\>

        security.kerberos.login.principal: <_用户名_\>

        例如：

        security.kerberos.login.keytab: /opt/Bigdata/client/Flink/flink/conf/user.keytab

        security.kerberos.login.principal: test

    6.  在Flink的客户端bin目录下，执行如下命令进行安全加固，请参考[认证和加密](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_1583.html)，password请重新设置为一个用于提交作业的密码。

        sh generate\_keystore.sh <_password_\>

        该脚本会自动替换“/opt/Bigdata/client/Flink/flink/conf/flink-conf.yaml”中关于SSL的值，针对MRS 3.x之前版本，安全集群默认没有开启外部SSL，用户如果需要启用外部SSL，进行配置后再次运行该脚本即可，配置参数在MRS的Flink默认配置中不存在，用户如果开启外部连接SSL，则需要添加[表4](#table780265116214)中参数。

        **表 4**  参数描述

        <a name="table780265116214"></a>
        <table><thead align="left"><tr id="row15803165118217"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p12167120161910"><a name="p12167120161910"></a><a name="p12167120161910"></a><strong id="b19167102011199"><a name="b19167102011199"></a><a name="b19167102011199"></a>参数</strong></p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p616732012193"><a name="p616732012193"></a><a name="p616732012193"></a><strong id="b12167820121913"><a name="b12167820121913"></a><a name="b12167820121913"></a>参数值示例</strong></p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p416716202199"><a name="p416716202199"></a><a name="p416716202199"></a><strong id="b12167182011192"><a name="b12167182011192"></a><a name="b12167182011192"></a>描述</strong></p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row480313519219"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p10167142001911"><a name="p10167142001911"></a><a name="p10167142001911"></a>security.ssl.rest.enabled</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p91673209191"><a name="p91673209191"></a><a name="p91673209191"></a>true</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p81671320171913"><a name="p81671320171913"></a><a name="p81671320171913"></a>打开外部SSL开关。</p>
        </td>
        </tr>
        <tr id="row1780315162114"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p81679206198"><a name="p81679206198"></a><a name="p81679206198"></a>security.ssl.rest.keystore</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p10167182020193"><a name="p10167182020193"></a><a name="p10167182020193"></a>${path}/flink.keystore</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1816712204198"><a name="p1816712204198"></a><a name="p1816712204198"></a>keystore的存放路径。</p>
        </td>
        </tr>
        <tr id="row1980335132115"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p14167112016198"><a name="p14167112016198"></a><a name="p14167112016198"></a>security.ssl.rest.keystore-password</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p116742017196"><a name="p116742017196"></a><a name="p116742017196"></a>123456</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p3168320171914"><a name="p3168320171914"></a><a name="p3168320171914"></a>keystore的password，“123456”表示需要用户输入自定义设置的密码值。</p>
        </td>
        </tr>
        <tr id="row2080314516218"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p20168182018194"><a name="p20168182018194"></a><a name="p20168182018194"></a>security.ssl.rest.key-password</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p9168182016198"><a name="p9168182016198"></a><a name="p9168182016198"></a>123456</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p7168102061917"><a name="p7168102061917"></a><a name="p7168102061917"></a>ssl key的password，“123456”表示需要用户输入自定义设置的密码值。</p>
        </td>
        </tr>
        <tr id="row480335192110"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p2016882061916"><a name="p2016882061916"></a><a name="p2016882061916"></a>security.ssl.rest.truststore</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p81681620101913"><a name="p81681620101913"></a><a name="p81681620101913"></a>${path}/flink.truststore</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p191681201196"><a name="p191681201196"></a><a name="p191681201196"></a>truststore存放路径。</p>
        </td>
        </tr>
        <tr id="row1880335122117"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p016842018197"><a name="p016842018197"></a><a name="p016842018197"></a>security.ssl.rest.truststore-password</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p31686205198"><a name="p31686205198"></a><a name="p31686205198"></a>123456</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1916892018196"><a name="p1916892018196"></a><a name="p1916892018196"></a>truststore的password，“123456”表示需要用户输入自定义设置的密码值。</p>
        </td>
        </tr>
        </tbody>
        </table>

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   针对MRS 3.x之前版本，generate\_keystore.sh脚本无需手动生成。
        >-   [认证和加密](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_1583.html)会将生成的flink.keystore、flink.truststore、security.cookie自动填充到“flink-conf.yaml“对应配置项中。
        >-   针对MRS 3.x及之后版本，“security.ssl.key-password“、“security.ssl.keystore-password“和“security.ssl.truststore-password“的值需要使用Manager明文加密API进行获取：
        >    **curl -k -i -u <_user name_\>:<_password_\> -X POST -HContent-type:application/json  -d '\{"plainText":"<_password_\>"\}' 'https://_x.x.x.x_:28443/web/api/v2/tools/encrypt'**；其中<_password_\>要与签发证书时使用的密码一致，_x.x.x.x_为集群Manager的浮动IP。

    7.  客户端访问flink.keystore和flink.truststore文件的路径配置。
        -   绝对路径：执行该脚本后，在flink-conf.yaml文件中将flink.keystore和flink.truststore文件路径自动配置为绝对路径“/opt/Bigdata/client/Flink/flink/conf/”，此时需要将conf目录中的flink.keystore和flink.truststore文件分别放置在Flink Client以及Yarn各个节点的该绝对路径上。
        -   相对路径：请执行如下步骤配置flink.keystore和flink.truststore文件路径为相对路径，并确保Flink Client执行命令的目录可以直接访问该相对路径。
            1.  在“/opt/Bigdata/client/Flink/flink/conf/”目录下新建目录，例如ssl。
            2.  移动flink.keystore和flink.truststore文件到“/opt/Bigdata/client/Flink/flink/conf/ssl/”中。
            3.  针对MRS 3.x及之后版本，修改flink-conf.yaml文件中如下两个参数为相对路径。

                ```
                security.ssl.keystore: ssl/flink.keystore
                security.ssl.truststore: ssl/flink.truststore
                ```

            4.  针对MRS 3.x之前版本，修改flink-conf.yaml文件中如下两个参数为相对路径。

                ```
                security.ssl.internal.keystore: ssl/flink.keystore
                security.ssl.internal.truststore: ssl/flink.truststore
                ```


    8.  如果客户端安装在集群外节点，请在配置文件（如：**“/opt/Bigdata/client/Flink/fink/conf/flink-conf.yaml”）**中增加如下配置值，其中**xx.xx.xxx.xxx**请替换为客户端所在节点的IP。

        ```
        web.access-control-allow-origin: xx.xx.xxx.xxx
        jobmanager.web.allow-access-address: xx.xx.xxx.xxx
        ```

4.  运行wordcount作业。
    -   普通集群（未开启Kerberos认证）
        -   执行如下命令启动session，并在session中提交作业。

            ```
            yarn-session.sh -nm "session-name"
            flink run /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
            ```

        -   执行如下命令在Yarn上提交单个作业。

            ```
            flink run -m yarn-cluster /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
            ```

    -   安全集群（开启Kerberos认证）
        -   flink.keystore和flink.truststore文件路径为绝对路径时：
            -   执行如下命令启动session，并在session中提交作业。

                ```
                yarn-session.sh -nm "session-name"
                flink run /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
                ```

            -   执行如下命令在Yarn上提交单个作业。

                ```
                flink run -m yarn-cluster /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
                ```

        -   flink.keystore和flink.truststore文件路径为相对路径时：
            -   在“ssl”的同级目录下执行如下命令启动session，并在session中提交作业，其中“ssl”是相对路径，如“ssl”所在目录是“opt/Bigdata/client/Flink/flink/conf/”，则在“opt/Bigdata/client/Flink/flink/conf/”目录下执行命令。

                ```
                yarn-session.sh -t ssl/ -nm "session-name"
                flink run /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
                ```

            -   执行如下命令在Yarn上提交单个作业。

                ```
                flink run -m yarn-cluster -yt ssl/ /opt/Bigdata/client/Flink/flink/examples/streaming/WordCount.jar
                ```





