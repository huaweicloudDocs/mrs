# CarbonData表简介<a name="ZH-CN_TOPIC_0057181208"></a>

## 简介<a name="zh-cn_topic_0056202762_section10564877163422"></a>

CarbonData表与RDBMS中的表类似，RDBMS数据存储在由行和列构成的表中。CarbonData表存储的也是结构化的数据，具有固定列和数据类型。CarbonData中的数据存储在表实体文件中。

## 支持的数据类型<a name="zh-cn_topic_0056202762_section43723840163430"></a>

CarbonData表支持以下数据类型：

-   Int
-   String
-   BigInt
-   Decimal
-   Double
-   TimeStamp

[表1](#zh-cn_topic_0056202762_table30592799163514)对所支持的数据类型和对应的范围进行了详细说明。

**表 1**  CarbonData数据类型

<a name="zh-cn_topic_0056202762_table30592799163514"></a>
<table><thead align="left"><tr id="zh-cn_topic_0056202762_row4946593163514"><th class="cellrowborder" valign="top" width="17.86%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0056202762_p51209983163529"><a name="zh-cn_topic_0056202762_p51209983163529"></a><a name="zh-cn_topic_0056202762_p51209983163529"></a><strong id="zh-cn_topic_0056202762_b58236667163529"><a name="zh-cn_topic_0056202762_b58236667163529"></a><a name="zh-cn_topic_0056202762_b58236667163529"></a>数据类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="82.14%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0056202762_p19549566163529"><a name="zh-cn_topic_0056202762_p19549566163529"></a><a name="zh-cn_topic_0056202762_p19549566163529"></a><strong id="zh-cn_topic_0056202762_b1317771721719"><a name="zh-cn_topic_0056202762_b1317771721719"></a><a name="zh-cn_topic_0056202762_b1317771721719"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0056202762_row34168359163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p42761489163529"><a name="zh-cn_topic_0056202762_p42761489163529"></a><a name="zh-cn_topic_0056202762_p42761489163529"></a>Int</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p41128552163529"><a name="zh-cn_topic_0056202762_p41128552163529"></a><a name="zh-cn_topic_0056202762_p41128552163529"></a>4字节有符号整数，从-2,147,483,648到2,147,483,647。</p>
<div class="note" id="zh-cn_topic_0056202762_note34017188163551"><a name="zh-cn_topic_0056202762_note34017188163551"></a><a name="zh-cn_topic_0056202762_note34017188163551"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0056202762_p37719241163551"><a name="zh-cn_topic_0056202762_p37719241163551"></a><a name="zh-cn_topic_0056202762_p37719241163551"></a>非字典列如果是Int类型，会在内部存储为BigInt类型。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0056202762_row46584929163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p64341018163529"><a name="zh-cn_topic_0056202762_p64341018163529"></a><a name="zh-cn_topic_0056202762_p64341018163529"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p44239936163529"><a name="zh-cn_topic_0056202762_p44239936163529"></a><a name="zh-cn_topic_0056202762_p44239936163529"></a>最大支持字符长度为100000。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202762_row1146502163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p38658978163529"><a name="zh-cn_topic_0056202762_p38658978163529"></a><a name="zh-cn_topic_0056202762_p38658978163529"></a>BigInt</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p44369517163529"><a name="zh-cn_topic_0056202762_p44369517163529"></a><a name="zh-cn_topic_0056202762_p44369517163529"></a>使用64-bit存储数据，支持从-9,223,372,036,854,775,808到9,223,372,036,854,775,807。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202762_row54105165163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p66014447163529"><a name="zh-cn_topic_0056202762_p66014447163529"></a><a name="zh-cn_topic_0056202762_p66014447163529"></a>Decimal</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p45569960163529"><a name="zh-cn_topic_0056202762_p45569960163529"></a><a name="zh-cn_topic_0056202762_p45569960163529"></a>默认值是(10,0)，最大值是(38,38)</p>
<div class="note" id="zh-cn_topic_0056202762_note390102163536"><a name="zh-cn_topic_0056202762_note390102163536"></a><a name="zh-cn_topic_0056202762_note390102163536"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0056202762_p3510922163536"><a name="zh-cn_topic_0056202762_p3510922163536"></a><a name="zh-cn_topic_0056202762_p3510922163536"></a>当进行带过滤条件的查询时，为了得到准确的结果，需要在数字后面加上BD。例如，<strong id="zh-cn_topic_0056202762_b5248331917280"><a name="zh-cn_topic_0056202762_b5248331917280"></a><a name="zh-cn_topic_0056202762_b5248331917280"></a>select * from carbon_table where num =  1234567890123456.22BD</strong>。</p>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0056202762_row4225586163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p35152293163529"><a name="zh-cn_topic_0056202762_p35152293163529"></a><a name="zh-cn_topic_0056202762_p35152293163529"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p28763504163529"><a name="zh-cn_topic_0056202762_p28763504163529"></a><a name="zh-cn_topic_0056202762_p28763504163529"></a>使用64-bit存储数据，从4.9E-324到1.7976931348623157E308。</p>
</td>
</tr>
<tr id="zh-cn_topic_0056202762_row5887162163514"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202762_p30629316163529"><a name="zh-cn_topic_0056202762_p30629316163529"></a><a name="zh-cn_topic_0056202762_p30629316163529"></a>TimeStamp</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0056202762_p65055527163529"><a name="zh-cn_topic_0056202762_p65055527163529"></a><a name="zh-cn_topic_0056202762_p65055527163529"></a>默认格式为“yyyy-MM-dd HH:mm:ss”。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>所有integer类型度量均以BigInt类型进行处理与显示。  

