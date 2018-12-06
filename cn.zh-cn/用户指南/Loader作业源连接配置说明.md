# Loader作业源连接配置说明<a name="ZH-CN_TOPIC_0071958195"></a>

## 基本介绍<a name="zh-cn_topic_0071084972_zh-cn_topic_0038340298_section35878706173614"></a>

Loader作业需要从不同数据源获取数据时，应该选择对应类型的连接，每种连接在该场景中需要配置连接的属性。

## obs-connector<a name="zh-cn_topic_0071084972_section19798241165732"></a>

**表 1**  obs-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table47534913165858"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row66371858165858"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p6548005165858"><a name="zh-cn_topic_0071084972_p6548005165858"></a><a name="zh-cn_topic_0071084972_p6548005165858"></a><strong id="zh-cn_topic_0071084972_b52923339165858"><a name="zh-cn_topic_0071084972_b52923339165858"></a><a name="zh-cn_topic_0071084972_b52923339165858"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p15732486165858"><a name="zh-cn_topic_0071084972_p15732486165858"></a><a name="zh-cn_topic_0071084972_p15732486165858"></a><strong id="zh-cn_topic_0071084972_b37214310155229"><a name="zh-cn_topic_0071084972_b37214310155229"></a><a name="zh-cn_topic_0071084972_b37214310155229"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row54950335165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p7411414165858"><a name="zh-cn_topic_0071084972_p7411414165858"></a><a name="zh-cn_topic_0071084972_p7411414165858"></a>桶名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p19734002165858"><a name="zh-cn_topic_0071084972_p19734002165858"></a><a name="zh-cn_topic_0071084972_p19734002165858"></a>保存源数据的OBS桶。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row60451203165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p24790973165858"><a name="zh-cn_topic_0071084972_p24790973165858"></a><a name="zh-cn_topic_0071084972_p24790973165858"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p48799571165858"><a name="zh-cn_topic_0071084972_p48799571165858"></a><a name="zh-cn_topic_0071084972_p48799571165858"></a>源数据实际存储的形态，可能是桶包含一个目录中的全部数据文件，或者是桶包含的单个数据文件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row41600313165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p7189921165858"><a name="zh-cn_topic_0071084972_p7189921165858"></a><a name="zh-cn_topic_0071084972_p7189921165858"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p62651421165858"><a name="zh-cn_topic_0071084972_p62651421165858"></a><a name="zh-cn_topic_0071084972_p62651421165858"></a>Loader支持OBS中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084972_ul371701117443"></a><a name="zh-cn_topic_0071084972_ul371701117443"></a><ul id="zh-cn_topic_0071084972_ul371701117443"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row61443009165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p547205051766"><a name="zh-cn_topic_0071084972_p547205051766"></a><a name="zh-cn_topic_0071084972_p547205051766"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p527477181766"><a name="zh-cn_topic_0071084972_p527477181766"></a><a name="zh-cn_topic_0071084972_p527477181766"></a>源数据的每行结束标识字符。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row2610221317611"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p1258785917611"><a name="zh-cn_topic_0071084972_p1258785917611"></a><a name="zh-cn_topic_0071084972_p1258785917611"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p1477620017611"><a name="zh-cn_topic_0071084972_p1477620017611"></a><a name="zh-cn_topic_0071084972_p1477620017611"></a>源数据的每个字段分割标识字符。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row4220377717611"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p4671978717611"><a name="zh-cn_topic_0071084972_p4671978717611"></a><a name="zh-cn_topic_0071084972_p4671978717611"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p5998571317611"><a name="zh-cn_topic_0071084972_p5998571317611"></a><a name="zh-cn_topic_0071084972_p5998571317611"></a>源数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row24435072165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p179695571766"><a name="zh-cn_topic_0071084972_p179695571766"></a><a name="zh-cn_topic_0071084972_p179695571766"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="zh-cn_topic_0071084972_p98470941766"><a name="zh-cn_topic_0071084972_p98470941766"></a><a name="zh-cn_topic_0071084972_p98470941766"></a>支持以下两种：<a name="zh-cn_topic_0071084972_ul200684591785"></a><a name="zh-cn_topic_0071084972_ul200684591785"></a><ul id="zh-cn_topic_0071084972_ul200684591785"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_parmvalue65660326171128"><a name="zh-cn_topic_0071084972_parmvalue65660326171128"></a><a name="zh-cn_topic_0071084972_parmvalue65660326171128"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_parmvalue1507545117121"><a name="zh-cn_topic_0071084972_parmvalue1507545117121"></a><a name="zh-cn_topic_0071084972_parmvalue1507545117121"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## generic-jdbc-connector<a name="zh-cn_topic_0071084972_section22577605171229"></a>

**表 2**  generic-jdbc-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table3633668171234"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row49651228171234"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p33247043171234"><a name="zh-cn_topic_0071084972_p33247043171234"></a><a name="zh-cn_topic_0071084972_p33247043171234"></a><strong id="zh-cn_topic_0071084972_b7426418171234"><a name="zh-cn_topic_0071084972_b7426418171234"></a><a name="zh-cn_topic_0071084972_b7426418171234"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p35893585171234"><a name="zh-cn_topic_0071084972_p35893585171234"></a><a name="zh-cn_topic_0071084972_p35893585171234"></a><strong id="zh-cn_topic_0071084972_b31055900171234"><a name="zh-cn_topic_0071084972_b31055900171234"></a><a name="zh-cn_topic_0071084972_b31055900171234"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row33950906171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p48702080171246"><a name="zh-cn_topic_0071084972_p48702080171246"></a><a name="zh-cn_topic_0071084972_p48702080171246"></a>模式或表空间</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p56912783171246"><a name="zh-cn_topic_0071084972_p56912783171246"></a><a name="zh-cn_topic_0071084972_p56912783171246"></a>表示源数据对应的数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row17988209171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p44342240171246"><a name="zh-cn_topic_0071084972_p44342240171246"></a><a name="zh-cn_topic_0071084972_p44342240171246"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p33917989171246"><a name="zh-cn_topic_0071084972_p33917989171246"></a><a name="zh-cn_topic_0071084972_p33917989171246"></a>存储源数据的数据表，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row57591502171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p37503647171246"><a name="zh-cn_topic_0071084972_p37503647171246"></a><a name="zh-cn_topic_0071084972_p37503647171246"></a>抽取分区字段</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p45041285171246"><a name="zh-cn_topic_0071084972_p45041285171246"></a><a name="zh-cn_topic_0071084972_p45041285171246"></a>分区字段，如果需读取多个字段，使用该字段分割结果并获取数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row16901145171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p63433219171246"><a name="zh-cn_topic_0071084972_p63433219171246"></a><a name="zh-cn_topic_0071084972_p63433219171246"></a><span id="zh-cn_topic_0071084972_ph1349216105726"><a name="zh-cn_topic_0071084972_ph1349216105726"></a><a name="zh-cn_topic_0071084972_ph1349216105726"></a>Where子句</span></p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p1705893171246"><a name="zh-cn_topic_0071084972_p1705893171246"></a><a name="zh-cn_topic_0071084972_p1705893171246"></a>表示读取数据库时使用的查询语句。</p>
</td>
</tr>
</tbody>
</table>

## ftp-connector或sftp-connector<a name="zh-cn_topic_0071084972_section64895548171739"></a>

**表 3**  ftp-connector或sftp-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table62801247171753"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row19753839171753"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p48044734171753"><a name="zh-cn_topic_0071084972_p48044734171753"></a><a name="zh-cn_topic_0071084972_p48044734171753"></a><strong id="zh-cn_topic_0071084972_b57270601171753"><a name="zh-cn_topic_0071084972_b57270601171753"></a><a name="zh-cn_topic_0071084972_b57270601171753"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p53951536171753"><a name="zh-cn_topic_0071084972_p53951536171753"></a><a name="zh-cn_topic_0071084972_p53951536171753"></a><strong id="zh-cn_topic_0071084972_b22477863171753"><a name="zh-cn_topic_0071084972_b22477863171753"></a><a name="zh-cn_topic_0071084972_b22477863171753"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row66223917171753"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p55459555172047"><a name="zh-cn_topic_0071084972_p55459555172047"></a><a name="zh-cn_topic_0071084972_p55459555172047"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p28781283172039"><a name="zh-cn_topic_0071084972_p28781283172039"></a><a name="zh-cn_topic_0071084972_p28781283172039"></a>源数据实际存储的形态，可能是文件服务器包含一个目录中的全部数据文件，或者是单个数据文件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row52058581172040"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p8729931172047"><a name="zh-cn_topic_0071084972_p8729931172047"></a><a name="zh-cn_topic_0071084972_p8729931172047"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p55956598172119"><a name="zh-cn_topic_0071084972_p55956598172119"></a><a name="zh-cn_topic_0071084972_p55956598172119"></a>Loader支持文件服务器中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084972_ul58690360172119"></a><a name="zh-cn_topic_0071084972_ul58690360172119"></a><ul id="zh-cn_topic_0071084972_ul58690360172119"><li><span id="zh-cn_topic_0071084972_ph990616311052"><a name="zh-cn_topic_0071084972_ph990616311052"></a><a name="zh-cn_topic_0071084972_ph990616311052"></a>CSV</span>_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row33694229172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p9386348172047"><a name="zh-cn_topic_0071084972_p9386348172047"></a><a name="zh-cn_topic_0071084972_p9386348172047"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p18362654172136"><a name="zh-cn_topic_0071084972_p18362654172136"></a><a name="zh-cn_topic_0071084972_p18362654172136"></a>源数据的每行结束标识字符。</p>
<div class="note" id="zh-cn_topic_0071084972_note51582238201935"><a name="zh-cn_topic_0071084972_note51582238201935"></a><a name="zh-cn_topic_0071084972_note51582238201935"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084972_p61586959201935"><a name="zh-cn_topic_0071084972_p61586959201935"></a><a name="zh-cn_topic_0071084972_p61586959201935"></a>ftp或sftp作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row35639873172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p8175384172047"><a name="zh-cn_topic_0071084972_p8175384172047"></a><a name="zh-cn_topic_0071084972_p8175384172047"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p58893187172136"><a name="zh-cn_topic_0071084972_p58893187172136"></a><a name="zh-cn_topic_0071084972_p58893187172136"></a>源数据的每个字段分割标识字符。</p>
<div class="note" id="zh-cn_topic_0071084972_note3407829012150"><a name="zh-cn_topic_0071084972_note3407829012150"></a><a name="zh-cn_topic_0071084972_note3407829012150"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084972_p3826915412150"><a name="zh-cn_topic_0071084972_p3826915412150"></a><a name="zh-cn_topic_0071084972_p3826915412150"></a>ftp或sftp作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row51231420172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p25330136172047"><a name="zh-cn_topic_0071084972_p25330136172047"></a><a name="zh-cn_topic_0071084972_p25330136172047"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p60663654172136"><a name="zh-cn_topic_0071084972_p60663654172136"></a><a name="zh-cn_topic_0071084972_p60663654172136"></a>源数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row3200752171753"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p35460550172047"><a name="zh-cn_topic_0071084972_p35460550172047"></a><a name="zh-cn_topic_0071084972_p35460550172047"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="zh-cn_topic_0071084972_p38855145172039"><a name="zh-cn_topic_0071084972_p38855145172039"></a><a name="zh-cn_topic_0071084972_p38855145172039"></a>支持以下两种：<a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"></a><ul id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## hbase-connector<a name="zh-cn_topic_0071084972_section12219532172546"></a>

**表 4**  hbase-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table12422568172551"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row10280917172551"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p57226257172551"><a name="zh-cn_topic_0071084972_p57226257172551"></a><a name="zh-cn_topic_0071084972_p57226257172551"></a><strong id="zh-cn_topic_0071084972_b32393719172551"><a name="zh-cn_topic_0071084972_b32393719172551"></a><a name="zh-cn_topic_0071084972_b32393719172551"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p36013604172551"><a name="zh-cn_topic_0071084972_p36013604172551"></a><a name="zh-cn_topic_0071084972_p36013604172551"></a><strong id="zh-cn_topic_0071084972_b41257530172551"><a name="zh-cn_topic_0071084972_b41257530172551"></a><a name="zh-cn_topic_0071084972_b41257530172551"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row55192162172551"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p2504175172551"><a name="zh-cn_topic_0071084972_p2504175172551"></a><a name="zh-cn_topic_0071084972_p2504175172551"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p40386056172551"><a name="zh-cn_topic_0071084972_p40386056172551"></a><a name="zh-cn_topic_0071084972_p40386056172551"></a>源数据实际存储的HBase表。</p>
</td>
</tr>
</tbody>
</table>

## hdfs-connector<a name="zh-cn_topic_0071084972_section14809312172642"></a>

**表 5**  hdfs-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table25755291172642"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row59351504172642"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p56085095172642"><a name="zh-cn_topic_0071084972_p56085095172642"></a><a name="zh-cn_topic_0071084972_p56085095172642"></a><strong id="zh-cn_topic_0071084972_b2503780172642"><a name="zh-cn_topic_0071084972_b2503780172642"></a><a name="zh-cn_topic_0071084972_b2503780172642"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p37527214172642"><a name="zh-cn_topic_0071084972_p37527214172642"></a><a name="zh-cn_topic_0071084972_p37527214172642"></a><strong id="zh-cn_topic_0071084972_b35696603172642"><a name="zh-cn_topic_0071084972_b35696603172642"></a><a name="zh-cn_topic_0071084972_b35696603172642"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row8594243172642"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p385045217275"><a name="zh-cn_topic_0071084972_p385045217275"></a><a name="zh-cn_topic_0071084972_p385045217275"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p7234929172824"><a name="zh-cn_topic_0071084972_p7234929172824"></a><a name="zh-cn_topic_0071084972_p7234929172824"></a>源数据实际存储的形态，可能是HDFS包含一个目录中的全部数据文件，或者是单个数据文件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row14603710172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p1116179417275"><a name="zh-cn_topic_0071084972_p1116179417275"></a><a name="zh-cn_topic_0071084972_p1116179417275"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p7296441172824"><a name="zh-cn_topic_0071084972_p7296441172824"></a><a name="zh-cn_topic_0071084972_p7296441172824"></a>Loader支持HDFS中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084972_ul16217734172824"></a><a name="zh-cn_topic_0071084972_ul16217734172824"></a><ul id="zh-cn_topic_0071084972_ul16217734172824"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row637397172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p3617915217275"><a name="zh-cn_topic_0071084972_p3617915217275"></a><a name="zh-cn_topic_0071084972_p3617915217275"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p65283279172824"><a name="zh-cn_topic_0071084972_p65283279172824"></a><a name="zh-cn_topic_0071084972_p65283279172824"></a>源数据的每行结束标识字符。</p>
<div class="note" id="zh-cn_topic_0071084972_note1318912018034"><a name="zh-cn_topic_0071084972_note1318912018034"></a><a name="zh-cn_topic_0071084972_note1318912018034"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084972_p5159321918034"><a name="zh-cn_topic_0071084972_p5159321918034"></a><a name="zh-cn_topic_0071084972_p5159321918034"></a>hdfs作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row30557070172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p5196810817275"><a name="zh-cn_topic_0071084972_p5196810817275"></a><a name="zh-cn_topic_0071084972_p5196810817275"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p50988175172824"><a name="zh-cn_topic_0071084972_p50988175172824"></a><a name="zh-cn_topic_0071084972_p50988175172824"></a>源数据的每个字段分割标识字符。</p>
<div class="note" id="zh-cn_topic_0071084972_note39941508121435"><a name="zh-cn_topic_0071084972_note39941508121435"></a><a name="zh-cn_topic_0071084972_note39941508121435"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084972_p23929257121435"><a name="zh-cn_topic_0071084972_p23929257121435"></a><a name="zh-cn_topic_0071084972_p23929257121435"></a>hdfs作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row39969862172656"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p1944259117275"><a name="zh-cn_topic_0071084972_p1944259117275"></a><a name="zh-cn_topic_0071084972_p1944259117275"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="zh-cn_topic_0071084972_p23212247172656"><a name="zh-cn_topic_0071084972_p23212247172656"></a><a name="zh-cn_topic_0071084972_p23212247172656"></a>支持以下两种：<a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785_1"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785_1"></a><ul id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785_1"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128_1"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128_1"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128_1"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121_1"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121_1"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121_1"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## hive-connector<a name="zh-cn_topic_0071084972_section9153511111751"></a>

**表 6**  hive-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table3236963111751"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row53393631111751"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p29916860111751"><a name="zh-cn_topic_0071084972_p29916860111751"></a><a name="zh-cn_topic_0071084972_p29916860111751"></a><strong id="zh-cn_topic_0071084972_b816290111751"><a name="zh-cn_topic_0071084972_b816290111751"></a><a name="zh-cn_topic_0071084972_b816290111751"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p66119529111751"><a name="zh-cn_topic_0071084972_p66119529111751"></a><a name="zh-cn_topic_0071084972_p66119529111751"></a><strong id="zh-cn_topic_0071084972_b58204852111751"><a name="zh-cn_topic_0071084972_b58204852111751"></a><a name="zh-cn_topic_0071084972_b58204852111751"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row9817386111751"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p57010763111751"><a name="zh-cn_topic_0071084972_p57010763111751"></a><a name="zh-cn_topic_0071084972_p57010763111751"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p54469085111751"><a name="zh-cn_topic_0071084972_p54469085111751"></a><a name="zh-cn_topic_0071084972_p54469085111751"></a>数据源的Hive数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row20459719111751"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p46624581111751"><a name="zh-cn_topic_0071084972_p46624581111751"></a><a name="zh-cn_topic_0071084972_p46624581111751"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p5159915511205"><a name="zh-cn_topic_0071084972_p5159915511205"></a><a name="zh-cn_topic_0071084972_p5159915511205"></a>数据源的Hive表名称，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

## voltdb-connector<a name="zh-cn_topic_0071084972_section36548053172948"></a>

**表 7**  voltdb-connector数据源连接属性

<a name="zh-cn_topic_0071084972_table53417707172948"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084972_row38145227172948"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084972_p50270734172948"><a name="zh-cn_topic_0071084972_p50270734172948"></a><a name="zh-cn_topic_0071084972_p50270734172948"></a><strong id="zh-cn_topic_0071084972_b45153969172948"><a name="zh-cn_topic_0071084972_b45153969172948"></a><a name="zh-cn_topic_0071084972_b45153969172948"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084972_p21245121172948"><a name="zh-cn_topic_0071084972_p21245121172948"></a><a name="zh-cn_topic_0071084972_p21245121172948"></a><strong id="zh-cn_topic_0071084972_b61004868172948"><a name="zh-cn_topic_0071084972_b61004868172948"></a><a name="zh-cn_topic_0071084972_b61004868172948"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084972_row64509191173017"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p7847995173017"><a name="zh-cn_topic_0071084972_p7847995173017"></a><a name="zh-cn_topic_0071084972_p7847995173017"></a><span id="zh-cn_topic_0071084972_ph6481474411442"><a name="zh-cn_topic_0071084972_ph6481474411442"></a><a name="zh-cn_topic_0071084972_ph6481474411442"></a>抽取分区字段</span></p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p61889546173017"><a name="zh-cn_topic_0071084972_p61889546173017"></a><a name="zh-cn_topic_0071084972_p61889546173017"></a><span id="zh-cn_topic_0071084972_ph4078776111458"><a name="zh-cn_topic_0071084972_ph4078776111458"></a><a name="zh-cn_topic_0071084972_ph4078776111458"></a>分区字段，如果需读取多个字段，使用该字段分割结果并获取数据。</span></p>
</td>
</tr>
<tr id="zh-cn_topic_0071084972_row56267396172948"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p53550804172948"><a name="zh-cn_topic_0071084972_p53550804172948"></a><a name="zh-cn_topic_0071084972_p53550804172948"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p21961666172948"><a name="zh-cn_topic_0071084972_p21961666172948"></a><a name="zh-cn_topic_0071084972_p21961666172948"></a>源数据实际存储的内存数据库表，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

