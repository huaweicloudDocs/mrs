# CarbonData表简介<a name="ZH-CN_TOPIC_0173179035"></a>

## 简介<a name="s37a167cf46534a5c86a6dd255f507313"></a>

CarbonData表与RDBMS中的表类似，RDBMS数据存储在由行和列构成的表中。CarbonData表存储的也是结构化的数据，具有固定列和数据类型。CarbonData中的数据存储在表实体文件中。

## 支持的数据类型<a name="s4d42c16cf1b345998429c2d60187f61b"></a>

CarbonData表支持以下数据类型：

-   Int
-   String
-   BigInt
-   Decimal
-   Double
-   TimeStamp

[表1](#te1b84a2aca034e4b9e5745ab6b7bb9fd)对所支持的数据类型和对应的范围进行了详细说明。

**表 1**  CarbonData数据类型

<a name="te1b84a2aca034e4b9e5745ab6b7bb9fd"></a>
<table><thead align="left"><tr id="rd3b328e62f2b4310bdef2241311e9aa0"><th class="cellrowborder" valign="top" width="17.86%" id="mcps1.2.3.1.1"><p id="aa28d1893b34e4eeaa48df18792631a86"><a name="aa28d1893b34e4eeaa48df18792631a86"></a><a name="aa28d1893b34e4eeaa48df18792631a86"></a><strong id="aff01f97dda44406f8696dc16db9755e6"><a name="aff01f97dda44406f8696dc16db9755e6"></a><a name="aff01f97dda44406f8696dc16db9755e6"></a>数据类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="82.14%" id="mcps1.2.3.1.2"><p id="a85bfd0562b2c48eb908159085edc4b2a"><a name="a85bfd0562b2c48eb908159085edc4b2a"></a><a name="a85bfd0562b2c48eb908159085edc4b2a"></a><strong id="acd837afd6a894dd38c2ed5b84054fce9"><a name="acd837afd6a894dd38c2ed5b84054fce9"></a><a name="acd837afd6a894dd38c2ed5b84054fce9"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r6ac513fe3c1349d09bd26a5604c5590f"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="a642277b4335e4f58a093239a03c99faf"><a name="a642277b4335e4f58a093239a03c99faf"></a><a name="a642277b4335e4f58a093239a03c99faf"></a>Int</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="a3b30403f1eed4272ae1aa9b51c59bc0d"><a name="a3b30403f1eed4272ae1aa9b51c59bc0d"></a><a name="a3b30403f1eed4272ae1aa9b51c59bc0d"></a>4字节有符号整数，从-2,147,483,648到2,147,483,647。</p>
<div class="note" id="n7445349efce143f592b2cad98a229a5d"><a name="n7445349efce143f592b2cad98a229a5d"></a><a name="n7445349efce143f592b2cad98a229a5d"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a6dbea4c08bf24cda85f5f62fd0ab8fab"><a name="a6dbea4c08bf24cda85f5f62fd0ab8fab"></a><a name="a6dbea4c08bf24cda85f5f62fd0ab8fab"></a>非字典列如果是Int类型，会在内部存储为BigInt类型。</p>
</div></div>
</td>
</tr>
<tr id="r6177c2e01b704ce294126970975cbc43"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="afeec3c1fd2ac4c84a7395cbb42ead7fc"><a name="afeec3c1fd2ac4c84a7395cbb42ead7fc"></a><a name="afeec3c1fd2ac4c84a7395cbb42ead7fc"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="a626dbc69aee1459aa9507338092e25c9"><a name="a626dbc69aee1459aa9507338092e25c9"></a><a name="a626dbc69aee1459aa9507338092e25c9"></a>最大支持字符长度为100000。</p>
</td>
</tr>
<tr id="r5ead914fca4b4de596d27b0f4b64e174"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="ae0a25f8a623d4deb989d6d0c3028f4a3"><a name="ae0a25f8a623d4deb989d6d0c3028f4a3"></a><a name="ae0a25f8a623d4deb989d6d0c3028f4a3"></a>BigInt</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="a07346125300442148b45db0c18bd69d2"><a name="a07346125300442148b45db0c18bd69d2"></a><a name="a07346125300442148b45db0c18bd69d2"></a>使用64-bit存储数据，支持从-9,223,372,036,854,775,808到9,223,372,036,854,775,807。</p>
</td>
</tr>
<tr id="rdda503697b19495198c30c8e0c627b4d"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="acf6443d6bd224c5fb89c21f31604eb7d"><a name="acf6443d6bd224c5fb89c21f31604eb7d"></a><a name="acf6443d6bd224c5fb89c21f31604eb7d"></a>Decimal</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="ad46da508c383488e84664641e9f4aa84"><a name="ad46da508c383488e84664641e9f4aa84"></a><a name="ad46da508c383488e84664641e9f4aa84"></a>默认值是(10,0)，最大值是(38,38)</p>
<div class="note" id="ne391f81fa0dd4db2a99fe35ca38fab0f"><a name="ne391f81fa0dd4db2a99fe35ca38fab0f"></a><a name="ne391f81fa0dd4db2a99fe35ca38fab0f"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a33e816c61afc446dbce30490a9e9411c"><a name="a33e816c61afc446dbce30490a9e9411c"></a><a name="a33e816c61afc446dbce30490a9e9411c"></a>当进行带过滤条件的查询时，为了得到准确的结果，需要在数字后面加上BD。例如，<strong id="abaac208bb93d4b05b7a8c9ee5b433c70"><a name="abaac208bb93d4b05b7a8c9ee5b433c70"></a><a name="abaac208bb93d4b05b7a8c9ee5b433c70"></a>select * from carbon_table where num =  1234567890123456.22BD</strong>。</p>
</div></div>
</td>
</tr>
<tr id="r1cdaa25b579b49f085957a2c9f17f0b6"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="a16752fb94c3e43c1a1689edc2a13b61d"><a name="a16752fb94c3e43c1a1689edc2a13b61d"></a><a name="a16752fb94c3e43c1a1689edc2a13b61d"></a>Double</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="a1d8592a7fa244b05851f90de48955904"><a name="a1d8592a7fa244b05851f90de48955904"></a><a name="a1d8592a7fa244b05851f90de48955904"></a>使用64-bit存储数据，从4.9E-324到1.7976931348623157E308。</p>
</td>
</tr>
<tr id="rd79a0af8d043482792b8cea697ace2f5"><td class="cellrowborder" valign="top" width="17.86%" headers="mcps1.2.3.1.1 "><p id="acbdeefa77b3a466cae261d060f709cd7"><a name="acbdeefa77b3a466cae261d060f709cd7"></a><a name="acbdeefa77b3a466cae261d060f709cd7"></a>TimeStamp</p>
</td>
<td class="cellrowborder" valign="top" width="82.14%" headers="mcps1.2.3.1.2 "><p id="a92b5ac6157034199bdd2ae14ebb79a93"><a name="a92b5ac6157034199bdd2ae14ebb79a93"></a><a name="a92b5ac6157034199bdd2ae14ebb79a93"></a>默认格式为“yyyy-MM-dd HH:mm:ss”。</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>所有integer类型度量均以BigInt类型进行处理与显示。  

