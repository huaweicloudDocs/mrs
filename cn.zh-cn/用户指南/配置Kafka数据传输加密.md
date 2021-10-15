# 配置Kafka数据传输加密<a name="admin_guide_000281"></a>

## 操作场景<a name="zh-cn_topic_0263899567_saa56dc5c8a964391aee8542e930eb2c7"></a>

Kafka客户端和Broker之间的数据传输默认采用明文传输，客户端可能部署在不受信任的网络中，传输的数据可能遭到泄漏和篡改。

## 操作步骤<a name="zh-cn_topic_0263899567_s6daaf30ddf924b25b7a3fb1cb5d0342a"></a>

默认情况下，组件间的通道是不加密的。用户可以配置如下参数，设置安全通道为加密的。

参数修改入口：在FusionInsight Manager系统中，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置”，展开“全部配置”页签。在搜索框中输入参数名称。

>![](public_sys-resources/icon-note.gif) **说明：** 
>配置后应重启对应服务使参数生效。

Kafka服务端的传输加密相关配置参数如[表1](#zh-cn_topic_0263899567_zh-cn_topic_0046736711_d0e28839)所示。

**表 1**  Kafka服务端传输加密参数

<a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_d0e28839"></a>
<table><thead align="left"><tr id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_row21883847"><th class="cellrowborder" valign="top" width="35.71%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p27761143"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p27761143"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p27761143"></a>配置项</p>
</th>
<th class="cellrowborder" valign="top" width="37.760000000000005%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p34060083"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p34060083"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p34060083"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="26.530000000000005%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p7403364"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p7403364"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p7403364"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_row62801650"><td class="cellrowborder" valign="top" width="35.71%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53768900"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53768900"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53768900"></a>ssl.mode.enable</p>
</td>
<td class="cellrowborder" valign="top" width="37.760000000000005%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p60313667"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p60313667"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p60313667"></a>是否开启SSL对应服务。如果设置为“true”，那么Broker启动过程中会启动SSL的相关服务。</p>
</td>
<td class="cellrowborder" valign="top" width="26.530000000000005%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53568854"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53568854"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p53568854"></a>false</p>
</td>
</tr>
<tr id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_row12357643"><td class="cellrowborder" valign="top" width="35.71%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p61445016"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p61445016"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p61445016"></a>security.inter.broker.protocol</p>
</td>
<td class="cellrowborder" valign="top" width="37.760000000000005%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p10990381"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p10990381"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p10990381"></a>Broker间通信协议。支持PLAINTEXT、SSL、SASL_PLAINTEXT、SASL_SSL这四种协议类型。</p>
</td>
<td class="cellrowborder" valign="top" width="26.530000000000005%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p17805683"><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p17805683"></a><a name="zh-cn_topic_0263899567_zh-cn_topic_0046736711_p17805683"></a>SASL_PLAINTEXT</p>
</td>
</tr>
</tbody>
</table>

“ssl.mode.enable”配置为“true”后，Broker会开启SSL、SASL\_SSL两种协议的服务，然后服务端或者客户端才能配置相关的SSL协议，进行传输加密通信。

