# 管理Kafka集群<a name="ZH-CN_TOPIC_0156828071"></a>

管理Kafka集群包含以下内容：

-   [添加集群到KafkaManager的WebUI界面](#section8713185103014)
-   [更新集群参数](#section776745110472)
-   [删除KafkaManager的WebUI界面的集群](#section656918369521)

## 添加集群到KafkaManager的WebUI界面<a name="section8713185103014"></a>

首次创建Kafka集群后会在KafkaManager的WebUI界面创建名为my-cluster的默认Kafka集群，用户也可以在KafkaManager的WebUI界面自行添加已经通过MRS控制台创建的Kafka集群，用于管理多个Kafka集群。

1.  登录KafkaManager的WebUI界面。
2.  在页面上方选择“Cluster \> Add Cluster“  。

    **图 1**  添加集群<a name="fig06211347173620"></a>  
    ![](figures/添加集群.png "添加集群")

3.  设置待添加集群的参数，如下参数请参考样例，其他参数默认不需要修改。

    **表 1**  需修改的集群参数

    <a name="table19287112011164"></a>
    <table><thead align="left"><tr id="row142881620161613"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p428832019167"><a name="p428832019167"></a><a name="p428832019167"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p1728811208167"><a name="p1728811208167"></a><a name="p1728811208167"></a>取值样例</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p16288152012163"><a name="p16288152012163"></a><a name="p16288152012163"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1328842018161"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p112881820151615"><a name="p112881820151615"></a><a name="p112881820151615"></a>Cluster Name</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p15288820191616"><a name="p15288820191616"></a><a name="p15288820191616"></a>mrs-demo</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p4288192015161"><a name="p4288192015161"></a><a name="p4288192015161"></a>待添加集群在KafkaManager的WebUI界面中显示的名称。</p>
    </td>
    </tr>
    <tr id="row428816206164"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1528819204161"><a name="p1528819204161"></a><a name="p1528819204161"></a>Cluster Zookeeper Hosts</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p569618424174"><a name="p569618424174"></a><a name="p569618424174"></a>zk1_ip:zk1_port, zk2_ip:zk2_port/kafka</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p62881220171610"><a name="p62881220171610"></a><a name="p62881220171610"></a>待添加集群的Zookeeper地址。</p>
    </td>
    </tr>
    <tr id="row192882020131615"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p2288520111616"><a name="p2288520111616"></a><a name="p2288520111616"></a>Kafka Version</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1128892081611"><a name="p1128892081611"></a><a name="p1128892081611"></a>1.1.0</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p072102521813"><a name="p072102521813"></a><a name="p072102521813"></a>待添加集群的Kafka版本，默认1.1.0。</p>
    </td>
    </tr>
    <tr id="row1225617469305"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p102561146143014"><a name="p102561146143014"></a><a name="p102561146143014"></a>Enable JMX Polling (Set JMX_PORT env variable before starting kafka server)</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p0256546113015"><a name="p0256546113015"></a><a name="p0256546113015"></a>勾选</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p14256134613010"><a name="p14256134613010"></a><a name="p14256134613010"></a>-</p>
    </td>
    </tr>
    <tr id="row162881620111612"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p034693182215"><a name="p034693182215"></a><a name="p034693182215"></a>Poll consumer information (Not recommended for large # of consumers)</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p144891512219"><a name="p144891512219"></a><a name="p144891512219"></a>勾选</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p19289720161616"><a name="p19289720161616"></a><a name="p19289720161616"></a>-</p>
    </td>
    </tr>
    <tr id="row228922016166"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p634693202212"><a name="p634693202212"></a><a name="p634693202212"></a>Enable Active OffsetCache (Not recommended for large # of consumers)</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1048715519225"><a name="p1048715519225"></a><a name="p1048715519225"></a>勾选</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p14289182017162"><a name="p14289182017162"></a><a name="p14289182017162"></a>-</p>
    </td>
    </tr>
    <tr id="row79341058112113"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p14935115817216"><a name="p14935115817216"></a><a name="p14935115817216"></a>Display Broker and Topic Size (only works after applying this patch)</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p10935458102110"><a name="p10935458102110"></a><a name="p10935458102110"></a>勾选</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1693585822118"><a name="p1693585822118"></a><a name="p1693585822118"></a>-</p>
    </td>
    </tr>
    <tr id="row201616212229"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p10288182011169"><a name="p10288182011169"></a><a name="p10288182011169"></a>Security Protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p162881620171616"><a name="p162881620171616"></a><a name="p162881620171616"></a>PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><a name="ul1533223923116"></a><a name="ul1533223923116"></a><ul id="ul1533223923116"><li>开启Kerberos的Kafka集群选择SASL_PLAINTEXT</li><li>未开启Kerberos集群选择PLAINTEXT</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“Save“完成添加集群。

## 更新集群参数<a name="section776745110472"></a>

1.  登录KafkaManager的WebUI界面。
2.  在对应集群的“Operations“列单击“Modify“。

    **图 2**  更新集群参数<a name="fig6644193915811"></a>  
    ![](figures/更新集群参数.png "更新集群参数")

3.  进入集群配置参数页面，修改集群参数。

## 删除KafkaManager的WebUI界面的集群<a name="section656918369521"></a>

1.  登录KafkaManager的WebUI界面。
2.  在对应集群的“Operations“列单击“Disable“。

    **图 3**  停用集群<a name="fig148908447119"></a>  
    ![](figures/停用集群.png "停用集群")

3.  等待集群列表页面的“Operations“列出现“Delete“或“Enable“时，单击“Delete“删除集群。也可以单击“Enable“启用集群。

    **图 4**  启用或删除集群<a name="fig1388733119417"></a>  
    ![](figures/启用或删除集群.png "启用或删除集群")


