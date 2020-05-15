# 在Ranger中配置HBase的访问权限<a name="ZH-CN_TOPIC_0207621833"></a>

在创建完安装了Ranger组件的MRS集群后，HBase的权限控制暂未集成在Ranger，本章节主要介绍HBase组件如何集成在Ranger中。

1.  登录Ranger WebUI界面。
2.  在“Service Manager”中的HBASE处，单击![](figures/zh-cn_image_0213987371.png)添加HBase Service。

    **图 1**  添加HBase Service<a name="fig1355517248383"></a>  
    ![](figures/添加HBase-Service.png "添加HBase-Service")

3.  请参考[表1](#table74220350178)填写添加HBase Service的相关参数，未在表中列出的参数请保持默认值。

    **表 1** **参数说明**

    <a name="table74220350178"></a>
    <table><thead align="left"><tr id="row1743935151719"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p13378105233519"><a name="p13378105233519"></a><a name="p13378105233519"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p7378652143515"><a name="p7378652143515"></a><a name="p7378652143515"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p337875211359"><a name="p337875211359"></a><a name="p337875211359"></a>示例值</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row94373551718"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p13783525354"><a name="p13783525354"></a><a name="p13783525354"></a><span>Service Name</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p10378952103511"><a name="p10378952103511"></a><a name="p10378952103511"></a>创建的service name名称，固定填写：hbasedev。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p143789524351"><a name="p143789524351"></a><a name="p143789524351"></a>hbasedev</p>
    </td>
    </tr>
    <tr id="row154353515177"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1037885253516"><a name="p1037885253516"></a><a name="p1037885253516"></a><span>Username</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p203781552183511"><a name="p203781552183511"></a><a name="p203781552183511"></a>可以任意填写。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p193781526356"><a name="p193781526356"></a><a name="p193781526356"></a>admin</p>
    </td>
    </tr>
    <tr id="row243143511179"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p13379115223515"><a name="p13379115223515"></a><a name="p13379115223515"></a><span>Password</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p437945273517"><a name="p437945273517"></a><a name="p437945273517"></a>可以任意填写。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p123791352153520"><a name="p123791352153520"></a><a name="p123791352153520"></a>-</p>
    </td>
    </tr>
    <tr id="row343153551716"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1243163517179"><a name="p1243163517179"></a><a name="p1243163517179"></a><span>hadoop.security.authentication</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p243103561716"><a name="p243103561716"></a><a name="p243103561716"></a>hadoop的认证方式，固定填写：Simple。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p843133512171"><a name="p843133512171"></a><a name="p843133512171"></a>Simple</p>
    </td>
    </tr>
    <tr id="row174315352174"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p12432355173"><a name="p12432355173"></a><a name="p12432355173"></a><span>hbase.security.authentication</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p54303512175"><a name="p54303512175"></a><a name="p54303512175"></a>HBase的认证方式，固定填写：Simple。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p184373591715"><a name="p184373591715"></a><a name="p184373591715"></a>Simple</p>
    </td>
    </tr>
    <tr id="row174314357170"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p343153517173"><a name="p343153517173"></a><a name="p343153517173"></a><span>hbase.zookeeper.property.clientPort</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1543173551716"><a name="p1543173551716"></a><a name="p1543173551716"></a>HBase集群中ZooKeeper的端口号。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p16432358177"><a name="p16432358177"></a><a name="p16432358177"></a>2181</p>
    </td>
    </tr>
    <tr id="row1043335111715"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p343183531710"><a name="p343183531710"></a><a name="p343183531710"></a><span>hbase.zookeeper.quorum</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p14431735181716"><a name="p14431735181716"></a><a name="p14431735181716"></a>HBase集群中ZooKeeper地址。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p13980205719194"><a name="p13980205719194"></a><a name="p13980205719194"></a>192.168.0.7,192.168.0.8,192.168.0.9</p>
    </td>
    </tr>
    <tr id="row19708163015201"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1370953092011"><a name="p1370953092011"></a><a name="p1370953092011"></a><span>zookeeper.znode.parent</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p4709123012208"><a name="p4709123012208"></a><a name="p4709123012208"></a>HBase存在ZooKeeper中的根节点路径，固定填写：/hbase。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p4709163092020"><a name="p4709163092020"></a><a name="p4709163092020"></a>/hbase</p>
    </td>
    </tr>
    </tbody>
    </table>

    **图 2**  Create hbasedev<a name="fig39091316015"></a>  
    ![](figures/Create-hbasedev.png "Create-hbasedev")

4.  单击“Add”添加服务。
5.  启动Ranger HBase Plugin，授权Ranger管理HBase。
    1.  在MRS控制台，单击集群名称进入集群详情页面。
    2.  选择“组件管理”。
    3.  选择“HBase \> 服务配置”，将“基础配置”切换为“全部配置”。
    4.  搜索并修改“hbase.security.authorization”为“true”（选择第一个HBase下的参数即可）。

        **图 3**  修改hbase.security.authorization<a name="fig12803731175714"></a>  
        ![](figures/修改hbase-security-authorization.png "修改hbase-security-authorization")

    5.  搜索“hbase.coprocessor.master.classes”，并在原值后追加“,org.apache.ranger.authorization.hbase.RangerAuthorizationCoprocessor”。

        **图 4**  hbase.coprocessor.master.classes<a name="fig18909164792616"></a>  
        ![](figures/hbase-coprocessor-master-classes.png "hbase-coprocessor-master-classes")

    6.  搜索“hbase.coprocessor.region.classes”，并在原值后追加“,org.apache.ranger.authorization.hbase.RangerAuthorizationCoprocessor”。

        **图 5**  hbase.coprocessor.region.classes<a name="fig996734412019"></a>  
        ![](figures/hbase-coprocessor-region-classes.png "hbase-coprocessor-region-classes")

    7.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启HMaster与RegionServer实例。

6.  在HBase Service hbasedev下创建对应的Policy。
    1.  登录Ranger WebUI界面。
    2.  在HBASE区域单击已添加的服务名称“hbasedev”。
    3.  单击“Add New Policy”，新增访问控制策略。
    4.  参考[表2](#table116322231534)配置参数，未在表中列出的参数请保持默认值。

        **表 2**  参数说明

        <a name="table116322231534"></a>
        <table><thead align="left"><tr id="row11633152314316"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p1260833016420"><a name="p1260833016420"></a><a name="p1260833016420"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p156082301046"><a name="p156082301046"></a><a name="p156082301046"></a>说明</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p1060811302417"><a name="p1060811302417"></a><a name="p1060811302417"></a>示例值</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1163310231234"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1865510429816"><a name="p1865510429816"></a><a name="p1865510429816"></a>Policy Name</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p19547132615414"><a name="p19547132615414"></a><a name="p19547132615414"></a>策略名称。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p46331231316"><a name="p46331231316"></a><a name="p46331231316"></a>Policy002</p>
        </td>
        </tr>
        <tr id="row9633142318314"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p11633172313315"><a name="p11633172313315"></a><a name="p11633172313315"></a><span>HBase Table</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p45473261944"><a name="p45473261944"></a><a name="p45473261944"></a>该策略允许访问的HBase表名称。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p2063314239314"><a name="p2063314239314"></a><a name="p2063314239314"></a>test1</p>
        </td>
        </tr>
        <tr id="row863372320317"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p16335231835"><a name="p16335231835"></a><a name="p16335231835"></a><span>HBase Column-family</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p054718261244"><a name="p054718261244"></a><a name="p054718261244"></a>该策略允许访问的HBase表对应的列族。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p176331023136"><a name="p176331023136"></a><a name="p176331023136"></a>cf1</p>
        </td>
        </tr>
        <tr id="row1663420237318"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p663414239318"><a name="p663414239318"></a><a name="p663414239318"></a><span>HBase Column</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1754752616416"><a name="p1754752616416"></a><a name="p1754752616416"></a>该策略允许访问的HBase表对应的表的列名。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1063412318311"><a name="p1063412318311"></a><a name="p1063412318311"></a>name</p>
        </td>
        </tr>
        <tr id="row463413231318"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1263412231934"><a name="p1263412231934"></a><a name="p1263412231934"></a>Allow Conditions</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><a name="ul291972075620"></a><a name="ul291972075620"></a><ul id="ul291972075620"><li>Select Group：该策略允许访问的用户组。</li><li>Select User：该策略允许访问的用户组中的用户。</li><li>Permissions：该策略允许用户使用的权限。</li></ul>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><a name="ul11428874228"></a><a name="ul11428874228"></a><ul id="ul11428874228"><li>Select Group：testuser</li><li>Select User：testuser</li><li>Permissions：Create和select</li></ul>
        </td>
        </tr>
        </tbody>
        </table>

        **图 6**  新增hbasedev的访问控制策略<a name="fig2047532791212"></a>  
        ![](figures/新增hbasedev的访问控制策略.png "新增hbasedev的访问控制策略")

    5.  单击“Add”，完成策略添加，依据如上Policy，testuser用户组中的testuser用户拥有对HBase中“default“namespace下的“test1”表中“cf1:name”列有Create和select的权限，而对于其他列则没有任何的访问权限。

7.  参见[从零开始使用HBase](从零开始使用HBase.md)更新并登录Hbase客户端，验证Ranger是否已经完成集成HBase。
    1.  执行如下命令，进入hbase shell。

        **source /opt/client/bigdata\_env**

        **hbase shell**

        **图 7**  进入hbase shell<a name="fig194139416157"></a>  
        ![](figures/进入hbase-shell.png "进入hbase-shell")

    2.  添加数据，验证Ranger是否已经集成成功。

        1.  为“test1”表中“cf1:name”列添加数据。

            **put 'test1','001','cf1:name','tom'**

        2.  为“test1”表中“cf1:age”列添加数据，该列用户无权限会添加数据失败。

            **put 'test1','001','cf1:age',10**

        **图 8**  验证Ranger集成HBase<a name="fig11361364170"></a>  
        ![](figures/验证Ranger集成HBase.png "验证Ranger集成HBase")



