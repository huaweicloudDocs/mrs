# 在Ranger中配置Hive的访问权限<a name="ZH-CN_TOPIC_0207621832"></a>

在创建完安装了Ranger组件的MRS集群后，Hive的权限控制暂未集成在Ranger中，本章节主要介绍Hive组件如何集成在Ranger中。

1.  登录Ranger WebUI界面。
2.  在“Service Manager”中的HIVE处，单击![](figures/zh-cn_image_0213708721.png)添加Hive Service。

    **图 1**  添加Hive Service<a name="fig1355517248383"></a>  
    ![](figures/添加Hive-Service.png "添加Hive-Service")

3.  请参考[表1](#table54444329411)填写添加Hive Service的相关参数，未在表中列出的参数请保持默认值。

    **表 1** **参数说明**

    <a name="table54444329411"></a>
    <table><thead align="left"><tr id="row1844243264112"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p12442193220418"><a name="p12442193220418"></a><a name="p12442193220418"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p1744210322416"><a name="p1744210322416"></a><a name="p1744210322416"></a>说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p84421328419"><a name="p84421328419"></a><a name="p84421328419"></a>示例值</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row644393284112"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p18442232184110"><a name="p18442232184110"></a><a name="p18442232184110"></a><span>Service Name</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p8442203254115"><a name="p8442203254115"></a><a name="p8442203254115"></a>创建的service name名称，固定填写：hivedev。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p14442133211411"><a name="p14442133211411"></a><a name="p14442133211411"></a>hivedev</p>
    </td>
    </tr>
    <tr id="row34433328419"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p6443153216418"><a name="p6443153216418"></a><a name="p6443153216418"></a><span>Username</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p12443832114118"><a name="p12443832114118"></a><a name="p12443832114118"></a>可以任意填写。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p0443532194110"><a name="p0443532194110"></a><a name="p0443532194110"></a>admin</p>
    </td>
    </tr>
    <tr id="row74431532164110"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p544313323411"><a name="p544313323411"></a><a name="p544313323411"></a><span>Password</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p7443133224114"><a name="p7443133224114"></a><a name="p7443133224114"></a>可以任意填写。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p044333212412"><a name="p044333212412"></a><a name="p044333212412"></a>-</p>
    </td>
    </tr>
    <tr id="row144353274113"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p94431332194118"><a name="p94431332194118"></a><a name="p94431332194118"></a><span>jdbc.driverClassName</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p14431132144114"><a name="p14431132144114"></a><a name="p14431132144114"></a>连接hive的驱动类，固定填写：org.apache.hive.jdbc.HiveDriver。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p5443153210414"><a name="p5443153210414"></a><a name="p5443153210414"></a>org.apache.hive.jdbc.HiveDriver</p>
    </td>
    </tr>
    <tr id="row104441332194110"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p13443123216418"><a name="p13443123216418"></a><a name="p13443123216418"></a><span>jdbc.url</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p15443132174118"><a name="p15443132174118"></a><a name="p15443132174118"></a>连接hive的url，格式为ZooKeeper Mode：</p>
    <p id="p11444132204117"><a name="p11444132204117"></a><a name="p11444132204117"></a>jdbc:hive2://&lt;host&gt;:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2</p>
    <p id="p717612451575"><a name="p717612451575"></a><a name="p717612451575"></a>其中&lt;host&gt;为ZooKeeper地址，ZooKeeper地址可通过<span>登录MRS Manager然后选择“服务管理 </span><span>&gt;</span><span> ZooKeeper </span><span>&gt;</span><span> 实例”，查看ZooKeeper实例的“管理IP”地址获取。</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p12444163244112"><a name="p12444163244112"></a><a name="p12444163244112"></a>jdbc:hive2://xx.xx.xx.xx:2181,xx.xx.xx.xx:2181,xx.xx.xx.xx:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2</p>
    </td>
    </tr>
    </tbody>
    </table>

    **图 2**  Create hivedev<a name="fig39091316015"></a>  
    ![](figures/Create-hivedev.png "Create-hivedev")

4.  单击“Add”添加服务。
5.  启动Ranger Hive Plugin，授权Ranger管理Hive。
    1.  在MRS控制台，单击集群名称进入集群详情页面。
    2.  选择“组件管理”。
    3.  选择“Hive \> 服务配置”，将“基础配置”切换为“全部配置”。
    4.  搜索配置“hive.security.authorization”，修改如下两个配置：

        -   hive.security.authorization.enabled = true
        -   hive.security.authorization.manager = org.apache.ranger.authorization.hive.authorizer.RangerHiveAuthorizerFactory

        **图 3**  修改hive.security.authorization<a name="fig225610511416"></a>  
        ![](figures/修改hive-security-authorization.png "修改hive-security-authorization")

    5.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。

6.  添加访问控制策略，即Policy。
    1.  登录Ranger WebUI界面。
    2.  在HIVE区域单击已添加的服务名称“hivedev”。
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
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p46331231316"><a name="p46331231316"></a><a name="p46331231316"></a>Policy001</p>
        </td>
        </tr>
        <tr id="row9633142318314"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p11633172313315"><a name="p11633172313315"></a><a name="p11633172313315"></a>database</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p45473261944"><a name="p45473261944"></a><a name="p45473261944"></a>该策略允许访问的数据库名称。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p2063314239314"><a name="p2063314239314"></a><a name="p2063314239314"></a>test</p>
        </td>
        </tr>
        <tr id="row863372320317"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p16335231835"><a name="p16335231835"></a><a name="p16335231835"></a>table</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p054718261244"><a name="p054718261244"></a><a name="p054718261244"></a>该策略允许访问的数据库对应的表名称。</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p176331023136"><a name="p176331023136"></a><a name="p176331023136"></a>table1</p>
        </td>
        </tr>
        <tr id="row1663420237318"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p663414239318"><a name="p663414239318"></a><a name="p663414239318"></a><span>Hive Column</span></p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p1754752616416"><a name="p1754752616416"></a><a name="p1754752616416"></a>该策略允许访问的数据库对应的表的列名。</p>
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

        **图 4**  新增hivedev的访问控制策略<a name="fig2047532791212"></a>  
        ![](figures/新增hivedev的访问控制策略.png "新增hivedev的访问控制策略")

    5.  单击“Add”，完成策略添加，依据如上Policy示例，testuser用户组中的testuser用户将对Hive的“test”数据库中的表“table1”的“name”列有Create和select的权限，而对于其他列则没有任何的访问权限。

7.  参见[从零开始使用Hive](从零开始使用Hive.md)登录hive客户端，验证Ranger是否已经完成集成Hive。
    1.  执行如下命令，进入hive beeline。

        **source /opt/client/bigdata\_env**

        **beeline**

    2.  执行如下命令，建立连接并使用testuser登录。

        **!connect jdbc:hive2://xx.xx.xx.xx:2181,xx.xx.3.81:2181,192.168.3.153:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2**

        **图 5**  登录Hive<a name="fig6187121122713"></a>  
        ![](figures/登录Hive.png "登录Hive")

    3.  查询数据，验证Ranger是否已经集成成功。

        **图 6**  验证Ranger集成Hive<a name="fig19585153615368"></a>  
        ![](figures/验证Ranger集成Hive.png "验证Ranger集成Hive")



