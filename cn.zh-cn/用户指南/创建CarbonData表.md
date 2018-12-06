# 创建CarbonData表<a name="ZH-CN_TOPIC_0057181209"></a>

## 操作场景<a name="zh-cn_topic_0056202763_section40834979163611"></a>

使用CarbonData前需先创建表，才可从表中加载数据和查询数据。

## 使用自定义列创建表<a name="zh-cn_topic_0056202763_section44893448163621"></a>

可通过指定各列及其数据类型来创建表。启用Kerberos认证的分析集群创建CarbonData表时，如果用户需要在默认数据库“default“以外的数据库创建新表，则需要在Hive角色管理中为用户绑定的角色添加指定数据库的“Create“权限。

命令示例：

**CREATE TABLE** **IF NOT EXISTS productdb.productSalesTable \(**

**productNumber Int,**

**productName String,**

**storeCity String,**

**storeProvince String,**

**revenue Int\)**

**STORED BY** _'_**org.apache.carbondata.format'**

**TBLPROPERTIES \(**

**'table\_blocksize'='128',**

**'DICTIONARY\_EXCLUDE'='productName',**

**'DICTIONARY\_INCLUDE'='productNumber'\);**

上述命令所创建的表的详细信息如下：

**表 1**  表信息定义

<a name="zh-cn_topic_0056202763_table12346762163739"></a>
<table><thead align="left"><tr id="zh-cn_topic_0056202763_row6757756163739"><th class="cellrowborder" valign="top" width="29.32%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0056202763_p13229816163756"><a name="zh-cn_topic_0056202763_p13229816163756"></a><a name="zh-cn_topic_0056202763_p13229816163756"></a><strong id="zh-cn_topic_0056202763_b67018665213228"><a name="zh-cn_topic_0056202763_b67018665213228"></a><a name="zh-cn_topic_0056202763_b67018665213228"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="70.67999999999999%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0056202763_p64982208163756"><a name="zh-cn_topic_0056202763_p64982208163756"></a><a name="zh-cn_topic_0056202763_p64982208163756"></a><strong id="zh-cn_topic_0056202763_b59802773213228"><a name="zh-cn_topic_0056202763_b59802773213228"></a><a name="zh-cn_topic_0056202763_b59802773213228"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0056202763_row18257003163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p5655656163756"><a name="zh-cn_topic_0056202763_p5655656163756"></a><a name="zh-cn_topic_0056202763_p5655656163756"></a>productSalesTable</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p55455001163756"><a name="zh-cn_topic_0056202763_p55455001163756"></a><a name="zh-cn_topic_0056202763_p55455001163756"></a>待创建的表的名称。该表用于加载数据进行分析。</p>
<p id="zh-cn_topic_0056202763_p29332965163756"><a name="zh-cn_topic_0056202763_p29332965163756"></a><a name="zh-cn_topic_0056202763_p29332965163756"></a>表名由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202763_row21018639163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p43113212163756"><a name="zh-cn_topic_0056202763_p43113212163756"></a><a name="zh-cn_topic_0056202763_p43113212163756"></a>productdb</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p2509311163756"><a name="zh-cn_topic_0056202763_p2509311163756"></a><a name="zh-cn_topic_0056202763_p2509311163756"></a>数据库名称。该数据库将与其中的表保持逻辑连接以便于识别和管理。</p>
<p id="zh-cn_topic_0056202763_p22583801163756"><a name="zh-cn_topic_0056202763_p22583801163756"></a><a name="zh-cn_topic_0056202763_p22583801163756"></a>数据库名称由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202763_row18335278163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p612995833313"><a name="zh-cn_topic_0056202763_p612995833313"></a><a name="zh-cn_topic_0056202763_p612995833313"></a>productNumber</p>
<p id="zh-cn_topic_0056202763_p21919341163756"><a name="zh-cn_topic_0056202763_p21919341163756"></a><a name="zh-cn_topic_0056202763_p21919341163756"></a>productName</p>
<p id="zh-cn_topic_0056202763_p63056345163756"><a name="zh-cn_topic_0056202763_p63056345163756"></a><a name="zh-cn_topic_0056202763_p63056345163756"></a>storeCity</p>
<p id="zh-cn_topic_0056202763_p30636201163756"><a name="zh-cn_topic_0056202763_p30636201163756"></a><a name="zh-cn_topic_0056202763_p30636201163756"></a>storeProvince</p>
<p id="zh-cn_topic_0056202763_p13070066163756"><a name="zh-cn_topic_0056202763_p13070066163756"></a><a name="zh-cn_topic_0056202763_p13070066163756"></a>revenue</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p52042448163756"><a name="zh-cn_topic_0056202763_p52042448163756"></a><a name="zh-cn_topic_0056202763_p52042448163756"></a>表中的列，代表执行分析所需的业务实体。</p>
<p id="zh-cn_topic_0056202763_p65728849163756"><a name="zh-cn_topic_0056202763_p65728849163756"></a><a name="zh-cn_topic_0056202763_p65728849163756"></a>列名（字段名）由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202763_row12539819163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p602436163756"><a name="zh-cn_topic_0056202763_p602436163756"></a><a name="zh-cn_topic_0056202763_p602436163756"></a>table_blocksize</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p48797355163756"><a name="zh-cn_topic_0056202763_p48797355163756"></a><a name="zh-cn_topic_0056202763_p48797355163756"></a>CarbonData表使用的数据文件的block大小，默认值为1024，取值范围为1～2048，单位为MB。</p>
<a name="zh-cn_topic_0056202763_ul1659707173646"></a><a name="zh-cn_topic_0056202763_ul1659707173646"></a><ul id="zh-cn_topic_0056202763_ul1659707173646"><li>如果“table_blocksize”值太小，数据加载时将生成过多的小数据文件，可能会影响HDFS的使用性能。</li><li>如果“table_blocksize”值太大，数据查询时索引匹配的block数据量较大，导致读取并发度不高，从而降低查询性能。</li></ul>
<p id="zh-cn_topic_0056202763_p5574161163756"><a name="zh-cn_topic_0056202763_p5574161163756"></a><a name="zh-cn_topic_0056202763_p5574161163756"></a>一般情况下，建议根据数据量级别来选择大小。例如：GB级别用256，TB级别用512，PB级别用1024。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202763_row51714485163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p37031667163756"><a name="zh-cn_topic_0056202763_p37031667163756"></a><a name="zh-cn_topic_0056202763_p37031667163756"></a>DICTIONARY_EXCLUDE</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p21862749174044"><a name="zh-cn_topic_0056202763_p21862749174044"></a><a name="zh-cn_topic_0056202763_p21862749174044"></a>设置指定列不生成字典，适用于数值复杂度高的列。系统默认为string类型的列做字典编码，但是如果字典值过多，会导致字典转换操作增加造成性能下降。</p>
<p id="zh-cn_topic_0056202763_p46775020163756"><a name="zh-cn_topic_0056202763_p46775020163756"></a><a name="zh-cn_topic_0056202763_p46775020163756"></a>一般情况下，列的数值复杂度高于5万，可以被认定为高复杂度，则需要排除掉字典编码，该参数为可选参数。</p>
<div class="note" id="zh-cn_topic_0056202763_note6533473163814"><a name="zh-cn_topic_0056202763_note6533473163814"></a><a name="zh-cn_topic_0056202763_note6533473163814"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0056202763_p58801264163814"><a name="zh-cn_topic_0056202763_p58801264163814"></a><a name="zh-cn_topic_0056202763_p58801264163814"></a>在非字典列中，只支持String和Timestamp数据类型。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0056202763_row34000127163739"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p18641369163756"><a name="zh-cn_topic_0056202763_p18641369163756"></a><a name="zh-cn_topic_0056202763_p18641369163756"></a>DICTIONARY_INCLUDE</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202763_p33555959163756"><a name="zh-cn_topic_0056202763_p33555959163756"></a><a name="zh-cn_topic_0056202763_p33555959163756"></a>设置指定列生成字典，适用于数值复杂度低的列，可以提升字典列上的<strong id="zh-cn_topic_0056202763_b7999246173921"><a name="zh-cn_topic_0056202763_b7999246173921"></a><a name="zh-cn_topic_0056202763_b7999246173921"></a>groupby</strong>性能，为可选参数。一般情况下，字典列的复杂度不应该高于5万。</p>
</td>
</tr>
</tbody>
</table>

