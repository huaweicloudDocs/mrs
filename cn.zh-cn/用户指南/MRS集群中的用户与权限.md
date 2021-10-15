# MRS集群中的用户与权限<a name="mrs_01_0341"></a>

## 概述<a name="s948e4bbe367f49a0ab0d2628a75dcd3f"></a>

-   **MRS集群用户**

    Manager中的安全帐号，包含用户名、密码等属性，MRS集群的使用者通过这类用户访问集群中的资源。每个启用Kerberos认证的MRS集群可以有多个用户。

-   **MRS集群角色**

    用户在实际使用MRS集群时需根据业务场景获取访问资源的权限，访问资源的权限是定义到MRS集群对象上的。集群的角色就是包含一个或者多个权限的集合。例如，HDFS中某个目录的访问权限，需要在指定的目录上配置，并保存在角色中。


Manager支持MRS集群用户权限管理功能，使权限管理与用户管理更加直观、易用。

-   权限管理：使用RBAC（Role-Based Access Control）方式，即基于角色授予权限，形成权限的集合。用户通过分配一个或多个已授权的角色取得对应的权限。
-   用户管理：使用Manager统一管理MRS集群用户，并通过Kerberos协议认证用户，LDAP协议存储用户信息。

## 权限管理<a name="sbe419f3367a1491492402109a0980047"></a>

MRS集群提供的权限包括Manager和各组件（例如HDFS、HBase、Hive和Yarn等）的操作维护权限，在实际应用时需根据业务场景为各用户分别配置不同权限。为了提升权限管理的易用性，Manager引入角色的功能，通过选取指定的权限并统一授予角色，以权限集合的形式实现了权限集中查看和管理，提升了权限管理的易用性和用户体验。

角色可以理解为集中一个或多个权限的逻辑体，角色被授予指定的权限，用户通过绑定角色获得对应的权限。

一个角色可以有多个权限，一个用户可以绑定多个角色。

-   角色1：授予操作权限A和B，用户a和用户b通过绑定角色1取得对应的权限。
-   角色2：授予操作权限C，用户c和用户d通过绑定角色2取得对应的权限。
-   角色3：授予操作权限D和F，用户a通过绑定配角色3取得对应的权限。

例如，MRS集群用户绑定了管理员角色，那么这个用户成为MRS集群的管理员用户。

Manager界面显示系统默认创建的角色如[表1](#te7b79730a8de49dc9a52be8196677697)所示。

**表 1**  Manager默认角色与描述

<a name="te7b79730a8de49dc9a52be8196677697"></a>
<table><thead align="left"><tr id="r1fbd785ba3e74fb8a41303a12ad301da"><th class="cellrowborder" valign="top" width="30.5%" id="mcps1.2.3.1.1"><p id="ae7e941b7de384a67b2fad8739c5a4a1f"><a name="ae7e941b7de384a67b2fad8739c5a4a1f"></a><a name="ae7e941b7de384a67b2fad8739c5a4a1f"></a><strong id="a4364bc0e0c4a45aabd673f6ab094c715"><a name="a4364bc0e0c4a45aabd673f6ab094c715"></a><a name="a4364bc0e0c4a45aabd673f6ab094c715"></a>默认角色</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.5%" id="mcps1.2.3.1.2"><p id="ad745c4d61d3f44aa9e40eaca2fab661c"><a name="ad745c4d61d3f44aa9e40eaca2fab661c"></a><a name="ad745c4d61d3f44aa9e40eaca2fab661c"></a><strong id="a1043ce6f96374c1f84da9d9a945fbd22"><a name="a1043ce6f96374c1f84da9d9a945fbd22"></a><a name="a1043ce6f96374c1f84da9d9a945fbd22"></a>角色描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r82ce0ebc84e94e64863ede4af89f419b"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a1d224f459e9b46259bf66db992e016a6"><a name="a1d224f459e9b46259bf66db992e016a6"></a><a name="a1d224f459e9b46259bf66db992e016a6"></a>default</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a149dd43b214e4e5ea64eccd7dbf905cf"><a name="a149dd43b214e4e5ea64eccd7dbf905cf"></a><a name="a149dd43b214e4e5ea64eccd7dbf905cf"></a>为租户创建的角色。</p>
</td>
</tr>
<tr id="r544e22b6ccc9428fa6cf564f62e8cd75"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="ae42779a7132647909936470d222378cc"><a name="ae42779a7132647909936470d222378cc"></a><a name="ae42779a7132647909936470d222378cc"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="acbc41bbc87474c29b6fa4f7596408d3f"><a name="acbc41bbc87474c29b6fa4f7596408d3f"></a><a name="acbc41bbc87474c29b6fa4f7596408d3f"></a>Manager管理员，具有Manager的管理权限。</p>
</td>
</tr>
<tr id="r8abefdfd49ec41d8ab0e39bd08a16058"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a4220119c37d0431db0e0f8a199fdb8aa"><a name="a4220119c37d0431db0e0f8a199fdb8aa"></a><a name="a4220119c37d0431db0e0f8a199fdb8aa"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a87023e1785dc4a05a786d191cb4a5047"><a name="a87023e1785dc4a05a786d191cb4a5047"></a><a name="a87023e1785dc4a05a786d191cb4a5047"></a>Manager审计员，具有查看和管理审计信息的权限。</p>
</td>
</tr>
<tr id="r31186eb7c5d44ad094b3df28a126777e"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a28c7b8c959c6497c90ce8caab50b4a47"><a name="a28c7b8c959c6497c90ce8caab50b4a47"></a><a name="a28c7b8c959c6497c90ce8caab50b4a47"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a57cd9d5f8ea54956829eccf13d76fbb3"><a name="a57cd9d5f8ea54956829eccf13d76fbb3"></a><a name="a57cd9d5f8ea54956829eccf13d76fbb3"></a>Manager操作员，具有除租户管理、配置管理和集群管理功能以外的权限。</p>
</td>
</tr>
<tr id="r0e4f5f9e99514a7684e8e4e8751dc195"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a761a144cf7fd42a3bc31a21cf7374ec0"><a name="a761a144cf7fd42a3bc31a21cf7374ec0"></a><a name="a761a144cf7fd42a3bc31a21cf7374ec0"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a4908f5ad7786421c9ca6c5505b174b99"><a name="a4908f5ad7786421c9ca6c5505b174b99"></a><a name="a4908f5ad7786421c9ca6c5505b174b99"></a>Manager查看员，具有查看系统概览，服务，主机，告警，审计日志等信息的权限。</p>
</td>
</tr>
<tr id="r47f630a5cf8b44fa981f8d3d0802b93f"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="ae90ea3977aa54fbcba12b5898ade3da3"><a name="ae90ea3977aa54fbcba12b5898ade3da3"></a><a name="ae90ea3977aa54fbcba12b5898ade3da3"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a1aa077567b3240849fbe0b8a5bad22dd"><a name="a1aa077567b3240849fbe0b8a5bad22dd"></a><a name="a1aa077567b3240849fbe0b8a5bad22dd"></a>系统管理员，具有Manager的管理权限及所有服务管理员的所有权限。</p>
</td>
</tr>
<tr id="r1767dac05c0843928dd73eb14c617849"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="af7ddc12ef3dc4010b4f4ea4f2e39a2cb"><a name="af7ddc12ef3dc4010b4f4ea4f2e39a2cb"></a><a name="af7ddc12ef3dc4010b4f4ea4f2e39a2cb"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a6e34afa612bf416f8ee9c2dccf788de7"><a name="a6e34afa612bf416f8ee9c2dccf788de7"></a><a name="a6e34afa612bf416f8ee9c2dccf788de7"></a>Manager租户管理页面查看角色，具有Manager“租户管理”页面查看权限。</p>
</td>
</tr>
</tbody>
</table>

通过Manager创建角色时支持对Manager和组件进行授权管理，如[表2](#t1eebab7f372e49fbb70f1802069f1001)所示。

**表 2**  Manager与组件授权管理

<a name="t1eebab7f372e49fbb70f1802069f1001"></a>
<table><thead align="left"><tr id="r39784088a2774ecbb9fcdb3d066e4f69"><th class="cellrowborder" valign="top" width="30.5%" id="mcps1.2.3.1.1"><p id="a0d51f832c3f84ef2835a4c525aec6279"><a name="a0d51f832c3f84ef2835a4c525aec6279"></a><a name="a0d51f832c3f84ef2835a4c525aec6279"></a><strong id="a00df0f1a07994ff383eb4aa7c3739b63"><a name="a00df0f1a07994ff383eb4aa7c3739b63"></a><a name="a00df0f1a07994ff383eb4aa7c3739b63"></a>授权类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.5%" id="mcps1.2.3.1.2"><p id="a619821826df9442bb948e4a225e07f17"><a name="a619821826df9442bb948e4a225e07f17"></a><a name="a619821826df9442bb948e4a225e07f17"></a><strong id="aed5db03a231544a4a6348b222a103bc4"><a name="aed5db03a231544a4a6348b222a103bc4"></a><a name="aed5db03a231544a4a6348b222a103bc4"></a>授权描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="r9454b0b2768c402fa4921f67cc5770ac"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="aade20e746123490cb0cc5b29cc94878b"><a name="aade20e746123490cb0cc5b29cc94878b"></a><a name="aade20e746123490cb0cc5b29cc94878b"></a>Manager</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a1335147bc5b04f6491cb95e50440b014"><a name="a1335147bc5b04f6491cb95e50440b014"></a><a name="a1335147bc5b04f6491cb95e50440b014"></a>Manager访问与登录权限。</p>
</td>
</tr>
<tr id="r210bd779b1114cc4b22d7823a39803ef"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a0c419d2ce20946e285c0d564185a7d77"><a name="a0c419d2ce20946e285c0d564185a7d77"></a><a name="a0c419d2ce20946e285c0d564185a7d77"></a>HBase</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="aad38c0e0d7b94c0fb8291766ccb89378"><a name="aad38c0e0d7b94c0fb8291766ccb89378"></a><a name="aad38c0e0d7b94c0fb8291766ccb89378"></a>HBase管理员权限设置和表、列族授权。</p>
</td>
</tr>
<tr id="r5a65baca7a4d4b4c8a4b5b936686289c"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a74bbf03598a3474c82560cf42127c17d"><a name="a74bbf03598a3474c82560cf42127c17d"></a><a name="a74bbf03598a3474c82560cf42127c17d"></a>HDFS</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="a1ac11e3eb2464311b2e75c94b42a1e2a"><a name="a1ac11e3eb2464311b2e75c94b42a1e2a"></a><a name="a1ac11e3eb2464311b2e75c94b42a1e2a"></a>HDFS中的目录和文件授权。</p>
</td>
</tr>
<tr id="rc156133b2b084b80b9d77605348751ec"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a361926e5f67048fbacee724830a50cdc"><a name="a361926e5f67048fbacee724830a50cdc"></a><a name="a361926e5f67048fbacee724830a50cdc"></a>Hive</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><a name="u152dfabcac93410bb1fd0b99568bb241"></a><a name="u152dfabcac93410bb1fd0b99568bb241"></a><ul id="u152dfabcac93410bb1fd0b99568bb241"><li>Hive Admin Privilege<p id="a8ae2aa0ff6d246b4a9f95600c7195dea"><a name="a8ae2aa0ff6d246b4a9f95600c7195dea"></a><a name="a8ae2aa0ff6d246b4a9f95600c7195dea"></a>Hive管理员权限。</p>
</li><li>Hive Read Write Privileges<p id="acd4d4bcc3d084685a078218a703eb557"><a name="acd4d4bcc3d084685a078218a703eb557"></a><a name="acd4d4bcc3d084685a078218a703eb557"></a>Hive数据表管理权限，可设置与管理已创建的表的数据操作权限。</p>
</li></ul>
</td>
</tr>
<tr id="row3228907510047"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="p6527826910047"><a name="p6527826910047"></a><a name="p6527826910047"></a>Hue</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><p id="p5304845610047"><a name="p5304845610047"></a><a name="p5304845610047"></a>存储策略管理员权限。</p>
</td>
</tr>
<tr id="r38c7b1a7bc5a49eb92a15b9610f136f3"><td class="cellrowborder" valign="top" width="30.5%" headers="mcps1.2.3.1.1 "><p id="a97c501e7086d4ee99a123e07273d3eaf"><a name="a97c501e7086d4ee99a123e07273d3eaf"></a><a name="a97c501e7086d4ee99a123e07273d3eaf"></a>Yarn</p>
</td>
<td class="cellrowborder" valign="top" width="69.5%" headers="mcps1.2.3.1.2 "><a name="u69d9287a1aca4746be7a4c69dea38dc6"></a><a name="u69d9287a1aca4746be7a4c69dea38dc6"></a><ul id="u69d9287a1aca4746be7a4c69dea38dc6"><li>Cluster Admin Operations<p id="ab65ab4e54f5a4df9af65fdef796bef30"><a name="ab65ab4e54f5a4df9af65fdef796bef30"></a><a name="ab65ab4e54f5a4df9af65fdef796bef30"></a>Yarn管理员权限。</p>
</li><li>Scheduler Queue<p id="abd6c4cc19e5e426786f18d2514884e38"><a name="abd6c4cc19e5e426786f18d2514884e38"></a><a name="abd6c4cc19e5e426786f18d2514884e38"></a>队列资源管理。</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

## 用户管理<a name="s8a5c54380c6d4f90a0a8c3ff9eef732d"></a>

支持Kerberos认证的MRS集群使用Kerberos协议和LDAP（Lightweight Directory Access Protocol）协议来配合工作，实现用户管理：

-   Kerberos用于在用户登录Manager与使用组件客户端时认证用户身份，未启用Kerberos认证的集群则不认证用户身份。
-   LDAP用于存储用户记录、用户组信息与权限信息等用户信息。

MRS集群支持在Manager执行创建用户或者修改用户等任务时，系统自动完成更新Kerberos和LDAP的用户数据，用户登录Manager或使用组件客户端时，系统自动完成认证用户身份和获取用户信息。这样一方面保证了用户管理的安全性，另一方面简化了用户管理的操作任务。Manager还提供了用户组功能，可对单个或多个用户进行分类管理：

-   用户组为一批用户的集合，可对用户进行分类管理。系统中的用户可以单独存在也可以加入到某个用户组中。
-   对已分配角色的用户组来说，当用户添加到该组时，用户组分配的角色权限将授权给用户。

MRS 3.x之前版本集群MRS Manager界面显示系统默认创建的用户组如[表3](#td676ae12a3a64c008ec055b498a52d78)所示。

MRS 3.x及之后版本集群FusionInsight Manager界面显示系统默认创建的用户组请参考[用户组](默认权限信息一览.md#zh-cn_topic_0263899337_section1031812876)。

**表 3**  Manager默认用户组与描述

<a name="td676ae12a3a64c008ec055b498a52d78"></a>
<table><thead align="left"><tr id="r92c51b79570b4196a45be4fe35b3a3c5"><th class="cellrowborder" valign="top" width="30.693069306930692%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0043021163_p486451514739"><a name="zh-cn_topic_0043021163_p486451514739"></a><a name="zh-cn_topic_0043021163_p486451514739"></a><strong id="zh-cn_topic_0043021163_b248510514747"><a name="zh-cn_topic_0043021163_b248510514747"></a><a name="zh-cn_topic_0043021163_b248510514747"></a>用户组名称</strong></p>
</th>
<th class="cellrowborder" valign="top" width="69.3069306930693%" id="mcps1.2.3.1.2"><p id="a6b10a480fc254471916a4244ea13d5d8"><a name="a6b10a480fc254471916a4244ea13d5d8"></a><a name="a6b10a480fc254471916a4244ea13d5d8"></a><strong id="aca5ef23651a04b3dbcd27e1b0d4b3a15"><a name="aca5ef23651a04b3dbcd27e1b0d4b3a15"></a><a name="aca5ef23651a04b3dbcd27e1b0d4b3a15"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="rc0ae883bba1144d1a090b7c62d1213b8"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="abd5637c274e845eca7c6ef8dd6c8729f"><a name="abd5637c274e845eca7c6ef8dd6c8729f"></a><a name="abd5637c274e845eca7c6ef8dd6c8729f"></a>hadoop</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="a78bbee0ee48c4baa8a4183431f2add6f"><a name="a78bbee0ee48c4baa8a4183431f2add6f"></a><a name="a78bbee0ee48c4baa8a4183431f2add6f"></a>将用户加入此用户组，可获得所有Yarn队列的任务提交权限。</p>
</td>
</tr>
<tr id="rcf29043ac8b840ac8d05e00beb289b6b"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="a1f3391c357954eda9bde2e6fccfbeb28"><a name="a1f3391c357954eda9bde2e6fccfbeb28"></a><a name="a1f3391c357954eda9bde2e6fccfbeb28"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="a2de3b17fba3f46f2b6bc68c93cbcf44e"><a name="a2de3b17fba3f46f2b6bc68c93cbcf44e"></a><a name="a2de3b17fba3f46f2b6bc68c93cbcf44e"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="r021484b01b7441bcbccc07289a07df17"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="a17ca637ad9f44c7b9e7e10a40f9bf2b1"><a name="a17ca637ad9f44c7b9e7e10a40f9bf2b1"></a><a name="a17ca637ad9f44c7b9e7e10a40f9bf2b1"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="a28690a36d3404283b9c8e9a8415ec082"><a name="a28690a36d3404283b9c8e9a8415ec082"></a><a name="a28690a36d3404283b9c8e9a8415ec082"></a>将用户加入此用户组，可以使用Hive。</p>
</td>
</tr>
<tr id="r125f6208d20c483daa9e4bacacc87713"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="af352507ea96f41ea9213beb75c219a7c"><a name="af352507ea96f41ea9213beb75c219a7c"></a><a name="af352507ea96f41ea9213beb75c219a7c"></a>spark</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="a64fe40fa2412488f89dc2d61b8b0b889"><a name="a64fe40fa2412488f89dc2d61b8b0b889"></a><a name="a64fe40fa2412488f89dc2d61b8b0b889"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="r1f5a7d097dd04f6c9856b7fa01baadcb"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="a9cf4097367db44ab87a70131e6a47ef1"><a name="a9cf4097367db44ab87a70131e6a47ef1"></a><a name="a9cf4097367db44ab87a70131e6a47ef1"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="af27cd7fb26e74ac58b1b7c9f693c463c"><a name="af27cd7fb26e74ac58b1b7c9f693c463c"></a><a name="af27cd7fb26e74ac58b1b7c9f693c463c"></a>将用户加入此用户组，可获得HBase、HDFS和Yarn的管理员权限，并可以使用Hive。</p>
</td>
</tr>
<tr id="row4213721515591"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p4369061915591"><a name="p4369061915591"></a><a name="p4369061915591"></a>flume</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p4927928715591"><a name="p4927928715591"></a><a name="p4927928715591"></a>普通用户组。添加到该用户组的用户无任何额外权限。</p>
</td>
</tr>
<tr id="row25758293172716"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p59914707172716"><a name="p59914707172716"></a><a name="p59914707172716"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p67054959172716"><a name="p67054959172716"></a><a name="p67054959172716"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限,才能访问对应Topic。</p>
</td>
</tr>
<tr id="row63807695172720"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p17144598172720"><a name="p17144598172720"></a><a name="p17144598172720"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p45064911172720"><a name="p45064911172720"></a><a name="p45064911172720"></a>添加入本组的用户，拥有所有Topic的读写权限。</p>
</td>
</tr>
<tr id="row19151905172724"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p24563126172724"><a name="p24563126172724"></a><a name="p24563126172724"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p51132992172724"><a name="p51132992172724"></a><a name="p51132992172724"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="row6240879172730"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p8235702172730"><a name="p8235702172730"></a><a name="p8235702172730"></a>storm</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p47040623172730"><a name="p47040623172730"></a><a name="p47040623172730"></a>Storm的普通用户组，属于该组的用户拥有提交拓扑和管理属于自己的拓扑的权限。</p>
</td>
</tr>
<tr id="row39302212172734"><td class="cellrowborder" valign="top" width="30.693069306930692%" headers="mcps1.2.3.1.1 "><p id="p2038471172734"><a name="p2038471172734"></a><a name="p2038471172734"></a>stormadmin</p>
</td>
<td class="cellrowborder" valign="top" width="69.3069306930693%" headers="mcps1.2.3.1.2 "><p id="p66085272172734"><a name="p66085272172734"></a><a name="p66085272172734"></a>Storm的管理员用户组，属于该组的用户拥有提交拓扑和管理所有拓扑的权限。</p>
</td>
</tr>
</tbody>
</table>

启用Kerberos认证的MRS集群默认创建“admin“用户帐号，用于集群管理员维护集群。

## 流程概述<a name="s9fffbfa836e84b47ba7113e6196cc9e1"></a>

在实际业务中，MRS集群用户需要先明确大数据的业务场景，规划集群用户对应的权限。然后在Manager界面创建角色，并设置角色包含的权限以匹配业务的需求。如果需要统一管理单个或多个相同业务场景中的用户，Manager提供了用户组的功能，管理员可以创建用户组。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果角色设置HDFS、HBase、Hive或Yarn各组件的权限，仅可以使用组件自身功能。如果还需要使用Manager，请在角色中添加对应的Manager权限。

**图 1**  创建用户流程示意<a name="f9a6048170fe14a80b4973d74d9d86a97"></a>  
![](figures/创建用户流程示意.png "创建用户流程示意")

