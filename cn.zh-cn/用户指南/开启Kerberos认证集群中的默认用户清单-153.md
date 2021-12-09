# 开启Kerberos认证集群中的默认用户清单<a name="mrs_01_0342"></a>

## 用户分类<a name="s6938c8b3b12d4493b56cb27c41fb2313"></a>

MRS集群提供以下3类用户，请用户定期修改密码，不建议使用默认密码。

<a name="te04570f84a8c4401a30e67359a9f6ef6"></a>
<table><thead align="left"><tr id="r58674799c6844f09aed1ca3adfa4f675"><th class="cellrowborder" valign="top" width="21.5%" id="mcps1.1.3.1.1"><p id="acd42a1f7bb434508bc9c100b4a0f2049"><a name="acd42a1f7bb434508bc9c100b4a0f2049"></a><a name="acd42a1f7bb434508bc9c100b4a0f2049"></a>用户类型</p>
</th>
<th class="cellrowborder" valign="top" width="78.5%" id="mcps1.1.3.1.2"><p id="a73f9735c2df340b2b3849dcad936de40"><a name="a73f9735c2df340b2b3849dcad936de40"></a><a name="a73f9735c2df340b2b3849dcad936de40"></a>使用说明</p>
</th>
</tr>
</thead>
<tbody><tr id="rc9176358376145afaa56341d700e3c79"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p337902391436"><a name="zh-cn_topic_0039905375_p337902391436"></a><a name="zh-cn_topic_0039905375_p337902391436"></a>系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="ub0050ca23d18471cb448f799f1ba6bc7"></a><a name="ub0050ca23d18471cb448f799f1ba6bc7"></a><ul id="ub0050ca23d18471cb448f799f1ba6bc7"><li>通过Manager创建，是MRS集群操作运维与业务场景中主要使用的用户，包含两种类型：<a name="ubb35dcd0d22c4433aab07175bfa9f39d"></a><a name="ubb35dcd0d22c4433aab07175bfa9f39d"></a><ul id="ubb35dcd0d22c4433aab07175bfa9f39d"><li>“人机”用户：用于在Manager的操作运维场景，以及在组件客户端操作的场景。</li><li>“机机”用户：用于MRS集群应用开发的场景。</li></ul>
</li><li>用于OMS系统进程运行的用户。</li></ul>
</td>
</tr>
<tr id="r5d8b415be7564664969223d1bdc1bb74"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="a4af0f57c3b5448c3b8374321986d0a37"><a name="a4af0f57c3b5448c3b8374321986d0a37"></a><a name="a4af0f57c3b5448c3b8374321986d0a37"></a>系统内部用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><p id="a516e3292d2984c70a638aa1dc13383c3"><a name="a516e3292d2984c70a638aa1dc13383c3"></a><a name="a516e3292d2984c70a638aa1dc13383c3"></a>MRS集群提供的用于进程通信、保存用户组信息和关联用户权限的内部用户。</p>
</td>
</tr>
<tr id="rd0d2c9eeacb64fe2839abdafd22cec7c"><td class="cellrowborder" valign="top" width="21.5%" headers="mcps1.1.3.1.1 "><p id="adf39dd76e0604fe7a64368a4457e4c15"><a name="adf39dd76e0604fe7a64368a4457e4c15"></a><a name="adf39dd76e0604fe7a64368a4457e4c15"></a>数据库用户</p>
</td>
<td class="cellrowborder" valign="top" width="78.5%" headers="mcps1.1.3.1.2 "><a name="u858bd206e90145b3851384ba2c0cacdb"></a><a name="u858bd206e90145b3851384ba2c0cacdb"></a><ul id="u858bd206e90145b3851384ba2c0cacdb"><li>用于OMS数据库管理和数据访问的用户。</li><li>用于业务组件（Hive、Hue、Loader和DBservice）数据库的用户。</li></ul>
</td>
</tr>
</tbody>
</table>

## 系统用户<a name="sab2bd13717334d708e5478e08ed5e616"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   MRS集群需要使用操作系统中ldap用户，此帐号不能删除，否则可能导致集群无法正常工作。密码管理策略由操作用户维护。
>-   首次修改“ommdba“和“omm“用户需要执行重置密码操作。找回密码后建议定期修改。

<a name="t6b8aac53ebdc49efaacdbccaaa559ab1"></a>
<table><thead align="left"><tr id="r5f6d7d4a51ab4e38b1f869ae95b6aeb3"><th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0039905375_p602860391613"><a name="zh-cn_topic_0039905375_p602860391613"></a><a name="zh-cn_topic_0039905375_p602860391613"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.2"><p id="acf9704788cec41d597b2465e4ee1d962"><a name="acf9704788cec41d597b2465e4ee1d962"></a><a name="acf9704788cec41d597b2465e4ee1d962"></a>用户名称</p>
</th>
<th class="cellrowborder" valign="top" width="21.09%" id="mcps1.1.5.1.3"><p id="acb498f43480549f3acfcb7877d910ead"><a name="acb498f43480549f3acfcb7877d910ead"></a><a name="acb498f43480549f3acfcb7877d910ead"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.730000000000004%" id="mcps1.1.5.1.4"><p id="a3255af176f334fc0a4eeba52971ae5c6"><a name="a3255af176f334fc0a4eeba52971ae5c6"></a><a name="a3255af176f334fc0a4eeba52971ae5c6"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r27bb0760f1eb4372804ab6a54665d5f4"><td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="aebf20281e7f141e8a6e9b241bd837e14"><a name="aebf20281e7f141e8a6e9b241bd837e14"></a><a name="aebf20281e7f141e8a6e9b241bd837e14"></a>MRS集群系统管理员</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="af3894562851b4654b850205d85e99843"><a name="af3894562851b4654b850205d85e99843"></a><a name="af3894562851b4654b850205d85e99843"></a>admin</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="a0aef5a6c9b1a4904813222a438e79a84"><a name="a0aef5a6c9b1a4904813222a438e79a84"></a><a name="a0aef5a6c9b1a4904813222a438e79a84"></a>在集群创建时由用户指定。</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="acdb5db3097f5437d91aa2b56029c5646"><a name="acdb5db3097f5437d91aa2b56029c5646"></a><a name="acdb5db3097f5437d91aa2b56029c5646"></a>Manager的管理员。</p>
<p id="p2240466591526"><a name="p2240466591526"></a><a name="p2240466591526"></a>此外还具有以下权限：</p>
<a name="ul77702491530"></a><a name="ul77702491530"></a><ul id="ul77702491530"><li>具有HDFS、ZooKeeper普通用户的权限。</li><li>具有提交、查询Mapreduce、YARN任务的权限，以及YARN队列管理权限和访问YARN WebUI的权限。</li><li>Storm中，具有提交、查询、激活、去激活、重分配、删除拓扑的权限，可以操作所有拓扑。</li><li>Kafka服务中，具有创建、删除、授权、Reassign、消费、写入、查询主题的权限。</li></ul>
</td>
</tr>
<tr id="rb2ac6e4bc5f1406094cfd31d367b7f69"><td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="ab1bf70004a404b60a7ed9294b2909244"><a name="ab1bf70004a404b60a7ed9294b2909244"></a><a name="ab1bf70004a404b60a7ed9294b2909244"></a>MRS集群节点操作系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="p10684945121110"><a name="p10684945121110"></a><a name="p10684945121110"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="p068494517111"><a name="p068494517111"></a><a name="p068494517111"></a>系统随机生成</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="p8684945131112"><a name="p8684945131112"></a><a name="p8684945131112"></a>MRS集群系统的内部运行用户。在全部节点生成，属于操作系统用户，无需设置为统一的密码。</p>
</td>
</tr>
<tr id="r0ecfdd4619934b0cb666fcbdf9c22b54"><td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.1 "><p id="p1190851873618"><a name="p1190851873618"></a><a name="p1190851873618"></a>MRS集群节点操作系统用户</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.2 "><p id="p11908518153613"><a name="p11908518153613"></a><a name="p11908518153613"></a>root</p>
</td>
<td class="cellrowborder" valign="top" width="21.09%" headers="mcps1.1.5.1.3 "><p id="p290881820369"><a name="p290881820369"></a><a name="p290881820369"></a>用户设置的密码。</p>
</td>
<td class="cellrowborder" valign="top" width="36.730000000000004%" headers="mcps1.1.5.1.4 "><p id="p390861893616"><a name="p390861893616"></a><a name="p390861893616"></a>MRS集群所属节点的登录用户。在全部节点生成，属于操作系统用户。</p>
</td>
</tr>
</tbody>
</table>

## 系统内部用户<a name="s7014b4bc5b1f49d1aaa0ba7dfc3e4e8b"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>以下系统内部用户不能删除，否则可能导致集群或组件无法正常工作。

<a name="t7c6eb02b0e9a47bf8c2beef04898f21c"></a>
<table><thead align="left"><tr id="rf891720ab8584bf29208367614e27a3c"><th class="cellrowborder" valign="top" width="20.47%" id="mcps1.1.5.1.1"><p id="a86ef5120d8a4405e9256272dadfecd0f"><a name="a86ef5120d8a4405e9256272dadfecd0f"></a><a name="a86ef5120d8a4405e9256272dadfecd0f"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="26.479999999999997%" id="mcps1.1.5.1.2"><p id="a1a3b31f329cc41c89d5baa4d2a9087e2"><a name="a1a3b31f329cc41c89d5baa4d2a9087e2"></a><a name="a1a3b31f329cc41c89d5baa4d2a9087e2"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="13.83%" id="mcps1.1.5.1.3"><p id="a775ea3b21c2d460a8877d30a8861b132"><a name="a775ea3b21c2d460a8877d30a8861b132"></a><a name="a775ea3b21c2d460a8877d30a8861b132"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="39.22%" id="mcps1.1.5.1.4"><p id="ac9a80b80fc7949d289ca25cbc3e44fe4"><a name="ac9a80b80fc7949d289ca25cbc3e44fe4"></a><a name="ac9a80b80fc7949d289ca25cbc3e44fe4"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r3ff2fe8e69004b31810e2978838a4098"><td class="cellrowborder" rowspan="4" valign="top" width="20.47%" headers="mcps1.1.5.1.1 "><p id="a09e79d22f72a42f8a2e16c4f839495c0"><a name="a09e79d22f72a42f8a2e16c4f839495c0"></a><a name="a09e79d22f72a42f8a2e16c4f839495c0"></a>组件运行用户</p>
</td>
<td class="cellrowborder" valign="top" width="26.479999999999997%" headers="mcps1.1.5.1.2 "><p id="a3ca0a44fd3094cfd9e7fa5e86feb687f"><a name="a3ca0a44fd3094cfd9e7fa5e86feb687f"></a><a name="a3ca0a44fd3094cfd9e7fa5e86feb687f"></a>hdfs</p>
</td>
<td class="cellrowborder" valign="top" width="13.83%" headers="mcps1.1.5.1.3 "><p id="abc2adb66b75b4ea2826036644fe86a81"><a name="abc2adb66b75b4ea2826036644fe86a81"></a><a name="abc2adb66b75b4ea2826036644fe86a81"></a>Hdfs@123</p>
</td>
<td class="cellrowborder" valign="top" width="39.22%" headers="mcps1.1.5.1.4 "><p id="abd7b74694f87487bb9e5f3eb750e2cc1"><a name="abd7b74694f87487bb9e5f3eb750e2cc1"></a><a name="abd7b74694f87487bb9e5f3eb750e2cc1"></a>HDFS系统管理员，用户权限：</p>
<a name="o794c106743664f50ae72e9bcbaaf90df"></a><a name="o794c106743664f50ae72e9bcbaaf90df"></a><ol id="o794c106743664f50ae72e9bcbaaf90df"><li>文件系统操作权限：<a name="u46279b3930304aa1a6200485750f4fc2"></a><a name="u46279b3930304aa1a6200485750f4fc2"></a><ul id="u46279b3930304aa1a6200485750f4fc2"><li>查看、修改、创建文件</li><li>查看、创建目录</li><li>查看、修改文件属组</li><li>查看、设置用户磁盘配额</li></ul>
</li><li>HDFS管理操作权限：<a name="u6c8113c615bc4eecb120e777123b9465"></a><a name="u6c8113c615bc4eecb120e777123b9465"></a><ul id="u6c8113c615bc4eecb120e777123b9465"><li>查看webUI页面状态</li><li>查看、设置HDFS主备状态</li><li>进入、退出HDFS安全模式</li><li>检查HDFS文件系统</li></ul>
</li></ol>
</td>
</tr>
<tr id="rac5ec1303d064f2f90143913f87697e6"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="aa8791baf97e449bcab3cce09f17406ab"><a name="aa8791baf97e449bcab3cce09f17406ab"></a><a name="aa8791baf97e449bcab3cce09f17406ab"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="a712c0d0dfb284096be1a944ef8183d03"><a name="a712c0d0dfb284096be1a944ef8183d03"></a><a name="a712c0d0dfb284096be1a944ef8183d03"></a>Hbase@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="a48226f3ff818428eab07b2c05c723b90"><a name="a48226f3ff818428eab07b2c05c723b90"></a><a name="a48226f3ff818428eab07b2c05c723b90"></a>HBase系统管理员，用户权限：</p>
<a name="ud1d77e5225744d7290262fa790d3f191"></a><a name="ud1d77e5225744d7290262fa790d3f191"></a><ul id="ud1d77e5225744d7290262fa790d3f191"><li>集群管理权限: 表的Enable、Disable操作，触发MajorCompact，ACL操作</li><li>授权或回收权限，集群关闭等操作相关的权限</li><li>表管理权限: 建表、修改表、删除表等操作权限</li><li>数据管理权限：表级别、列族级别以及列级别的数据读写权限</li><li>访问HBase WebUI的权限</li></ul>
</td>
</tr>
<tr id="r9db6e464e2f34aa38a1e93eda7704dd4"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="a80f1f3b9b14a4983ab75bffb7bd041e2"><a name="a80f1f3b9b14a4983ab75bffb7bd041e2"></a><a name="a80f1f3b9b14a4983ab75bffb7bd041e2"></a>mapred</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="a6e3f65103daa460f9f38e0110172df42"><a name="a6e3f65103daa460f9f38e0110172df42"></a><a name="a6e3f65103daa460f9f38e0110172df42"></a>Mapred@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="aef97b376d6654246bb03fb5f569d3b00"><a name="aef97b376d6654246bb03fb5f569d3b00"></a><a name="aef97b376d6654246bb03fb5f569d3b00"></a>MapReduce系统管理员，用户权限：</p>
<a name="ufb9017f24be64ef5b60f0e9e909db2c1"></a><a name="ufb9017f24be64ef5b60f0e9e909db2c1"></a><ul id="ufb9017f24be64ef5b60f0e9e909db2c1"><li>提交、停止和查看MapReduce任务的权限</li><li>修改Yarn配置参数的权限</li><li>访问Yarn、MapReduce WebUI的权限</li></ul>
</td>
</tr>
<tr id="rb372546960344fd7bca6cb7fbfae0187"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="a6adaae55d083493abb17382b33a32a39"><a name="a6adaae55d083493abb17382b33a32a39"></a><a name="a6adaae55d083493abb17382b33a32a39"></a>spark</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="a949806e96af84e31af4f35172bd2d52f"><a name="a949806e96af84e31af4f35172bd2d52f"></a><a name="a949806e96af84e31af4f35172bd2d52f"></a>Spark@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="a60bae9783a194e7ab6102c49521576fd"><a name="a60bae9783a194e7ab6102c49521576fd"></a><a name="a60bae9783a194e7ab6102c49521576fd"></a>Spark系统管理员，用户权限：</p>
<a name="u0c233dae119d4b428a85424b1496dc6e"></a><a name="u0c233dae119d4b428a85424b1496dc6e"></a><ul id="u0c233dae119d4b428a85424b1496dc6e"><li>访问Spark WebUI的权限</li><li>提交Spark任务的权限</li></ul>
</td>
</tr>
</tbody>
</table>

## 用户组信息<a name="s7e903a7017034fb28fc5ce90846c9111"></a>

<a name="t2b63afe6ad6d4687b5cbcd106db57a53"></a>
<table><thead align="left"><tr id="r9b7a023125c6493ab4668a6fc069cfe8"><th class="cellrowborder" valign="top" width="35%" id="mcps1.1.3.1.1"><p id="afb8b3a42df9d46f4ac70366e65a8099b"><a name="afb8b3a42df9d46f4ac70366e65a8099b"></a><a name="afb8b3a42df9d46f4ac70366e65a8099b"></a>默认用户组</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.1.3.1.2"><p id="a4188a9c106b843d6b480c4e0e3ec9e7d"><a name="a4188a9c106b843d6b480c4e0e3ec9e7d"></a><a name="a4188a9c106b843d6b480c4e0e3ec9e7d"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r0cc2588b18524853a66a482184b43332"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a7feff961662e4ff4989046eeef9d9ed7"><a name="a7feff961662e4ff4989046eeef9d9ed7"></a><a name="a7feff961662e4ff4989046eeef9d9ed7"></a>hadoop</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="adabbf87da93044249cf2b5b7261265b9"><a name="adabbf87da93044249cf2b5b7261265b9"></a><a name="adabbf87da93044249cf2b5b7261265b9"></a>将用户加入此用户组，可获得所有Yarn队列的任务提交权限。</p>
</td>
</tr>
<tr id="r7e10a4a62c8046b1823d3ce86718fdb3"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a84235225147c476182e5e1a812d8d6d7"><a name="a84235225147c476182e5e1a812d8d6d7"></a><a name="a84235225147c476182e5e1a812d8d6d7"></a>hbase</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a43a9611866f64cf9869ddc7666481179"><a name="a43a9611866f64cf9869ddc7666481179"></a><a name="a43a9611866f64cf9869ddc7666481179"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="r9555b1ba9f0f4ce5876ba3981f67da95"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a5b44543ef01e408fb9524e98d7e71fca"><a name="a5b44543ef01e408fb9524e98d7e71fca"></a><a name="a5b44543ef01e408fb9524e98d7e71fca"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="aa8b6b17fcf524472a9e2ff43f3386191"><a name="aa8b6b17fcf524472a9e2ff43f3386191"></a><a name="aa8b6b17fcf524472a9e2ff43f3386191"></a>将用户加入此用户组，可以使用Hive。</p>
</td>
</tr>
<tr id="r34089980bf714a7f98710737ddf040ac"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a940844d173984a988e3f0d2a4b866081"><a name="a940844d173984a988e3f0d2a4b866081"></a><a name="a940844d173984a988e3f0d2a4b866081"></a>spark</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a9d3cff5becbb4e2b82c43c5100c3e62b"><a name="a9d3cff5becbb4e2b82c43c5100c3e62b"></a><a name="a9d3cff5becbb4e2b82c43c5100c3e62b"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="r2e6cd4e9639b45b6914a95a9f376d4cd"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a15ca38ced204424b9d952ea0ffa355c4"><a name="a15ca38ced204424b9d952ea0ffa355c4"></a><a name="a15ca38ced204424b9d952ea0ffa355c4"></a>supergroup</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p484018194426"><a name="zh-cn_topic_0039905375_p484018194426"></a><a name="zh-cn_topic_0039905375_p484018194426"></a>将用户加入此用户组，可获得HBase、HDFS和Yarn的管理员权限，并可以使用Hive。</p>
</td>
</tr>
<tr id="r2c4cc40bf96840e1934ba4d875ab8b78"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a939aa842190f4015a9f42db701576a75"><a name="a939aa842190f4015a9f42db701576a75"></a><a name="a939aa842190f4015a9f42db701576a75"></a>check_sec_ldap</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a69f3a09d45d840d89c8d43068d542d69"><a name="a69f3a09d45d840d89c8d43068d542d69"></a><a name="a69f3a09d45d840d89c8d43068d542d69"></a>用于内部测试主LDAP是否工作正常。用户组随机存在，每次测试时创建，测试完成后自动删除。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="rc46aa0d3f9504e8999fa5e0cca62a118"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a27573a850cf64afdabaca4d01d97705a"><a name="a27573a850cf64afdabaca4d01d97705a"></a><a name="a27573a850cf64afdabaca4d01d97705a"></a>Manager_tenant</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a1a87b6544fd440db8129b6bea7fe8870"><a name="a1a87b6544fd440db8129b6bea7fe8870"></a><a name="a1a87b6544fd440db8129b6bea7fe8870"></a>租户系统用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="rd0c13a41abbb41be931f7473e727cf8d"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a6b9ce7f67dcf401dae2f456c8ab4ce0d"><a name="a6b9ce7f67dcf401dae2f456c8ab4ce0d"></a><a name="a6b9ce7f67dcf401dae2f456c8ab4ce0d"></a>System_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a2e05f9bef0e64d9a8ded665d82f800b1"><a name="a2e05f9bef0e64d9a8ded665d82f800b1"></a><a name="a2e05f9bef0e64d9a8ded665d82f800b1"></a>MRS集群系统管理员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="r14d895d67025458d933aa4aa5b6f25a7"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p330046794426"><a name="zh-cn_topic_0039905375_p330046794426"></a><a name="zh-cn_topic_0039905375_p330046794426"></a>Manager_viewer</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a92b846c06539489e9d5c02a8660cae75"><a name="a92b846c06539489e9d5c02a8660cae75"></a><a name="a92b846c06539489e9d5c02a8660cae75"></a>MRS Manager系统查看员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="rdb8d0295e79a4081bfeee4c04ab9a449"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a882453dde6404e2aa7b7204c2d6d22ec"><a name="a882453dde6404e2aa7b7204c2d6d22ec"></a><a name="a882453dde6404e2aa7b7204c2d6d22ec"></a>Manager_operator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a6d816c93930f42b6a5ff51de06e705e3"><a name="a6d816c93930f42b6a5ff51de06e705e3"></a><a name="a6d816c93930f42b6a5ff51de06e705e3"></a>MRS Manager系统操作员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="rd7f2d3e8587c4895aa4712fe203f1fef"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a65a50708a57848f48a50365be49a4a68"><a name="a65a50708a57848f48a50365be49a4a68"></a><a name="a65a50708a57848f48a50365be49a4a68"></a>Manager_auditor</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="ab1e5ffa592e94d5db2e5fdb5c07ba24d"><a name="ab1e5ffa592e94d5db2e5fdb5c07ba24d"></a><a name="ab1e5ffa592e94d5db2e5fdb5c07ba24d"></a>MRS Manager系统审计员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="rdda370f173474c47ab27c2cec7fea59a"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="abd8593eb855744a09df892c87cecc5aa"><a name="abd8593eb855744a09df892c87cecc5aa"></a><a name="abd8593eb855744a09df892c87cecc5aa"></a>Manager_administrator</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a05348c51b79943fd852cf4a898f55be7"><a name="a05348c51b79943fd852cf4a898f55be7"></a><a name="a05348c51b79943fd852cf4a898f55be7"></a>MRS Manager系统管理员组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="r7766035de7164e83af6f574b17b67ea3"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a1cf1bfb8f82a42e98073c8ffbc3bc71f"><a name="a1cf1bfb8f82a42e98073c8ffbc3bc71f"></a><a name="a1cf1bfb8f82a42e98073c8ffbc3bc71f"></a>compcommon</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="ad6654265ef634bdfa1f59be322789ceb"><a name="ad6654265ef634bdfa1f59be322789ceb"></a><a name="ad6654265ef634bdfa1f59be322789ceb"></a>MRS系统内部组，用于访问集群公共资源。所有系统用户和系统运行用户默认加入此用户组。</p>
</td>
</tr>
<tr id="r8eabd320d9f44da1a77a7ff00aea627b"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="ae834a92432b4495e87ed8afe26382e62"><a name="ae834a92432b4495e87ed8afe26382e62"></a><a name="ae834a92432b4495e87ed8afe26382e62"></a>default_1000</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a73209d5b31884b1a9a504293113d5d1d"><a name="a73209d5b31884b1a9a504293113d5d1d"></a><a name="a73209d5b31884b1a9a504293113d5d1d"></a>为租户创建的用户组。系统内部组，仅限组件间内部使用。</p>
</td>
</tr>
<tr id="r05b9c2b0a96749daa1501b0f38c2ecd4"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a928e9974dc2a468aa78038d3bd00cbac"><a name="a928e9974dc2a468aa78038d3bd00cbac"></a><a name="a928e9974dc2a468aa78038d3bd00cbac"></a>kafka</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a3f6961143de94d7a97afb2a40490b93f"><a name="a3f6961143de94d7a97afb2a40490b93f"></a><a name="a3f6961143de94d7a97afb2a40490b93f"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限,才能访问对应Topic。</p>
</td>
</tr>
<tr id="r38782380cf314f34a6b66537ffa8c9b5"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="afc83cb0962234871a1d189d4e6e95177"><a name="afc83cb0962234871a1d189d4e6e95177"></a><a name="afc83cb0962234871a1d189d4e6e95177"></a>kafkasuperuser</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a6bdad5adf8514b9cb7eac7d5ba76da09"><a name="a6bdad5adf8514b9cb7eac7d5ba76da09"></a><a name="a6bdad5adf8514b9cb7eac7d5ba76da09"></a>添加入本组的用户，拥有所有Topic的读写权限。</p>
</td>
</tr>
<tr id="re7a7cef3b33649738d39421c1c7d0b47"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="afa32625786b84845b61e362d8b9db361"><a name="afa32625786b84845b61e362d8b9db361"></a><a name="afa32625786b84845b61e362d8b9db361"></a>kafkaadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a0ef55c8643954d3bbd0407b9b0a75f3c"><a name="a0ef55c8643954d3bbd0407b9b0a75f3c"></a><a name="a0ef55c8643954d3bbd0407b9b0a75f3c"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
</td>
</tr>
<tr id="rb81c359f38cf42e182169417619071b5"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="ab2954e7055fb4f6c83872a53c9116780"><a name="ab2954e7055fb4f6c83872a53c9116780"></a><a name="ab2954e7055fb4f6c83872a53c9116780"></a>storm</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="ac49a11ddf7aa4630a74916753b22cc9a"><a name="ac49a11ddf7aa4630a74916753b22cc9a"></a><a name="ac49a11ddf7aa4630a74916753b22cc9a"></a>Storm的普通用户组，属于该组的用户拥有提交拓扑和管理属于自己的拓扑的权限。</p>
</td>
</tr>
<tr id="r0ae245b8b9ff4207a2093debbbeb6e43"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="a5bd373bf0eaa43beaefc7e6ec628b09d"><a name="a5bd373bf0eaa43beaefc7e6ec628b09d"></a><a name="a5bd373bf0eaa43beaefc7e6ec628b09d"></a>stormadmin</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="a173acadcc8f84d5291f5501df94fb3e1"><a name="a173acadcc8f84d5291f5501df94fb3e1"></a><a name="a173acadcc8f84d5291f5501df94fb3e1"></a>Storm的管理员用户组，属于该组的用户拥有提交拓扑和管理所有拓扑的权限。</p>
</td>
</tr>
<tr id="row27417114223"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p167651112216"><a name="p167651112216"></a><a name="p167651112216"></a>opentsdb</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p20764132213"><a name="p20764132213"></a><a name="p20764132213"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="row19592192215"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p1295182132220"><a name="p1295182132220"></a><a name="p1295182132220"></a>presto</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p09519262216"><a name="p09519262216"></a><a name="p09519262216"></a>普通用户组，将用户加入此用户组不会获得额外的权限。</p>
</td>
</tr>
<tr id="row034022733613"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p1234162763610"><a name="p1234162763610"></a><a name="p1234162763610"></a>flume</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p33413274361"><a name="p33413274361"></a><a name="p33413274361"></a>普通用户组，添加到该用户组的用户无任何额外权限。</p>
</td>
</tr>
<tr id="row132616287364"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.1.3.1.1 "><p id="p192611228183611"><a name="p192611228183611"></a><a name="p192611228183611"></a>launcher-job</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.1.3.1.2 "><p id="p92611528163616"><a name="p92611528163616"></a><a name="p92611528163616"></a>MRS系统内部组，用于使用V2接口提交作业。</p>
</td>
</tr>
</tbody>
</table>

<a name="tb626363ed65e402db25e807c2d3b9bf8"></a>
<table><thead align="left"><tr id="rf7d8dfafbe3c4db380c6ca9ae6e3de9a"><th class="cellrowborder" valign="top" width="35.449999999999996%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0039905375_p108162799453"><a name="zh-cn_topic_0039905375_p108162799453"></a><a name="zh-cn_topic_0039905375_p108162799453"></a>操作系统用户组</p>
</th>
<th class="cellrowborder" valign="top" width="64.55%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0039905375_p315392209453"><a name="zh-cn_topic_0039905375_p315392209453"></a><a name="zh-cn_topic_0039905375_p315392209453"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="rd96b4b9a827a45b89d177b6c69899956"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p412556129453"><a name="zh-cn_topic_0039905375_p412556129453"></a><a name="zh-cn_topic_0039905375_p412556129453"></a>wheel</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p280260249453"><a name="zh-cn_topic_0039905375_p280260249453"></a><a name="zh-cn_topic_0039905375_p280260249453"></a>MRS集群系统内部运行用户“omm”的主组。</p>
</td>
</tr>
<tr id="r1516690e1114405ab6277ba6046e41a7"><td class="cellrowborder" valign="top" width="35.449999999999996%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0039905375_p371687299453"><a name="zh-cn_topic_0039905375_p371687299453"></a><a name="zh-cn_topic_0039905375_p371687299453"></a>ficommon</p>
</td>
<td class="cellrowborder" valign="top" width="64.55%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0039905375_p575311339453"><a name="zh-cn_topic_0039905375_p575311339453"></a><a name="zh-cn_topic_0039905375_p575311339453"></a>MRS集群系统公共组，对应“compcommon”，可以访问集群在操作系统中保存的公共资源文件。</p>
</td>
</tr>
</tbody>
</table>

## 数据库用户<a name="s440b3ede47f644ba9487dfcb0c33946a"></a>

MRS集群系统数据库用户包含OMS数据库用户、DBService数据库用户。

>![](public_sys-resources/icon-note.gif) **说明：** 
>数据库用户不能删除，否则可能导致集群或组件服务无法正常工作。

<a name="td88a77ed35f74ba58ec71944adb700ec"></a>
<table><thead align="left"><tr id="r3f2f2e5a358247e99299781263514b27"><th class="cellrowborder" valign="top" width="21.172117211721172%" id="mcps1.1.5.1.1"><p id="a8fea2203ff3c4e87b2ce27e3bc8ab10a"><a name="a8fea2203ff3c4e87b2ce27e3bc8ab10a"></a><a name="a8fea2203ff3c4e87b2ce27e3bc8ab10a"></a>类别</p>
</th>
<th class="cellrowborder" valign="top" width="21.03210321032103%" id="mcps1.1.5.1.2"><p id="a71838f8eb417474fb9da0c87da81a82e"><a name="a71838f8eb417474fb9da0c87da81a82e"></a><a name="a71838f8eb417474fb9da0c87da81a82e"></a>默认用户</p>
</th>
<th class="cellrowborder" valign="top" width="20.862086208620862%" id="mcps1.1.5.1.3"><p id="a6b8c0dccb89a4f1995c8bdfa97c090ac"><a name="a6b8c0dccb89a4f1995c8bdfa97c090ac"></a><a name="a6b8c0dccb89a4f1995c8bdfa97c090ac"></a>初始密码</p>
</th>
<th class="cellrowborder" valign="top" width="36.933693369336936%" id="mcps1.1.5.1.4"><p id="aa32827fce9f94389921e7944c8544486"><a name="aa32827fce9f94389921e7944c8544486"></a><a name="aa32827fce9f94389921e7944c8544486"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="r23e2048060c649f796e2da4451f26ba3"><td class="cellrowborder" rowspan="2" valign="top" width="21.172117211721172%" headers="mcps1.1.5.1.1 "><p id="a77b1dfce79f545efa4af627a3993b302"><a name="a77b1dfce79f545efa4af627a3993b302"></a><a name="a77b1dfce79f545efa4af627a3993b302"></a>OMS数据库</p>
</td>
<td class="cellrowborder" valign="top" width="21.03210321032103%" headers="mcps1.1.5.1.2 "><p id="a564f46a9a8a046fbb03cc124434167e0"><a name="a564f46a9a8a046fbb03cc124434167e0"></a><a name="a564f46a9a8a046fbb03cc124434167e0"></a>ommdba</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="ab2447cdd41e9428ca1ff5211e734d283"><a name="ab2447cdd41e9428ca1ff5211e734d283"></a><a name="ab2447cdd41e9428ca1ff5211e734d283"></a>dbChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="a02523534bc8b46e4a480b3a205b58d7e"><a name="a02523534bc8b46e4a480b3a205b58d7e"></a><a name="a02523534bc8b46e4a480b3a205b58d7e"></a>OMS数据库管理员用户，用于创建、启动和停止等维护操作</p>
</td>
</tr>
<tr id="reb4963b4936e42d0ab009f72d3df32d3"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="aeb04d10838f541a0bf0061611d757d63"><a name="aeb04d10838f541a0bf0061611d757d63"></a><a name="aeb04d10838f541a0bf0061611d757d63"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="a678c5db3f5b5455889c1b6d94901aecb"><a name="a678c5db3f5b5455889c1b6d94901aecb"></a><a name="a678c5db3f5b5455889c1b6d94901aecb"></a>ChangeMe@123456</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="a7536eb415f6e4cc7ade6fefa85c59ee0"><a name="a7536eb415f6e4cc7ade6fefa85c59ee0"></a><a name="a7536eb415f6e4cc7ade6fefa85c59ee0"></a>OMS数据库数据访问用户</p>
</td>
</tr>
<tr id="r4ea56ebeb5184a52ad24591ca75cb100"><td class="cellrowborder" rowspan="5" valign="top" width="21.172117211721172%" headers="mcps1.1.5.1.1 "><p id="a5bf21fd8ad014379acc952eccbc04415"><a name="a5bf21fd8ad014379acc952eccbc04415"></a><a name="a5bf21fd8ad014379acc952eccbc04415"></a>DBService数据库</p>
<p id="p16816104761518"><a name="p16816104761518"></a><a name="p16816104761518"></a></p>
</td>
<td class="cellrowborder" valign="top" width="21.03210321032103%" headers="mcps1.1.5.1.2 "><p id="ab65e71a4a6b74a3dac40b77f86ff8eae"><a name="ab65e71a4a6b74a3dac40b77f86ff8eae"></a><a name="ab65e71a4a6b74a3dac40b77f86ff8eae"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="20.862086208620862%" headers="mcps1.1.5.1.3 "><p id="a63c64a4581724f9da63cdfd02f6ad012"><a name="a63c64a4581724f9da63cdfd02f6ad012"></a><a name="a63c64a4581724f9da63cdfd02f6ad012"></a>dbserverAdmin@123</p>
</td>
<td class="cellrowborder" valign="top" width="36.933693369336936%" headers="mcps1.1.5.1.4 "><p id="a16fba29a1a7845e593a1494f1a87e7f0"><a name="a16fba29a1a7845e593a1494f1a87e7f0"></a><a name="a16fba29a1a7845e593a1494f1a87e7f0"></a>DBService组件中GaussDB数据库的管理员用户</p>
</td>
</tr>
<tr id="rb9412b2fa8c34f8f8449befa4ff9001a"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="ac30260ef088f4c93a77a40e105ebb921"><a name="ac30260ef088f4c93a77a40e105ebb921"></a><a name="ac30260ef088f4c93a77a40e105ebb921"></a>hive</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0039905375_p103531994551"><a name="zh-cn_topic_0039905375_p103531994551"></a><a name="zh-cn_topic_0039905375_p103531994551"></a>HiveUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="abe48921bebd24b6aa26eb47bc8e48639"><a name="abe48921bebd24b6aa26eb47bc8e48639"></a><a name="abe48921bebd24b6aa26eb47bc8e48639"></a>Hive连接DBService数据库用户</p>
</td>
</tr>
<tr id="red2aae28995f4e9bbeec4ec5345a6174"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="ae00c4991cebc4fa8a8d633302f4e4c16"><a name="ae00c4991cebc4fa8a8d633302f4e4c16"></a><a name="ae00c4991cebc4fa8a8d633302f4e4c16"></a>hue</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="a7c77ef536cfb44408633d65ba0a65859"><a name="a7c77ef536cfb44408633d65ba0a65859"></a><a name="a7c77ef536cfb44408633d65ba0a65859"></a>HueUser@123</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="af2032b5030dd4fbeab1821a8b743e153"><a name="af2032b5030dd4fbeab1821a8b743e153"></a><a name="af2032b5030dd4fbeab1821a8b743e153"></a>Hue连接DBService数据库用户</p>
</td>
</tr>
<tr id="row35344708105120"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p35509001105120"><a name="p35509001105120"></a><a name="p35509001105120"></a>sqoop</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p57656838105120"><a name="p57656838105120"></a><a name="p57656838105120"></a>SqoopUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p39692320105120"><a name="p39692320105120"></a><a name="p39692320105120"></a>Loader连接DBService数据库的用户</p>
</td>
</tr>
<tr id="row128151547151515"><td class="cellrowborder" valign="top" headers="mcps1.1.5.1.1 "><p id="p128161347101511"><a name="p128161347101511"></a><a name="p128161347101511"></a>ranger</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.2 "><p id="p16816154781516"><a name="p16816154781516"></a><a name="p16816154781516"></a>RangerUser@</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.1.5.1.3 "><p id="p2081612477158"><a name="p2081612477158"></a><a name="p2081612477158"></a>Ranger连接DBService数据库的用户</p>
</td>
</tr>
</tbody>
</table>

