# REST API介绍<a name="ZH-CN_TOPIC_0109962552"></a>

MapReduce服务（MRS）提供REST（Representational State Transfer）API。

REST从资源的角度观察整个网络，分布在各处的资源由URI（Uniform Resource Identifier）确定，客户端的应用通过URL（Unified Resource Locator）获取资源。

URL的一般格式为：https://Endpoint/uri。其中uri为资源路径，也即API访问的路径。

URL中的参数说明如[表1](#zh-cn_topic_0043477063_table2083638111650)所示。

**表 1**  URL中的参数说明

<a name="zh-cn_topic_0043477063_table2083638111650"></a>
<table><thead align="left"><tr id="zh-cn_topic_0043477063_row34424003111650"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0043477063_p63492280111650"><a name="zh-cn_topic_0043477063_p63492280111650"></a><a name="zh-cn_topic_0043477063_p63492280111650"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0043477063_p42601090111650"><a name="zh-cn_topic_0043477063_p42601090111650"></a><a name="zh-cn_topic_0043477063_p42601090111650"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0043477063_row47865497111650"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043477063_p12035466111719"><a name="zh-cn_topic_0043477063_p12035466111719"></a><a name="zh-cn_topic_0043477063_p12035466111719"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043477063_p35348718111719"><a name="zh-cn_topic_0043477063_p35348718111719"></a><a name="zh-cn_topic_0043477063_p35348718111719"></a>指定承载REST服务端点的服务器域名或IP，从<a href="https://developer.huaweicloud.com/endpoint?MRS" target="_blank" rel="noopener noreferrer">终端节点及区域说明</a>获取。</p>
</td>
</tr>
<tr id="zh-cn_topic_0043477063_row52843923111650"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0043477063_p61816971111719"><a name="zh-cn_topic_0043477063_p61816971111719"></a><a name="zh-cn_topic_0043477063_p61816971111719"></a>uri</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0043477063_p41118740111719"><a name="zh-cn_topic_0043477063_p41118740111719"></a><a name="zh-cn_topic_0043477063_p41118740111719"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
</tbody>
</table>

公有云接口采用HTTP传输协议，请求/响应报文使用JSON报文，媒体类型表示为Application/json。

REST从资源的角度来观察整个网络，提供创建、查询、更新、删掉等方法访问服务的资源。

REST API请求/响应对可以分为五个部分：

-   请求URI
-   请求方法
-   请求消息头
-   请求消息体
-   响应消息头
-   响应消息体

## 请求URI<a name="section12592211135413"></a>

请求URI由如下部分组成。

**\{URI-scheme\} :// \{Endpoint\} / \{resource-path\} ? \{query-string\}**

尽管请求URI包含在请求消息头中，但大多数语言或框架都要求您从请求消息中单独传递它，所有我们在此单独拿出来强调。

**表 2**  URI中的参数说明

<a name="table1637277135646"></a>
<table><thead align="left"><tr id="row42856273135646"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p48806094135646"><a name="p48806094135646"></a><a name="p48806094135646"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p60979560135646"><a name="p60979560135646"></a><a name="p60979560135646"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row50093829135713"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p13294067135723"><a name="p13294067135723"></a><a name="p13294067135723"></a>URI-scheme</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p23672669135728"><a name="p23672669135728"></a><a name="p23672669135728"></a>表示用于传输请求的协议。MRS的API都必须采用https。</p>
</td>
</tr>
<tr id="row40397318135646"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p50957329135646"><a name="p50957329135646"></a><a name="p50957329135646"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p33902960135646"><a name="p33902960135646"></a><a name="p33902960135646"></a>指定承载REST服务端点的服务器域名或IP，从<a href="https://developer.huaweicloud.com/endpoint?MRS" target="_blank" rel="noopener noreferrer">终端节点及区域说明</a>获取。</p>
</td>
</tr>
<tr id="row1377075135915"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p44434271135915"><a name="p44434271135915"></a><a name="p44434271135915"></a>resource-path</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p42406232135915"><a name="p42406232135915"></a><a name="p42406232135915"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
<tr id="row11383469135646"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p62949675135953"><a name="p62949675135953"></a><a name="p62949675135953"></a>Query string</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p61886121135646"><a name="p61886121135646"></a><a name="p61886121135646"></a>可选参数，例如API版本或资源选择标准。</p>
</td>
</tr>
</tbody>
</table>

## 请求方法<a name="section9691923143458"></a>

HTTP方法（也称为操作或动词），它告诉服务你正在请求什么类型的操作。

**表 3**  HTTP方法

<a name="table53502852143643"></a>
<table><thead align="left"><tr id="row5952395143643"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.3.1.1"><p id="p12382001143643"><a name="p12382001143643"></a><a name="p12382001143643"></a>方法</p>
</th>
<th class="cellrowborder" valign="top" width="82%" id="mcps1.2.3.1.2"><p id="p63418031143643"><a name="p63418031143643"></a><a name="p63418031143643"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row36586926143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p10751062143643"><a name="p10751062143643"></a><a name="p10751062143643"></a>GET</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p65529678143643"><a name="p65529678143643"></a><a name="p65529678143643"></a>请求服务器返回指定资源。</p>
</td>
</tr>
<tr id="row52896191143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p56733107143643"><a name="p56733107143643"></a><a name="p56733107143643"></a>PUT</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p31978955143643"><a name="p31978955143643"></a><a name="p31978955143643"></a>请求服务器更新指定资源。</p>
</td>
</tr>
<tr id="row19375144143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p25882866143643"><a name="p25882866143643"></a><a name="p25882866143643"></a>POST</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p16137429143643"><a name="p16137429143643"></a><a name="p16137429143643"></a>请求服务器新增资源或执行特殊操作。</p>
</td>
</tr>
<tr id="row11019135143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p20134713143643"><a name="p20134713143643"></a><a name="p20134713143643"></a>DELETE</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p20299039143643"><a name="p20299039143643"></a><a name="p20299039143643"></a>请求服务器删除指定资源，如删除对象等。</p>
</td>
</tr>
<tr id="row48473631143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p34050035143643"><a name="p34050035143643"></a><a name="p34050035143643"></a>HEAD</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p6589480143643"><a name="p6589480143643"></a><a name="p6589480143643"></a>请求服务器资源头部。</p>
</td>
</tr>
<tr id="row59305326143643"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p39002135143643"><a name="p39002135143643"></a><a name="p39002135143643"></a>PATCH</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p5056372143643"><a name="p5056372143643"></a><a name="p5056372143643"></a>请求服务器更新资源的部分内容。</p>
<p id="p45507354143643"><a name="p45507354143643"></a><a name="p45507354143643"></a>当资源不存在的时候，PATCH可能会去创建一个新的资源。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息头<a name="section52916988135413"></a>

请求消息头由若干头域构成，每个头域由一个域名，冒号\(: \)和域值组成。

可选的附加请求头字段，如指定的URI和HTTP方法所要求的字段。详细的MRS公共请求消息头字段请参见[表4](#td181b06f1c0949cb913acd8d77f21ec3)，其中请求认证信息请参见[获取请求认证](获取请求认证.md)。

**表 4**  公共请求消息头

<a name="td181b06f1c0949cb913acd8d77f21ec3"></a>
<table><thead align="left"><tr id="r97d2c57e12614bd3afdc94a4204ed595"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="aa019e06442ea43f7a2dd236b9eeb153c"><a name="aa019e06442ea43f7a2dd236b9eeb153c"></a><a name="aa019e06442ea43f7a2dd236b9eeb153c"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.5.1.2"><p id="a0b5237510efb47c185142788a435c90a"><a name="a0b5237510efb47c185142788a435c90a"></a><a name="a0b5237510efb47c185142788a435c90a"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p id="a8df98fec2ab9432c90753890865721a1"><a name="a8df98fec2ab9432c90753890865721a1"></a><a name="a8df98fec2ab9432c90753890865721a1"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0037324703_p865237161145"><a name="zh-cn_topic_0037324703_p865237161145"></a><a name="zh-cn_topic_0037324703_p865237161145"></a>示例</p>
</th>
</tr>
</thead>
<tbody><tr id="r775e22ddde31427cb0c75310d3b275f5"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="ad5553c8196a14fbcb91cb55152fee53d"><a name="ad5553c8196a14fbcb91cb55152fee53d"></a><a name="ad5553c8196a14fbcb91cb55152fee53d"></a>X-Sdk-Date</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="a7cd5e01a2bc34080b44f606c2c248dc7"><a name="a7cd5e01a2bc34080b44f606c2c248dc7"></a><a name="a7cd5e01a2bc34080b44f606c2c248dc7"></a>请求的发生时间，格式为(YYYYMMDD'T'HHMMSS'Z')。</p>
<p id="a5ea5e42d645143bbbae5f9c4ab452d7d"><a name="a5ea5e42d645143bbbae5f9c4ab452d7d"></a><a name="a5ea5e42d645143bbbae5f9c4ab452d7d"></a>取值为当前系统的GMT时间。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="ab64471a82ff44053a057c927cbf9ddc9"><a name="ab64471a82ff44053a057c927cbf9ddc9"></a><a name="ab64471a82ff44053a057c927cbf9ddc9"></a>使用AK/SK认证时必选。</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="a3e18fe766b9a4185830a0fe282eb2680"><a name="a3e18fe766b9a4185830a0fe282eb2680"></a><a name="a3e18fe766b9a4185830a0fe282eb2680"></a>20150907T101459Z</p>
</td>
</tr>
<tr id="r446afcc099224426825f2074cb6dad86"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="a5c231595ff8f439f9493fbf05f7c0b96"><a name="a5c231595ff8f439f9493fbf05f7c0b96"></a><a name="a5c231595ff8f439f9493fbf05f7c0b96"></a>Authorization</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="a0cb62c6f303e49d8898af85a6c83785d"><a name="a0cb62c6f303e49d8898af85a6c83785d"></a><a name="a0cb62c6f303e49d8898af85a6c83785d"></a>签名认证信息。</p>
<p id="af4b9d51334e04157bacb25dbe881e65c"><a name="af4b9d51334e04157bacb25dbe881e65c"></a><a name="af4b9d51334e04157bacb25dbe881e65c"></a>该值来源于请求签名结果。</p>
<p id="ac33cb31eaf60498086ea2ba390a81e99"><a name="ac33cb31eaf60498086ea2ba390a81e99"></a><a name="ac33cb31eaf60498086ea2ba390a81e99"></a>请参考<a href="获取请求认证.md#li15980726144052">请求签名流程</a>。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a335f6ca4e84b4b65b60d6a8c946d4c38"><a name="a335f6ca4e84b4b65b60d6a8c946d4c38"></a><a name="a335f6ca4e84b4b65b60d6a8c946d4c38"></a>使用AK/SK认证时必选。</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="p53912097152735"><a name="p53912097152735"></a><a name="p53912097152735"></a>SDK-HMAC-SHA256 Credential=QRUP2R3QFNAOVAWMYHZW/20160202/northchina/test/sdk_request, SignedHeaders=host;x-sdk-date, Signature=9d8b56b055c0e1f7a9498d881a7cb726be91b4f0cde1773b0b1557e987a480ce</p>
</td>
</tr>
<tr id="r982b99c7ac074e80b63e96059bc375ff"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="a6a9ab4af31ef41978c7cd032050ae14a"><a name="a6a9ab4af31ef41978c7cd032050ae14a"></a><a name="a6a9ab4af31ef41978c7cd032050ae14a"></a>Host</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="aaa38a9c8e2dc4fb78234cbb5c1cd580d"><a name="aaa38a9c8e2dc4fb78234cbb5c1cd580d"></a><a name="aaa38a9c8e2dc4fb78234cbb5c1cd580d"></a>请求的服务器信息，从服务API的URL中获取。值为hostname[:port]。端口缺省时使用默认的端口，https的默认端口为443。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a084e3b07cf104f05944d08ef2a96b1c4"><a name="a084e3b07cf104f05944d08ef2a96b1c4"></a><a name="a084e3b07cf104f05944d08ef2a96b1c4"></a>使用AK/SK认证时必选。</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="a8de4dbac3b7a483b9d39efbdf632998a"><a name="a8de4dbac3b7a483b9d39efbdf632998a"></a><a name="a8de4dbac3b7a483b9d39efbdf632998a"></a>code.test.com</p>
<p id="ac8a2d0ee992c40cfa38782c0b85210a9"><a name="ac8a2d0ee992c40cfa38782c0b85210a9"></a><a name="ac8a2d0ee992c40cfa38782c0b85210a9"></a>or</p>
<p id="ab29d121a7fb94fe3822dca91b79fe760"><a name="ab29d121a7fb94fe3822dca91b79fe760"></a><a name="ab29d121a7fb94fe3822dca91b79fe760"></a>code.test.com:443</p>
</td>
</tr>
<tr id="rc7911eda8b784dceb1da661d56877f0c"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="a5f1759adb3ce437a842cc9af6a3fb071"><a name="a5f1759adb3ce437a842cc9af6a3fb071"></a><a name="a5f1759adb3ce437a842cc9af6a3fb071"></a>Content-type</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="a04c3e10d1a6f4dca8febf610be4079f8"><a name="a04c3e10d1a6f4dca8febf610be4079f8"></a><a name="a04c3e10d1a6f4dca8febf610be4079f8"></a>发送的实体的MIME类型。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a2ca751e0d5904460aae7f6d5f5dc3334"><a name="a2ca751e0d5904460aae7f6d5f5dc3334"></a><a name="a2ca751e0d5904460aae7f6d5f5dc3334"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="a17e3634848fc49ae9ea11717665e49ea"><a name="a17e3634848fc49ae9ea11717665e49ea"></a><a name="a17e3634848fc49ae9ea11717665e49ea"></a>application/json</p>
</td>
</tr>
<tr id="r38eb00e3fde947918d9a8cf46c11b74f"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="aa2ffb672489a4ff4b2b47b0ee711625e"><a name="aa2ffb672489a4ff4b2b47b0ee711625e"></a><a name="aa2ffb672489a4ff4b2b47b0ee711625e"></a>Content-Length</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="a67d79ec8bb3d412fb1f2d59a3767248a"><a name="a67d79ec8bb3d412fb1f2d59a3767248a"></a><a name="a67d79ec8bb3d412fb1f2d59a3767248a"></a>请求body长度，单位为Byte。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a9815cc0accf94167b7f3607db7b90880"><a name="a9815cc0accf94167b7f3607db7b90880"></a><a name="a9815cc0accf94167b7f3607db7b90880"></a>POST/PUT请求必填。 GET不能包含。</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="af6f5766e2ad548dcb9e40b3a0074c125"><a name="af6f5766e2ad548dcb9e40b3a0074c125"></a><a name="af6f5766e2ad548dcb9e40b3a0074c125"></a>3495</p>
</td>
</tr>
<tr id="r47347abb1c994c38bacebe25ec1d218e"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="ab8ee25b819d94be08bf7cabf1d921b9a"><a name="ab8ee25b819d94be08bf7cabf1d921b9a"></a><a name="ab8ee25b819d94be08bf7cabf1d921b9a"></a>X-Project-Id</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="af63b53a9158e418c9317dd79ddcac3db"><a name="af63b53a9158e418c9317dd79ddcac3db"></a><a name="af63b53a9158e418c9317dd79ddcac3db"></a>project id，用于不同project取token。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a234f4a7f440b4413b1aa19c9462695ab"><a name="a234f4a7f440b4413b1aa19c9462695ab"></a><a name="a234f4a7f440b4413b1aa19c9462695ab"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="a148d7ff92e5e49cfbb4ac0238cd2ebd4"><a name="a148d7ff92e5e49cfbb4ac0238cd2ebd4"></a><a name="a148d7ff92e5e49cfbb4ac0238cd2ebd4"></a>e9993fc787d94b6c886cbaa340f9c0f4</p>
</td>
</tr>
<tr id="rbec1d01d1f9b4bcb8a183ded144e2f0a"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="a5ad0cfc3781243c9ac6fd8e5c47b8894"><a name="a5ad0cfc3781243c9ac6fd8e5c47b8894"></a><a name="a5ad0cfc3781243c9ac6fd8e5c47b8894"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="a399eb5e20970416186d95d614e84af10"><a name="a399eb5e20970416186d95d614e84af10"></a><a name="a399eb5e20970416186d95d614e84af10"></a>用户Token。</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="a8ef6da5c4a3742a0b50adb96d3a52baf"><a name="a8ef6da5c4a3742a0b50adb96d3a52baf"></a><a name="a8ef6da5c4a3742a0b50adb96d3a52baf"></a>否</p>
<p id="a90d30c52a285436c8efb6b0924bc3912"><a name="a90d30c52a285436c8efb6b0924bc3912"></a><a name="a90d30c52a285436c8efb6b0924bc3912"></a>使用Token认证时必选。</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="ac1a9d7862596407ba9dc5ca0dfa508c8"><a name="ac1a9d7862596407ba9dc5ca0dfa508c8"></a><a name="ac1a9d7862596407ba9dc5ca0dfa508c8"></a>-</p>
</td>
</tr>
<tr id="row16125640113240"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p31108482113240"><a name="p31108482113240"></a><a name="p31108482113240"></a>X-Language</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="p36759104113240"><a name="p36759104113240"></a><a name="p36759104113240"></a>请求语言，支持配置如下值：</p>
<a name="ul5220882114910"></a><a name="ul5220882114910"></a><ul id="ul5220882114910"><li>zh-cn：中文</li><li>en-us：英文</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p24697451113240"><a name="p24697451113240"></a><a name="p24697451113240"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="p54336490113240"><a name="p54336490113240"></a><a name="p54336490113240"></a>en-us</p>
</td>
</tr>
<tr id="row1305912154611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p59561232104612"><a name="p59561232104612"></a><a name="p59561232104612"></a>X-Domain-Id</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.2 "><p id="p33051712144616"><a name="p33051712144616"></a><a name="p33051712144616"></a>账号ID</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p id="p2305312124612"><a name="p2305312124612"></a><a name="p2305312124612"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.5.1.4 "><p id="p193051912134613"><a name="p193051912134613"></a><a name="p193051912134613"></a>-</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>其它header属性，请遵照http协议。  

## 请求消息体<a name="section58417634135413"></a>

请求消息体通常以结构化格式（如JSON或XML）发出，与请求消息头中Content-type对应，传递除请求消息头之外的内容。

## 响应消息头<a name="section34207884135413"></a>

响应消息头包含如下两部分。

-   一个HTTP状态代码，从2xx成功代码到4xx或5xx错误代码。 或者，可以返回服务定义的状态码，如API文档中所示。
-   附加响应头字段，如支持请求的响应所需，如Content-type响应消息头。详细的公共响应消息头字段请参见[表5](#t07321716e8254cfeb412ed51c17ee843)。

    **表 5**  公共响应消息头

    <a name="t07321716e8254cfeb412ed51c17ee843"></a>
    <table><thead align="left"><tr id="r587f288aeb27478f8b29d026ecf10be2"><th class="cellrowborder" valign="top" width="26.240000000000002%" id="mcps1.2.4.1.1"><p id="a0bea622f75a043109d1ea5cc2b064b61"><a name="a0bea622f75a043109d1ea5cc2b064b61"></a><a name="a0bea622f75a043109d1ea5cc2b064b61"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="39.17%" id="mcps1.2.4.1.2"><p id="a930a22683ca7458a898bb7bf92940418"><a name="a930a22683ca7458a898bb7bf92940418"></a><a name="a930a22683ca7458a898bb7bf92940418"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="34.589999999999996%" id="mcps1.2.4.1.3"><p id="p51197077145241"><a name="p51197077145241"></a><a name="p51197077145241"></a>示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row5946719145144"><td class="cellrowborder" valign="top" width="26.240000000000002%" headers="mcps1.2.4.1.1 "><p id="p11922260145144"><a name="p11922260145144"></a><a name="p11922260145144"></a>Date</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.17%" headers="mcps1.2.4.1.2 "><p id="p26999394145213"><a name="p26999394145213"></a><a name="p26999394145213"></a>HTTP协议标准报头。表示消息发送的时间，时间的描述格式由rfc822定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="34.589999999999996%" headers="mcps1.2.4.1.3 "><p id="p53322585145241"><a name="p53322585145241"></a><a name="p53322585145241"></a>Mon, 12 Nov 2007 15:55:01 GMT</p>
    </td>
    </tr>
    <tr id="row59561348145156"><td class="cellrowborder" valign="top" width="26.240000000000002%" headers="mcps1.2.4.1.1 "><p id="p59739888145156"><a name="p59739888145156"></a><a name="p59739888145156"></a>Server</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.17%" headers="mcps1.2.4.1.2 "><p id="p7092756145156"><a name="p7092756145156"></a><a name="p7092756145156"></a>HTTP协议标准报头。包含了服务器用来处理请求的软件信息。</p>
    </td>
    <td class="cellrowborder" valign="top" width="34.589999999999996%" headers="mcps1.2.4.1.3 "><p id="p24162092145241"><a name="p24162092145241"></a><a name="p24162092145241"></a>Apache</p>
    </td>
    </tr>
    <tr id="r582bc5aea91d492da5e8aa7723ebb085"><td class="cellrowborder" valign="top" width="26.240000000000002%" headers="mcps1.2.4.1.1 "><p id="a571a99a07c204364a933eb42674a1cd0"><a name="a571a99a07c204364a933eb42674a1cd0"></a><a name="a571a99a07c204364a933eb42674a1cd0"></a>Content-Length</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.17%" headers="mcps1.2.4.1.2 "><p id="abfc85a6a3cf84d008a4078d0468a40ff"><a name="abfc85a6a3cf84d008a4078d0468a40ff"></a><a name="abfc85a6a3cf84d008a4078d0468a40ff"></a>HTTP协议标准报头。用于指明实体正文的长度，以字节方式存储的十进制数字来表示。</p>
    </td>
    <td class="cellrowborder" valign="top" width="34.589999999999996%" headers="mcps1.2.4.1.3 "><p id="p10972473145241"><a name="p10972473145241"></a><a name="p10972473145241"></a>xxx</p>
    </td>
    </tr>
    <tr id="r39096ac780e24a1495618bd24421f1ef"><td class="cellrowborder" valign="top" width="26.240000000000002%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0037324704_p645562162223"><a name="zh-cn_topic_0037324704_p645562162223"></a><a name="zh-cn_topic_0037324704_p645562162223"></a>Content-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.17%" headers="mcps1.2.4.1.2 "><p id="p2503917714544"><a name="p2503917714544"></a><a name="p2503917714544"></a>HTTP协议标准报头。用于指明发送给接收者的实体正文的媒体类型。</p>
    </td>
    <td class="cellrowborder" valign="top" width="34.589999999999996%" headers="mcps1.2.4.1.3 "><p id="p49695515145241"><a name="p49695515145241"></a><a name="p49695515145241"></a>application/json</p>
    </td>
    </tr>
    </tbody>
    </table>


## 响应消息体<a name="section19375202135413"></a>

响应消息体通常以结构化格式（如JSON或XML）返回，与响应消息头中Content-type对应，传递除响应消息头之外的内容。

## 发起请求<a name="section25887566135413"></a>

共有三种方式可以基于已构建好的请求消息发起请求，分别为：

-   cURL

    cURL是一个命令行工具，用来执行各种URL操作和信息传输。cURL充当的是HTTP客户端，可以发送HTTP请求给服务端，并接收响应消息。cURL适用于接口调试。关于cURL详细信息请参见[https://curl.haxx.se/](https://curl.haxx.se/)。

-   编码

    通过编码调用接口，组装请求消息，并发送处理请求消息。

-   REST客户端

    Mozilla、Google都为REST提供了图形化的浏览器插件，发送处理请求消息。针对Firefox，请参见[Firefox REST Client](https://addons.mozilla.org/en-US/firefox/addon/restclient/)。针对Chrome，请参见[Postman](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop)。


