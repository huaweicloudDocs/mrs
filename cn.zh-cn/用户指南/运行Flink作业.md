# 运行Flink作业<a name="ZH-CN_TOPIC_0173264856"></a>

用户可将自己开发的程序提交到MRS中，执行程序并获取结果。本章节教您在MRS集群页面如何提交一个新的Flink作业。Flink作业用于提交jar程序处理流式数据。

## 前提条件<a name="section2335951116026"></a>

用户已经将运行作业所需的程序包和数据文件上传至OBS系统或HDFS中。

## 通过界面提交作业<a name="section75299125395"></a>

1.  登录MRS管理控制台。
2.  选择“集群列表 \> 现有集群”，选中一个运行中的集群并单击集群名称，进入集群信息页面。
3.  若集群开启Kerberos认证时执行该步骤，若集群未开启Kerberos认证，请无需执行该步骤。

    在“概览“页签的基本信息区域，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0182828410.png)进行IAM用户同步，具体介绍请参考[IAM用户同步MRS](IAM用户同步MRS.md)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   MRS 1.8.7之前版本或者MRS 2.0.1版本开启Kerberos认证集群不支持“作业管理”功能，请通过后台功能提交作业。  
    >-   当IAM用户的用户组的所属策略从MRS Viewer向MRS User、MRS Admin、MRS Administrator变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，等待新修改策略生效之后，再进行提交作业。否则，会出现提交作业失败的情况。  
    >-   当IAM用户的用户组的所属策略从MRS User、MRS Admin、MRS Administrator向MRS Viewer变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，新修改策略才能生效。  

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
    <a name="ul1375493195654"></a><a name="ul1375493195654"></a><ul id="ul1375493195654"><li>最多为1023字符，不能包含;|&amp;&gt;,&lt;'$特殊字符，且不可为空或全空格。</li><li>执行程序路径可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。<a name="zh-cn_topic_0173264852_ul56833471484"></a><a name="zh-cn_topic_0173264852_ul56833471484"></a><ul id="zh-cn_topic_0173264852_ul56833471484"><li>OBS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue15615586113316"><a name="zh-cn_topic_0173264852_parmvalue15615586113316"></a><a name="zh-cn_topic_0173264852_parmvalue15615586113316"></a>“s3a://”</span>开头。示例：s3a://wordcount/program/xxx.jar</li><li>OBS：以<span class="parmvalue" id="parmvalue206061837142219"><a name="parmvalue206061837142219"></a><a name="parmvalue206061837142219"></a>“obs://”</span>开头。示例：obs://wordcount/program/xxx.jar。（MRS 2.1.0及之后版本版本支持。）</li><li>HDFS：以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue5002226915745"><a name="zh-cn_topic_0173264852_parmvalue5002226915745"></a><a name="zh-cn_topic_0173264852_parmvalue5002226915745"></a>“/user”</span>开头。</li></ul>
    </li><li>Spark Script需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue3709601695914"><a name="zh-cn_topic_0173264852_parmvalue3709601695914"></a><a name="zh-cn_topic_0173264852_parmvalue3709601695914"></a>“.sql”</span>结尾，MR和Spark需要以<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue940908595918"><a name="zh-cn_topic_0173264852_parmvalue940908595918"></a><a name="zh-cn_topic_0173264852_parmvalue940908595918"></a>“.jar”</span>结尾。sql、jar不区分大小写。</li></ul>
    <div class="note" id="note37771150161214"><a name="note37771150161214"></a><a name="note37771150161214"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p12108437424"><a name="p12108437424"></a><a name="p12108437424"></a>若使用<span class="parmvalue" id="parmvalue11701104312329"><a name="parmvalue11701104312329"></a><a name="parmvalue11701104312329"></a>“s3a://”</span>开头的OBS路径，请参考<a href="使用Huawei-OBS方式对接.md#section269994210283">访问OBS</a>页面进行配置访问OBS的对应权限。</p>
    <div class="p" id="p56653124212"><a name="p56653124212"></a><a name="p56653124212"></a>若使用<span class="parmvalue" id="parmvalue14232435424"><a name="parmvalue14232435424"></a><a name="parmvalue14232435424"></a>“obs://”</span>开头的OBS路径，请参考如下场景配置访问OBS的对应权限。<a name="ul123943154216"></a><a name="ul123943154216"></a><ul id="ul123943154216"><li>创建集群时开启“OBS权限控制”功能时，可直接使用<span class="parmvalue" id="parmvalue72314344218"><a name="parmvalue72314344218"></a><a name="parmvalue72314344218"></a>“obs://”</span>路径，无需单独配置。</li><li>创建集群时未开启或不支持“OBS权限控制”功能时，请执行如下步骤配置。<a name="ol3543105619436"></a><a name="ol3543105619436"></a><ol id="ol3543105619436"><li>在集群详情页选择“节点管理”并展开节点组。</li><li>单击节点名称，进入云服务器控制台。</li><li>单击“委托”右侧的<a name="image4963141134811"></a><a name="image4963141134811"></a><span><img id="image4963141134811" src="figures/zh-cn_image_0203389088.png"></span>，选择并添加“MRS_ECS_DEFAULT_AGENCY”委托。</li><li>重复以上步骤为集群中的所有节点添加委托。</li></ol>
    </li></ul>
    </div>
    </div></div>
    </td>
    </tr>
    <tr id="row17824727141"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p482420210144"><a name="p482420210144"></a><a name="p482420210144"></a>运行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1652632614145"><a name="p1652632614145"></a><a name="p1652632614145"></a>为本次执行的作业配置相关优化参数（例如线程、内存、CPU核数等），用于优化资源使用效率，提升作业的执行性能。</p>
    </td>
    </tr>
    <tr id="r7dcde55c00da4bc88afb2b022bce0abd"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="a61afb54329564e458086d7622bda3b89"><a name="a61afb54329564e458086d7622bda3b89"></a><a name="a61afb54329564e458086d7622bda3b89"></a>执行程序参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="ad6f1110b8e38456193949182f7a05980"><a name="ad6f1110b8e38456193949182f7a05980"></a><a name="ad6f1110b8e38456193949182f7a05980"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。多个参数间使用空格隔开。</p>
    <p id="a6c44712b37c74651afe354f3cbf9e02f"><a name="a6c44712b37c74651afe354f3cbf9e02f"></a><a name="a6c44712b37c74651afe354f3cbf9e02f"></a>最多为2047字符，不能包含;|&amp;&gt;&lt;'$特殊字符，可为空。</p>
    <div class="note" id="note62371709174814"><a name="note62371709174814"></a><a name="note62371709174814"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0173264852_p20521095174814"><a name="zh-cn_topic_0173264852_p20521095174814"></a><a name="zh-cn_topic_0173264852_p20521095174814"></a>用户输入带有敏感信息（如登录密码）的参数时，可通过在参数名前添加“@”的方式，为该参数值加密，以防止敏感信息被明文形式持久化。在MRS管理控制台查看作业信息时，敏感信息显示为“*”。</p>
    <p id="zh-cn_topic_0173264852_p1265001117571"><a name="zh-cn_topic_0173264852_p1265001117571"></a><a name="zh-cn_topic_0173264852_p1265001117571"></a>例如：username=admin @password=admin_123</p>
    </div></div>
    </td>
    </tr>
    <tr id="row7582163653214"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1527715406327"><a name="p1527715406327"></a><a name="p1527715406327"></a>服务配置参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p0595819249"><a name="p0595819249"></a><a name="p0595819249"></a>可选参数，用于为本次执行的作业修改服务配置参数。该参数的修改仅适用于本次执行的作业，如需对集群永久生效，请参考<a href="配置服务参数.md">配置服务参数</a>页面进行修改。</p>
    <p id="p1793619348256"><a name="p1793619348256"></a><a name="p1793619348256"></a>如需添加多个参数，请单击右侧<a name="zh-cn_topic_0173264852_image137133942711"></a><a name="zh-cn_topic_0173264852_image137133942711"></a><span><img id="zh-cn_topic_0173264852_image137133942711" src="figures/zh-cn_image_0183017691.png"></span>增加，如需删除参数，请单击右侧<span class="parmvalue" id="zh-cn_topic_0173264852_parmvalue163711139122718"><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a><a name="zh-cn_topic_0173264852_parmvalue163711139122718"></a>“删除”</span>。</p>
    </td>
    </tr>
    <tr id="row17661172893316"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p10661142818337"><a name="p10661142818337"></a><a name="p10661142818337"></a>命令参考</p>
    </td>
    <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p204063412410"><a name="p204063412410"></a><a name="p204063412410"></a>用于展示提交作业时提交到后台执行的命令。</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  确认作业配置信息，单击“确定“，完成作业的新增。

    作业新增完成后，可对作业进行管理。


