# 配置HBase允许修改操作的IP地址白名单<a name="admin_guide_000278"></a>

当HBase集群开启Replication功能时，为了保护主备集群的HBase数据一致性，对备集群HBase增加了数据修改操作的保护。当备集群HBase接收到数据修改操作的RPC请求时，首先检查发出该请求的用户的权限，只有HBase管理用户才有修改权限；其次检查发出该请求的IP的有效性，备集群只接收来自IP白名单中的机器发起的修改请求。IP白名单通过配置项“hbase.replication.allowedIPs”配置。

参数修改入口：在FusionInsight Manager系统中，选择“集群 \>  _待操作集群的名称_  \> 服务 \>  _服务名_  \> 配置”，展开“全部配置”页签。在搜索框中输入参数名称。

**表 1**  参数说明

<a name="zh-cn_topic_0046736705_table62042342"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046736705_row63757280"><th class="cellrowborder" valign="top" width="28.28%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0046736705_p64066064"><a name="zh-cn_topic_0046736705_p64066064"></a><a name="zh-cn_topic_0046736705_p64066064"></a>配置参数</p>
</th>
<th class="cellrowborder" valign="top" width="56.57%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0046736705_p63500359"><a name="zh-cn_topic_0046736705_p63500359"></a><a name="zh-cn_topic_0046736705_p63500359"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0046736705_p53754906"><a name="zh-cn_topic_0046736705_p53754906"></a><a name="zh-cn_topic_0046736705_p53754906"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="row408194120658"><td class="cellrowborder" valign="top" width="28.28%" headers="mcps1.2.4.1.1 "><p id="p3673747720658"><a name="p3673747720658"></a><a name="p3673747720658"></a>hbase.replication.allowedIPs</p>
</td>
<td class="cellrowborder" valign="top" width="56.57%" headers="mcps1.2.4.1.2 "><p id="p44373286202629"><a name="p44373286202629"></a><a name="p44373286202629"></a>仅允许指定IP地址的复制请求。支持逗号分隔型regex模式。以下模式均支持：</p>
<a name="ul38669003202645"></a><a name="ul38669003202645"></a><ul id="ul38669003202645"><li>Regex模式<p id="p108725611462"><a name="p108725611462"></a><a name="p108725611462"></a>例如: 10.18.40.* , 10.18.* , 10.18.40.11</p>
</li><li>Range模式（只能指定八位字节的最后一个的范围）<p id="p981694194710"><a name="p981694194710"></a><a name="p981694194710"></a>例如: 10.18.40.[10-20]</p>
</li></ul>
<p id="p6750859161715"><a name="p6750859161715"></a><a name="p6750859161715"></a>参数值默认为空，为空时IP白名单为备集群RegionServer的IP，表示只接受来自备集群RegionServer的修改请求。</p>
</td>
<td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.4.1.3 "><p id="p4665895820658"><a name="p4665895820658"></a><a name="p4665895820658"></a>N/A</p>
</td>
</tr>
</tbody>
</table>

