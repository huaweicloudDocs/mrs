# Loader作业源连接配置说明<a name="ZH-CN_TOPIC_0173178137"></a>

## 基本介绍<a name="se787b8d017e44b12aff2f6e2f1b4e627"></a>

Loader作业需要从不同数据源获取数据时，应该选择对应类型的连接，每种连接在该场景中需要配置连接的属性。

## obs-connector<a name="sdd455438f59c455d868736ad52d1097c"></a>

**表 1**  obs-connector数据源连接属性

<a name="t965be05e8bc445ceb862e8444f43702d"></a>
<table><thead align="left"><tr id="r89610f38a3bd4777bd5e9ca134b222e5"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a8072335d76834b18b0f44b7f9c2d21a1"><a name="a8072335d76834b18b0f44b7f9c2d21a1"></a><a name="a8072335d76834b18b0f44b7f9c2d21a1"></a><strong id="a86e31a65a62e446cade4a5e6152a5912"><a name="a86e31a65a62e446cade4a5e6152a5912"></a><a name="a86e31a65a62e446cade4a5e6152a5912"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="adc3b79b34b2d4c05ad3783fe1724431e"><a name="adc3b79b34b2d4c05ad3783fe1724431e"></a><a name="adc3b79b34b2d4c05ad3783fe1724431e"></a><strong id="ac981ba453e5e45a9a9a5cd645b131045"><a name="ac981ba453e5e45a9a9a5cd645b131045"></a><a name="ac981ba453e5e45a9a9a5cd645b131045"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="rf0eae9e862f14c50ad7b3ad004b45b49"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="af0e31907c16b4f3ab5df0206def965ef"><a name="af0e31907c16b4f3ab5df0206def965ef"></a><a name="af0e31907c16b4f3ab5df0206def965ef"></a>桶名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a485981e1bcdc42828eeaed6308d4a663"><a name="a485981e1bcdc42828eeaed6308d4a663"></a><a name="a485981e1bcdc42828eeaed6308d4a663"></a>保存源数据的OBS桶。</p>
</td>
</tr>
<tr id="r9e0c98cd97f549c98fd562c1fb8ce2ce"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a202f05431f8e4102ad9a9fb58f7f6e34"><a name="a202f05431f8e4102ad9a9fb58f7f6e34"></a><a name="a202f05431f8e4102ad9a9fb58f7f6e34"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a95f75beacfc5450581e99147c1f7f892"><a name="a95f75beacfc5450581e99147c1f7f892"></a><a name="a95f75beacfc5450581e99147c1f7f892"></a>源数据实际存储的形态，可能是桶包含一个目录中的全部数据文件，或者是桶包含的单个数据文件。</p>
</td>
</tr>
<tr id="rcf91c52be99d428ea9d9d0418b409504"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a49a663116b1e4a29a383fa8104f0c818"><a name="a49a663116b1e4a29a383fa8104f0c818"></a><a name="a49a663116b1e4a29a383fa8104f0c818"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a15457bb719344f6e880a4319fa42c522"><a name="a15457bb719344f6e880a4319fa42c522"></a><a name="a15457bb719344f6e880a4319fa42c522"></a>Loader支持OBS中存储数据的文件格式，默认支持以下两种：</p>
<a name="ue5bdb47f32be4b6e9883eadcc42874d5"></a><a name="ue5bdb47f32be4b6e9883eadcc42874d5"></a><ul id="ue5bdb47f32be4b6e9883eadcc42874d5"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="rc2a65a9a1f9d45a889a2b7d892065e33"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p547205051766"><a name="zh-cn_topic_0071084972_p547205051766"></a><a name="zh-cn_topic_0071084972_p547205051766"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084972_p527477181766"><a name="zh-cn_topic_0071084972_p527477181766"></a><a name="zh-cn_topic_0071084972_p527477181766"></a>源数据的每行结束标识字符。</p>
</td>
</tr>
<tr id="r2c130675a2be4d11a2ddf516de4413e3"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a06fc20d8943048638481cac86001b285"><a name="a06fc20d8943048638481cac86001b285"></a><a name="a06fc20d8943048638481cac86001b285"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a8a4d1140c3a143c7b1766f0995064d1d"><a name="a8a4d1140c3a143c7b1766f0995064d1d"></a><a name="a8a4d1140c3a143c7b1766f0995064d1d"></a>源数据的每个字段分割标识字符。</p>
</td>
</tr>
<tr id="rcde61c44288b43ac9c08c0a24cb1eea3"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a8e482078c4934372826fe1b572c9a290"><a name="a8e482078c4934372826fe1b572c9a290"></a><a name="a8e482078c4934372826fe1b572c9a290"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aad20a27929c142f7b8f3b7fd77de565f"><a name="aad20a27929c142f7b8f3b7fd77de565f"></a><a name="aad20a27929c142f7b8f3b7fd77de565f"></a>源数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
<tr id="r4b8fe32f452747bd9f0c984691398638"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p179695571766"><a name="zh-cn_topic_0071084972_p179695571766"></a><a name="zh-cn_topic_0071084972_p179695571766"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="zh-cn_topic_0071084972_p98470941766"><a name="zh-cn_topic_0071084972_p98470941766"></a><a name="zh-cn_topic_0071084972_p98470941766"></a>支持以下两种：<a name="u9354c314b2a94b48b61fb993acf15d96"></a><a name="u9354c314b2a94b48b61fb993acf15d96"></a><ul id="u9354c314b2a94b48b61fb993acf15d96"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="p7ebd23b7ae8644198a18c75f7146e115"><a name="p7ebd23b7ae8644198a18c75f7146e115"></a><a name="p7ebd23b7ae8644198a18c75f7146e115"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="p3d63f6c7f66f41f0b08a5071f9287f6a"><a name="p3d63f6c7f66f41f0b08a5071f9287f6a"></a><a name="p3d63f6c7f66f41f0b08a5071f9287f6a"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## generic-jdbc-connector<a name="sd84e31a43f93483d8f37f23ccdbb3c1e"></a>

**表 2**  generic-jdbc-connector数据源连接属性

<a name="tf66599c326bf46bb841b6a108b17321e"></a>
<table><thead align="left"><tr id="rd407a71a8db34b509b61a8d99dbc56bb"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a43d562c8796944ce94ea7e5a8b7e27da"><a name="a43d562c8796944ce94ea7e5a8b7e27da"></a><a name="a43d562c8796944ce94ea7e5a8b7e27da"></a><strong id="ac60a4149274749479042d8ce738a7272"><a name="ac60a4149274749479042d8ce738a7272"></a><a name="ac60a4149274749479042d8ce738a7272"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a792bdea57e474891b6489f864801ed05"><a name="a792bdea57e474891b6489f864801ed05"></a><a name="a792bdea57e474891b6489f864801ed05"></a><strong id="a188ba66d73504d878574d7fb8193bcf7"><a name="a188ba66d73504d878574d7fb8193bcf7"></a><a name="a188ba66d73504d878574d7fb8193bcf7"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r3cbc3267179045eea5bcb44d9260a94f"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2cc54c2a2da242c794767cfcfafbc346"><a name="a2cc54c2a2da242c794767cfcfafbc346"></a><a name="a2cc54c2a2da242c794767cfcfafbc346"></a>模式或表空间</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a99e448b09d484d3f89d2d391ac5eeac3"><a name="a99e448b09d484d3f89d2d391ac5eeac3"></a><a name="a99e448b09d484d3f89d2d391ac5eeac3"></a>表示源数据对应的数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="r6e9c2a3e9d1e4dfc93132e217e84ea7d"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a8fa190bea6bf4cf0bf8e086bbe79840e"><a name="a8fa190bea6bf4cf0bf8e086bbe79840e"></a><a name="a8fa190bea6bf4cf0bf8e086bbe79840e"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="abaaa2b7a360a4569a8b0f856f0cf02e5"><a name="abaaa2b7a360a4569a8b0f856f0cf02e5"></a><a name="abaaa2b7a360a4569a8b0f856f0cf02e5"></a>存储源数据的数据表，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="ra31516f8d3de41d2b2e350d4eb3b740c"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a8bb598fba7764f55ae931fa979fedd42"><a name="a8bb598fba7764f55ae931fa979fedd42"></a><a name="a8bb598fba7764f55ae931fa979fedd42"></a>抽取分区字段</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a9f254e46e7504c0e984e8fdd87e4e12e"><a name="a9f254e46e7504c0e984e8fdd87e4e12e"></a><a name="a9f254e46e7504c0e984e8fdd87e4e12e"></a>分区字段，如果需读取多个字段，使用该字段分割结果并获取数据。</p>
</td>
</tr>
<tr id="r58dad8320ec34e29b3280d73bd844969"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a48e8ee41ce2d4010ab5976b1c7bf5260"><a name="a48e8ee41ce2d4010ab5976b1c7bf5260"></a><a name="a48e8ee41ce2d4010ab5976b1c7bf5260"></a>Where子句</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aaa8d4660374743a492dc69465e398c6a"><a name="aaa8d4660374743a492dc69465e398c6a"></a><a name="aaa8d4660374743a492dc69465e398c6a"></a>表示读取数据库时使用的查询语句。</p>
</td>
</tr>
</tbody>
</table>

## ftp-connector或sftp-connector<a name="s033d5edc10164032b9ea23d01081beae"></a>

**表 3**  ftp-connector或sftp-connector数据源连接属性

<a name="t48b1b68e9563446d8689be9e4db828e0"></a>
<table><thead align="left"><tr id="rbac17e98fe924d9c9170415379a10b36"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a67a7341ae37a4161b65189b65b8fb3d8"><a name="a67a7341ae37a4161b65189b65b8fb3d8"></a><a name="a67a7341ae37a4161b65189b65b8fb3d8"></a><strong id="a4194d21d595346258cae3be901d74dec"><a name="a4194d21d595346258cae3be901d74dec"></a><a name="a4194d21d595346258cae3be901d74dec"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="ad08f3f4f9f924eae8e3c405db1a05f45"><a name="ad08f3f4f9f924eae8e3c405db1a05f45"></a><a name="ad08f3f4f9f924eae8e3c405db1a05f45"></a><strong id="a08276b49e18f469a8052cb88d568f892"><a name="a08276b49e18f469a8052cb88d568f892"></a><a name="a08276b49e18f469a8052cb88d568f892"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="ra42b9b35b6b741ac978f2dfe198c8651"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a36540afb5ffa49de8aa79acd1f597bfb"><a name="a36540afb5ffa49de8aa79acd1f597bfb"></a><a name="a36540afb5ffa49de8aa79acd1f597bfb"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ad6f49542380a44adac6e02a34e5d2149"><a name="ad6f49542380a44adac6e02a34e5d2149"></a><a name="ad6f49542380a44adac6e02a34e5d2149"></a>源数据实际存储的形态，可能是文件服务器包含一个目录中的全部数据文件，或者是单个数据文件。</p>
</td>
</tr>
<tr id="rd80060b048364dea95f430ef620c1045"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a464198f64d3b4357a725fe95d6b32545"><a name="a464198f64d3b4357a725fe95d6b32545"></a><a name="a464198f64d3b4357a725fe95d6b32545"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa6bfc9fcb4fd4459a74516700b94b1f5"><a name="aa6bfc9fcb4fd4459a74516700b94b1f5"></a><a name="aa6bfc9fcb4fd4459a74516700b94b1f5"></a>Loader支持文件服务器中存储数据的文件格式，默认支持以下两种：</p>
<a name="uc1fb4b67fa7a40b8802fe069c1c4a5e1"></a><a name="uc1fb4b67fa7a40b8802fe069c1c4a5e1"></a><ul id="uc1fb4b67fa7a40b8802fe069c1c4a5e1"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="r6075ad2b6e7e4aaf895d7d93651a40d3"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a39cbaf2d9d17449d9e1834255d231318"><a name="a39cbaf2d9d17449d9e1834255d231318"></a><a name="a39cbaf2d9d17449d9e1834255d231318"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a9dc23093b3b54e709a62c2aee1b183b7"><a name="a9dc23093b3b54e709a62c2aee1b183b7"></a><a name="a9dc23093b3b54e709a62c2aee1b183b7"></a>源数据的每行结束标识字符。</p>
<div class="note" id="n14452d7c4e10432f96e42859bb7b0860"><a name="n14452d7c4e10432f96e42859bb7b0860"></a><a name="n14452d7c4e10432f96e42859bb7b0860"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="ad46fbccebc4d439eaf1eeb910b99b781"><a name="ad46fbccebc4d439eaf1eeb910b99b781"></a><a name="ad46fbccebc4d439eaf1eeb910b99b781"></a>ftp或sftp作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="r9461de09b93c48248b8fb56358b3fb03"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ac9f0f153056148faa8df41590deaa5a2"><a name="ac9f0f153056148faa8df41590deaa5a2"></a><a name="ac9f0f153056148faa8df41590deaa5a2"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aec1a8685dd7d4d409a65df82132a7897"><a name="aec1a8685dd7d4d409a65df82132a7897"></a><a name="aec1a8685dd7d4d409a65df82132a7897"></a>源数据的每个字段分割标识字符。</p>
<div class="note" id="n3a78d39b9ff241e2ad62dac2e8d81a63"><a name="n3a78d39b9ff241e2ad62dac2e8d81a63"></a><a name="n3a78d39b9ff241e2ad62dac2e8d81a63"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a8760c2ab5b794168a5a39db4e3a7622a"><a name="a8760c2ab5b794168a5a39db4e3a7622a"></a><a name="a8760c2ab5b794168a5a39db4e3a7622a"></a>ftp或sftp作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效</p>
</div></div>
</td>
</tr>
<tr id="re66c91fd98c74fe6b4390b4125d9a09d"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ab5055adc799e472d92b78746524524ec"><a name="ab5055adc799e472d92b78746524524ec"></a><a name="ab5055adc799e472d92b78746524524ec"></a>编码类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aea6207e7e660498b8eba02c82dfc8b98"><a name="aea6207e7e660498b8eba02c82dfc8b98"></a><a name="aea6207e7e660498b8eba02c82dfc8b98"></a>源数据的文本编码类型。只对文本类型文件有效。</p>
</td>
</tr>
<tr id="rce09f49b2e224a7a90d3b485dffa0054"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ae61c499e201f4ecf9ea8ff99281d6d1e"><a name="ae61c499e201f4ecf9ea8ff99281d6d1e"></a><a name="ae61c499e201f4ecf9ea8ff99281d6d1e"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="acc3a803d73fa45559033f392c885fbab"><a name="acc3a803d73fa45559033f392c885fbab"></a><a name="acc3a803d73fa45559033f392c885fbab"></a>支持以下两种：<a name="ub3e19f90832e4366a4d2c81f8ebb0431"></a><a name="ub3e19f90832e4366a4d2c81f8ebb0431"></a><ul id="ub3e19f90832e4366a4d2c81f8ebb0431"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="pba2118a2307e49b29a6ccb2207083f3f"><a name="pba2118a2307e49b29a6ccb2207083f3f"></a><a name="pba2118a2307e49b29a6ccb2207083f3f"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="p0afd333a2bd34c94ab9ac386cd0c1eed"><a name="p0afd333a2bd34c94ab9ac386cd0c1eed"></a><a name="p0afd333a2bd34c94ab9ac386cd0c1eed"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## hbase-connector<a name="s14d5b5fb6b6d4767847a0b8ea25b3da7"></a>

**表 4**  hbase-connector数据源连接属性

<a name="t4b650ca517a146df971786eaa4af2ad2"></a>
<table><thead align="left"><tr id="r560adc7480434d588126b2a821b29d87"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="ac373b4206d484352a38b18378af82b7a"><a name="ac373b4206d484352a38b18378af82b7a"></a><a name="ac373b4206d484352a38b18378af82b7a"></a><strong id="addffede8dba9454882ff5f497d4a89eb"><a name="addffede8dba9454882ff5f497d4a89eb"></a><a name="addffede8dba9454882ff5f497d4a89eb"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="adf019a29b0b14801b6992a81625c917d"><a name="adf019a29b0b14801b6992a81625c917d"></a><a name="adf019a29b0b14801b6992a81625c917d"></a><strong id="ab54f2a12130546da9048e6def60fe60b"><a name="ab54f2a12130546da9048e6def60fe60b"></a><a name="ab54f2a12130546da9048e6def60fe60b"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r3cca16159e92414f87fc8a3cdaa2b3ba"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a7b07040abad3438bad3550996b27ee5c"><a name="a7b07040abad3438bad3550996b27ee5c"></a><a name="a7b07040abad3438bad3550996b27ee5c"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ac0d12bdb2af548ad8f59e896260085ef"><a name="ac0d12bdb2af548ad8f59e896260085ef"></a><a name="ac0d12bdb2af548ad8f59e896260085ef"></a>源数据实际存储的HBase表。</p>
</td>
</tr>
</tbody>
</table>

## hdfs-connector<a name="sf7d0abeee0644e4396f4d4666ba879f3"></a>

**表 5**  hdfs-connector数据源连接属性

<a name="tb77070175c9049beaeb9b100dc5df454"></a>
<table><thead align="left"><tr id="r7558ba2fe7dc4b14a76a7c98a7cf05ae"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a2dc201da49a941eca588fb1da4e4165d"><a name="a2dc201da49a941eca588fb1da4e4165d"></a><a name="a2dc201da49a941eca588fb1da4e4165d"></a><strong id="ad396ee76d88e44138b9039333811212c"><a name="ad396ee76d88e44138b9039333811212c"></a><a name="ad396ee76d88e44138b9039333811212c"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a67507f5c293842699f1f33667113faa4"><a name="a67507f5c293842699f1f33667113faa4"></a><a name="a67507f5c293842699f1f33667113faa4"></a><strong id="a6febf15991a3446199983b9378a62bdc"><a name="a6febf15991a3446199983b9378a62bdc"></a><a name="a6febf15991a3446199983b9378a62bdc"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r7867d379e7734023b4798166ce8a1b76"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084972_p385045217275"><a name="zh-cn_topic_0071084972_p385045217275"></a><a name="zh-cn_topic_0071084972_p385045217275"></a>源目录或文件</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ad29a9fced04f418ba257fcff25a3e2ce"><a name="ad29a9fced04f418ba257fcff25a3e2ce"></a><a name="ad29a9fced04f418ba257fcff25a3e2ce"></a>源数据实际存储的形态，可能是HDFS包含一个目录中的全部数据文件，或者是单个数据文件。</p>
</td>
</tr>
<tr id="red833ae7f38d4f1cab5c68222dc7d048"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a4e6624234a364bbcbe6b3b52332ae441"><a name="a4e6624234a364bbcbe6b3b52332ae441"></a><a name="a4e6624234a364bbcbe6b3b52332ae441"></a>文件格式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a4fff3fc891ba44e2aac6847f32f2ad82"><a name="a4fff3fc891ba44e2aac6847f32f2ad82"></a><a name="a4fff3fc891ba44e2aac6847f32f2ad82"></a>Loader支持HDFS中存储数据的文件格式，默认支持以下两种：</p>
<a name="uacba7d5c84d84514ba2c61eaa36805a4"></a><a name="uacba7d5c84d84514ba2c61eaa36805a4"></a><ul id="uacba7d5c84d84514ba2c61eaa36805a4"><li>CSV_FILE：表示文本格式文件。目的连接为数据库型连接时，只支持文本格式。</li><li>BINARY_FILE：表示文本格式以外的二进制文件。</li></ul>
</td>
</tr>
<tr id="r0dd938cd29d24e958b3bfc840a28dab3"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a661a6871ff7d42e1ade037600f140172"><a name="a661a6871ff7d42e1ade037600f140172"></a><a name="a661a6871ff7d42e1ade037600f140172"></a>换行符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a6c6b3edaa22f4fd79591332f6483b11b"><a name="a6c6b3edaa22f4fd79591332f6483b11b"></a><a name="a6c6b3edaa22f4fd79591332f6483b11b"></a>源数据的每行结束标识字符。</p>
<div class="note" id="n891b951ef4c7493a9b9025e9ed2e817c"><a name="n891b951ef4c7493a9b9025e9ed2e817c"></a><a name="n891b951ef4c7493a9b9025e9ed2e817c"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="ade7060074ac149d6b337f1ff8d92e899"><a name="ade7060074ac149d6b337f1ff8d92e899"></a><a name="ade7060074ac149d6b337f1ff8d92e899"></a>hdfs作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“换行符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="r9ec8ef25ff2647dc8465aefc2a075c4a"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a34ba003afd8e4c52bc3d8ae1888172b1"><a name="a34ba003afd8e4c52bc3d8ae1888172b1"></a><a name="a34ba003afd8e4c52bc3d8ae1888172b1"></a>字段分割符</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ae8acbfb210504a93a6fb4dc368887d05"><a name="ae8acbfb210504a93a6fb4dc368887d05"></a><a name="ae8acbfb210504a93a6fb4dc368887d05"></a>源数据的每个字段分割标识字符。</p>
<div class="note" id="n84553400b67d4b7baa520df16c9a5079"><a name="n84553400b67d4b7baa520df16c9a5079"></a><a name="n84553400b67d4b7baa520df16c9a5079"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="ae27fd36befe640fe89bb27bdfbc88ea8"><a name="ae27fd36befe640fe89bb27bdfbc88ea8"></a><a name="ae27fd36befe640fe89bb27bdfbc88ea8"></a>hdfs作为源连接时，当“文件格式”配置为BINARY_FILE时，高级属性中的“字段分割符”配置无效。</p>
</div></div>
</td>
</tr>
<tr id="r89e2cb7caae045f5952e9fb06d16423e"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a4d90c32d837140c5bcb8355995d227cd"><a name="a4d90c32d837140c5bcb8355995d227cd"></a><a name="a4d90c32d837140c5bcb8355995d227cd"></a>文件分割方式</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><div class="p" id="ad91cb084f4fd4c199075a3310e9e63d3"><a name="ad91cb084f4fd4c199075a3310e9e63d3"></a><a name="ad91cb084f4fd4c199075a3310e9e63d3"></a>支持以下两种：<a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"></a><ul id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_ul200684591785"><li>File：按总文件个数分配map任务处理的文件数量，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue65660326171128"></a>“文件总个数/抽取并发数”</span>。</li><li>Size：按文件总大小分配map任务处理的文件大小，计算规则为<span class="parmvalue" id="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"></a><a name="zh-cn_topic_0071084972_zh-cn_topic_0071084972_parmvalue1507545117121"></a>“文件总大小/抽取并发数”</span>。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## hive-connector<a name="s792acd5598e84c68bd801ad8f80e728c"></a>

**表 6**  hive-connector数据源连接属性

<a name="t907d02227ef5419eb1d3871e25546a5c"></a>
<table><thead align="left"><tr id="r5c7b95c178894c9d9e546ce6fc22c3bc"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a26825152cbe548bea9d6598ced7a9565"><a name="a26825152cbe548bea9d6598ced7a9565"></a><a name="a26825152cbe548bea9d6598ced7a9565"></a><strong id="zh-cn_topic_0071084972_b816290111751"><a name="zh-cn_topic_0071084972_b816290111751"></a><a name="zh-cn_topic_0071084972_b816290111751"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="aba7826d72809468dbe05dc94c62a9a50"><a name="aba7826d72809468dbe05dc94c62a9a50"></a><a name="aba7826d72809468dbe05dc94c62a9a50"></a><strong id="ab9f2253b6eef43dc8630ecf93d6625f3"><a name="ab9f2253b6eef43dc8630ecf93d6625f3"></a><a name="ab9f2253b6eef43dc8630ecf93d6625f3"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="rdf7f60b2307a4e4eaa7e8d2b24e9f906"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ae2bd3f3c804148abb83107bafd536a38"><a name="ae2bd3f3c804148abb83107bafd536a38"></a><a name="ae2bd3f3c804148abb83107bafd536a38"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa18a4f696ab14f8d870e5402be551b02"><a name="aa18a4f696ab14f8d870e5402be551b02"></a><a name="aa18a4f696ab14f8d870e5402be551b02"></a>数据源的Hive数据库名称，支持通过界面查询并选择。</p>
</td>
</tr>
<tr id="ra1f979146752439cbbde30a256fac209"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2b51c5d42b24478292f0f13d42bc7e25"><a name="a2b51c5d42b24478292f0f13d42bc7e25"></a><a name="a2b51c5d42b24478292f0f13d42bc7e25"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a1bc7c9d129444cf3995d9487fe10eb3c"><a name="a1bc7c9d129444cf3995d9487fe10eb3c"></a><a name="a1bc7c9d129444cf3995d9487fe10eb3c"></a>数据源的Hive表名称，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

## voltdb-connector<a name="s1477869fff754c83b5662e062db3fd90"></a>

**表 7**  voltdb-connector数据源连接属性

<a name="t4692a87efb1a4f458a2e61f55cf7134e"></a>
<table><thead align="left"><tr id="r6a4138511ab0475d8cb4fdefc8349e63"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a16dac4cf31424bb1a422082571946a40"><a name="a16dac4cf31424bb1a422082571946a40"></a><a name="a16dac4cf31424bb1a422082571946a40"></a><strong id="a096f22b73f754e528f9b322fdef95499"><a name="a096f22b73f754e528f9b322fdef95499"></a><a name="a096f22b73f754e528f9b322fdef95499"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="adafd82d1bfff4640b379ecc8ed2aaa8f"><a name="adafd82d1bfff4640b379ecc8ed2aaa8f"></a><a name="adafd82d1bfff4640b379ecc8ed2aaa8f"></a><strong id="abf1fcb5972054f7c8deaf75b20370aff"><a name="abf1fcb5972054f7c8deaf75b20370aff"></a><a name="abf1fcb5972054f7c8deaf75b20370aff"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r493ba7c4f8db4c08829e1a2ad3dfb8bc"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a4997169bdfcc4a279f7a6f11606bfb6c"><a name="a4997169bdfcc4a279f7a6f11606bfb6c"></a><a name="a4997169bdfcc4a279f7a6f11606bfb6c"></a>抽取分区字段</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a93f7e716e74a42f1b5636da1da5cb25b"><a name="a93f7e716e74a42f1b5636da1da5cb25b"></a><a name="a93f7e716e74a42f1b5636da1da5cb25b"></a>分区字段，如果需读取多个字段，使用该字段分割结果并获取数据。</p>
</td>
</tr>
<tr id="r73d0284fa68e49bcb4d9a0e84c666d26"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="abfc2ed0ecd3348d19dca79151581e0de"><a name="abfc2ed0ecd3348d19dca79151581e0de"></a><a name="abfc2ed0ecd3348d19dca79151581e0de"></a>表名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a4fda9099894e4e488d8e03568335313d"><a name="a4fda9099894e4e488d8e03568335313d"></a><a name="a4fda9099894e4e488d8e03568335313d"></a>源数据实际存储的内存数据库表，支持通过界面查询并选择。</p>
</td>
</tr>
</tbody>
</table>

