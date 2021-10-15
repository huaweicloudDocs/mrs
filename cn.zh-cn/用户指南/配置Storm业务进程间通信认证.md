# 配置Storm业务进程间通信认证<a name="admin_guide_000283"></a>

## 操作场景<a name="zh-cn_topic_0263899630_sd03886ad93be4d978770d1e0270da941"></a>

Storm的业务进程在通信过程的认证功能默认是关闭的，客户端可能部署在不受信任的网络中，传输的数据可能遭到泄漏和篡改。

## 操作步骤<a name="zh-cn_topic_0263899630_s17f10bb95c2245c6846a1976c3480ae0"></a>

参数修改入口：在FusionInsight Manager系统中，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Storm \> 配置”，展开“全部配置”页签。在搜索框中输入参数名称。

>![](public_sys-resources/icon-note.gif) **说明：** 
>配置后应重启对应服务使参数生效。

**表 1**  参数说明

<a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_table14847872"></a>
<table><thead align="left"><tr id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_row32979223"><th class="cellrowborder" valign="top" width="35.71%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p54071387"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p54071387"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p54071387"></a>配置项</p>
</th>
<th class="cellrowborder" valign="top" width="37.760000000000005%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p17706220"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p17706220"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p17706220"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="26.530000000000005%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p24917681"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p24917681"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p24917681"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_row5066258"><td class="cellrowborder" valign="top" width="35.71%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p7713785"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p7713785"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p7713785"></a>storm.messaging.netty.authentication</p>
</td>
<td class="cellrowborder" valign="top" width="37.760000000000005%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p20836811"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p20836811"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p20836811"></a>是否开启业务进程间Netty通信认证，默认关闭，可以为指定拓扑选择开启。如果在客户端配置该参数，以客户端配置为准，没有则以集群侧的配置为准。</p>
<div class="note" id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_note53313577"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_note53313577"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_note53313577"></a><span class="notetitle"> 说明： </span><div class="notebody"><p class="textintable" id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p10060146"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p10060146"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p10060146"></a>该配置项开启会对拓扑的吞吐量造成较大影响，请谨慎使用。</p>
</div></div>
</td>
<td class="cellrowborder" valign="top" width="26.530000000000005%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p9565526"><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p9565526"></a><a name="zh-cn_topic_0263899630_zh-cn_topic_0046736713_p9565526"></a>false</p>
</td>
</tr>
</tbody>
</table>

