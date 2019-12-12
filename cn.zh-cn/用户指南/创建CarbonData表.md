# 创建CarbonData表<a name="ZH-CN_TOPIC_0173178043"></a>

## 操作场景<a name="s04fe989cc3e44e14b13bc7fa1584c13b"></a>

使用CarbonData前需先创建表，才可从表中加载数据和查询数据。

## 使用自定义列创建表<a name="s94d4db704b464d6dba4dfc22ebbb6600"></a>

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

<a name="tdb3ba8cd1bab4fdcb0a0da845c4f5f51"></a>
<table><thead align="left"><tr id="r59952bcf5d084fadb741934035455513"><th class="cellrowborder" valign="top" width="29.32%" id="mcps1.2.3.1.1"><p id="add7e7f04c2e64ee095458338f1de915c"><a name="add7e7f04c2e64ee095458338f1de915c"></a><a name="add7e7f04c2e64ee095458338f1de915c"></a><strong id="a526046f5206e4fdf857da365da958842"><a name="a526046f5206e4fdf857da365da958842"></a><a name="a526046f5206e4fdf857da365da958842"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="70.67999999999999%" id="mcps1.2.3.1.2"><p id="a8c45041613794ccc8f5df3510b7a651f"><a name="a8c45041613794ccc8f5df3510b7a651f"></a><a name="a8c45041613794ccc8f5df3510b7a651f"></a><strong id="ab5884260115a4fc3be7e6de8fcc2d8fa"><a name="ab5884260115a4fc3be7e6de8fcc2d8fa"></a><a name="ab5884260115a4fc3be7e6de8fcc2d8fa"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r55a8ee59077444a98114003627556cec"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="ad66c651acc6d442597cf1604f54183f8"><a name="ad66c651acc6d442597cf1604f54183f8"></a><a name="ad66c651acc6d442597cf1604f54183f8"></a>productSalesTable</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="a5f0b744c1b214e069b3229cc592eeee8"><a name="a5f0b744c1b214e069b3229cc592eeee8"></a><a name="a5f0b744c1b214e069b3229cc592eeee8"></a>待创建的表的名称。该表用于加载数据进行分析。</p>
<p id="a67b8521959c545cc9dc890e876a4970c"><a name="a67b8521959c545cc9dc890e876a4970c"></a><a name="a67b8521959c545cc9dc890e876a4970c"></a>表名由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="r7dd40895e5de451fa625520247f510e9"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="ac5fdbe998dc44807b99b66e75a5164c3"><a name="ac5fdbe998dc44807b99b66e75a5164c3"></a><a name="ac5fdbe998dc44807b99b66e75a5164c3"></a>productdb</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="ae651ec505a8c41fb9d634294fd7afd13"><a name="ae651ec505a8c41fb9d634294fd7afd13"></a><a name="ae651ec505a8c41fb9d634294fd7afd13"></a>数据库名称。该数据库将与其中的表保持逻辑连接以便于识别和管理。</p>
<p id="af51a69c7c7e242c2b984062949a2bbff"><a name="af51a69c7c7e242c2b984062949a2bbff"></a><a name="af51a69c7c7e242c2b984062949a2bbff"></a>数据库名称由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="r206baa4d82ae4b108f3f2e12de72a8cf"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p612995833313"><a name="zh-cn_topic_0056202763_p612995833313"></a><a name="zh-cn_topic_0056202763_p612995833313"></a>productNumber</p>
<p id="a823644c53de64c739f9dbff45238aa71"><a name="a823644c53de64c739f9dbff45238aa71"></a><a name="a823644c53de64c739f9dbff45238aa71"></a>productName</p>
<p id="a9483e634d8f54ed9a41d4cf044107de5"><a name="a9483e634d8f54ed9a41d4cf044107de5"></a><a name="a9483e634d8f54ed9a41d4cf044107de5"></a>storeCity</p>
<p id="af317714a9b9847e8b9dd0fa057343ae2"><a name="af317714a9b9847e8b9dd0fa057343ae2"></a><a name="af317714a9b9847e8b9dd0fa057343ae2"></a>storeProvince</p>
<p id="a805ac63767704dd5ad31d945e5742c83"><a name="a805ac63767704dd5ad31d945e5742c83"></a><a name="a805ac63767704dd5ad31d945e5742c83"></a>revenue</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="aa9525d1ef0334c7bb5eaee1a21a66f8c"><a name="aa9525d1ef0334c7bb5eaee1a21a66f8c"></a><a name="aa9525d1ef0334c7bb5eaee1a21a66f8c"></a>表中的列，代表执行分析所需的业务实体。</p>
<p id="ad05b218e43fd4776a001a63d6f1ffd5c"><a name="ad05b218e43fd4776a001a63d6f1ffd5c"></a><a name="ad05b218e43fd4776a001a63d6f1ffd5c"></a>列名（字段名）由字母、数字、下划线组成。</p>
</td>
</tr>
<tr id="r2ae65d69ffd547ce99cf800438a5d65b"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0056202763_p602436163756"><a name="zh-cn_topic_0056202763_p602436163756"></a><a name="zh-cn_topic_0056202763_p602436163756"></a>table_blocksize</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="ae8a81772a89e44f09cf1bd2206179f9f"><a name="ae8a81772a89e44f09cf1bd2206179f9f"></a><a name="ae8a81772a89e44f09cf1bd2206179f9f"></a>CarbonData表使用的数据文件的block大小，默认值为1024，取值范围为1～2048，单位为MB。</p>
<a name="u109abaceaf8c4fbaa9ffc1b98510aef2"></a><a name="u109abaceaf8c4fbaa9ffc1b98510aef2"></a><ul id="u109abaceaf8c4fbaa9ffc1b98510aef2"><li>如果“table_blocksize”值太小，数据加载时将生成过多的小数据文件，可能会影响HDFS的使用性能。</li><li>如果“table_blocksize”值太大，数据查询时索引匹配的block数据量较大，导致读取并发度不高，从而降低查询性能。</li></ul>
<p id="adc72ed51abe64a059e4e87a66c353b31"><a name="adc72ed51abe64a059e4e87a66c353b31"></a><a name="adc72ed51abe64a059e4e87a66c353b31"></a>一般情况下，建议根据数据量级别来选择大小。例如：GB级别用256，TB级别用512，PB级别用1024。</p>
</td>
</tr>
<tr id="r4b77ff362bed41d3a0967e7e3dc05a52"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="a2134a14aaab24cfe8440d5f758cf2f4c"><a name="a2134a14aaab24cfe8440d5f758cf2f4c"></a><a name="a2134a14aaab24cfe8440d5f758cf2f4c"></a>DICTIONARY_EXCLUDE</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="a5e449955b1fe48b0ae209a88dd5be1ae"><a name="a5e449955b1fe48b0ae209a88dd5be1ae"></a><a name="a5e449955b1fe48b0ae209a88dd5be1ae"></a>设置指定列不生成字典，适用于数值复杂度高的列。系统默认为string类型的列做字典编码，但是如果字典值过多，会导致字典转换操作增加造成性能下降。</p>
<p id="a888378f915f54cb2af4b201482ff6daf"><a name="a888378f915f54cb2af4b201482ff6daf"></a><a name="a888378f915f54cb2af4b201482ff6daf"></a>一般情况下，列的数值复杂度高于5万，可以被认定为高复杂度，则需要排除掉字典编码，该参数为可选参数。</p>
<div class="note" id="nc292433cf7994dcbbe4c010fa31c2bc2"><a name="nc292433cf7994dcbbe4c010fa31c2bc2"></a><a name="nc292433cf7994dcbbe4c010fa31c2bc2"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a75f7557253fd44cabdb3ae917734c5a9"><a name="a75f7557253fd44cabdb3ae917734c5a9"></a><a name="a75f7557253fd44cabdb3ae917734c5a9"></a>在非字典列中，只支持String和Timestamp数据类型。</p>
</div></div>
</td>
</tr>
<tr id="r63bef83b23d94048b9c8d11ca8f14929"><td class="cellrowborder" valign="top" width="29.32%" headers="mcps1.2.3.1.1 "><p id="a299200c13660457ea4ed18fcfb6ca7a1"><a name="a299200c13660457ea4ed18fcfb6ca7a1"></a><a name="a299200c13660457ea4ed18fcfb6ca7a1"></a>DICTIONARY_INCLUDE</p>
</td>
<td class="cellrowborder" valign="top" width="70.67999999999999%" headers="mcps1.2.3.1.2 "><p id="a0d526d7d713a44da91a9127b169fd53e"><a name="a0d526d7d713a44da91a9127b169fd53e"></a><a name="a0d526d7d713a44da91a9127b169fd53e"></a>设置指定列生成字典，适用于数值复杂度低的列，可以提升字典列上的<strong id="a882237625b93435daa8b89f8e6726fb5"><a name="a882237625b93435daa8b89f8e6726fb5"></a><a name="a882237625b93435daa8b89f8e6726fb5"></a>groupby</strong>性能，为可选参数。一般情况下，字典列的复杂度不应该高于5万。</p>
</td>
</tr>
</tbody>
</table>

