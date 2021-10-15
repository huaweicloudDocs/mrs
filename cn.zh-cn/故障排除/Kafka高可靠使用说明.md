# Kafka高可靠使用说明<a name="mrs_03_0198"></a>

## Kafka 高可靠、高可用说明<a name="zh-cn_topic_0167274830_section13352172843014"></a>

Kafka消息传输保障机制，可以通过配置不同的参数来保障消息传输，进而满足不同的性能和可靠性要求的应用场景。

-   **Kafka高可用、高性能**

    如果业务需要保证高可用和高性能，可以采用参数：

    <a name="zh-cn_topic_0167274830_table184941310114317"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0167274830_row157614102438"><th class="cellrowborder" valign="top" width="26%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0167274830_p1557681015437"><a name="zh-cn_topic_0167274830_p1557681015437"></a><a name="zh-cn_topic_0167274830_p1557681015437"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="10%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0167274830_p18576141017437"><a name="zh-cn_topic_0167274830_p18576141017437"></a><a name="zh-cn_topic_0167274830_p18576141017437"></a>默认值</p>
    </th>
    <th class="cellrowborder" valign="top" width="64%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0167274830_p1857611016439"><a name="zh-cn_topic_0167274830_p1857611016439"></a><a name="zh-cn_topic_0167274830_p1857611016439"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0167274830_row105761510154316"><td class="cellrowborder" valign="top" width="26%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0167274830_p1657614103433"><a name="zh-cn_topic_0167274830_p1657614103433"></a><a name="zh-cn_topic_0167274830_p1657614103433"></a>unclean.leader.election.enable</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0167274830_p185761310114312"><a name="zh-cn_topic_0167274830_p185761310114312"></a><a name="zh-cn_topic_0167274830_p185761310114312"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0167274830_p8576410164319"><a name="zh-cn_topic_0167274830_p8576410164319"></a><a name="zh-cn_topic_0167274830_p8576410164319"></a>是否允许不在ISR中的副本被选举为Leader，若设置为true，可能会造成数据丢失。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row14576201019435"><td class="cellrowborder" valign="top" width="26%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0167274830_p657618108434"><a name="zh-cn_topic_0167274830_p657618108434"></a><a name="zh-cn_topic_0167274830_p657618108434"></a>auto.leader.rebalance.enable</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0167274830_p135767105433"><a name="zh-cn_topic_0167274830_p135767105433"></a><a name="zh-cn_topic_0167274830_p135767105433"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0167274830_p64841155185920"><a name="zh-cn_topic_0167274830_p64841155185920"></a><a name="zh-cn_topic_0167274830_p64841155185920"></a>是否使用Leader自动均衡功能。</p>
    <p id="zh-cn_topic_0167274830_p1357612107436"><a name="zh-cn_topic_0167274830_p1357612107436"></a><a name="zh-cn_topic_0167274830_p1357612107436"></a>如果设为true，Controller会周期性的为所有节点的每个分区均衡Leader，将Leader分配给更优先的副本。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row1657701018436"><td class="cellrowborder" valign="top" width="26%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0167274830_p4577191004312"><a name="zh-cn_topic_0167274830_p4577191004312"></a><a name="zh-cn_topic_0167274830_p4577191004312"></a>acks</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0167274830_p15577171024316"><a name="zh-cn_topic_0167274830_p15577171024316"></a><a name="zh-cn_topic_0167274830_p15577171024316"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0167274830_p194641391446"><a name="zh-cn_topic_0167274830_p194641391446"></a><a name="zh-cn_topic_0167274830_p194641391446"></a>需要Leader确认消息是否已经接收并认为已经处理完成。该参数会影响消息的可靠性和性能。</p>
    <a name="zh-cn_topic_0167274830_ul94002931718"></a><a name="zh-cn_topic_0167274830_ul94002931718"></a><ul id="zh-cn_topic_0167274830_ul94002931718"><li>acks=0 ：如果设置为0，Producer将不会等待服务端任何响应。消息将会被认为成功。</li><li>acks=1 ：如果设置为1，当副本所在Leader确认数据已写入，但是其不会等待所有的副本完全写入即返回响应。在这种情况下，如果Leader确认后但是副本未同步完成时Leader异常，那么数据就会丢失。</li><li>acks=-1 ：如果设置为-1（all），意味着等待所有的同步副本确认后才认为成功，配合min.insync.replicas可以确保多副本写入成功，只要有一个副本保持活跃状态，记录将不会丢失。<div class="note" id="note52701758279"><a name="note52701758279"></a><a name="note52701758279"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p152701451274"><a name="p152701451274"></a><a name="p152701451274"></a>该参数在kafka客户端配置文件中配置。</p>
    </div></div>
    </li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row4919345439"><td class="cellrowborder" valign="top" width="26%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0167274830_p55772010144315"><a name="zh-cn_topic_0167274830_p55772010144315"></a><a name="zh-cn_topic_0167274830_p55772010144315"></a>min.insync.replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0167274830_p2577510114314"><a name="zh-cn_topic_0167274830_p2577510114314"></a><a name="zh-cn_topic_0167274830_p2577510114314"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0167274830_p7577171017434"><a name="zh-cn_topic_0167274830_p7577171017434"></a><a name="zh-cn_topic_0167274830_p7577171017434"></a>当Producer设置acks为-1时，指定需要写入成功的副本的最小数目。</p>
    </td>
    </tr>
    </tbody>
    </table>

    配置高可用、高性能的影响：

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >配置高可用、高性能模式后，数据可靠性会降低。在磁盘故障、节点故障等场景下存在数据丢失风险。

-   **Kafka高可靠性配置说明**

    如果业务需要保证数据高可靠性，可以采用相关参数：

    <a name="zh-cn_topic_0167274830_table1486721814582"></a>
    <table><tbody><tr id="zh-cn_topic_0167274830_row1691731855816"><td class="cellrowborder" valign="top" width="26%"><p id="zh-cn_topic_0167274830_p12918818185817"><a name="zh-cn_topic_0167274830_p12918818185817"></a><a name="zh-cn_topic_0167274830_p12918818185817"></a>参数</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%"><p id="zh-cn_topic_0167274830_p0918111814583"><a name="zh-cn_topic_0167274830_p0918111814583"></a><a name="zh-cn_topic_0167274830_p0918111814583"></a>建议值</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%"><p id="zh-cn_topic_0167274830_p59183188584"><a name="zh-cn_topic_0167274830_p59183188584"></a><a name="zh-cn_topic_0167274830_p59183188584"></a>说明</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row1891841819583"><td class="cellrowborder" valign="top" width="26%"><p id="zh-cn_topic_0167274830_p391891810586"><a name="zh-cn_topic_0167274830_p391891810586"></a><a name="zh-cn_topic_0167274830_p391891810586"></a>unclean.leader.election.enable</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%"><p id="zh-cn_topic_0167274830_p1791814186587"><a name="zh-cn_topic_0167274830_p1791814186587"></a><a name="zh-cn_topic_0167274830_p1791814186587"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%"><p id="zh-cn_topic_0167274830_p189181618175813"><a name="zh-cn_topic_0167274830_p189181618175813"></a><a name="zh-cn_topic_0167274830_p189181618175813"></a>是否允许不在ISR中的副本被选举为Leader。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row2084062916584"><td class="cellrowborder" valign="top" width="26%"><p id="zh-cn_topic_0167274830_p1683432945820"><a name="zh-cn_topic_0167274830_p1683432945820"></a><a name="zh-cn_topic_0167274830_p1683432945820"></a>acks</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%"><p id="zh-cn_topic_0167274830_p12834112915583"><a name="zh-cn_topic_0167274830_p12834112915583"></a><a name="zh-cn_topic_0167274830_p12834112915583"></a>-1</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%"><p id="zh-cn_topic_0167274830_p148341829135818"><a name="zh-cn_topic_0167274830_p148341829135818"></a><a name="zh-cn_topic_0167274830_p148341829135818"></a>Producer需要Leader确认消息是否已经接收并认为已经处理完成。</p>
    <p id="zh-cn_topic_0167274830_p78341129145815"><a name="zh-cn_topic_0167274830_p78341129145815"></a><a name="zh-cn_topic_0167274830_p78341129145815"></a>acks=-1需要表示等待在ISR列表的副本都确认接收到消息并处理完成才表示消息成功。配合min.insync.replicas可以确保多副本写入成功，只要有一个副本保持活跃状态，记录将不会丢失。</p>
    <div class="note" id="note1171033112710"><a name="note1171033112710"></a><a name="note1171033112710"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1317203310278"><a name="p1317203310278"></a><a name="p1317203310278"></a>该参数在kafka客户端配置文件中配置。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274830_row18840152955818"><td class="cellrowborder" valign="top" width="26%"><p id="zh-cn_topic_0167274830_p108340299588"><a name="zh-cn_topic_0167274830_p108340299588"></a><a name="zh-cn_topic_0167274830_p108340299588"></a>min.insync.replicas</p>
    </td>
    <td class="cellrowborder" valign="top" width="10%"><p id="zh-cn_topic_0167274830_p983420299583"><a name="zh-cn_topic_0167274830_p983420299583"></a><a name="zh-cn_topic_0167274830_p983420299583"></a>2</p>
    </td>
    <td class="cellrowborder" valign="top" width="64%"><p id="zh-cn_topic_0167274830_p583482913589"><a name="zh-cn_topic_0167274830_p583482913589"></a><a name="zh-cn_topic_0167274830_p583482913589"></a>当Producer设置acks为-1时，指定需要写入成功的副本的最小数目。</p>
    <p id="zh-cn_topic_0167274830_p43901435141810"><a name="zh-cn_topic_0167274830_p43901435141810"></a><a name="zh-cn_topic_0167274830_p43901435141810"></a>需要满足min.insync.replicas &lt;= replication.factor。</p>
    </td>
    </tr>
    </tbody>
    </table>

    配置高可靠性的影响：

    -   性能降低：

        需要所有的ISR列表副本，且满足最小成功的副本数确认写入成功。这样会导致单条消息时延增加，客户端处理能力下降，具体性能以现场实际测试数据为准。

    -   可用性降低：

        不允许不在ISR中的副本被选举为Leader。如果Leader下线时，其他副本均不在ISR列表中，那么该分区将保持不可用，直到Leader节点恢复。

        需要所有的ISR列表副本，且满足最小成功的副本数确认写入成功。当分区的一个副本所在节点故障时，无法满足最小成功的副本数，那么将会导致业务写入失败。



## 配置影响<a name="zh-cn_topic_0167274830_section1833312011532"></a>

请根据业务场景对可靠性和性能要求进行评估，采用合理参数配置。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   对于价值数据，两种场景下建议Kafka数据目录磁盘配置raid1或者raid5，从而提高单个磁盘故障情况下数据可靠性。
>-   不同Producer API对应的acks参数名称不同
>    -   新Producer API
>        指**org.apache.kafka.clients.producer.KafkaProducer**中定义的接口，acks配置为acks。
>    -   旧Producer API
>        指**kafka.producer.Producer**中定义的接口，acks配置名称为request.required.acks。
>-   参数配置项均为Topic级别可修改的参数，默认采用服务级配置。可针对不同Topic可靠性要求对Topic进行单独配置。
>    例如，配置Topic名称为test的可靠性参数：
>    _**kafka-topics.sh --zookeeper 192.168.1.205:2181/kafka --alter --topic test  --config  unclean.leader.election.enable=false --config min.insync.replicas=2**_
>    其中192.168.1.205为ZooKeeper业务IP地址。
>-   如果修改服务级配置需要重启Kafka，建议在变更窗口做服务级配置修改。

