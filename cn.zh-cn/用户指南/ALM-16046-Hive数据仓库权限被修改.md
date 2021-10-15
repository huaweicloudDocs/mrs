# ALM-16046 Hive数据仓库权限被修改<a name="ALM-16046"></a>

## 告警解释<a name="section6164578"></a>

系统每60秒周期性检测Hive数据仓库的权限是否被修改，如果修改发出告警。

## 告警属性<a name="section55481207"></a>

<a name="table53284255"></a>
<table><thead align="left"><tr id="row47341147"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p9427704"><a name="p9427704"></a><a name="p9427704"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p25446578"><a name="p25446578"></a><a name="p25446578"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p47906928"><a name="p47906928"></a><a name="p47906928"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row55255963"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46547994"><a name="p46547994"></a><a name="p46547994"></a>16046</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p12291158"><a name="p12291158"></a><a name="p12291158"></a>紧急</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p56059702"><a name="p56059702"></a><a name="p56059702"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section29568819"></a>

<a name="table44541986"></a>
<table><thead align="left"><tr id="row29181518"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p14892770"><a name="p14892770"></a><a name="p14892770"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p65463685"><a name="p65463685"></a><a name="p65463685"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row487465518215"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row958306"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46323684"><a name="p46323684"></a><a name="p46323684"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row14259978"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p9959664"><a name="p9959664"></a><a name="p9959664"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row22528119"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p33276087"><a name="p33276087"></a><a name="p33276087"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section64792783"></a>

Hive默认数据仓库的权限被修改，会影响当前用户，用户组，其他用户在默认数据仓库中创建库、创建表等操作的操作权限范围。会扩大或缩小权限。

## 可能原因<a name="section46264140"></a>

Hive定时查看默认数据仓库的状态，发现Hive默认数据仓库权限发生更改。

## 处理步骤<a name="section91416156914"></a>

**检查Hive默认数据仓库权限情况。**

1.  以**root**用户登录客户端所在节点，用户密码为安装前用户自定义，请咨询系统管理员。

1.  请使用具有supergroup组权限的用户，根据当前集群情况恢复目录权限：
    -   安全环境：执行命令**hdfs dfs -chmod 770 hdfs://hacluster/user/hive/warehouse**修复默认数据仓库权限。
    -   非安全环境：执行命令**hdfs dfs -chmod 777 hdfs://hacluster/user/hive/warehouse**修复默认数据仓库权限。

2.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[4](#li14150557160)。


**收集故障信息。**

1.  <a name="li14150557160"></a>收集客户端后台“hdfs://hacluster/user/hive/warehouse”目录下内容的相关信息。
2.  请联系运维人员，并发送已收集的故障信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

