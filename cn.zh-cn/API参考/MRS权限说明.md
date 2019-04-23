# MRS权限说明<a name="ZH-CN_TOPIC_0155078529"></a>

管理员用户权限：拥有对MRS服务的所有执行权限。

子用户权限：子用户的操作由管理员用户授权。若管理员用户为子用户设置了具体的权限策略，则子用户可以拥有策略内容中对应的权限。

>![](public_sys-resources/icon-note.gif) **说明：**   
>策略是描述一组权限集的语言，它可以精确地描述被授权的资源集和操作集。如果系统可选策略不满足您的要求， 您可以创建自定义策略，精确定义用户组需要的权限。策略详情请参考：[细粒度策略](https://support.huaweicloud.com/usermanual-iam/iam_01_019.html)。  

管理员用户可以通过系统策略或自定义策略为子用户设置具体权限，目前与MRS相关的系统策略有MRS Admin、MRS Viewer、MRS User三种。具体策略内容中的Action项说明请参见[表1](#table19741148205616)。

-   MRS Admin：拥有MRS服务的所有权限，具体策略内容如下。

    ```
    {
            "Version": "1.1",
            "Statement": [
                    {
                            "Action": [
                    "mrs:*:*",
                    "ecs:*:*",
                    "evs:*:*",
                    "vpc:*:*"
                ],
                "Effect": "Allow"
                    }
            ]
    }
    ```

-   MRS Viewer：拥有MRS服务的只读权限，具体策略内容如下。

    ```
    {
             "Version": "1.1",
             "Statement": [
                     {
                             "Action": [
                                     "mrs:*:get*",
                                     "mrs:*:list*",
                                     "ecs:*:get*",
                                     "ecs:*:list*",
                                     "evs:*:get*",
                                     "evs:*:list*",
                                     "vpc:*:get*",
                                     "vpc:*:list*",
                 ],
                             "Effect": "Allow"
                     },
                     {
                             "Action": [
                                     "mrs:cluster:create",
                                     "mrs:cluster:resize",
                                     "mrs:cluster:scaleUp",
                                     "mrs:cluster:delete",
                                     "mrs:cluster:policy",
                                     "mrs:job:submit",
                                     "mrs:job:stop",
                                     "mrs:job:delete",
                                     "mrs:job:batchDelete",
                                     "mrs:file:create",
                                     "mrs:file:delete",
                                     "mrs:tag:batchOperate",
                                     "mrs:tag:create",
                                     "mrs:tag:delete",
                                     "mrs:manager:access",
                                     "mrs:patch:install",
                                     "mrs:patch:uninstall",
                                     "mrs:ops:grant",
                                     "mrs:ops:shareLog",
                                     "mrs:alarm:subscribe"
                              ],
                             "Effect": "Deny"
                     }
             ]
     }
    ```

-   MRS User：拥有MRS服务使用权限，无新增、删除资源权限，具体策略内容如下。

    ```
    {
             "Version": "1.1",
             "Statement": [
                     {
                             "Action": [
                                     "mrs:*:get*",
                                     "mrs:*:list*",
                                     "ecs:*:get*",
                                     "ecs:*:list*",
                                     "evs:*:get*",
                                     "evs:*:list*",
                                     "vpc:*:get*",
                                     "vpc:*:list*",
                                     "mrs:job:submit",
                                     "mrs:job:stop",
                                     "mrs:job:delete",
                                     "mrs:job:batchDelete",
                                     "mrs:file:create",
                                     "mrs:file:delete",
                                     "mrs:tag:batchOperate",
                                     "mrs:tag:create",
                                     "mrs:tag:delete",
                                     "mrs:manager:access",
                                     "mrs:patch:install",
                                     "mrs:patch:uninstall",
                                     "mrs:ops:grant",
                                     "mrs:ops:shareLog",
                                     "mrs:alarm:subscribe"
                             ],
                             "Effect": "Allow"
                     },
                     {
                             "Action": [
                                     "mrs:cluster:create",
                                     "mrs:cluster:resize",
                                     "mrs:cluster:scaleUp",
                                     "mrs:cluster:delete",
                                     "mrs:cluster:policy",
                              ],
                             "Effect": "Deny"
                     }
             ]
     }
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   在IAM侧为用户组设置策略时，该策略对所有企业项目生效。  
    >-   在企业管理侧的企业项目管理与人员管理中设置策略时，仅对绑定的企业项目生效。  
    >-   针对已使用企业项目的子用户，权限可能存在变化（看不到default企业项目、无法查看资源、无法迁入迁出资源），请根据所需要的权限进行策略配置。具体操作请参见  [其他操作](https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0109989489.html#zh-cn_topic_0109989489__s7e950880a4304eadaa855d866b87fcef)  。  

    **表 1**  MRS服务Action列表

    <a name="table19741148205616"></a>
    <table><thead align="left"><tr id="row4742584567"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p157421887563"><a name="p157421887563"></a><a name="p157421887563"></a>Action项</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p37420819565"><a name="p37420819565"></a><a name="p37420819565"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row17742486560"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p913942319587"><a name="p913942319587"></a><a name="p913942319587"></a>mrs:cluster:create</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p191399238587"><a name="p191399238587"></a><a name="p191399238587"></a>创建集群</p>
    </td>
    </tr>
    <tr id="row1574218195617"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4139192313583"><a name="p4139192313583"></a><a name="p4139192313583"></a>mrs:cluster:resize</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p913942305814"><a name="p913942305814"></a><a name="p913942305814"></a>调整集群</p>
    </td>
    </tr>
    <tr id="row1174298125615"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p81398236580"><a name="p81398236580"></a><a name="p81398236580"></a>mrs:cluster:scaleUp</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1313952318584"><a name="p1313952318584"></a><a name="p1313952318584"></a>升级节点规格</p>
    </td>
    </tr>
    <tr id="row974217825614"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10139122345813"><a name="p10139122345813"></a><a name="p10139122345813"></a>mrs:cluster:delete</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p913982311582"><a name="p913982311582"></a><a name="p913982311582"></a>删除集群</p>
    </td>
    </tr>
    <tr id="row137429805618"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1813910230589"><a name="p1813910230589"></a><a name="p1813910230589"></a>mrs:cluster:get</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p141391923145811"><a name="p141391923145811"></a><a name="p141391923145811"></a>查询集群详情</p>
    </td>
    </tr>
    <tr id="row1613585712572"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p213922395818"><a name="p213922395818"></a><a name="p213922395818"></a>mrs:cluster:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p8139823185819"><a name="p8139823185819"></a><a name="p8139823185819"></a>查询集群列表</p>
    </td>
    </tr>
    <tr id="row15679138175814"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p21396232589"><a name="p21396232589"></a><a name="p21396232589"></a>mrs:cluster:policy</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p413920233589"><a name="p413920233589"></a><a name="p413920233589"></a>设置弹性伸缩策略</p>
    </td>
    </tr>
    <tr id="row11882988589"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p141395234585"><a name="p141395234585"></a><a name="p141395234585"></a>mrs:host:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p14139323185812"><a name="p14139323185812"></a><a name="p14139323185812"></a>查询主机列表</p>
    </td>
    </tr>
    <tr id="row781139205816"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p19139162315816"><a name="p19139162315816"></a><a name="p19139162315816"></a>mrs:log:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p413912237586"><a name="p413912237586"></a><a name="p413912237586"></a>查询操作日志</p>
    </td>
    </tr>
    <tr id="row12272193582"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p161392231580"><a name="p161392231580"></a><a name="p161392231580"></a>mrs:job:submit</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1413910233586"><a name="p1413910233586"></a><a name="p1413910233586"></a>创建并执行作业</p>
    </td>
    </tr>
    <tr id="row1745169185816"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10139123195817"><a name="p10139123195817"></a><a name="p10139123195817"></a>mrs:job:stop</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1714015237584"><a name="p1714015237584"></a><a name="p1714015237584"></a>停止作业</p>
    </td>
    </tr>
    <tr id="row76573945815"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p114042375820"><a name="p114042375820"></a><a name="p114042375820"></a>mrs:job:delete</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1314042335819"><a name="p1314042335819"></a><a name="p1314042335819"></a>删除单个作业</p>
    </td>
    </tr>
    <tr id="row285311916586"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p12140152311585"><a name="p12140152311585"></a><a name="p12140152311585"></a>mrs:job:batchDelete</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p814011234588"><a name="p814011234588"></a><a name="p814011234588"></a>批量删除作业</p>
    </td>
    </tr>
    <tr id="row181689102586"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2140423145810"><a name="p2140423145810"></a><a name="p2140423145810"></a>mrs:job:get</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p141401723175816"><a name="p141401723175816"></a><a name="p141401723175816"></a>查询作业详情</p>
    </td>
    </tr>
    <tr id="row526911109583"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p151401123155820"><a name="p151401123155820"></a><a name="p151401123155820"></a>mrs:job:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1114052335811"><a name="p1114052335811"></a><a name="p1114052335811"></a>查询作业列表</p>
    </td>
    </tr>
    <tr id="row105791310105810"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1414022310583"><a name="p1414022310583"></a><a name="p1414022310583"></a>mrs:file:create</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p121405237586"><a name="p121405237586"></a><a name="p121405237586"></a>新建文件夹</p>
    </td>
    </tr>
    <tr id="row11769181012585"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p7140132314583"><a name="p7140132314583"></a><a name="p7140132314583"></a>mrs:file:delete</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18140122395811"><a name="p18140122395811"></a><a name="p18140122395811"></a>删除文件</p>
    </td>
    </tr>
    <tr id="row189572010165812"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11401523165816"><a name="p11401523165816"></a><a name="p11401523165816"></a>mrs:file:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18140182395819"><a name="p18140182395819"></a><a name="p18140182395819"></a>查询文件列表</p>
    </td>
    </tr>
    <tr id="row16143191120581"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p214072317585"><a name="p214072317585"></a><a name="p214072317585"></a>mrs:tag:batchOperate</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1814062315812"><a name="p1814062315812"></a><a name="p1814062315812"></a>批量操作集群标签</p>
    </td>
    </tr>
    <tr id="row19325191120581"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1214011235583"><a name="p1214011235583"></a><a name="p1214011235583"></a>mrs:tag:create</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p11140102385819"><a name="p11140102385819"></a><a name="p11140102385819"></a>创建单个集群标签</p>
    </td>
    </tr>
    <tr id="row17515161111580"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p214052315582"><a name="p214052315582"></a><a name="p214052315582"></a>mrs:tag:delete</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p131401223155812"><a name="p131401223155812"></a><a name="p131401223155812"></a>删除单个集群标签</p>
    </td>
    </tr>
    <tr id="row177037114580"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p81401723125818"><a name="p81401723125818"></a><a name="p81401723125818"></a>mrs:tag:listResource</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p114182312585"><a name="p114182312585"></a><a name="p114182312585"></a>按照标签查询资源列表</p>
    </td>
    </tr>
    <tr id="row14892101165818"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1814132335819"><a name="p1814132335819"></a><a name="p1814132335819"></a>mrs:tag:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p61411123175820"><a name="p61411123175820"></a><a name="p61411123175820"></a>查询集群标签</p>
    </td>
    </tr>
    <tr id="row1992121214588"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p121410236582"><a name="p121410236582"></a><a name="p121410236582"></a>mrs.manager.access</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1914132365818"><a name="p1914132365818"></a><a name="p1914132365818"></a>访问MRS manager页面</p>
    </td>
    </tr>
    <tr id="row11277161216582"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p8141623135819"><a name="p8141623135819"></a><a name="p8141623135819"></a>mrs:patch:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p51418238583"><a name="p51418238583"></a><a name="p51418238583"></a>查询补丁列表</p>
    </td>
    </tr>
    <tr id="row54621912185817"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p11141123195819"><a name="p11141123195819"></a><a name="p11141123195819"></a>mrs:patch:install</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10141923105818"><a name="p10141923105818"></a><a name="p10141923105818"></a>安装补丁</p>
    </td>
    </tr>
    <tr id="row964891211586"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1714102318584"><a name="p1714102318584"></a><a name="p1714102318584"></a>mrs:patch:uninstall</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10141172319585"><a name="p10141172319585"></a><a name="p10141172319585"></a>卸载补丁</p>
    </td>
    </tr>
    <tr id="row18856191212580"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2141923165819"><a name="p2141923165819"></a><a name="p2141923165819"></a>mrs:ops:grant</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p19141172318583"><a name="p19141172318583"></a><a name="p19141172318583"></a>运维通道授权</p>
    </td>
    </tr>
    <tr id="row267121316583"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p16141202310583"><a name="p16141202310583"></a><a name="p16141202310583"></a>mrs:ops:shareLog</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1141823125810"><a name="p1141823125810"></a><a name="p1141823125810"></a>运维通道日志共享</p>
    </td>
    </tr>
    <tr id="row6233313195811"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p914182316587"><a name="p914182316587"></a><a name="p914182316587"></a>mrs:alarm:list</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7141142312582"><a name="p7141142312582"></a><a name="p7141142312582"></a>查询告警列表</p>
    </td>
    </tr>
    <tr id="row17479151365819"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1114115235582"><a name="p1114115235582"></a><a name="p1114115235582"></a>mrs:alarm:subscribe</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p514112375812"><a name="p514112375812"></a><a name="p514112375812"></a>订阅告警消息提醒</p>
    </td>
    </tr>
    </tbody>
    </table>


