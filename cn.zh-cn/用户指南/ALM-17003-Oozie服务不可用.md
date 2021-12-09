# ALM-17003 Oozie服务不可用<a name="ALM-17003"></a>

## 告警解释<a name="section42896681"></a>

系统每5秒周期性检测Oozie服务状态，当Oozie或者Oozie所依赖的组件无法正常提供服务时，系统产生此告警。

当Oozie服务恢复可用状态时，告警自动消除。

## 告警属性<a name="section50525815"></a>

<a name="table61893760"></a>
<table><thead align="left"><tr id="row9197749"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p6820189"><a name="p6820189"></a><a name="p6820189"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p15564413"><a name="p15564413"></a><a name="p15564413"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p52757950"><a name="p52757950"></a><a name="p52757950"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row45535559"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p64501697"><a name="p64501697"></a><a name="p64501697"></a>17003</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57254996"><a name="p57254996"></a><a name="p57254996"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p7143079"><a name="p7143079"></a><a name="p7143079"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section52079156"></a>

<a name="table41718498"></a>
<table><thead align="left"><tr id="row3441097"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p10293461"><a name="p10293461"></a><a name="p10293461"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p28464046"><a name="p28464046"></a><a name="p28464046"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row316519506210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row23886395"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19444883"><a name="p19444883"></a><a name="p19444883"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row40786223"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p35373576"><a name="p35373576"></a><a name="p35373576"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row49926729"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10903797"><a name="p10903797"></a><a name="p10903797"></a>产生告警的主机名。</p>
</td>
</tr>
<tr id="row9938136386"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p17939103173818"><a name="p17939103173818"></a><a name="p17939103173818"></a>Details</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p0939232386"><a name="p0939232386"></a><a name="p0939232386"></a>对告警信息的补充。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section66059225"></a>

无法使用Oozie服务提交作业。

## 可能原因<a name="section57662120"></a>

-   DBService服务异常或者Oozie存储在DBService中的数据遭到破坏，导致Oozie服务不可用。
-   HDFS服务异常或者Oozie存储在HDFS中的数据遭到破坏时，导致Oozie服务不可用。
-   Yarn服务异常，导致Oozie服务不可用。
-   Nodeagent进程故障，导致Oozie服务不可用。

## 处理步骤<a name="section49197032"></a>

**查询Oozie服务健康状态码。**

1.  在FusionInsight Manager中，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Oozie”，单击“oozie WebUI”的“oozie”（两个任选一个），进入Oozie WebUI页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >**admin**用户默认不具备其他组件的管理权限，如果访问组件原生界面时出现因权限不足而打不开页面或内容显示不全时，可手动创建具备对应组件管理权限的用户进行登录。

2.  在浏览器地址栏的URL地址后追加“/servicehealth”重新访问，“statusCode”对应的值即为当前Oozie的服务健康状态码。

    例如，在浏览器中访问“https://10.10.0.117:20026/Oozie/oozie/130/oozie/servicehealth”，显示结果为：

    ```
    {"beans":[{"name":"serviceStatus","statusCode":0}]}
    ```

    如果无法查询出健康状态码或者浏览器一直无响应，可能是由于Oozie进程故障导致服务不可用，请参考[13](#li4094569118479)进行处理。

3.  根据查询到的错误码执行相关处理步骤，请参考[表1](#table1317697618479)。

    **表 1**  Oozie服务健康状态码一览表

    <a name="table1317697618479"></a>
    <table><thead align="left"><tr id="row67029318479"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p5410670518479"><a name="p5410670518479"></a><a name="p5410670518479"></a>状态码</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p2056701618479"><a name="p2056701618479"></a><a name="p2056701618479"></a>错误描述</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p5531556218479"><a name="p5531556218479"></a><a name="p5531556218479"></a>错误原因</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p5137555318479"><a name="p5137555318479"></a><a name="p5137555318479"></a>处理步骤</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row6133989918479"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5429377318479"><a name="p5429377318479"></a><a name="p5429377318479"></a>0</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p3571950618479"><a name="p3571950618479"></a><a name="p3571950618479"></a>服务正常</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p759885918479"><a name="p759885918479"></a><a name="p759885918479"></a>无</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p1152784118479"><a name="p1152784118479"></a><a name="p1152784118479"></a>无</p>
    </td>
    </tr>
    <tr id="row1874764118479"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1518818118479"><a name="p1518818118479"></a><a name="p1518818118479"></a>18002</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p2228315318479"><a name="p2228315318479"></a><a name="p2228315318479"></a>DBService服务异常</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p6010496518479"><a name="p6010496518479"></a><a name="p6010496518479"></a>Oozie连接DBservice失败或者存储在DBService中的数据遭到破坏</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p6154078418479"><a name="p6154078418479"></a><a name="p6154078418479"></a>请参考<a href="#li1823310618479">4</a>。</p>
    </td>
    </tr>
    <tr id="row557711218479"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3451104618479"><a name="p3451104618479"></a><a name="p3451104618479"></a>18003</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p4393130818479"><a name="p4393130818479"></a><a name="p4393130818479"></a>HDFS服务异常</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p166619518479"><a name="p166619518479"></a><a name="p166619518479"></a>Oozie连接HDFS失败或者存储在HDFS中的数据遭到破坏</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p669688918479"><a name="p669688918479"></a><a name="p669688918479"></a>请参考<a href="#li4813769918479">7</a>。</p>
    </td>
    </tr>
    <tr id="row6077507118479"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5019401118479"><a name="p5019401118479"></a><a name="p5019401118479"></a>18005</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p3918306018479"><a name="p3918306018479"></a><a name="p3918306018479"></a>Mapreduce服务异常</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1971125318479"><a name="p1971125318479"></a><a name="p1971125318479"></a>Yarn服务异常</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p820684918479"><a name="p820684918479"></a><a name="p820684918479"></a>请参考<a href="#li3361692218479">11</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>


**检查DBService服务。**

1.  <a name="li1823310618479"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务”，检查DBService服务当前状态是否正常。
    -   是，执行[6](#li2956081718479)。
    -   否，执行[5](#li1921083018479)。

2.  <a name="li1921083018479"></a>参考DBService服务的相关告警帮助进行处理，然后查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li3737274418479)。

3.  <a name="li2956081718479"></a>登录Oozie数据库检查数据是否完整。
    1.  以**root**用户登录DBService主节点，用户密码为安装前用户自定义，请咨询系统管理员。

        在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务 \> DBService \> 实例”，即可查看DBService主节点IP地址信息。

    2.  执行以下命令登录Oozie数据库。

        **su - omm**

        **source $\{BIGDATA\_HOME\}/FusionInsight\_BASE\_8.1.0.1/install/FusionInsight-dbservice-2.7.0/.dbservice\_profile**

        **gsql -U **_用户名_**-W **_ Oozie__数据库密码__ _**-p 20051 -d **_数据库名称_

    3.  登录成功后，输入**\\d**，检查数据表是否共有15张。

        Oozie服务默认有15张数据表，如果这些数据表被删除或者表结构被修改都可能导致Oozie服务不可用，请联系运维人员备份相关数据后进行恢复。



**检查HDFS服务。**

1.  <a name="li4813769918479"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务”，检查HDFS服务当前状态是否正常。
    -   是，执行[9](#li245582218479)。
    -   否，执行[8](#li1998722318479)。

2.  <a name="li1998722318479"></a>参考HDFS服务的相关告警帮助进行处理，然后查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li3737274418479)。

3.  <a name="li245582218479"></a>登录HDFS检查Oozie文件目录是否完整。
    1.  下载并安装HDFS客户端。
    2.  以**root**用户登录客户端所在节点，执行以下命令，检查“/user/oozie/share”路径是否存在，用户密码为安装前用户自定义，请咨询系统管理员。

        如果集群采用安全版本，要进行安全认证。

        **kinit admin**

        **hdfs dfs -ls /user/oozie/share**

    -   是，执行[18](#li3737274418479)。
    -   否，执行[10](#li5883752018479)。

4.  <a name="li5883752018479"></a>在Oozie客户端安装目录中手动将share目录上传至HDFS的“/user/oozie”路径下，检查告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li3737274418479)。


**检查Yarn/Mapreduce服务。**

1.  <a name="li3361692218479"></a>在FusionInsight Manager界面，选择“集群 \>  _待操作集群的名称_  \> 服务”，检查Yarn、Mapreduce服务当前状态是否正常。
    -   是，执行[18](#li3737274418479)。
    -   否，执行[12](#li2453213218479)。

2.  <a name="li2453213218479"></a>参考Yarn、Mapreduce服务的相关告警帮助进行处理，然后查看本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li3737274418479)。


**检查Oozie进程。**

1.  <a name="li4094569118479"></a>以**root**用户分别登录Oozie服务两个节点，用户密码为安装前用户自定义，请咨询系统管理员。

    在FusionInsight Manager界面单击“集群 \>  _待操作集群的名称_  \> 服务 \> Oozie \> 实例”，即可查看服务所在节点的IP地址信息。

2.  执行命令**ps -ef | grep oozie**，检查Oozie进程是否存在。
    -   是，执行[15](#li3532841118479)。
    -   否，执行[18](#li3737274418479)。

3.  <a name="li3532841118479"></a>分别检查和收集Oozie日志目录“/var/log/Bigdata/oozie”中的prestartDetail.log、oozie.log、catalina.out里的异常信息，确认非人为误操作导致的问题后，执行[16](#li3644023818479)。

**检查Nodeagent进程。**

1.  <a name="li3644023818479"></a>以**root**用户分别登录Oozie服务两个节点。执行命令**ps -ef | grep nodeagent**，检查Nodeagent进程是否存在。
    -   是，执行[17](#li460391418479)。
    -   否，执行[18](#li3737274418479)。

2.  <a name="li460391418479"></a>执行**kill -9 **_查询到的nodeagent__进程ID_命令，等待10分钟后，检查本告警是否恢复。
    -   是，处理完毕。
    -   否，执行[18](#li3737274418479)。

3.  <a name="li3737274418479"></a>请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40120107"></a>

无。

