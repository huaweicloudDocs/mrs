# 创建MRS操作用户<a name="mrs_01_0453"></a>

如果您需要对您所拥有的MapReduce服务（MapReduce Service）进行精细的权限管理，您可以使用[统一身份认证服务](https://support.huaweicloud.com/usermanual-iam/iam_01_0001.html)（Identity and Access Management，简称IAM），通过IAM，您可以：

-   根据企业的业务组织，在您的华为云账号中，给企业中不同职能部门的员工创建IAM用户，让员工拥有唯一安全凭证，并使用MRS资源。
-   根据企业用户的职能，设置不同的访问权限，以达到用户之间的权限隔离。
-   将MRS资源委托给更专业、高效的其他华为云账号或者云服务，这些账号或者云服务可以根据权限进行代运维。

如果华为云账号已经能满足您的要求，不需要创建独立的IAM用户，您可以跳过本章节，不影响您使用MRS服务的其它功能。

本章节为您介绍对用户授权的方法，操作流程如[图1](#fig8523123435310)所示。

## 前提条件<a name="section1861611314511"></a>

给用户组授权之前，请您了解用户组可以添加的MRS权限，并结合实际需求进行选择，MRS支持的系统权限，请参见[权限管理](https://support.huaweicloud.com/productdesc-mrs/mrs_08_0033.html)。若您需要对除MRS之外的其它服务授权，IAM支持服务的所有策略请参见[权限策略](https://support.huaweicloud.com/usermanual-permissions/iam_01_0001.html)。

## 示例流程<a name="section02683813578"></a>

**图 1**  给用户授权MRS权限流程<a name="fig8523123435310"></a>  
![](figures/给用户授权MRS权限流程.gif "给用户授权MRS权限流程")

1.  <a name="li895020818018"></a>[创建用户组并授权](https://support.huaweicloud.com/usermanual-iam/iam_03_0001.html)

    在IAM控制台创建用户组，并授予MRS服务对应权限。

2.  [创建用户并加入用户组](https://support.huaweicloud.com/usermanual-iam/iam_02_0001.html)

    在IAM控制台创建用户，并将其加入[1.创建用户组并授权](#li895020818018)中创建的用户组。

3.  [用户登录](https://support.huaweicloud.com/usermanual-iam/iam_01_0552.html)并验证权限

    新创建的用户登录控制台，切换至授权区域，验证权限：

    -   在“服务列表”中选择MRS服务，进入MRS主界面，单击右上角“购买集群”，尝试购买MRS集群，如果无法购买MRS集群（假设当前权限仅包含MRS ReadOnlyAccess），表示“MRS ReadOnlyAccess”已生效。
    -   在“服务列表”中选择除MRS服务外（假设当前策略仅包含MRS ReadOnlyAccess）的任一服务，若提示权限不足，表示“MRS ReadOnlyAccess”已生效。


## MRS权限说明<a name="section2662120181120"></a>

默认情况下，管理员创建的IAM用户没有任何权限，需要将其加入用户组，并给用户组授予策略或角色，才能使得用户组中的用户获得对应的权限，这一过程称为授权。授权后，用户就可以基于被授予的权限对云服务进行操作。

MRS部署时通过物理区域划分，为项目级服务。授权时，“作用范围”需要选择“区域级项目”，然后在指定区域（如华北-北京1）对应的项目（cn-north-1）中设置相关权限，并且该权限仅对此项目生效；如果在“所有项目”中设置权限，则该权限在所有区域项目中都生效。访问MRS时，需要先切换至授权区域。

权限根据授权精细程度分为角色和策略。

-   角色：IAM最初提供的一种根据用户的工作职能定义权限的粗粒度授权机制。该机制以服务为粒度，提供有限的服务相关角色用于授权。由于各服务之间存在业务依赖关系，因此给用户授予角色时，可能需要一并授予依赖的其他角色，才能正确完成业务。角色并不能满足用户对精细化授权的要求，无法完全达到企业对权限最小化的安全管控要求。
-   策略：IAM最新提供的一种细粒度授权的能力，可以精确到具体服务的操作、资源以及请求条件等。基于策略的授权是一种更加灵活的授权方式，能够满足企业对权限最小化的安全管控要求。例如：针对MRS服务，管理员能够控制IAM用户仅能对集群进行指定的管理操作。如不允许某用户组删除集群，仅允许操作MRS集群基本操作，如创建集群、查询集群列表等。多数细粒度策略以API接口为粒度进行权限拆分，MRS支持的API授权项请参见[权限策略和授权项](https://support.huaweicloud.com/api-mrs/mrs_02_0083.html)。

如[表1](#zh-cn_topic_0264277873_table13757124105911)所示，包括了MRS的所有系统策略。

**表 1**  MRS系统策略

<a name="zh-cn_topic_0264277873_table13757124105911"></a>
<table><thead align="left"><tr id="zh-cn_topic_0264277873_row147561841125914"><th class="cellrowborder" valign="top" width="27.27%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0264277873_p11756114125919"><a name="zh-cn_topic_0264277873_p11756114125919"></a><a name="zh-cn_topic_0264277873_p11756114125919"></a>策略名称</p>
</th>
<th class="cellrowborder" valign="top" width="48.05%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0264277873_p77563413592"><a name="zh-cn_topic_0264277873_p77563413592"></a><a name="zh-cn_topic_0264277873_p77563413592"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="24.68%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0264277873_p1475614112599"><a name="zh-cn_topic_0264277873_p1475614112599"></a><a name="zh-cn_topic_0264277873_p1475614112599"></a>策略类别</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0264277873_row14757204114596"><td class="cellrowborder" valign="top" width="27.27%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0264277873_p1595641213136"><a name="zh-cn_topic_0264277873_p1595641213136"></a><a name="zh-cn_topic_0264277873_p1595641213136"></a>MRS FullAccess</p>
</td>
<td class="cellrowborder" valign="top" width="48.05%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0264277873_p2756114114591"><a name="zh-cn_topic_0264277873_p2756114114591"></a><a name="zh-cn_topic_0264277873_p2756114114591"></a>MRS管理员权限，拥有该权限的用户可以拥有MRS所有权限。</p>
</td>
<td class="cellrowborder" valign="top" width="24.68%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0264277873_p67561741125910"><a name="zh-cn_topic_0264277873_p67561741125910"></a><a name="zh-cn_topic_0264277873_p67561741125910"></a>细粒度策略</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1375794119594"><td class="cellrowborder" valign="top" width="27.27%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0264277873_p19972356141319"><a name="zh-cn_topic_0264277873_p19972356141319"></a><a name="zh-cn_topic_0264277873_p19972356141319"></a>MRS CommonOperations</p>
</td>
<td class="cellrowborder" valign="top" width="48.05%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0264277873_p1475710413598"><a name="zh-cn_topic_0264277873_p1475710413598"></a><a name="zh-cn_topic_0264277873_p1475710413598"></a>MRS服务普通用户权限，拥有该权限的用户可以拥有MRS服务使用权限，无新增、删除资源权限。</p>
</td>
<td class="cellrowborder" valign="top" width="24.68%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0264277873_p175714419598"><a name="zh-cn_topic_0264277873_p175714419598"></a><a name="zh-cn_topic_0264277873_p175714419598"></a>细粒度策略</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1075714119599"><td class="cellrowborder" valign="top" width="27.27%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0264277873_p563117291134"><a name="zh-cn_topic_0264277873_p563117291134"></a><a name="zh-cn_topic_0264277873_p563117291134"></a>MRS ReadOnlyAccess</p>
</td>
<td class="cellrowborder" valign="top" width="48.05%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0264277873_p475764117599"><a name="zh-cn_topic_0264277873_p475764117599"></a><a name="zh-cn_topic_0264277873_p475764117599"></a>MRS服务只读权限，拥有该权限的用户仅能查看MRS的资源。</p>
</td>
<td class="cellrowborder" valign="top" width="24.68%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0264277873_p275744155912"><a name="zh-cn_topic_0264277873_p275744155912"></a><a name="zh-cn_topic_0264277873_p275744155912"></a>细粒度策略</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1575714112597"><td class="cellrowborder" valign="top" width="27.27%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0264277873_p17757114125912"><a name="zh-cn_topic_0264277873_p17757114125912"></a><a name="zh-cn_topic_0264277873_p17757114125912"></a>MRS Administrator</p>
</td>
<td class="cellrowborder" valign="top" width="48.05%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0264277873_p157571041175916"><a name="zh-cn_topic_0264277873_p157571041175916"></a><a name="zh-cn_topic_0264277873_p157571041175916"></a>操作权限：</p>
<a name="zh-cn_topic_0264277873_ul1975774114599"></a><a name="zh-cn_topic_0264277873_ul1975774114599"></a><ul id="zh-cn_topic_0264277873_ul1975774114599"><li>对MRS服务的所有执行权限。</li><li>拥有该权限的用户必须同时拥有Tenant Guest、Server Administrator和BSS Administrator权限。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="24.68%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0264277873_p3757194155912"><a name="zh-cn_topic_0264277873_p3757194155912"></a><a name="zh-cn_topic_0264277873_p3757194155912"></a>RBAC策略</p>
</td>
</tr>
</tbody>
</table>

[表2](#zh-cn_topic_0264277873_table64841036185016)列出了MRS常用操作与系统权限的授权关系，您可以参照该表选择合适的系统权限。

**表 2**  常用操作与系统策略的授权关系

<a name="zh-cn_topic_0264277873_table64841036185016"></a>
<table><thead align="left"><tr id="zh-cn_topic_0264277873_row658115361505"><th class="cellrowborder" valign="top" width="16.328367163283673%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0264277873_p858133695011"><a name="zh-cn_topic_0264277873_p858133695011"></a><a name="zh-cn_topic_0264277873_p858133695011"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0264277873_p19603175671418"><a name="zh-cn_topic_0264277873_p19603175671418"></a><a name="zh-cn_topic_0264277873_p19603175671418"></a>MRS FullAccess</p>
</th>
<th class="cellrowborder" valign="top" width="24.48755124487551%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0264277873_p226218261420"><a name="zh-cn_topic_0264277873_p226218261420"></a><a name="zh-cn_topic_0264277873_p226218261420"></a>MRS CommonOperations</p>
</th>
<th class="cellrowborder" valign="top" width="21.42785721427857%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0264277873_p1658163617509"><a name="zh-cn_topic_0264277873_p1658163617509"></a><a name="zh-cn_topic_0264277873_p1658163617509"></a>MRS ReadOnlyAccess</p>
</th>
<th class="cellrowborder" valign="top" width="18.36816318368163%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0264277873_p1358173611500"><a name="zh-cn_topic_0264277873_p1358173611500"></a><a name="zh-cn_topic_0264277873_p1358173611500"></a>MRS Administrator</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0264277873_row358153695016"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1258193675012"><a name="zh-cn_topic_0264277873_p1258193675012"></a><a name="zh-cn_topic_0264277873_p1258193675012"></a>创建集群</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p18581103612504"><a name="zh-cn_topic_0264277873_p18581103612504"></a><a name="zh-cn_topic_0264277873_p18581103612504"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p175815365501"><a name="zh-cn_topic_0264277873_p175815365501"></a><a name="zh-cn_topic_0264277873_p175815365501"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p11581123665016"><a name="zh-cn_topic_0264277873_p11581123665016"></a><a name="zh-cn_topic_0264277873_p11581123665016"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p95819363506"><a name="zh-cn_topic_0264277873_p95819363506"></a><a name="zh-cn_topic_0264277873_p95819363506"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row3581936145013"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p95811336195018"><a name="zh-cn_topic_0264277873_p95811336195018"></a><a name="zh-cn_topic_0264277873_p95811336195018"></a>调整集群</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1358263685018"><a name="zh-cn_topic_0264277873_p1358263685018"></a><a name="zh-cn_topic_0264277873_p1358263685018"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p6303111145810"><a name="zh-cn_topic_0264277873_p6303111145810"></a><a name="zh-cn_topic_0264277873_p6303111145810"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p876255825416"><a name="zh-cn_topic_0264277873_p876255825416"></a><a name="zh-cn_topic_0264277873_p876255825416"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1258283613501"><a name="zh-cn_topic_0264277873_p1258283613501"></a><a name="zh-cn_topic_0264277873_p1258283613501"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row115821436145013"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p165821336125016"><a name="zh-cn_topic_0264277873_p165821336125016"></a><a name="zh-cn_topic_0264277873_p165821336125016"></a>升级节点规格</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p0905144025017"><a name="zh-cn_topic_0264277873_p0905144025017"></a><a name="zh-cn_topic_0264277873_p0905144025017"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p77321528586"><a name="zh-cn_topic_0264277873_p77321528586"></a><a name="zh-cn_topic_0264277873_p77321528586"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p14671918559"><a name="zh-cn_topic_0264277873_p14671918559"></a><a name="zh-cn_topic_0264277873_p14671918559"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p26319588818"><a name="zh-cn_topic_0264277873_p26319588818"></a><a name="zh-cn_topic_0264277873_p26319588818"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row45826360505"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p6582136195015"><a name="zh-cn_topic_0264277873_p6582136195015"></a><a name="zh-cn_topic_0264277873_p6582136195015"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p09964412507"><a name="zh-cn_topic_0264277873_p09964412507"></a><a name="zh-cn_topic_0264277873_p09964412507"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p8755133115819"><a name="zh-cn_topic_0264277873_p8755133115819"></a><a name="zh-cn_topic_0264277873_p8755133115819"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1815192185510"><a name="zh-cn_topic_0264277873_p1815192185510"></a><a name="zh-cn_topic_0264277873_p1815192185510"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p9633759880"><a name="zh-cn_topic_0264277873_p9633759880"></a><a name="zh-cn_topic_0264277873_p9633759880"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1080713242455"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p158081124164513"><a name="zh-cn_topic_0264277873_p158081124164513"></a><a name="zh-cn_topic_0264277873_p158081124164513"></a>查询集群详情</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p12901104620503"><a name="zh-cn_topic_0264277873_p12901104620503"></a><a name="zh-cn_topic_0264277873_p12901104620503"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p7808172412453"><a name="zh-cn_topic_0264277873_p7808172412453"></a><a name="zh-cn_topic_0264277873_p7808172412453"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1212710711556"><a name="zh-cn_topic_0264277873_p1212710711556"></a><a name="zh-cn_topic_0264277873_p1212710711556"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p115701012914"><a name="zh-cn_topic_0264277873_p115701012914"></a><a name="zh-cn_topic_0264277873_p115701012914"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row118081924174519"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p3808142415452"><a name="zh-cn_topic_0264277873_p3808142415452"></a><a name="zh-cn_topic_0264277873_p3808142415452"></a>查询集群列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p20600547195014"><a name="zh-cn_topic_0264277873_p20600547195014"></a><a name="zh-cn_topic_0264277873_p20600547195014"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p148081224164511"><a name="zh-cn_topic_0264277873_p148081224164511"></a><a name="zh-cn_topic_0264277873_p148081224164511"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p074114919553"><a name="zh-cn_topic_0264277873_p074114919553"></a><a name="zh-cn_topic_0264277873_p074114919553"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p01371311698"><a name="zh-cn_topic_0264277873_p01371311698"></a><a name="zh-cn_topic_0264277873_p01371311698"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row19808424154519"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1880872494516"><a name="zh-cn_topic_0264277873_p1880872494516"></a><a name="zh-cn_topic_0264277873_p1880872494516"></a>设置弹性伸缩策略</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p15387349135011"><a name="zh-cn_topic_0264277873_p15387349135011"></a><a name="zh-cn_topic_0264277873_p15387349135011"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p550681765812"><a name="zh-cn_topic_0264277873_p550681765812"></a><a name="zh-cn_topic_0264277873_p550681765812"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p63351317115511"><a name="zh-cn_topic_0264277873_p63351317115511"></a><a name="zh-cn_topic_0264277873_p63351317115511"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1377761896"><a name="zh-cn_topic_0264277873_p1377761896"></a><a name="zh-cn_topic_0264277873_p1377761896"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1180892419454"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p19808724204510"><a name="zh-cn_topic_0264277873_p19808724204510"></a><a name="zh-cn_topic_0264277873_p19808724204510"></a>查询主机列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1997124911507"><a name="zh-cn_topic_0264277873_p1997124911507"></a><a name="zh-cn_topic_0264277873_p1997124911507"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p108087243456"><a name="zh-cn_topic_0264277873_p108087243456"></a><a name="zh-cn_topic_0264277873_p108087243456"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p177241622155519"><a name="zh-cn_topic_0264277873_p177241622155519"></a><a name="zh-cn_topic_0264277873_p177241622155519"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1837142291"><a name="zh-cn_topic_0264277873_p1837142291"></a><a name="zh-cn_topic_0264277873_p1837142291"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row7171161934512"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p19172919174514"><a name="zh-cn_topic_0264277873_p19172919174514"></a><a name="zh-cn_topic_0264277873_p19172919174514"></a>查询操作日志</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p20569150115017"><a name="zh-cn_topic_0264277873_p20569150115017"></a><a name="zh-cn_topic_0264277873_p20569150115017"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p1417212191456"><a name="zh-cn_topic_0264277873_p1417212191456"></a><a name="zh-cn_topic_0264277873_p1417212191456"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p13840142455516"><a name="zh-cn_topic_0264277873_p13840142455516"></a><a name="zh-cn_topic_0264277873_p13840142455516"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p12966024913"><a name="zh-cn_topic_0264277873_p12966024913"></a><a name="zh-cn_topic_0264277873_p12966024913"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row127881479461"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p37891347124613"><a name="zh-cn_topic_0264277873_p37891347124613"></a><a name="zh-cn_topic_0264277873_p37891347124613"></a>创建并执行作业</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p51561251115015"><a name="zh-cn_topic_0264277873_p51561251115015"></a><a name="zh-cn_topic_0264277873_p51561251115015"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p12789447204610"><a name="zh-cn_topic_0264277873_p12789447204610"></a><a name="zh-cn_topic_0264277873_p12789447204610"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p69512945516"><a name="zh-cn_topic_0264277873_p69512945516"></a><a name="zh-cn_topic_0264277873_p69512945516"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p15546163299"><a name="zh-cn_topic_0264277873_p15546163299"></a><a name="zh-cn_topic_0264277873_p15546163299"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row27891447114617"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1478994719464"><a name="zh-cn_topic_0264277873_p1478994719464"></a><a name="zh-cn_topic_0264277873_p1478994719464"></a>停止作业</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p157422510509"><a name="zh-cn_topic_0264277873_p157422510509"></a><a name="zh-cn_topic_0264277873_p157422510509"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p47891447124612"><a name="zh-cn_topic_0264277873_p47891447124612"></a><a name="zh-cn_topic_0264277873_p47891447124612"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p492415292557"><a name="zh-cn_topic_0264277873_p492415292557"></a><a name="zh-cn_topic_0264277873_p492415292557"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p18305141591"><a name="zh-cn_topic_0264277873_p18305141591"></a><a name="zh-cn_topic_0264277873_p18305141591"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row878924719462"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p117891447144610"><a name="zh-cn_topic_0264277873_p117891447144610"></a><a name="zh-cn_topic_0264277873_p117891447144610"></a>删除单个作业</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1631645255012"><a name="zh-cn_topic_0264277873_p1631645255012"></a><a name="zh-cn_topic_0264277873_p1631645255012"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p1778994715462"><a name="zh-cn_topic_0264277873_p1778994715462"></a><a name="zh-cn_topic_0264277873_p1778994715462"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p9615143095516"><a name="zh-cn_topic_0264277873_p9615143095516"></a><a name="zh-cn_topic_0264277873_p9615143095516"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p118746410913"><a name="zh-cn_topic_0264277873_p118746410913"></a><a name="zh-cn_topic_0264277873_p118746410913"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1378974704618"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p87904474464"><a name="zh-cn_topic_0264277873_p87904474464"></a><a name="zh-cn_topic_0264277873_p87904474464"></a>批量删除作业</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p69291252195018"><a name="zh-cn_topic_0264277873_p69291252195018"></a><a name="zh-cn_topic_0264277873_p69291252195018"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p117901547174619"><a name="zh-cn_topic_0264277873_p117901547174619"></a><a name="zh-cn_topic_0264277873_p117901547174619"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p55741394552"><a name="zh-cn_topic_0264277873_p55741394552"></a><a name="zh-cn_topic_0264277873_p55741394552"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1579755910"><a name="zh-cn_topic_0264277873_p1579755910"></a><a name="zh-cn_topic_0264277873_p1579755910"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1217271964514"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1817218194455"><a name="zh-cn_topic_0264277873_p1817218194455"></a><a name="zh-cn_topic_0264277873_p1817218194455"></a>查询作业详情</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p448835345019"><a name="zh-cn_topic_0264277873_p448835345019"></a><a name="zh-cn_topic_0264277873_p448835345019"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p51721319154512"><a name="zh-cn_topic_0264277873_p51721319154512"></a><a name="zh-cn_topic_0264277873_p51721319154512"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1318825155613"><a name="zh-cn_topic_0264277873_p1318825155613"></a><a name="zh-cn_topic_0264277873_p1318825155613"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p8214116391"><a name="zh-cn_topic_0264277873_p8214116391"></a><a name="zh-cn_topic_0264277873_p8214116391"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row2172131974519"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p9173201974515"><a name="zh-cn_topic_0264277873_p9173201974515"></a><a name="zh-cn_topic_0264277873_p9173201974515"></a>查询作业列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p288154135010"><a name="zh-cn_topic_0264277873_p288154135010"></a><a name="zh-cn_topic_0264277873_p288154135010"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p11173201924515"><a name="zh-cn_topic_0264277873_p11173201924515"></a><a name="zh-cn_topic_0264277873_p11173201924515"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p44812945615"><a name="zh-cn_topic_0264277873_p44812945615"></a><a name="zh-cn_topic_0264277873_p44812945615"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1301173911"><a name="zh-cn_topic_0264277873_p1301173911"></a><a name="zh-cn_topic_0264277873_p1301173911"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row2364161214519"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1036421219454"><a name="zh-cn_topic_0264277873_p1036421219454"></a><a name="zh-cn_topic_0264277873_p1036421219454"></a>新建文件夹</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p13942355145018"><a name="zh-cn_topic_0264277873_p13942355145018"></a><a name="zh-cn_topic_0264277873_p13942355145018"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p7364512204517"><a name="zh-cn_topic_0264277873_p7364512204517"></a><a name="zh-cn_topic_0264277873_p7364512204517"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p23641112114518"><a name="zh-cn_topic_0264277873_p23641112114518"></a><a name="zh-cn_topic_0264277873_p23641112114518"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p7807314894"><a name="zh-cn_topic_0264277873_p7807314894"></a><a name="zh-cn_topic_0264277873_p7807314894"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1348107459"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p205101064511"><a name="zh-cn_topic_0264277873_p205101064511"></a><a name="zh-cn_topic_0264277873_p205101064511"></a>删除文件</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1746017562506"><a name="zh-cn_topic_0264277873_p1746017562506"></a><a name="zh-cn_topic_0264277873_p1746017562506"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p175010174510"><a name="zh-cn_topic_0264277873_p175010174510"></a><a name="zh-cn_topic_0264277873_p175010174510"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p65310104514"><a name="zh-cn_topic_0264277873_p65310104514"></a><a name="zh-cn_topic_0264277873_p65310104514"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1263819155919"><a name="zh-cn_topic_0264277873_p1263819155919"></a><a name="zh-cn_topic_0264277873_p1263819155919"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row25825369509"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p14582173614505"><a name="zh-cn_topic_0264277873_p14582173614505"></a><a name="zh-cn_topic_0264277873_p14582173614505"></a>查询文件列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p5501257145017"><a name="zh-cn_topic_0264277873_p5501257145017"></a><a name="zh-cn_topic_0264277873_p5501257145017"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p358203605015"><a name="zh-cn_topic_0264277873_p358203605015"></a><a name="zh-cn_topic_0264277873_p358203605015"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p557052135615"><a name="zh-cn_topic_0264277873_p557052135615"></a><a name="zh-cn_topic_0264277873_p557052135615"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p53331316992"><a name="zh-cn_topic_0264277873_p53331316992"></a><a name="zh-cn_topic_0264277873_p53331316992"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row26641241104614"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p96641041104611"><a name="zh-cn_topic_0264277873_p96641041104611"></a><a name="zh-cn_topic_0264277873_p96641041104611"></a>批量操作集群标签</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1318125815019"><a name="zh-cn_topic_0264277873_p1318125815019"></a><a name="zh-cn_topic_0264277873_p1318125815019"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p17665114110465"><a name="zh-cn_topic_0264277873_p17665114110465"></a><a name="zh-cn_topic_0264277873_p17665114110465"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p634512995615"><a name="zh-cn_topic_0264277873_p634512995615"></a><a name="zh-cn_topic_0264277873_p634512995615"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p393421719911"><a name="zh-cn_topic_0264277873_p393421719911"></a><a name="zh-cn_topic_0264277873_p393421719911"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row3237154016489"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p162371240124814"><a name="zh-cn_topic_0264277873_p162371240124814"></a><a name="zh-cn_topic_0264277873_p162371240124814"></a>创建单个集群标签</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p768912588502"><a name="zh-cn_topic_0264277873_p768912588502"></a><a name="zh-cn_topic_0264277873_p768912588502"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p523815402482"><a name="zh-cn_topic_0264277873_p523815402482"></a><a name="zh-cn_topic_0264277873_p523815402482"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p13380731195619"><a name="zh-cn_topic_0264277873_p13380731195619"></a><a name="zh-cn_topic_0264277873_p13380731195619"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p5811131810915"><a name="zh-cn_topic_0264277873_p5811131810915"></a><a name="zh-cn_topic_0264277873_p5811131810915"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1523804074814"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p3238104084817"><a name="zh-cn_topic_0264277873_p3238104084817"></a><a name="zh-cn_topic_0264277873_p3238104084817"></a>删除单个集群标签</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p152552590501"><a name="zh-cn_topic_0264277873_p152552590501"></a><a name="zh-cn_topic_0264277873_p152552590501"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p923816401480"><a name="zh-cn_topic_0264277873_p923816401480"></a><a name="zh-cn_topic_0264277873_p923816401480"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p12583103375617"><a name="zh-cn_topic_0264277873_p12583103375617"></a><a name="zh-cn_topic_0264277873_p12583103375617"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p442517198915"><a name="zh-cn_topic_0264277873_p442517198915"></a><a name="zh-cn_topic_0264277873_p442517198915"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row11238740134810"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1623804054811"><a name="zh-cn_topic_0264277873_p1623804054811"></a><a name="zh-cn_topic_0264277873_p1623804054811"></a>按照标签查询资源列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1888613599505"><a name="zh-cn_topic_0264277873_p1888613599505"></a><a name="zh-cn_topic_0264277873_p1888613599505"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p523874012488"><a name="zh-cn_topic_0264277873_p523874012488"></a><a name="zh-cn_topic_0264277873_p523874012488"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1723844014489"><a name="zh-cn_topic_0264277873_p1723844014489"></a><a name="zh-cn_topic_0264277873_p1723844014489"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p820616208916"><a name="zh-cn_topic_0264277873_p820616208916"></a><a name="zh-cn_topic_0264277873_p820616208916"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row10676335164813"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p19677173554810"><a name="zh-cn_topic_0264277873_p19677173554810"></a><a name="zh-cn_topic_0264277873_p19677173554810"></a>查询集群标签</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1994911085120"><a name="zh-cn_topic_0264277873_p1994911085120"></a><a name="zh-cn_topic_0264277873_p1994911085120"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p146771935134816"><a name="zh-cn_topic_0264277873_p146771935134816"></a><a name="zh-cn_topic_0264277873_p146771935134816"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p0677173534811"><a name="zh-cn_topic_0264277873_p0677173534811"></a><a name="zh-cn_topic_0264277873_p0677173534811"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p45136221992"><a name="zh-cn_topic_0264277873_p45136221992"></a><a name="zh-cn_topic_0264277873_p45136221992"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1677183518481"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p146771235184810"><a name="zh-cn_topic_0264277873_p146771235184810"></a><a name="zh-cn_topic_0264277873_p146771235184810"></a>访问Manager页面</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p42319395111"><a name="zh-cn_topic_0264277873_p42319395111"></a><a name="zh-cn_topic_0264277873_p42319395111"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p15677735104814"><a name="zh-cn_topic_0264277873_p15677735104814"></a><a name="zh-cn_topic_0264277873_p15677735104814"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p7235155515560"><a name="zh-cn_topic_0264277873_p7235155515560"></a><a name="zh-cn_topic_0264277873_p7235155515560"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p113171723395"><a name="zh-cn_topic_0264277873_p113171723395"></a><a name="zh-cn_topic_0264277873_p113171723395"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1067772914481"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p567816294484"><a name="zh-cn_topic_0264277873_p567816294484"></a><a name="zh-cn_topic_0264277873_p567816294484"></a>查询补丁列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1222544145111"><a name="zh-cn_topic_0264277873_p1222544145111"></a><a name="zh-cn_topic_0264277873_p1222544145111"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p186781029154817"><a name="zh-cn_topic_0264277873_p186781029154817"></a><a name="zh-cn_topic_0264277873_p186781029154817"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p19678129164819"><a name="zh-cn_topic_0264277873_p19678129164819"></a><a name="zh-cn_topic_0264277873_p19678129164819"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p3260241897"><a name="zh-cn_topic_0264277873_p3260241897"></a><a name="zh-cn_topic_0264277873_p3260241897"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row435918459494"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p1035910453497"><a name="zh-cn_topic_0264277873_p1035910453497"></a><a name="zh-cn_topic_0264277873_p1035910453497"></a>安装补丁</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1813124125112"><a name="zh-cn_topic_0264277873_p1813124125112"></a><a name="zh-cn_topic_0264277873_p1813124125112"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p1035914514916"><a name="zh-cn_topic_0264277873_p1035914514916"></a><a name="zh-cn_topic_0264277873_p1035914514916"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1335964584911"><a name="zh-cn_topic_0264277873_p1335964584911"></a><a name="zh-cn_topic_0264277873_p1335964584911"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p139685241693"><a name="zh-cn_topic_0264277873_p139685241693"></a><a name="zh-cn_topic_0264277873_p139685241693"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row735904515499"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p133601945204915"><a name="zh-cn_topic_0264277873_p133601945204915"></a><a name="zh-cn_topic_0264277873_p133601945204915"></a>卸载补丁</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p3538125185115"><a name="zh-cn_topic_0264277873_p3538125185115"></a><a name="zh-cn_topic_0264277873_p3538125185115"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p93608454499"><a name="zh-cn_topic_0264277873_p93608454499"></a><a name="zh-cn_topic_0264277873_p93608454499"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p183601945184913"><a name="zh-cn_topic_0264277873_p183601945184913"></a><a name="zh-cn_topic_0264277873_p183601945184913"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p20911326795"><a name="zh-cn_topic_0264277873_p20911326795"></a><a name="zh-cn_topic_0264277873_p20911326795"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row119841039114913"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p69852039174911"><a name="zh-cn_topic_0264277873_p69852039174911"></a><a name="zh-cn_topic_0264277873_p69852039174911"></a>运维通道授权</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p6672611516"><a name="zh-cn_topic_0264277873_p6672611516"></a><a name="zh-cn_topic_0264277873_p6672611516"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p179854397494"><a name="zh-cn_topic_0264277873_p179854397494"></a><a name="zh-cn_topic_0264277873_p179854397494"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1198515392497"><a name="zh-cn_topic_0264277873_p1198515392497"></a><a name="zh-cn_topic_0264277873_p1198515392497"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p158101526499"><a name="zh-cn_topic_0264277873_p158101526499"></a><a name="zh-cn_topic_0264277873_p158101526499"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1369223724919"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p16693153744910"><a name="zh-cn_topic_0264277873_p16693153744910"></a><a name="zh-cn_topic_0264277873_p16693153744910"></a>运维通道日志共享</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p869516625114"><a name="zh-cn_topic_0264277873_p869516625114"></a><a name="zh-cn_topic_0264277873_p869516625114"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p166932037104910"><a name="zh-cn_topic_0264277873_p166932037104910"></a><a name="zh-cn_topic_0264277873_p166932037104910"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p46931537164911"><a name="zh-cn_topic_0264277873_p46931537164911"></a><a name="zh-cn_topic_0264277873_p46931537164911"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p15464102720911"><a name="zh-cn_topic_0264277873_p15464102720911"></a><a name="zh-cn_topic_0264277873_p15464102720911"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1744081712503"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p2044051785013"><a name="zh-cn_topic_0264277873_p2044051785013"></a><a name="zh-cn_topic_0264277873_p2044051785013"></a>查询告警列表</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p1637467135114"><a name="zh-cn_topic_0264277873_p1637467135114"></a><a name="zh-cn_topic_0264277873_p1637467135114"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p18440817195013"><a name="zh-cn_topic_0264277873_p18440817195013"></a><a name="zh-cn_topic_0264277873_p18440817195013"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1027219185712"><a name="zh-cn_topic_0264277873_p1027219185712"></a><a name="zh-cn_topic_0264277873_p1027219185712"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p791728195"><a name="zh-cn_topic_0264277873_p791728195"></a><a name="zh-cn_topic_0264277873_p791728195"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row1582636155014"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p2582143617504"><a name="zh-cn_topic_0264277873_p2582143617504"></a><a name="zh-cn_topic_0264277873_p2582143617504"></a>订阅告警消息提醒</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p105768125119"><a name="zh-cn_topic_0264277873_p105768125119"></a><a name="zh-cn_topic_0264277873_p105768125119"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p558311360501"><a name="zh-cn_topic_0264277873_p558311360501"></a><a name="zh-cn_topic_0264277873_p558311360501"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1058333695020"><a name="zh-cn_topic_0264277873_p1058333695020"></a><a name="zh-cn_topic_0264277873_p1058333695020"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p1889372812912"><a name="zh-cn_topic_0264277873_p1889372812912"></a><a name="zh-cn_topic_0264277873_p1889372812912"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row486822715455"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p188691027194517"><a name="zh-cn_topic_0264277873_p188691027194517"></a><a name="zh-cn_topic_0264277873_p188691027194517"></a>提交SQL语句</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p786902711450"><a name="zh-cn_topic_0264277873_p786902711450"></a><a name="zh-cn_topic_0264277873_p786902711450"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p148697271458"><a name="zh-cn_topic_0264277873_p148697271458"></a><a name="zh-cn_topic_0264277873_p148697271458"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p17869427104520"><a name="zh-cn_topic_0264277873_p17869427104520"></a><a name="zh-cn_topic_0264277873_p17869427104520"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p20869927194510"><a name="zh-cn_topic_0264277873_p20869927194510"></a><a name="zh-cn_topic_0264277873_p20869927194510"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row13316228164511"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p18317028164519"><a name="zh-cn_topic_0264277873_p18317028164519"></a><a name="zh-cn_topic_0264277873_p18317028164519"></a>查询SQL结果</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p3317172816459"><a name="zh-cn_topic_0264277873_p3317172816459"></a><a name="zh-cn_topic_0264277873_p3317172816459"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p1031752864514"><a name="zh-cn_topic_0264277873_p1031752864514"></a><a name="zh-cn_topic_0264277873_p1031752864514"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p1631762813452"><a name="zh-cn_topic_0264277873_p1631762813452"></a><a name="zh-cn_topic_0264277873_p1631762813452"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p113171928184510"><a name="zh-cn_topic_0264277873_p113171928184510"></a><a name="zh-cn_topic_0264277873_p113171928184510"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0264277873_row585552884511"><td class="cellrowborder" valign="top" width="16.328367163283673%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264277873_p138552283458"><a name="zh-cn_topic_0264277873_p138552283458"></a><a name="zh-cn_topic_0264277873_p138552283458"></a>取消SQL执行任务</p>
</td>
<td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264277873_p685592817459"><a name="zh-cn_topic_0264277873_p685592817459"></a><a name="zh-cn_topic_0264277873_p685592817459"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.48755124487551%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264277873_p68558289458"><a name="zh-cn_topic_0264277873_p68558289458"></a><a name="zh-cn_topic_0264277873_p68558289458"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.42785721427857%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264277873_p148551028114520"><a name="zh-cn_topic_0264277873_p148551028114520"></a><a name="zh-cn_topic_0264277873_p148551028114520"></a>x</p>
</td>
<td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264277873_p10855142844520"><a name="zh-cn_topic_0264277873_p10855142844520"></a><a name="zh-cn_topic_0264277873_p10855142844520"></a>√</p>
</td>
</tr>
</tbody>
</table>

