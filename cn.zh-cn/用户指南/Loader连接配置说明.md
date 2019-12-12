# Loader连接配置说明<a name="ZH-CN_TOPIC_0173178181"></a>

## 基本介绍<a name="s928381114aed4b4eb08f287c5d5c9ff0"></a>

Loader支持以下多种连接，每种连接的配置介绍可根据本章节内容了解。

-   obs-connector
-   generic-jdbc-connector
-   ftp-connector或sftp-connector
-   hbase-connector、hdfs-connector或hive-connector
-   voltdb-connector

## OBS连接<a name="s5482eab8b69a44a48a2fcb069390d769"></a>

OBS连接是Loader与OBS进行数据交换的通道，配置参数如[表1](#t6fd2dae9f81e4309906aec5754a1bf77)所示。

**表 1**  obs-connector配置

<a name="t6fd2dae9f81e4309906aec5754a1bf77"></a>
<table><thead align="left"><tr id="r137dee3f5f374cc0aa2586646ee6e7f4"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a627d04c3bed542ca886bfc68a9b8e9f8"><a name="a627d04c3bed542ca886bfc68a9b8e9f8"></a><a name="a627d04c3bed542ca886bfc68a9b8e9f8"></a><strong id="a97d1acfadad44d5a926d041a8e2e863f"><a name="a97d1acfadad44d5a926d041a8e2e863f"></a><a name="a97d1acfadad44d5a926d041a8e2e863f"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="ad3b306f3d0a64bafaa221cf2fe77da4c"><a name="ad3b306f3d0a64bafaa221cf2fe77da4c"></a><a name="ad3b306f3d0a64bafaa221cf2fe77da4c"></a><strong id="a49c97940f3e04724a0da0a348d818873"><a name="a49c97940f3e04724a0da0a348d818873"></a><a name="a49c97940f3e04724a0da0a348d818873"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r75b3ea3932de44b088048608c4c28ce9"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a88056ffebe56418a9581070f10620af3"><a name="a88056ffebe56418a9581070f10620af3"></a><a name="a88056ffebe56418a9581070f10620af3"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="adc68371588e644e2a905780696e5bd2c"><a name="adc68371588e644e2a905780696e5bd2c"></a><a name="adc68371588e644e2a905780696e5bd2c"></a>指定一个Loader连接的名称。</p>
</td>
</tr>
<tr id="r83539d320ccf4f29a0f97e7c7dfbb1a7"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a1dca11d6ea8c4978a1bae3fb0dff116f"><a name="a1dca11d6ea8c4978a1bae3fb0dff116f"></a><a name="a1dca11d6ea8c4978a1bae3fb0dff116f"></a>OBS服务器</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="adfe2884f2ceb4bc0b25206cfbb6bf641"><a name="adfe2884f2ceb4bc0b25206cfbb6bf641"></a><a name="adfe2884f2ceb4bc0b25206cfbb6bf641"></a>输入OBS endpoint地址，一般格式为<strong id="aceeeb94841bc459fa8b9f749138de3b3"><a name="aceeeb94841bc459fa8b9f749138de3b3"></a><a name="aceeeb94841bc459fa8b9f749138de3b3"></a>OBS.<em id="zh-cn_topic_0070859523_i482166816102"><a name="zh-cn_topic_0070859523_i482166816102"></a><a name="zh-cn_topic_0070859523_i482166816102"></a>Region</em>.<em id="aa2c209b2e4ef4c4da4837926077ae9fe"><a name="aa2c209b2e4ef4c4da4837926077ae9fe"></a><a name="aa2c209b2e4ef4c4da4837926077ae9fe"></a>DomainName</em></strong>。</p>
<p id="ad44d6bb798c8427fa9fe799fe5e47b14"><a name="ad44d6bb798c8427fa9fe799fe5e47b14"></a><a name="ad44d6bb798c8427fa9fe799fe5e47b14"></a>例如执行如下命令查看OBS endpoint地址：</p>
<p id="a3bdfda38c7d04f4caec64efc28de5005"><a name="a3bdfda38c7d04f4caec64efc28de5005"></a><a name="a3bdfda38c7d04f4caec64efc28de5005"></a>cat /opt/Bigdata/apache-tomcat-7.0.78/webapps/web/WEB-INF/classes/cloud-obs.properties</p>
</td>
</tr>
<tr id="r3a39b60ab21a4a5aaf15f5c2ffc704f7"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a8b4fc4fa805f42429edde9f47ad17eba"><a name="a8b4fc4fa805f42429edde9f47ad17eba"></a><a name="a8b4fc4fa805f42429edde9f47ad17eba"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a40679334b4ed40c8a4b04e91e6d76f31"><a name="a40679334b4ed40c8a4b04e91e6d76f31"></a><a name="a40679334b4ed40c8a4b04e91e6d76f31"></a>访问OBS数据的端口。默认值为<span class="parmvalue" id="pb570e71caa614318be2247a8f18062d4"><a name="pb570e71caa614318be2247a8f18062d4"></a><a name="pb570e71caa614318be2247a8f18062d4"></a>“443”</span>。</p>
</td>
</tr>
<tr id="rc2e8e22efedb4d3d838f7974f7bcb6b4"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a16fafb8f3a124bce92f19224ead7f9b6"><a name="a16fafb8f3a124bce92f19224ead7f9b6"></a><a name="a16fafb8f3a124bce92f19224ead7f9b6"></a>访问标识(AK)</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a431e5ad7b6994ed0ac2d29b45ade0209"><a name="a431e5ad7b6994ed0ac2d29b45ade0209"></a><a name="a431e5ad7b6994ed0ac2d29b45ade0209"></a>表示访问OBS的用户的访问密钥AK。</p>
</td>
</tr>
<tr id="rd91ff600dac148dd8aacb26451ee7282"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2a090421a28641f79a56cb9bbc06c882"><a name="a2a090421a28641f79a56cb9bbc06c882"></a><a name="a2a090421a28641f79a56cb9bbc06c882"></a>密钥(SK)</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa5b12f69d23149da9fb23e2ebdffcd80"><a name="aa5b12f69d23149da9fb23e2ebdffcd80"></a><a name="aa5b12f69d23149da9fb23e2ebdffcd80"></a>表示访问密钥对应的SK。</p>
</td>
</tr>
</tbody>
</table>

## 关系型数据库连接<a name="s3adba992c44845858448dc54a3ac5cf9"></a>

关系型数据库连接是Loader与关系型数据库进行数据交换的通道，配置参数如[表2](#t938c9f27e7004e4dbcca6c3c0ba5d8a2)所示。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分参数需要单击“显示高级属性“后展开，否则默认隐藏。  

**表 2**  generic-jdbc-connector配置

<a name="t938c9f27e7004e4dbcca6c3c0ba5d8a2"></a>
<table><thead align="left"><tr id="r661eb1d54660464287aba708fc753996"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a20a6f27b9d31433f840a881b1206815c"><a name="a20a6f27b9d31433f840a881b1206815c"></a><a name="a20a6f27b9d31433f840a881b1206815c"></a><strong id="a3af9f277f2594034acb1796e72df7766"><a name="a3af9f277f2594034acb1796e72df7766"></a><a name="a3af9f277f2594034acb1796e72df7766"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="adfb44363195440f2a7280697a12a8c63"><a name="adfb44363195440f2a7280697a12a8c63"></a><a name="adfb44363195440f2a7280697a12a8c63"></a><strong id="a97b6a18354114dd4a14e846b2be19fec"><a name="a97b6a18354114dd4a14e846b2be19fec"></a><a name="a97b6a18354114dd4a14e846b2be19fec"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="ra5933fe0252d43f48c2fb0208e405579"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a3275474d3c0b4d1991f36b2fa1a3b63a"><a name="a3275474d3c0b4d1991f36b2fa1a3b63a"></a><a name="a3275474d3c0b4d1991f36b2fa1a3b63a"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a1a7573b8837c489996efba3fd736257d"><a name="a1a7573b8837c489996efba3fd736257d"></a><a name="a1a7573b8837c489996efba3fd736257d"></a>指定一个Loader连接的名称。</p>
</td>
</tr>
<tr id="r3fc53024658642fcb2c64af3f6b7e434"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="af635ba364828447ca4ef60ffbd43d2a4"><a name="af635ba364828447ca4ef60ffbd43d2a4"></a><a name="af635ba364828447ca4ef60ffbd43d2a4"></a>数据库类型</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ab7e9e57963be46cdb3e02e52a36f856b"><a name="ab7e9e57963be46cdb3e02e52a36f856b"></a><a name="ab7e9e57963be46cdb3e02e52a36f856b"></a>表示Loader连接支持的数据，可以选择<span class="parmvalue" id="p4ca7431253b842f5a4be685faef25d4d"><a name="p4ca7431253b842f5a4be685faef25d4d"></a><a name="p4ca7431253b842f5a4be685faef25d4d"></a>“ORACLE”</span>、<span class="parmvalue" id="p2b4f58e86ca2476b95c3d8b32b9f486e"><a name="p2b4f58e86ca2476b95c3d8b32b9f486e"></a><a name="p2b4f58e86ca2476b95c3d8b32b9f486e"></a>“MYSQL”</span>和<span class="parmvalue" id="pec191e334cd440579600ccd9011e65e0"><a name="pec191e334cd440579600ccd9011e65e0"></a><a name="pec191e334cd440579600ccd9011e65e0"></a>“MPPDB”</span>。</p>
</td>
</tr>
<tr id="r4311edf3c2b047ccb5f76102f88b6884"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a0ae257455c41460e927354b8c0ecb9e3"><a name="a0ae257455c41460e927354b8c0ecb9e3"></a><a name="a0ae257455c41460e927354b8c0ecb9e3"></a>数据库服务器</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a157eb7708b17412794a0763f577b497f"><a name="a157eb7708b17412794a0763f577b497f"></a><a name="a157eb7708b17412794a0763f577b497f"></a>表示数据库的访问地址，可以是IP地址或者域名。</p>
</td>
</tr>
<tr id="rf73f722e1124452fb7110e1e0cf7ae63"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ad059997a2cc54945b12ae54f74c9b37d"><a name="ad059997a2cc54945b12ae54f74c9b37d"></a><a name="ad059997a2cc54945b12ae54f74c9b37d"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ad5356c0b42f745398b2eb3e07498ebd7"><a name="ad5356c0b42f745398b2eb3e07498ebd7"></a><a name="ad5356c0b42f745398b2eb3e07498ebd7"></a>表示数据库的访问端口。</p>
</td>
</tr>
<tr id="r772165140c1842b086c536808b2d78fe"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a127a3254cdfc49569b6c977cca823cdc"><a name="a127a3254cdfc49569b6c977cca823cdc"></a><a name="a127a3254cdfc49569b6c977cca823cdc"></a>数据库名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a46cf76cd1e27423eb62f37c50c1b8315"><a name="a46cf76cd1e27423eb62f37c50c1b8315"></a><a name="a46cf76cd1e27423eb62f37c50c1b8315"></a>表示保存数据的具体数据库名。</p>
</td>
</tr>
<tr id="r4eab374a45ce4443a4c1ec51a21fee56"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a7918e2a020ce42aabba551fe9f2184e3"><a name="a7918e2a020ce42aabba551fe9f2184e3"></a><a name="a7918e2a020ce42aabba551fe9f2184e3"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aa1156464e7da46348d07b7d3c6925998"><a name="aa1156464e7da46348d07b7d3c6925998"></a><a name="aa1156464e7da46348d07b7d3c6925998"></a>表示连接数据库使用的用户名称。</p>
</td>
</tr>
<tr id="r69bb7673014d4f9cbab32855f42f9082"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a352b7c1090c547ebb482d5c3361f879a"><a name="a352b7c1090c547ebb482d5c3361f879a"></a><a name="a352b7c1090c547ebb482d5c3361f879a"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p806192162119"><a name="zh-cn_topic_0070859523_p806192162119"></a><a name="zh-cn_topic_0070859523_p806192162119"></a>表示此用户对应的密码。需要与实际密码保持一致。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  高级属性配置

<a name="t30f489226f7443c48d00aba34748e7e9"></a>
<table><thead align="left"><tr id="r9aad057702e3479eb8333fe4a7a59067"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a4ed3e9b266124dc39c6ab45df420592a"><a name="a4ed3e9b266124dc39c6ab45df420592a"></a><a name="a4ed3e9b266124dc39c6ab45df420592a"></a><strong id="a41335f9f566944098fe3b62810521a84"><a name="a41335f9f566944098fe3b62810521a84"></a><a name="a41335f9f566944098fe3b62810521a84"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a2b1d0c4851d0490682a3f27cb28290d2"><a name="a2b1d0c4851d0490682a3f27cb28290d2"></a><a name="a2b1d0c4851d0490682a3f27cb28290d2"></a><strong id="aa1d14928c48242059feb30ad343ebffd"><a name="aa1d14928c48242059feb30ad343ebffd"></a><a name="aa1d14928c48242059feb30ad343ebffd"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="ra0ccb42f274647d789a595e748cb7610"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a730ee559f70e46c8817bf06ed45fb1fb"><a name="a730ee559f70e46c8817bf06ed45fb1fb"></a><a name="a730ee559f70e46c8817bf06ed45fb1fb"></a>一次请求行数</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="af443076bb81c4a4e96d6c769116ac0b4"><a name="af443076bb81c4a4e96d6c769116ac0b4"></a><a name="af443076bb81c4a4e96d6c769116ac0b4"></a>表示每次连接数据库时，最多可获取的数据量。</p>
</td>
</tr>
<tr id="r307d76119ab8451f8c5b5d9e684a0a9f"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a6289e89f766d4b8fb691e7b54c6d3096"><a name="a6289e89f766d4b8fb691e7b54c6d3096"></a><a name="a6289e89f766d4b8fb691e7b54c6d3096"></a>连接属性</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ab42f409947ce4f46a2797a9db0064fb4"><a name="ab42f409947ce4f46a2797a9db0064fb4"></a><a name="ab42f409947ce4f46a2797a9db0064fb4"></a>不同类型数据库支持该数据库连接特有的驱动属性，例如MYSQL的<span class="parmname" id="p796e02d97991427bb1ce9ce1807f80fa"><a name="p796e02d97991427bb1ce9ce1807f80fa"></a><a name="p796e02d97991427bb1ce9ce1807f80fa"></a>“autoReconnect”</span>。如果需要定义驱动属性，单击<span class="uicontrol" id="u0331134384b6442597038da80adfed57"><a name="u0331134384b6442597038da80adfed57"></a><a name="u0331134384b6442597038da80adfed57"></a>“添加”</span>。</p>
</td>
</tr>
<tr id="r081305e477a84585abca25cc1b22b7e6"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a50787e91ce0d4a518125aea32823fcc3"><a name="a50787e91ce0d4a518125aea32823fcc3"></a><a name="a50787e91ce0d4a518125aea32823fcc3"></a>引用符号</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a2c428ddb0d454b1aad3e019fcb955a40"><a name="a2c428ddb0d454b1aad3e019fcb955a40"></a><a name="a2c428ddb0d454b1aad3e019fcb955a40"></a>表示数据库的SQL中保留关键字的定界符，不同类型数据库定义的定界符不完全相同。</p>
</td>
</tr>
</tbody>
</table>

## 文件服务器连接<a name="s73ada4f9d7e94890a00a2c7a90856ba6"></a>

文件服务器连接包含FTP连接和SFTP连接，是Loader与文件服务器进行数据交换的通道，配置参数如[表4](#t15d36a6a4bda4efe8b7dd5d4abb70019)所示。

**表 4**  ftp-connector或sftp-connector配置

<a name="t15d36a6a4bda4efe8b7dd5d4abb70019"></a>
<table><thead align="left"><tr id="r9c1a011a175249e49afb7265fc80fff5"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a9efe23ac1f544dee8e837d1db5979e43"><a name="a9efe23ac1f544dee8e837d1db5979e43"></a><a name="a9efe23ac1f544dee8e837d1db5979e43"></a><strong id="abc3eabb4d3004f38b495e90617cf2ce6"><a name="abc3eabb4d3004f38b495e90617cf2ce6"></a><a name="abc3eabb4d3004f38b495e90617cf2ce6"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a271f379076824840a5c88fa8531af562"><a name="a271f379076824840a5c88fa8531af562"></a><a name="a271f379076824840a5c88fa8531af562"></a><strong id="aadbbcabc4ce242a0927761ce21c6350a"><a name="aadbbcabc4ce242a0927761ce21c6350a"></a><a name="aadbbcabc4ce242a0927761ce21c6350a"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r0961571163fc4d38b510ef27d85e0e6f"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2fbe412a8f3747fdb6632be895e386af"><a name="a2fbe412a8f3747fdb6632be895e386af"></a><a name="a2fbe412a8f3747fdb6632be895e386af"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a08c97dd694c74c1cb6f40b7c8a983954"><a name="a08c97dd694c74c1cb6f40b7c8a983954"></a><a name="a08c97dd694c74c1cb6f40b7c8a983954"></a>指定一个Loader连接的名称。</p>
</td>
</tr>
<tr id="r778dca00da264f99a40091a8264fdca8"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a7460771288324fcfae18a327d2db15d1"><a name="a7460771288324fcfae18a327d2db15d1"></a><a name="a7460771288324fcfae18a327d2db15d1"></a>主机名或IP</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a3f3e13f5f72343068daf47c873bbe6bd"><a name="a3f3e13f5f72343068daf47c873bbe6bd"></a><a name="a3f3e13f5f72343068daf47c873bbe6bd"></a>输入文件服务器的访问地址，可以是服务器的主机名或者IP地址。</p>
</td>
</tr>
<tr id="r9d4370c88f1c443186d1bf066f12c7d2"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a9b42b4e816fb4c679b324c2797c92a7f"><a name="a9b42b4e816fb4c679b324c2797c92a7f"></a><a name="a9b42b4e816fb4c679b324c2797c92a7f"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="afa2c0342b5b74c1999ef4de5f11c8e0c"><a name="afa2c0342b5b74c1999ef4de5f11c8e0c"></a><a name="afa2c0342b5b74c1999ef4de5f11c8e0c"></a>访问文件服务器的端口。</p>
<a name="ubacd452575c14d83baa3ceb00e53f1b4"></a><a name="ubacd452575c14d83baa3ceb00e53f1b4"></a><ul id="ubacd452575c14d83baa3ceb00e53f1b4"><li>FTP协议请使用端口<span class="parmvalue" id="p438c53d55fc04ad19e0e46e9fbfbf3ec"><a name="p438c53d55fc04ad19e0e46e9fbfbf3ec"></a><a name="p438c53d55fc04ad19e0e46e9fbfbf3ec"></a>“21”</span>。</li><li>SFTP协议请使用端口<span class="parmvalue" id="pa34e4048da8148ecb5690201042eea4e"><a name="pa34e4048da8148ecb5690201042eea4e"></a><a name="pa34e4048da8148ecb5690201042eea4e"></a>“22”</span>。</li></ul>
</td>
</tr>
<tr id="r8205631f6d344155b338f71c9513bf5e"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a2189dec77c094a5999e0939eb7c83d30"><a name="a2189dec77c094a5999e0939eb7c83d30"></a><a name="a2189dec77c094a5999e0939eb7c83d30"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a50155294694b48ca885323431e8c6cca"><a name="a50155294694b48ca885323431e8c6cca"></a><a name="a50155294694b48ca885323431e8c6cca"></a>表示文件服务器的用户名称。</p>
</td>
</tr>
<tr id="r2bb8b33d1b144d1fbff83cf4ee8eb969"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="afe76cd83f59c4b718b8c585feb4f2c42"><a name="afe76cd83f59c4b718b8c585feb4f2c42"></a><a name="afe76cd83f59c4b718b8c585feb4f2c42"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a4c031e198a25489c8a36770bf6078b15"><a name="a4c031e198a25489c8a36770bf6078b15"></a><a name="a4c031e198a25489c8a36770bf6078b15"></a>表示此用户对应的密码。</p>
</td>
</tr>
</tbody>
</table>

## MRS集群连接<a name="s363f37eedcd7492bb75ef7b426b0000b"></a>

MRS集群连接包含HBase连接、HDFS连接和Hive连接，是Loader与对应各数据进行数据交换的通道。

配置MRS集群连接时，需要设置名称、选择对应的连接器“hbase-connector“、“hdfs-connector“或“hive-connector“，然后保存即可。

## 内存数据库连接<a name="s4cce8f18af2140399f068f3984d2b716"></a>

VoltDB连接是Loader与内存数据库进行数据交换的通道，配置参数如[表5](#t938be9e8c69d48a3947f014a9fdd20f0)所示。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分参数需要单击“显示高级属性“后展开，否则默认隐藏。  

**表 5**  voltdb-connector配置

<a name="t938be9e8c69d48a3947f014a9fdd20f0"></a>
<table><thead align="left"><tr id="r097a75420a3b4ed88bc51c782e4fae87"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a6365043186e343539338bad370524e53"><a name="a6365043186e343539338bad370524e53"></a><a name="a6365043186e343539338bad370524e53"></a><strong id="a2b65222c22a0498c87341e20e64fea4e"><a name="a2b65222c22a0498c87341e20e64fea4e"></a><a name="a2b65222c22a0498c87341e20e64fea4e"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a28d5885193484914b01a86b697b5b24c"><a name="a28d5885193484914b01a86b697b5b24c"></a><a name="a28d5885193484914b01a86b697b5b24c"></a><strong id="ad9bad41fd3b84c17b6c4da4106be81ce"><a name="ad9bad41fd3b84c17b6c4da4106be81ce"></a><a name="ad9bad41fd3b84c17b6c4da4106be81ce"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r43fd02900bae416f8e9e695511407ba8"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="abe7462ef44de44b7845af2806e90535b"><a name="abe7462ef44de44b7845af2806e90535b"></a><a name="abe7462ef44de44b7845af2806e90535b"></a>名称</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ae9924d3044534a7c9d3da7aa6726a9e9"><a name="ae9924d3044534a7c9d3da7aa6726a9e9"></a><a name="ae9924d3044534a7c9d3da7aa6726a9e9"></a>指定一个Loader连接的名称。</p>
</td>
</tr>
<tr id="r49c85370e93a4f4cb7879f28290c4e96"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a90dfb6a0f13248eaa0a98141517f7d33"><a name="a90dfb6a0f13248eaa0a98141517f7d33"></a><a name="a90dfb6a0f13248eaa0a98141517f7d33"></a>数据库服务器列表</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p856836816354"><a name="zh-cn_topic_0070859523_p856836816354"></a><a name="zh-cn_topic_0070859523_p856836816354"></a>表示数据库的访问地址，可以是IP地址或者域名。支持配置多个数据库地址，使用英文逗号分隔。</p>
</td>
</tr>
<tr id="rbaa2f2854d1b44c18045513d1589c811"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0070859523_p521594416354"><a name="zh-cn_topic_0070859523_p521594416354"></a><a name="zh-cn_topic_0070859523_p521594416354"></a>端口</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a307ddc5e2fe145e5a120511e8884ca21"><a name="a307ddc5e2fe145e5a120511e8884ca21"></a><a name="a307ddc5e2fe145e5a120511e8884ca21"></a>表示数据库的访问端口。</p>
</td>
</tr>
<tr id="rcae5106c02f74407a0204eb0f91e2fcb"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a428164e5478345208fb08c31b3b76992"><a name="a428164e5478345208fb08c31b3b76992"></a><a name="a428164e5478345208fb08c31b3b76992"></a>用户名</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0070859523_p853035416354"><a name="zh-cn_topic_0070859523_p853035416354"></a><a name="zh-cn_topic_0070859523_p853035416354"></a>表示连接数据库使用的用户名称。</p>
</td>
</tr>
<tr id="r005521f35d4540c0beba4562718c2119"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a1e031466ee554438aa0d9ea42753c286"><a name="a1e031466ee554438aa0d9ea42753c286"></a><a name="a1e031466ee554438aa0d9ea42753c286"></a>密码</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="aaf84a36a4a6d44bb899f5ee948b826ef"><a name="aaf84a36a4a6d44bb899f5ee948b826ef"></a><a name="aaf84a36a4a6d44bb899f5ee948b826ef"></a>表示此用户对应的密码。需要与实际密码保持一致。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  高级属性配置

<a name="tf302c3bdf27a4cc499e26406b30fff77"></a>
<table><thead align="left"><tr id="r0d1328207d0c43adaffeef5814fb4725"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a67b542802a9a4a1185557ced7b43dd30"><a name="a67b542802a9a4a1185557ced7b43dd30"></a><a name="a67b542802a9a4a1185557ced7b43dd30"></a><strong id="a99955ffdf2da4c10a7fc991c79008dda"><a name="a99955ffdf2da4c10a7fc991c79008dda"></a><a name="a99955ffdf2da4c10a7fc991c79008dda"></a>参数</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a3267a2a74c68441b9725c5a422effd20"><a name="a3267a2a74c68441b9725c5a422effd20"></a><a name="a3267a2a74c68441b9725c5a422effd20"></a><strong id="aefcf540f0e3c48fe90c271fd766e47b4"><a name="aefcf540f0e3c48fe90c271fd766e47b4"></a><a name="aefcf540f0e3c48fe90c271fd766e47b4"></a>说明</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r66af99a6ab784692a191f7fe6ec3cf07"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ad93a6e121d204bae9d01a20d567c2f9e"><a name="ad93a6e121d204bae9d01a20d567c2f9e"></a><a name="ad93a6e121d204bae9d01a20d567c2f9e"></a>连接属性</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="ac9f7f7e5f29649d5a0c8dd8508b46823"><a name="ac9f7f7e5f29649d5a0c8dd8508b46823"></a><a name="ac9f7f7e5f29649d5a0c8dd8508b46823"></a>内存数据库的SQL中保留关键字的定界符。</p>
</td>
</tr>
</tbody>
</table>

