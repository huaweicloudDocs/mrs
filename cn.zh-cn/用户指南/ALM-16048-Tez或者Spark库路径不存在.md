# ALM-16048 Tez或者Spark库路径不存在<a name="ALM-16048"></a>

## 告警解释<a name="section42896681"></a>

系统每180秒周期性检测Tez和Spark库路径，不存在则产生该告警。

## 告警属性<a name="section50525815"></a>

<a name="table61893760"></a>
<table><thead align="left"><tr id="row9197749"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p6820189"><a name="p6820189"></a><a name="p6820189"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p15564413"><a name="p15564413"></a><a name="p15564413"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p52757950"><a name="p52757950"></a><a name="p52757950"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row45535559"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p640291610276"><a name="p640291610276"></a><a name="p640291610276"></a>16048</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p440210164273"><a name="p440210164273"></a><a name="p440210164273"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1240317163275"><a name="p1240317163275"></a><a name="p1240317163275"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section52079156"></a>

<a name="table41718498"></a>
<table><thead align="left"><tr id="row3441097"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p10293461"><a name="p10293461"></a><a name="p10293461"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p28464046"><a name="p28464046"></a><a name="p28464046"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row316519506210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p156438591896"><a name="p156438591896"></a><a name="p156438591896"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row23886395"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p65062640"><a name="p65062640"></a><a name="p65062640"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19444883"><a name="p19444883"></a><a name="p19444883"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row40786223"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p35626567"><a name="p35626567"></a><a name="p35626567"></a>角色名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p35373576"><a name="p35373576"></a><a name="p35373576"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="row49926729"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p51620924"><a name="p51620924"></a><a name="p51620924"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p10903797"><a name="p10903797"></a><a name="p10903797"></a>产生告警的主机名。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section66059225"></a>

Tez或者Spark库路径不存在，会影响Hive on Tez，Hive on Spark的功能。

## 可能原因<a name="section57662120"></a>

Tez或者Spark在HDFS上库路径被删除。

## 处理步骤<a name="section17691921153318"></a>

**检查Tez和Spark库路径。**

1.  以**root**用户登录客户端所在节点，用户密码为安装前用户自定义，请咨询系统管理员。

1.  执行以下命令，检查“hdfs://hacluster/user/_\{用户名\}_/.Trash/Current/ ”目录下是否存在该tezlib或者sparklib目录。

    **hdfs dfs -ls hdfs://hacluster/user/**_<用户名\>_**/.Trash/Current/**

    例如存在“/user/hive/tezlib/8.1.0.1/”和“/user/hive/sparklib/8.1.0.1/”：

    ```
    host01:/opt/Bigdata/client # hdfs dfs -ls hdfs://hacluster/user/test/.Trash/Current/
    Found 1 items
    drwx------   - test hadoop          0 2019-06-17 19:53 hdfs://hacluster/user/test/.Trash/Current/user
    ```

    -   是，执行[3](#li1470212916466)。
    -   否，执行[5](#li185241657121312)。


1.  <a name="li1470212916466"></a>执行以下命令，将tezlib和sparklib重新复原。

    **hdfs dfs -mv hdfs://hacluster/user/**_<用户名\>_**/.Trash/Current/user/hive/tezlib/8.1.0.1/tez.tar.gz /user/hive/tezlib/8.1.0.1/tez.tar.gz**

2.  查看本告警是否恢复。
    -   是，操作结束。
    -   否，执行[5](#li185241657121312)。


**收集故障信息。**

1.  <a name="li185241657121312"></a>收集客户端后台“/.Trash/Current/”目录下内容的相关信息。
2.  请联系运维人员，并发送已收集的故障信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40120107"></a>

无。

