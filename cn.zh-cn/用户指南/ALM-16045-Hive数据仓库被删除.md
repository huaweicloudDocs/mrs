# ALM-16045 Hive数据仓库被删除<a name="ALM-16045"></a>

## 告警解释<a name="section6164578"></a>

系统每60秒周期性检测Hive数据仓库情况，Hive数据仓库被删除告警。

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
<tbody><tr id="row55255963"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p46547994"><a name="p46547994"></a><a name="p46547994"></a>16045</p>
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
<tbody><tr id="row10942151132215"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
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

Hive默认数据仓库被删除，会导致在默认数据仓库中创建库、创建表失败，影响业务正常使用。

## 可能原因<a name="section46264140"></a>

Hive定时查看默认数据仓库的状态，发现Hive默认数据仓库被删除。

## 处理步骤<a name="section91416156914"></a>

**检查Hive默认数据仓库。**

1.  以**root**用户登录客户端所在节点，用户密码为安装前用户自定义，请咨询系统管理员。

1.  执行以下命令，检查“hdfs://hacluster/user/_\{用户名\}_/.Trash/Current/ ”目录下是否存在该warehouse目录。

    **hdfs dfs -ls hdfs://hacluster/user/**_<用户名\>_**/.Trash/Current/**

    例如存在“user/hive/warehouse“：

    ```
    host01:/opt/Bigdata/client # hdfs dfs -ls hdfs://hacluster/user/test/.Trash/Current/
    Found 1 items
    drwx------   - test hadoop          0 2019-06-17 19:53 hdfs://hacluster/user/test/.Trash/Current/user
    ```

    -   是，执行[3](#li1470212916466)。
    -   否，执行[5](#li185241657121312)。


1.  <a name="li1470212916466"></a>默认数据仓库存在自动恢复机制，用户可等待默认数据仓库的恢复（5 \~10s）。如果未恢复，用户可执行以下命令，将warehouse重新复原。

    **hdfs dfs -mv hdfs://hacluster/user/**_<用户名\>_**/.Trash/Current/user/hive/warehouse /user/hive/warehouse**

2.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[5](#li185241657121312)。


**收集故障信息。**

1.  <a name="li185241657121312"></a>收集客户端后台“/.Trash/Current/”目录下内容的相关信息。
2.  请联系运维人员，并发送已收集的故障信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section56407894"></a>

无。

