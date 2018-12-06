# Loader连接配置说明<a name="ZH-CN_TOPIC_0071958193"></a>

## 基本介绍<a name="zh-cn_topic_0070859523_zh-cn_topic_0038340298_section35878706173614"></a>

Loader支持以下多种连接，每种连接的配置介绍可根据本章节内容了解。

-   obs-connector
-   generic-jdbc-connector
-   ftp-connector或sftp-connector
-   hbase-connector、hdfs-connector或hive-connector
-   voltdb-connector

## OBS连接<a name="zh-cn_topic_0070859523_section6038798515402"></a>

OBS连接是Loader与OBS进行数据交换的通道，配置参数如[表1](#zh-cn_topic_0070859523_table47534913165858)所示。

**表 1**  obs-connector配置

<a name="zh-cn_topic_0070859523_table47534913165858"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row66371858165858"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p6548005165858"><a name="zh-cn_topic_0070859523_p6548005165858"></a><a name="zh-cn_topic_0070859523_p6548005165858"></a><strong id="zh-cn_topic_0070859523_b52923339165858"><a name="zh-cn_topic_0070859523_b52923339165858"></a><a name="zh-cn_topic_0070859523_b52923339165858"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p15732486165858"><a name="zh-cn_topic_0070859523_p15732486165858"></a><a name="zh-cn_topic_0070859523_p15732486165858"></a><strong id="zh-cn_topic_0070859523_b37214310155229"><a name="zh-cn_topic_0070859523_b37214310155229"></a><a name="zh-cn_topic_0070859523_b37214310155229"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row54950335165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p7411414165858"><a name="zh-cn_topic_0070859523_p7411414165858"></a><a name="zh-cn_topic_0070859523_p7411414165858"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p19734002165858"><a name="zh-cn_topic_0070859523_p19734002165858"></a><a name="zh-cn_topic_0070859523_p19734002165858"></a>指定一个Loader连接的名称<span id="zh-cn_topic_0070859523_ph544139310225"><a name="zh-cn_topic_0070859523_ph544139310225"></a><a name="zh-cn_topic_0070859523_ph544139310225"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row60451203165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p24790973165858"><a name="zh-cn_topic_0070859523_p24790973165858"></a><a name="zh-cn_topic_0070859523_p24790973165858"></a>OBS服务器</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p48799571165858"><a name="zh-cn_topic_0070859523_p48799571165858"></a><a name="zh-cn_topic_0070859523_p48799571165858"></a>输入OBS endpoint地址，一般格式为<strong id="zh-cn_topic_0070859523_b5982578416109"><a name="zh-cn_topic_0070859523_b5982578416109"></a><a name="zh-cn_topic_0070859523_b5982578416109"></a>OBS.<em id="zh-cn_topic_0070859523_i482166816102"><a name="zh-cn_topic_0070859523_i482166816102"></a><a name="zh-cn_topic_0070859523_i482166816102"></a>Region</em>.<em id="zh-cn_topic_0070859523_i6132438216104"><a name="zh-cn_topic_0070859523_i6132438216104"></a><a name="zh-cn_topic_0070859523_i6132438216104"></a>DomainName</em></strong>。</p>
<p id="zh-cn_topic_0070859523_ab444f92ae94e4c8d9e81244e5c681e10"><a name="zh-cn_topic_0070859523_ab444f92ae94e4c8d9e81244e5c681e10"></a><a name="zh-cn_topic_0070859523_ab444f92ae94e4c8d9e81244e5c681e10"></a><span id="zh-cn_topic_0070859523_ph35836268105653"><a name="zh-cn_topic_0070859523_ph35836268105653"></a><a name="zh-cn_topic_0070859523_ph35836268105653"></a>例如执行如下命令查看OBS endpoint地址：</span></p>
<p id="zh-cn_topic_0070859523_p3775240105413"><a name="zh-cn_topic_0070859523_p3775240105413"></a><a name="zh-cn_topic_0070859523_p3775240105413"></a>cat /opt/Bigdata/apache-tomcat-7.0.78/webapps/web/WEB-INF/classes/cloud-obs.properties</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row41600313165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p7189921165858"><a name="zh-cn_topic_0070859523_p7189921165858"></a><a name="zh-cn_topic_0070859523_p7189921165858"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p62651421165858"><a name="zh-cn_topic_0070859523_p62651421165858"></a><a name="zh-cn_topic_0070859523_p62651421165858"></a>访问OBS数据的端口。默认值为<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue33537595161030"><a name="zh-cn_topic_0070859523_parmvalue33537595161030"></a><a name="zh-cn_topic_0070859523_parmvalue33537595161030"></a>“443”</span>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row61443009165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p38858504165858"><a name="zh-cn_topic_0070859523_p38858504165858"></a><a name="zh-cn_topic_0070859523_p38858504165858"></a>访问标识(AK)</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p4072573165858"><a name="zh-cn_topic_0070859523_p4072573165858"></a><a name="zh-cn_topic_0070859523_p4072573165858"></a>表示访问OBS的用户的访问密钥AK。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row24435072165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p16116169165858"><a name="zh-cn_topic_0070859523_p16116169165858"></a><a name="zh-cn_topic_0070859523_p16116169165858"></a>密钥(SK)</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p41726892165858"><a name="zh-cn_topic_0070859523_p41726892165858"></a><a name="zh-cn_topic_0070859523_p41726892165858"></a>表示访问密钥对应的SK。</p>
</td>
</tr>
</tbody>
</table>

## 关系型数据库连接<a name="zh-cn_topic_0070859523_section36272096161636"></a>

关系型数据库连接是Loader与关系型数据库进行数据交换的通道，配置参数如[表2](#zh-cn_topic_0070859523_table50810889161810)所示。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分参数需要单击“显示高级属性“后展开，否则默认隐藏。  

**表 2**  generic-jdbc-connector配置

<a name="zh-cn_topic_0070859523_table50810889161810"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row60543302161810"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p5060392161810"><a name="zh-cn_topic_0070859523_p5060392161810"></a><a name="zh-cn_topic_0070859523_p5060392161810"></a><strong id="zh-cn_topic_0070859523_b45543534161810"><a name="zh-cn_topic_0070859523_b45543534161810"></a><a name="zh-cn_topic_0070859523_b45543534161810"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p65147614161810"><a name="zh-cn_topic_0070859523_p65147614161810"></a><a name="zh-cn_topic_0070859523_p65147614161810"></a><strong id="zh-cn_topic_0070859523_b49457619161810"><a name="zh-cn_topic_0070859523_b49457619161810"></a><a name="zh-cn_topic_0070859523_b49457619161810"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row46644203161810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p20084112161810"><a name="zh-cn_topic_0070859523_p20084112161810"></a><a name="zh-cn_topic_0070859523_p20084112161810"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p16200361161810"><a name="zh-cn_topic_0070859523_p16200361161810"></a><a name="zh-cn_topic_0070859523_p16200361161810"></a>指定一个Loader连接的名称<span id="zh-cn_topic_0070859523_ph2452068510339"><a name="zh-cn_topic_0070859523_ph2452068510339"></a><a name="zh-cn_topic_0070859523_ph2452068510339"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row11585525161810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p66012312161810"><a name="zh-cn_topic_0070859523_p66012312161810"></a><a name="zh-cn_topic_0070859523_p66012312161810"></a>数据库类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p45397027161810"><a name="zh-cn_topic_0070859523_p45397027161810"></a><a name="zh-cn_topic_0070859523_p45397027161810"></a>表示Loader连接支持的数据，可以选择<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue52972145161911"><a name="zh-cn_topic_0070859523_parmvalue52972145161911"></a><a name="zh-cn_topic_0070859523_parmvalue52972145161911"></a>“ORACLE”</span>、<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue63262900161918"><a name="zh-cn_topic_0070859523_parmvalue63262900161918"></a><a name="zh-cn_topic_0070859523_parmvalue63262900161918"></a>“MYSQL”</span>和<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue16176778161927"><a name="zh-cn_topic_0070859523_parmvalue16176778161927"></a><a name="zh-cn_topic_0070859523_parmvalue16176778161927"></a>“MPPDB”</span>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row20759315161810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p3782984161810"><a name="zh-cn_topic_0070859523_p3782984161810"></a><a name="zh-cn_topic_0070859523_p3782984161810"></a>数据库服务器</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p37986310161810"><a name="zh-cn_topic_0070859523_p37986310161810"></a><a name="zh-cn_topic_0070859523_p37986310161810"></a>表示数据库的访问地址，可以是IP地址或者域名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row56992244161810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p9446596162115"><a name="zh-cn_topic_0070859523_p9446596162115"></a><a name="zh-cn_topic_0070859523_p9446596162115"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p43620698162115"><a name="zh-cn_topic_0070859523_p43620698162115"></a><a name="zh-cn_topic_0070859523_p43620698162115"></a>表示数据库的访问端口。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row26825429162118"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p25376166162118"><a name="zh-cn_topic_0070859523_p25376166162118"></a><a name="zh-cn_topic_0070859523_p25376166162118"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p42203604162118"><a name="zh-cn_topic_0070859523_p42203604162118"></a><a name="zh-cn_topic_0070859523_p42203604162118"></a>表示保存数据的具体数据库名。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row59455409162118"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p51158834162118"><a name="zh-cn_topic_0070859523_p51158834162118"></a><a name="zh-cn_topic_0070859523_p51158834162118"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p50224891162118"><a name="zh-cn_topic_0070859523_p50224891162118"></a><a name="zh-cn_topic_0070859523_p50224891162118"></a>表示连接数据库使用的用户名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row50283185162119"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p46406204162119"><a name="zh-cn_topic_0070859523_p46406204162119"></a><a name="zh-cn_topic_0070859523_p46406204162119"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p806192162119"><a name="zh-cn_topic_0070859523_p806192162119"></a><a name="zh-cn_topic_0070859523_p806192162119"></a>表示此用户对应的密码。需要与实际密码保持一致。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  高级属性配置

<a name="zh-cn_topic_0070859523_table66974111162242"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row59314260162242"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p39725721162242"><a name="zh-cn_topic_0070859523_p39725721162242"></a><a name="zh-cn_topic_0070859523_p39725721162242"></a><strong id="zh-cn_topic_0070859523_b21987170162242"><a name="zh-cn_topic_0070859523_b21987170162242"></a><a name="zh-cn_topic_0070859523_b21987170162242"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p36130385162242"><a name="zh-cn_topic_0070859523_p36130385162242"></a><a name="zh-cn_topic_0070859523_p36130385162242"></a><strong id="zh-cn_topic_0070859523_b56738017162242"><a name="zh-cn_topic_0070859523_b56738017162242"></a><a name="zh-cn_topic_0070859523_b56738017162242"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row63910201162242"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p9343783162242"><a name="zh-cn_topic_0070859523_p9343783162242"></a><a name="zh-cn_topic_0070859523_p9343783162242"></a>一次请求行数</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p18648962162242"><a name="zh-cn_topic_0070859523_p18648962162242"></a><a name="zh-cn_topic_0070859523_p18648962162242"></a>表示每次连接数据库时，最多可获取的数据量。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row33622931162242"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p56218263141119"><a name="zh-cn_topic_0070859523_p56218263141119"></a><a name="zh-cn_topic_0070859523_p56218263141119"></a>连接属性</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p54611015141119"><a name="zh-cn_topic_0070859523_p54611015141119"></a><a name="zh-cn_topic_0070859523_p54611015141119"></a>不同类型数据库支持该数据库连接特有的驱动属性，例如MYSQL的<span class="parmname" id="zh-cn_topic_0070859523_parmname5337903714227"><a name="zh-cn_topic_0070859523_parmname5337903714227"></a><a name="zh-cn_topic_0070859523_parmname5337903714227"></a>“autoReconnect”</span>。如果需要定义驱动属性，单击<span class="uicontrol" id="zh-cn_topic_0070859523_uicontrol19702542144319"><a name="zh-cn_topic_0070859523_uicontrol19702542144319"></a><a name="zh-cn_topic_0070859523_uicontrol19702542144319"></a>“添加”</span>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row51861677162242"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p40046281162242"><a name="zh-cn_topic_0070859523_p40046281162242"></a><a name="zh-cn_topic_0070859523_p40046281162242"></a>引用符号</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p22523354162242"><a name="zh-cn_topic_0070859523_p22523354162242"></a><a name="zh-cn_topic_0070859523_p22523354162242"></a>表示数据库的SQL中保留关键字的定界符，不同类型数据库定义的定界符不完全相同。</p>
</td>
</tr>
</tbody>
</table>

## 文件服务器连接<a name="zh-cn_topic_0070859523_section27102035161636"></a>

文件服务器连接包含FTP连接和SFTP连接，是Loader与文件服务器进行数据交换的通道，配置参数如[表4](#zh-cn_topic_0070859523_table45072347161636)所示。

**表 4**  ftp-connector或sftp-connector配置

<a name="zh-cn_topic_0070859523_table45072347161636"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row59243288161636"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p33977024161636"><a name="zh-cn_topic_0070859523_p33977024161636"></a><a name="zh-cn_topic_0070859523_p33977024161636"></a><strong id="zh-cn_topic_0070859523_b37357765161636"><a name="zh-cn_topic_0070859523_b37357765161636"></a><a name="zh-cn_topic_0070859523_b37357765161636"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p6080159161636"><a name="zh-cn_topic_0070859523_p6080159161636"></a><a name="zh-cn_topic_0070859523_p6080159161636"></a><strong id="zh-cn_topic_0070859523_b54721438161636"><a name="zh-cn_topic_0070859523_b54721438161636"></a><a name="zh-cn_topic_0070859523_b54721438161636"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row3251492161636"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p62044270161636"><a name="zh-cn_topic_0070859523_p62044270161636"></a><a name="zh-cn_topic_0070859523_p62044270161636"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p59529956161636"><a name="zh-cn_topic_0070859523_p59529956161636"></a><a name="zh-cn_topic_0070859523_p59529956161636"></a>指定一个Loader连接的名称<span id="zh-cn_topic_0070859523_ph61479602103436"><a name="zh-cn_topic_0070859523_ph61479602103436"></a><a name="zh-cn_topic_0070859523_ph61479602103436"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row66007564161636"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p45012464161636"><a name="zh-cn_topic_0070859523_p45012464161636"></a><a name="zh-cn_topic_0070859523_p45012464161636"></a>主机名或IP</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p22130997161636"><a name="zh-cn_topic_0070859523_p22130997161636"></a><a name="zh-cn_topic_0070859523_p22130997161636"></a>输入文件服务器的访问地址，可以是服务器的主机名或者IP地址。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row45003521161636"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p21406551161636"><a name="zh-cn_topic_0070859523_p21406551161636"></a><a name="zh-cn_topic_0070859523_p21406551161636"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p56209070161636"><a name="zh-cn_topic_0070859523_p56209070161636"></a><a name="zh-cn_topic_0070859523_p56209070161636"></a>访问文件服务器的端口。</p>
<a name="zh-cn_topic_0070859523_ul35013240163027"></a><a name="zh-cn_topic_0070859523_ul35013240163027"></a><ul id="zh-cn_topic_0070859523_ul35013240163027"><li>FTP协议请使用端口<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue66766709163051"><a name="zh-cn_topic_0070859523_parmvalue66766709163051"></a><a name="zh-cn_topic_0070859523_parmvalue66766709163051"></a>“21”</span>。</li><li>SFTP协议请使用端口<span class="parmvalue" id="zh-cn_topic_0070859523_parmvalue24833339163046"><a name="zh-cn_topic_0070859523_parmvalue24833339163046"></a><a name="zh-cn_topic_0070859523_parmvalue24833339163046"></a>“22”</span>。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row56640813161636"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p24503165161636"><a name="zh-cn_topic_0070859523_p24503165161636"></a><a name="zh-cn_topic_0070859523_p24503165161636"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p38599366161636"><a name="zh-cn_topic_0070859523_p38599366161636"></a><a name="zh-cn_topic_0070859523_p38599366161636"></a>表示文件服务器的用户名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row11849975161636"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p20323879161636"><a name="zh-cn_topic_0070859523_p20323879161636"></a><a name="zh-cn_topic_0070859523_p20323879161636"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p35621475161636"><a name="zh-cn_topic_0070859523_p35621475161636"></a><a name="zh-cn_topic_0070859523_p35621475161636"></a>表示此用户对应的密码。</p>
</td>
</tr>
</tbody>
</table>

## MRS集群连接<a name="zh-cn_topic_0070859523_section39769106163153"></a>

MRS集群连接包含HBase连接、HDFS连接和Hive连接，是Loader与对应各数据进行数据交换的通道。

配置MRS集群连接时，需要设置名称、选择对应的连接器“hbase-connector“、“hdfs-connector“或“hive-connector“，然后保存即可。

## 内存数据库连接<a name="zh-cn_topic_0070859523_section5959318316354"></a>

VoltDB连接是Loader与内存数据库进行数据交换的通道，配置参数如[表5](#zh-cn_topic_0070859523_table1463518916354)所示。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分参数需要单击“显示高级属性“后展开，否则默认隐藏。  

**表 5**  voltdb-connector配置

<a name="zh-cn_topic_0070859523_table1463518916354"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row2389087116354"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p5611236016354"><a name="zh-cn_topic_0070859523_p5611236016354"></a><a name="zh-cn_topic_0070859523_p5611236016354"></a><strong id="zh-cn_topic_0070859523_b3524919516354"><a name="zh-cn_topic_0070859523_b3524919516354"></a><a name="zh-cn_topic_0070859523_b3524919516354"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p3661257216354"><a name="zh-cn_topic_0070859523_p3661257216354"></a><a name="zh-cn_topic_0070859523_p3661257216354"></a><strong id="zh-cn_topic_0070859523_b6107770016354"><a name="zh-cn_topic_0070859523_b6107770016354"></a><a name="zh-cn_topic_0070859523_b6107770016354"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row4834668716354"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p2376758716354"><a name="zh-cn_topic_0070859523_p2376758716354"></a><a name="zh-cn_topic_0070859523_p2376758716354"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p4612635816354"><a name="zh-cn_topic_0070859523_p4612635816354"></a><a name="zh-cn_topic_0070859523_p4612635816354"></a>指定一个Loader连接的名称<span id="zh-cn_topic_0070859523_ph30175909103633"><a name="zh-cn_topic_0070859523_ph30175909103633"></a><a name="zh-cn_topic_0070859523_ph30175909103633"></a>。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row2393588016354"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p5975810516354"><a name="zh-cn_topic_0070859523_p5975810516354"></a><a name="zh-cn_topic_0070859523_p5975810516354"></a>数据库服务器列表</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p856836816354"><a name="zh-cn_topic_0070859523_p856836816354"></a><a name="zh-cn_topic_0070859523_p856836816354"></a>表示数据库的访问地址，可以是IP地址或者域名。支持配置多个数据库地址，使用英文逗号分隔。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row1000644816354"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p521594416354"><a name="zh-cn_topic_0070859523_p521594416354"></a><a name="zh-cn_topic_0070859523_p521594416354"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p1983829616354"><a name="zh-cn_topic_0070859523_p1983829616354"></a><a name="zh-cn_topic_0070859523_p1983829616354"></a>表示数据库的访问端口。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row1454615616354"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p3738801516354"><a name="zh-cn_topic_0070859523_p3738801516354"></a><a name="zh-cn_topic_0070859523_p3738801516354"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p853035416354"><a name="zh-cn_topic_0070859523_p853035416354"></a><a name="zh-cn_topic_0070859523_p853035416354"></a>表示连接数据库使用的用户名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0070859523_row966432316354"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p4461268116354"><a name="zh-cn_topic_0070859523_p4461268116354"></a><a name="zh-cn_topic_0070859523_p4461268116354"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p5685744516354"><a name="zh-cn_topic_0070859523_p5685744516354"></a><a name="zh-cn_topic_0070859523_p5685744516354"></a>表示此用户对应的密码。需要与实际密码保持一致。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  高级属性配置

<a name="zh-cn_topic_0070859523_table26736023163752"></a>
<table><thead align="left"><tr id="zh-cn_topic_0070859523_row62201782163752"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0070859523_p5179558163752"><a name="zh-cn_topic_0070859523_p5179558163752"></a><a name="zh-cn_topic_0070859523_p5179558163752"></a><strong id="zh-cn_topic_0070859523_b46616027163752"><a name="zh-cn_topic_0070859523_b46616027163752"></a><a name="zh-cn_topic_0070859523_b46616027163752"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0070859523_p17801843163752"><a name="zh-cn_topic_0070859523_p17801843163752"></a><a name="zh-cn_topic_0070859523_p17801843163752"></a><strong id="zh-cn_topic_0070859523_b25998864163752"><a name="zh-cn_topic_0070859523_b25998864163752"></a><a name="zh-cn_topic_0070859523_b25998864163752"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0070859523_row18549979163752"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p26153360163752"><a name="zh-cn_topic_0070859523_p26153360163752"></a><a name="zh-cn_topic_0070859523_p26153360163752"></a>连接属性</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p38047438163752"><a name="zh-cn_topic_0070859523_p38047438163752"></a><a name="zh-cn_topic_0070859523_p38047438163752"></a>内存数据库的SQL中保留关键字的定界符。</p>
</td>
</tr>
</tbody>
</table>

