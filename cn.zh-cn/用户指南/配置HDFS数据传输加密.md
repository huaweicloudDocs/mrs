# 配置HDFS数据传输加密<a name="admin_guide_000282"></a>

## 设置HDFS安全通道加密<a name="sfe6311ba7b3341a6b4950c8bf6fd6646"></a>

默认情况下，组件间的通道是不加密的。您可以配置如下参数，设置安全通道为加密的。

参数修改入口：在FusionInsight Manager系统中，选择“集群 \>  _待操作集群的名称_  \> 服务 \> HDFS \> 配置”，展开“全部配置”页签。在搜索框中输入参数名称。

>![](public_sys-resources/icon-note.gif) **说明：** 
>配置后应重启对应服务使参数生效。

**表 1**  参数说明

<a name="zh-cn_topic_0046736712_table11673056"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046736712_row42803771"><th class="cellrowborder" valign="top" width="30.61%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0046736712_p44553466"><a name="zh-cn_topic_0046736712_p44553466"></a><a name="zh-cn_topic_0046736712_p44553466"></a>配置项</p>
</th>
<th class="cellrowborder" valign="top" width="46.94%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0046736712_p52061026"><a name="zh-cn_topic_0046736712_p52061026"></a><a name="zh-cn_topic_0046736712_p52061026"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="22.45%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0046736712_p56193562"><a name="zh-cn_topic_0046736712_p56193562"></a><a name="zh-cn_topic_0046736712_p56193562"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046736712_row55384650"><td class="cellrowborder" valign="top" width="30.61%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736712_p56971675"><a name="zh-cn_topic_0046736712_p56971675"></a><a name="zh-cn_topic_0046736712_p56971675"></a>hadoop.rpc.protection</p>
</td>
<td class="cellrowborder" valign="top" width="46.94%" headers="mcps1.2.4.1.2 "><div class="notice" id="note1537703014317"><a name="note1537703014317"></a><a name="note1537703014317"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><a name="ul1950212178439"></a><a name="ul1950212178439"></a><ul id="ul1950212178439"><li>设置后需要重启服务生效，且不支持滚动重启。</li><li>设置后需要重新下载客户端配置，否则HDFS无法提供读写服务。</li></ul>
</div></div>
<p id="zh-cn_topic_0046736712_p51302964"><a name="zh-cn_topic_0046736712_p51302964"></a><a name="zh-cn_topic_0046736712_p51302964"></a>设置Hadoop中各模块的RPC通道是否加密。通道包括：</p>
<a name="zh-cn_topic_0046736712_ul59073500"></a><a name="zh-cn_topic_0046736712_ul59073500"></a><ul id="zh-cn_topic_0046736712_ul59073500"><li>客户端访问HDFS的RPC通道。</li><li>HDFS中各模块间的RPC通道，如DataNode与NameNode间。</li><li>客户端访问Yarn的RPC通道</li><li>NodeManager和ResourceManager间的RPC通道。</li><li>Spark访问Yarn，Spark访问HDFS的RPC通道。</li><li>Mapreduce访问Yarn，MapReduce访问HDFS的RPC通道。</li><li>HBase访问HDFS的RPC通道。</li></ul>
<div class="note" id="zh-cn_topic_0046736712_note4893323"><a name="zh-cn_topic_0046736712_note4893323"></a><a name="zh-cn_topic_0046736712_note4893323"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="p154556399431"><a name="p154556399431"></a><a name="p154556399431"></a>设置后全局生效，即Hadoop中各模块的RPC通道的加密属性全部生效。</p>
</div></div>
</td>
<td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.3 "><a name="ul126721846184612"></a><a name="ul126721846184612"></a><ul id="ul126721846184612"><li>安全模式：privacy</li><li>普通模式：authentication</li></ul>
<div class="note" id="zh-cn_topic_0046736712_note27061374"><a name="zh-cn_topic_0046736712_note27061374"></a><a name="zh-cn_topic_0046736712_note27061374"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0046736712_ul42225780"></a><a name="zh-cn_topic_0046736712_ul42225780"></a><ul id="zh-cn_topic_0046736712_ul42225780"><li>“authentication”：只进行认证，不加密。</li><li>“integrity”：进行认证和一致性校验。</li><li>“privacy”：进行认证、一致性校验、加密。</li></ul>
</div></div>
</td>
</tr>
<tr id="zh-cn_topic_0046736712_row17957024"><td class="cellrowborder" valign="top" width="30.61%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736712_p45232806"><a name="zh-cn_topic_0046736712_p45232806"></a><a name="zh-cn_topic_0046736712_p45232806"></a>dfs.encrypt.data.transfer</p>
</td>
<td class="cellrowborder" valign="top" width="46.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736712_p39978669"><a name="zh-cn_topic_0046736712_p39978669"></a><a name="zh-cn_topic_0046736712_p39978669"></a>设置客户端访问HDFS的通道和HDFS数据传输通道是否加密。HDFS数据传输通道包括DataNode间的数据传输通道，客户端访问DataNode的DT（Data Transfer）通道。设置为“true”表示加密，默认不加密。</p>
<div class="note" id="zh-cn_topic_0046736712_note24263704"><a name="zh-cn_topic_0046736712_note24263704"></a><a name="zh-cn_topic_0046736712_note24263704"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="zh-cn_topic_0046736712_ul17046748"></a><a name="zh-cn_topic_0046736712_ul17046748"></a><ul id="zh-cn_topic_0046736712_ul17046748"><li>仅当hadoop.rpc.protection设置为privacy时使用。</li><li>业务数据传输量较大时，默认启用加密对性能影响严重，使用时请注意。</li><li>如果互信集群的一端集群配置了数据传输加密，则对端集群也需配置同样的数据传输加密。</li></ul>
</div></div>
</td>
<td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736712_p40351445"><a name="zh-cn_topic_0046736712_p40351445"></a><a name="zh-cn_topic_0046736712_p40351445"></a>false</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736712_row27618686"><td class="cellrowborder" valign="top" width="30.61%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736712_p22521054"><a name="zh-cn_topic_0046736712_p22521054"></a><a name="zh-cn_topic_0046736712_p22521054"></a>dfs.encrypt.data.transfer.algorithm</p>
</td>
<td class="cellrowborder" valign="top" width="46.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736712_p12266058"><a name="zh-cn_topic_0046736712_p12266058"></a><a name="zh-cn_topic_0046736712_p12266058"></a>设置客户端访问HDFS的通道和HDFS数据传输通道的加密算法。只有在dfs.encrypt.data.transfer配置项设置为“true”，此参数才会生效。</p>
<div class="note" id="zh-cn_topic_0046736712_note43285665"><a name="zh-cn_topic_0046736712_note43285665"></a><a name="zh-cn_topic_0046736712_note43285665"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0046736712_p54026667"><a name="zh-cn_topic_0046736712_p54026667"></a><a name="zh-cn_topic_0046736712_p54026667"></a>缺省值为“3des”，表示采用3DES算法进行加密。此处的值还可以设置为“rc4”，避免出现安全隐患，不推荐设置为该值。</p>
</div></div>
</td>
<td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736712_p14083945"><a name="zh-cn_topic_0046736712_p14083945"></a><a name="zh-cn_topic_0046736712_p14083945"></a>3des</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736712_row59646646"><td class="cellrowborder" valign="top" width="30.61%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736712_p66649034"><a name="zh-cn_topic_0046736712_p66649034"></a><a name="zh-cn_topic_0046736712_p66649034"></a>dfs.encrypt.data.transfer.cipher.suites</p>
</td>
<td class="cellrowborder" valign="top" width="46.94%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736712_p29862637"><a name="zh-cn_topic_0046736712_p29862637"></a><a name="zh-cn_topic_0046736712_p29862637"></a>可以设置为空或“AES/CTR/NoPadding”，用于指定数据加密的密码套件。如果不指定此参数，则使用“dfs.encrypt.data.transfer.algorithm”参数指定的加密算法进行数据加密。默认值为<span class="filepath" id="filepath5082750992652"><a name="filepath5082750992652"></a><a name="filepath5082750992652"></a>“AES/CTR/NoPadding”</span>。</p>
</td>
<td class="cellrowborder" valign="top" width="22.45%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736712_p2954570"><a name="zh-cn_topic_0046736712_p2954570"></a><a name="zh-cn_topic_0046736712_p2954570"></a>AES/CTR/NoPadding</p>
</td>
</tr>
</tbody>
</table>

