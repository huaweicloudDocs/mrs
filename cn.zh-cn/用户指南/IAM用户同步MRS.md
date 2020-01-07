# IAM用户同步MRS<a name="ZH-CN_TOPIC_0183742963"></a>

IAM用户同步是指将绑定MRS相关策略的IAM用户同步至MRS系统中，创建同用户名、不同密码的账号，用于集群管理。同步之后，用户可以使用IAM用户名（密码需要MRS Manager的管理员admin重置后方可使用）管理集群。也可以在开启Kerberos认证的集群中，通过界面方式提交作业。

该功能针对MRS 1.8.x版本支持MRS 1.8.7及之后版本，针对MRS 1.9.x支持所有版本，针对2.x版本支持MRS 2.0.5及之后版本。

IAM用户权限策略及同步MRS后权限对比请参考[表1](#table3878619101919)，MRS Manager对应默认权限说明请参考[MRS集群中的用户与权限](MRS集群中的用户与权限.md)。

**表 1**  IAM权限策略与MRS权限同步映射

<a name="table3878619101919"></a>
<table><thead align="left"><tr id="row5879191971913"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.1"><p id="p135212352216"><a name="p135212352216"></a><a name="p135212352216"></a>策略类别</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.2"><p id="p12879101917195"><a name="p12879101917195"></a><a name="p12879101917195"></a>IAM策略</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.3"><p id="p724173216312"><a name="p724173216312"></a><a name="p724173216312"></a>同步后用户在MRS对应默认权限</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.4"><p id="p12472158103113"><a name="p12472158103113"></a><a name="p12472158103113"></a>是否有权限执行同步操作</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.6.1.5"><p id="p14949142373515"><a name="p14949142373515"></a><a name="p14949142373515"></a>是否有权限提交作业</p>
</th>
</tr>
</thead>
<tbody><tr id="row1087961921914"><td class="cellrowborder" rowspan="3" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p2104201613119"><a name="p2104201613119"></a><a name="p2104201613119"></a><span>细粒度</span></p>
<p id="p191048161316"><a name="p191048161316"></a><a name="p191048161316"></a></p>
<p id="p16104101643115"><a name="p16104101643115"></a><a name="p16104101643115"></a></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p4306134273012"><a name="p4306134273012"></a><a name="p4306134273012"></a>MRS Viewer</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><p id="p10949195293012"><a name="p10949195293012"></a><a name="p10949195293012"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p7473381310"><a name="p7473381310"></a><a name="p7473381310"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p16423218365"><a name="p16423218365"></a><a name="p16423218365"></a>否</p>
</td>
</tr>
<tr id="row987918191191"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p230604216306"><a name="p230604216306"></a><a name="p230604216306"></a>MRS User</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><a name="ul4444174612152"></a><a name="ul4444174612152"></a><ul id="ul4444174612152"><li>Manager_viewer</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p1347315893112"><a name="p1347315893112"></a><a name="p1347315893112"></a>否</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p15642122116367"><a name="p15642122116367"></a><a name="p15642122116367"></a>是</p>
</td>
</tr>
<tr id="row7879181971912"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p1530654223011"><a name="p1530654223011"></a><a name="p1530654223011"></a>MRS Admin</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><a name="ul7241758151514"></a><a name="ul7241758151514"></a><ul id="ul7241758151514"><li>Manager_administrator</li><li>Manager_auditor</li><li>Manager_operator</li><li>Manager_tenant</li><li>Manager_viewer</li><li>System_administrator</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p84738823119"><a name="p84738823119"></a><a name="p84738823119"></a>是</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p16425213366"><a name="p16425213366"></a><a name="p16425213366"></a>是</p>
</td>
</tr>
<tr id="row688031916194"><td class="cellrowborder" rowspan="3" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p18374033173417"><a name="p18374033173417"></a><a name="p18374033173417"></a><span>RBAC</span></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p1530634213017"><a name="p1530634213017"></a><a name="p1530634213017"></a>MRS Administrator</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><a name="ul162146189167"></a><a name="ul162146189167"></a><ul id="ul162146189167"><li>Manager_administrator</li><li>Manager_auditor</li><li>Manager_operator</li><li>Manager_tenant</li><li>Manager_viewer</li><li>System_administrator</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><p id="p164738811313"><a name="p164738811313"></a><a name="p164738811313"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p3642192173610"><a name="p3642192173610"></a><a name="p3642192173610"></a>是</p>
</td>
</tr>
<tr id="row18880151911919"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p19306114211307"><a name="p19306114211307"></a><a name="p19306114211307"></a>Server Administrator、Tenant Guest和MRS Administrator</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><a name="ul1336513422162"></a><a name="ul1336513422162"></a><ul id="ul1336513422162"><li>Manager_administrator</li><li>Manager_auditor</li><li>Manager_operator</li><li>Manager_tenant</li><li>Manager_viewer</li><li>System_administrator</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p2473178103117"><a name="p2473178103117"></a><a name="p2473178103117"></a>是</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p2020173383615"><a name="p2020173383615"></a><a name="p2020173383615"></a>是</p>
</td>
</tr>
<tr id="row11873260273"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="p1530624211302"><a name="p1530624211302"></a><a name="p1530624211302"></a>Tenant Administrator</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.2 "><a name="ul1514932717501"></a><a name="ul1514932717501"></a><ul id="ul1514932717501"><li>Manager_administrator</li><li>Manager_auditor</li><li>Manager_operator</li><li>Manager_tenant</li><li>Manager_viewer</li><li>System_administrator</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.3 "><p id="p1147318123117"><a name="p1147318123117"></a><a name="p1147318123117"></a>是</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.4 "><p id="p172011033183610"><a name="p172011033183610"></a><a name="p172011033183610"></a>是</p>
</td>
</tr>
<tr id="row46716711273"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.1 "><p id="p01044164313"><a name="p01044164313"></a><a name="p01044164313"></a>自定义</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.2 "><p id="p123065424306"><a name="p123065424306"></a><a name="p123065424306"></a>Custom policy(自定义策略)</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.3 "><a name="ul47440335173"></a><a name="ul47440335173"></a><ul id="ul47440335173"><li>Manager_viewer</li><li>default</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.4 "><a name="ul1344810351981"></a><a name="ul1344810351981"></a><ul id="ul1344810351981"><li>自定义策略以RBAC策略为模板则参考RBAC策略。</li><li>自定义策略以细粒度策略为模板则参考细粒度策略，建议使用细粒度策略。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.6.1.5 "><p id="p112018336360"><a name="p112018336360"></a><a name="p112018336360"></a>是</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>RBAC策略详细信息请参考[策略语法：RBAC](策略语法-RBAC.md)，细粒度详细信息策略请参考[策略语法：细粒度策略](策略语法-细粒度策略.md)。为了更方便进行用户权限管理，请尽可能使用细粒度策略，减少RBAC策略的使用，细粒度策略判断action时以deny优先原则。  
>-   RBAC策略只有具有Tenant Administrator或同时具有Server Administrator、Tenant Guest、MRS Administrator才在MRS集群中拥有同步IAM用户的权限。  
>-   细粒度策略只要拥有**action:mrs:cluster:syncUser**就在MRS集群中拥有同步IAM用户的权限。  

## 操作步骤<a name="section1968244415315"></a>

1.  创建用户并授权使用MRS服务，具体请参考[创建用户并授权使用MRS](创建用户并授权使用MRS.md)。
2.  登录MRS控制台并创建集群，具体请参考[购买方式简介](购买方式简介.md)。
3.  在左侧导航栏中选择“集群列表  \>  现有集群“，单击集群名称进入集群详情页面。
4.  <a name="li6999515311"></a>在“概览“页签的基本信息区域，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0183939377.png)进行IAM用户同步。
5.  同步请求下发后，在MRS控制台左侧导航栏中选择“操作日志”页面查看同步是否同步成功，日志相关说明请参考[查看操作日志](查看操作日志.md)。
6.  同步成功后，即可使用IAM同步用户进行后续操作。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   当IAM用户的用户组的所属策略从MRS Viewer向MRS User、MRS Admin、MRS Administrator变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，等待新修改策略生效之后，再进行提交作业。否则，会出现提交作业失败的情况。  
    >-   当IAM用户的用户组的所属策略从MRS User、MRS Admin、MRS Administrator向MRS Viewer变化时，由于集群节点的sssd缓存刷新需要时间，因此同步完成后，请等待5分钟，新修改策略才能生效。  
    >-   单击“IAM用户同步”按钮后，集群详情页面会出现短时间空白，这是由于正在进行用户数据同步中，请耐心等待，数据同步完成后，页面将会正常显示。  

    -   安全集群提交作业：安全集群中用户可通过界面“作业管理”功能提交作业，具体请参考[运行MapReduce作业](运行MapReduce作业.md)。
    -   集群详情页面页签显示完整（包含“组件管理”，“租户管理”和“备份恢复”）。
    -   登录MRS Manager页面。

        1.  使用admin账号登录MRS Manager，具体请参考[访问MRS Manager](访问MRS-Manager.md)。
        2.  <a name="li169901714175"></a>初始化IAM同步用户密码，具体请参考[初始化系统用户密码](初始化系统用户密码.md)。
        3.  修改用户所在用户组绑定的角色，精确控制MRS Manager下用户权限，具体请参考[相关任务](创建用户组.md#s855da92cb75446818be082dff6e197f1)修改用户组绑定的角色，如需创建修改角色请参考[创建角色](创建角色.md)。用户所在用户组绑定的组件角色修改后，权限生效需要一定时间，请耐心等待。
        4.  使用IAM同步用户及[6.b](#li169901714175)修改的密码登录MRS Manager。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >当IAM用户权限发生变化时，需要执行[4](#li6999515311)进行二次同步。对于系统用户，二次同步后用户的权限为IAM系统策略定义的权限和用户在MRS Manager自行添加角色的权限的并集。对于自定义用户，二次同步后用户的权限以MRS Manager配置的权限为准。  
        >-   系统用户：如果IAM用户所在用户组全部都绑定系统策略（RABC策略和细粒度策略均属于系统策略），则该用户为系统用户。  
        >-   自定义用户：如果IAM用户所在用户组只要有绑定任何自定义策略，则该用户为自定义用户。  



