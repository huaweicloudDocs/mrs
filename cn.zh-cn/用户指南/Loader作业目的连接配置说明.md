# Loader作业目的连接配置说明<a name="ZH-CN_TOPIC_0071958196"></a>

## 基本介绍<a name="zh-cn_topic_0071084973_zh-cn_topic_0038340298_section35878706173614"></a>

Loader作业需要将数据保存到不同目的存储位置时，应该选择对应类型的目的连接，每种连接在该场景中需要配置连接的属性。

## obs-connector<a name="zh-cn_topic_0071084973_section19798241165732"></a>

**表 1**  obs-connector目的连接属性

<a name="zh-cn_topic_0071084973_table47534913165858"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row66371858165858"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p6548005165858"><a name="zh-cn_topic_0071084973_p6548005165858"></a><a name="zh-cn_topic_0071084973_p6548005165858"></a><strong id="zh-cn_topic_0071084973_b52923339165858"><a name="zh-cn_topic_0071084973_b52923339165858"></a><a name="zh-cn_topic_0071084973_b52923339165858"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p15732486165858"><a name="zh-cn_topic_0071084973_p15732486165858"></a><a name="zh-cn_topic_0071084973_p15732486165858"></a><strong id="zh-cn_topic_0071084973_b37214310155229"><a name="zh-cn_topic_0071084973_b37214310155229"></a><a name="zh-cn_topic_0071084973_b37214310155229"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row48350712175514"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p32261596175514"><a name="zh-cn_topic_0071084973_p32261596175514"></a><a name="zh-cn_topic_0071084973_p32261596175514"></a>桶名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p20953428175514"><a name="zh-cn_topic_0071084973_p20953428175514"></a><a name="zh-cn_topic_0071084973_p20953428175514"></a>保存最终数据的OBS桶。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row60451203165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p24790973165858"><a name="zh-cn_topic_0071084973_p24790973165858"></a><a name="zh-cn_topic_0071084973_p24790973165858"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p48799571165858"><a name="zh-cn_topic_0071084973_p48799571165858"></a><a name="zh-cn_topic_0071084973_p48799571165858"></a>最终数据在桶保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row41600313165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p15299979175527"><a name="zh-cn_topic_0071084973_p15299979175527"></a><a name="zh-cn_topic_0071084973_p15299979175527"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p14053896175527"><a name="zh-cn_topic_0071084973_p14053896175527"></a><a name="zh-cn_topic_0071084973_p14053896175527"></a>Loader支持OBS中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084973_ul53730545175527"></a><a name="zh-cn_topic_0071084973_ul53730545175527"></a><ul id="zh-cn_topic_0071084973_ul53730545175527"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row61443009165858"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p42617954175527"><a name="zh-cn_topic_0071084973_p42617954175527"></a><a name="zh-cn_topic_0071084973_p42617954175527"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p19249732175527"><a name="zh-cn_topic_0071084973_p19249732175527"></a><a name="zh-cn_topic_0071084973_p19249732175527"></a>最终数据的每行结束标识字符。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row2610221317611"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p45652901175527"><a name="zh-cn_topic_0071084973_p45652901175527"></a><a name="zh-cn_topic_0071084973_p45652901175527"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p2148810175527"><a name="zh-cn_topic_0071084973_p2148810175527"></a><a name="zh-cn_topic_0071084973_p2148810175527"></a>最终数据的每个字段分割标识字符。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row4220377717611"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p9777027175527"><a name="zh-cn_topic_0071084973_p9777027175527"></a><a name="zh-cn_topic_0071084973_p9777027175527"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p40499551175527"><a name="zh-cn_topic_0071084973_p40499551175527"></a><a name="zh-cn_topic_0071084973_p40499551175527"></a>最终数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
</tbody>
</table>

## generic-jdbc-connector<a name="zh-cn_topic_0071084973_section22577605171229"></a>

**表 2**  generic-jdbc-connector目的连接属性

<a name="zh-cn_topic_0071084973_table3633668171234"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row49651228171234"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p33247043171234"><a name="zh-cn_topic_0071084973_p33247043171234"></a><a name="zh-cn_topic_0071084973_p33247043171234"></a><strong id="zh-cn_topic_0071084973_b7426418171234"><a name="zh-cn_topic_0071084973_b7426418171234"></a><a name="zh-cn_topic_0071084973_b7426418171234"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p35893585171234"><a name="zh-cn_topic_0071084973_p35893585171234"></a><a name="zh-cn_topic_0071084973_p35893585171234"></a><strong id="zh-cn_topic_0071084973_b31055900171234"><a name="zh-cn_topic_0071084973_b31055900171234"></a><a name="zh-cn_topic_0071084973_b31055900171234"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row33950906171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p48702080171246"><a name="zh-cn_topic_0071084973_p48702080171246"></a><a name="zh-cn_topic_0071084973_p48702080171246"></a>模式名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p50704670175348"><a name="zh-cn_topic_0071084973_p50704670175348"></a><a name="zh-cn_topic_0071084973_p50704670175348"></a>保存最终数据的数据库名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row17988209171234"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p44342240171246"><a name="zh-cn_topic_0071084973_p44342240171246"></a><a name="zh-cn_topic_0071084973_p44342240171246"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p8487979175348"><a name="zh-cn_topic_0071084973_p8487979175348"></a><a name="zh-cn_topic_0071084973_p8487979175348"></a>保存最终数据的数据表名称。</p>
</td>
</tr>
</tbody>
</table>

## ftp-connector或sftp-connector<a name="zh-cn_topic_0071084973_section64895548171739"></a>

**表 3**  ftp-connector或sftp-connector目的连接属性

<a name="zh-cn_topic_0071084973_table62801247171753"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row19753839171753"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p48044734171753"><a name="zh-cn_topic_0071084973_p48044734171753"></a><a name="zh-cn_topic_0071084973_p48044734171753"></a><strong id="zh-cn_topic_0071084973_b57270601171753"><a name="zh-cn_topic_0071084973_b57270601171753"></a><a name="zh-cn_topic_0071084973_b57270601171753"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p53951536171753"><a name="zh-cn_topic_0071084973_p53951536171753"></a><a name="zh-cn_topic_0071084973_p53951536171753"></a><strong id="zh-cn_topic_0071084973_b22477863171753"><a name="zh-cn_topic_0071084973_b22477863171753"></a><a name="zh-cn_topic_0071084973_b22477863171753"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row66223917171753"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p55459555172047"><a name="zh-cn_topic_0071084973_p55459555172047"></a><a name="zh-cn_topic_0071084973_p55459555172047"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p58458739175350"><a name="zh-cn_topic_0071084973_p58458739175350"></a><a name="zh-cn_topic_0071084973_p58458739175350"></a>最终数据在文件服务器保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row52058581172040"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p8729931172047"><a name="zh-cn_topic_0071084973_p8729931172047"></a><a name="zh-cn_topic_0071084973_p8729931172047"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p8890734175746"><a name="zh-cn_topic_0071084973_p8890734175746"></a><a name="zh-cn_topic_0071084973_p8890734175746"></a>Loader支持文件服务器中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084973_ul17514923175746"></a><a name="zh-cn_topic_0071084973_ul17514923175746"></a><ul id="zh-cn_topic_0071084973_ul17514923175746"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row33694229172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p9386348172047"><a name="zh-cn_topic_0071084973_p9386348172047"></a><a name="zh-cn_topic_0071084973_p9386348172047"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p19783063175746"><a name="zh-cn_topic_0071084973_p19783063175746"></a><a name="zh-cn_topic_0071084973_p19783063175746"></a>最终数据的每行结束标识字符。</p>
<div class="note" id="zh-cn_topic_0071084973_note1286808614559"><a name="zh-cn_topic_0071084973_note1286808614559"></a><a name="zh-cn_topic_0071084973_note1286808614559"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084973_p4870391314559"><a name="zh-cn_topic_0071084973_p4870391314559"></a><a name="zh-cn_topic_0071084973_p4870391314559"></a>ftp或sftp作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row35639873172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p8175384172047"><a name="zh-cn_topic_0071084973_p8175384172047"></a><a name="zh-cn_topic_0071084973_p8175384172047"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p19485559175746"><a name="zh-cn_topic_0071084973_p19485559175746"></a><a name="zh-cn_topic_0071084973_p19485559175746"></a>最终数据的每个字段分割标识字符。</p>
<div class="note" id="zh-cn_topic_0071084973_note63326504121257"><a name="zh-cn_topic_0071084973_note63326504121257"></a><a name="zh-cn_topic_0071084973_note63326504121257"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084973_p33067631121257"><a name="zh-cn_topic_0071084973_p33067631121257"></a><a name="zh-cn_topic_0071084973_p33067631121257"></a>ftp或sftp作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row51231420172041"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p25330136172047"><a name="zh-cn_topic_0071084973_p25330136172047"></a><a name="zh-cn_topic_0071084973_p25330136172047"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p52191870175746"><a name="zh-cn_topic_0071084973_p52191870175746"></a><a name="zh-cn_topic_0071084973_p52191870175746"></a>最终数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
</tbody>
</table>

## hbase-connector<a name="zh-cn_topic_0071084973_section12219532172546"></a>

**表 4**  hbase-connector目的连接属性

<a name="zh-cn_topic_0071084973_table12422568172551"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row10280917172551"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p57226257172551"><a name="zh-cn_topic_0071084973_p57226257172551"></a><a name="zh-cn_topic_0071084973_p57226257172551"></a><strong id="zh-cn_topic_0071084973_b32393719172551"><a name="zh-cn_topic_0071084973_b32393719172551"></a><a name="zh-cn_topic_0071084973_b32393719172551"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p36013604172551"><a name="zh-cn_topic_0071084973_p36013604172551"></a><a name="zh-cn_topic_0071084973_p36013604172551"></a><strong id="zh-cn_topic_0071084973_b41257530172551"><a name="zh-cn_topic_0071084973_b41257530172551"></a><a name="zh-cn_topic_0071084973_b41257530172551"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row55192162172551"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p2504175172551"><a name="zh-cn_topic_0071084973_p2504175172551"></a><a name="zh-cn_topic_0071084973_p2504175172551"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p3985918175822"><a name="zh-cn_topic_0071084973_p3985918175822"></a><a name="zh-cn_topic_0071084973_p3985918175822"></a>保存最终数据的HBase表名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row3069739317583"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p6097844717583"><a name="zh-cn_topic_0071084973_p6097844717583"></a><a name="zh-cn_topic_0071084973_p6097844717583"></a>导入方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p56528462175822"><a name="zh-cn_topic_0071084973_p56528462175822"></a><a name="zh-cn_topic_0071084973_p56528462175822"></a>支持<span id="zh-cn_topic_0071084973_ph63089002111531"><a name="zh-cn_topic_0071084973_ph63089002111531"></a><a name="zh-cn_topic_0071084973_ph63089002111531"></a>BULKLOAD</span>、<span id="zh-cn_topic_0071084973_ph29898395111548"><a name="zh-cn_topic_0071084973_ph29898395111548"></a><a name="zh-cn_topic_0071084973_ph29898395111548"></a>PUTLIST</span>两种方式导入数据到HBase表。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row3526441117583"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p4012715117583"><a name="zh-cn_topic_0071084973_p4012715117583"></a><a name="zh-cn_topic_0071084973_p4012715117583"></a>导入前清空数据</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p3632474017593"><a name="zh-cn_topic_0071084973_p3632474017593"></a><a name="zh-cn_topic_0071084973_p3632474017593"></a>标识是否需要清空目标HBase表中的数据，支持以下两种类型：</p>
<a name="zh-cn_topic_0071084973_ul27062205175915"></a><a name="zh-cn_topic_0071084973_ul27062205175915"></a><ul id="zh-cn_topic_0071084973_ul27062205175915"><li><span id="zh-cn_topic_0071084973_ph6188229511156"><a name="zh-cn_topic_0071084973_ph6188229511156"></a><a name="zh-cn_topic_0071084973_ph6188229511156"></a>T</span>rue：清空表中的数据。</li><li><span id="zh-cn_topic_0071084973_ph34357702111511"><a name="zh-cn_topic_0071084973_ph34357702111511"></a><a name="zh-cn_topic_0071084973_ph34357702111511"></a>F</span>alse：不清空表中的数据，选择<span id="zh-cn_topic_0071084973_ph58584572161644"><a name="zh-cn_topic_0071084973_ph58584572161644"></a><a name="zh-cn_topic_0071084973_ph58584572161644"></a>F</span>alse时如果表中存在数据，则作业运行会报错。</li></ul>
</td>
</tr>
</tbody>
</table>

## hdfs-connector<a name="zh-cn_topic_0071084973_section14809312172642"></a>

**表 5**  hdfs-connector目的连接属性

<a name="zh-cn_topic_0071084973_table25755291172642"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row59351504172642"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p56085095172642"><a name="zh-cn_topic_0071084973_p56085095172642"></a><a name="zh-cn_topic_0071084973_p56085095172642"></a><strong id="zh-cn_topic_0071084973_b2503780172642"><a name="zh-cn_topic_0071084973_b2503780172642"></a><a name="zh-cn_topic_0071084973_b2503780172642"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p37527214172642"><a name="zh-cn_topic_0071084973_p37527214172642"></a><a name="zh-cn_topic_0071084973_p37527214172642"></a><strong id="zh-cn_topic_0071084973_b35696603172642"><a name="zh-cn_topic_0071084973_b35696603172642"></a><a name="zh-cn_topic_0071084973_b35696603172642"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row8594243172642"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p385045217275"><a name="zh-cn_topic_0071084973_p385045217275"></a><a name="zh-cn_topic_0071084973_p385045217275"></a>写入目录</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p4115327818040"><a name="zh-cn_topic_0071084973_p4115327818040"></a><a name="zh-cn_topic_0071084973_p4115327818040"></a>最终数据在HDFS保存时的具体目录。必须指定一个目录。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row14603710172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p1116179417275"><a name="zh-cn_topic_0071084973_p1116179417275"></a><a name="zh-cn_topic_0071084973_p1116179417275"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p7296441172824"><a name="zh-cn_topic_0071084973_p7296441172824"></a><a name="zh-cn_topic_0071084973_p7296441172824"></a>Loader支持HDFS中存储数据的文件格式，默认支持以下两种：</p>
<a name="zh-cn_topic_0071084973_ul16217734172824"></a><a name="zh-cn_topic_0071084973_ul16217734172824"></a><ul id="zh-cn_topic_0071084973_ul16217734172824"><li><span id="zh-cn_topic_0071084973_ph62592937111719"><a name="zh-cn_topic_0071084973_ph62592937111719"></a><a name="zh-cn_topic_0071084973_ph62592937111719"></a>CSV</span>_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row1093303118121"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p402135418121"><a name="zh-cn_topic_0071084973_p402135418121"></a><a name="zh-cn_topic_0071084973_p402135418121"></a>压缩格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p6325487018121"><a name="zh-cn_topic_0071084973_p6325487018121"></a><a name="zh-cn_topic_0071084973_p6325487018121"></a>文件在HDFS保存时的压缩行为。支持NONE、DEFLATE、GZIP、BZIP2、LZ4<span id="zh-cn_topic_0071084973_ph1467465914453"><a name="zh-cn_topic_0071084973_ph1467465914453"></a><a name="zh-cn_topic_0071084973_ph1467465914453"></a>和</span>SNAPPY。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row5002624318216"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p5837924518216"><a name="zh-cn_topic_0071084973_p5837924518216"></a><a name="zh-cn_topic_0071084973_p5837924518216"></a>是否覆盖</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p1083725718216"><a name="zh-cn_topic_0071084973_p1083725718216"></a><a name="zh-cn_topic_0071084973_p1083725718216"></a>文件在导入HDFS时对写入目录中原有文件的处理行为，支持以下两种：</p>
<a name="zh-cn_topic_0071084973_ul976868618352"></a><a name="zh-cn_topic_0071084973_ul976868618352"></a><ul id="zh-cn_topic_0071084973_ul976868618352"><li>True：默认清空目录中的文件并导入新文件。</li><li>False：不清空文件。如果写入目录中有文件，则作业运行失败。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row637397172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p3617915217275"><a name="zh-cn_topic_0071084973_p3617915217275"></a><a name="zh-cn_topic_0071084973_p3617915217275"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p1426099417540"><a name="zh-cn_topic_0071084973_p1426099417540"></a><a name="zh-cn_topic_0071084973_p1426099417540"></a>最终数据的每行结束标识字符。</p>
<div class="note" id="zh-cn_topic_0071084973_note6502132316347"><a name="zh-cn_topic_0071084973_note6502132316347"></a><a name="zh-cn_topic_0071084973_note6502132316347"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084973_p4832099516347"><a name="zh-cn_topic_0071084973_p4832099516347"></a><a name="zh-cn_topic_0071084973_p4832099516347"></a>hdfs作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row30557070172655"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p5196810817275"><a name="zh-cn_topic_0071084973_p5196810817275"></a><a name="zh-cn_topic_0071084973_p5196810817275"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p4501580717540"><a name="zh-cn_topic_0071084973_p4501580717540"></a><a name="zh-cn_topic_0071084973_p4501580717540"></a>最终数据的每个字段分割标识字符。</p>
<div class="note" id="zh-cn_topic_0071084973_note54892332121332"><a name="zh-cn_topic_0071084973_note54892332121332"></a><a name="zh-cn_topic_0071084973_note54892332121332"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084973_p24268945121332"><a name="zh-cn_topic_0071084973_p24268945121332"></a><a name="zh-cn_topic_0071084973_p24268945121332"></a>hdfs作为目的连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## hive-connector<a name="zh-cn_topic_0071084973_section9153511111751"></a>

**表 6**  hive-connector目的连接属性

<a name="zh-cn_topic_0071084973_table3236963111751"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row53393631111751"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p29916860111751"><a name="zh-cn_topic_0071084973_p29916860111751"></a><a name="zh-cn_topic_0071084973_p29916860111751"></a><strong id="zh-cn_topic_0071084973_b816290111751"><a name="zh-cn_topic_0071084973_b816290111751"></a><a name="zh-cn_topic_0071084973_b816290111751"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p66119529111751"><a name="zh-cn_topic_0071084973_p66119529111751"></a><a name="zh-cn_topic_0071084973_p66119529111751"></a><strong id="zh-cn_topic_0071084973_b58204852111751"><a name="zh-cn_topic_0071084973_b58204852111751"></a><a name="zh-cn_topic_0071084973_b58204852111751"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row9817386111751"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p57010763111751"><a name="zh-cn_topic_0071084973_p57010763111751"></a><a name="zh-cn_topic_0071084973_p57010763111751"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p54469085111751"><a name="zh-cn_topic_0071084973_p54469085111751"></a><a name="zh-cn_topic_0071084973_p54469085111751"></a>保存最终数据的Hive数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="zh-cn_topic_0071084973_row20459719111751"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p46624581111751"><a name="zh-cn_topic_0071084973_p46624581111751"></a><a name="zh-cn_topic_0071084973_p46624581111751"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p5159915511205"><a name="zh-cn_topic_0071084973_p5159915511205"></a><a name="zh-cn_topic_0071084973_p5159915511205"></a>保存最终数据的Hive表名称，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

## voltdb-connector<a name="zh-cn_topic_0071084973_section36548053172948"></a>

**表 7**  voltdb-connector目的连接属性

<a name="zh-cn_topic_0071084973_table53417707172948"></a>
<table><thead align="left"><tr id="zh-cn_topic_0071084973_row38145227172948"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084973_p50270734172948"><a name="zh-cn_topic_0071084973_p50270734172948"></a><a name="zh-cn_topic_0071084973_p50270734172948"></a><strong id="zh-cn_topic_0071084973_b45153969172948"><a name="zh-cn_topic_0071084973_b45153969172948"></a><a name="zh-cn_topic_0071084973_b45153969172948"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084973_p21245121172948"><a name="zh-cn_topic_0071084973_p21245121172948"></a><a name="zh-cn_topic_0071084973_p21245121172948"></a><strong id="zh-cn_topic_0071084973_b61004868172948"><a name="zh-cn_topic_0071084973_b61004868172948"></a><a name="zh-cn_topic_0071084973_b61004868172948"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0071084973_row56267396172948"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084973_p53550804172948"><a name="zh-cn_topic_0071084973_p53550804172948"></a><a name="zh-cn_topic_0071084973_p53550804172948"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084973_p6495801918611"><a name="zh-cn_topic_0071084973_p6495801918611"></a><a name="zh-cn_topic_0071084973_p6495801918611"></a>保存最终数据的内存数据库表，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

