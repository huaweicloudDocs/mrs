# 使用HBase客户端<a name="mrs_01_24187"></a>

## 操作场景<a name="zh-cn_topic_0264266039_sa6f26f4d73194c3aac199d5a2504b08f"></a>

该任务指导用户在运维场景或业务场景中使用HBase客户端。

## 前提条件<a name="zh-cn_topic_0264266039_s575f22d757a24b5a85a68692161d0106"></a>

-   已安装客户端。例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。
-   各组件业务用户由系统管理员根据业务需要创建。

    “机机”用户需要下载keytab文件，“人机”用户第一次登录时需修改密码。

-   非**root**用户使用HBase客户端，请确保该HBase客户端目录的属主为该用户，否则请参考如下命令修改属主。

    **chown user:group -R** _客户端安装目录_**/HBase**


## 使用Hbase客户端（MRS 3.x之前版本）<a name="zh-cn_topic_0264266039_section639319572712"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令切换到客户端目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户，当前用户需要具有创建HBase表的权限，具体请参见[创建角色](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0343.html)配置拥有对应权限的角色，参考[创建用户](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0345.html)章节，为用户绑定对应角色。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** _组件业务用户_

    例如，**kinit** **hbaseuser**。

6.  直接执行HBase组件的客户端命令。

    **hbase shell**


## 使用HBase客户端（MRS 3.x及之后版本）<a name="zh-cn_topic_0264266039_section3155145073312"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。
2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令切换到客户端目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  若安装了HBase多实例，在使用客户端连接具体HBase实例时，请执行以下命令加载具体实例的环境变量，否则请跳过此步骤。例如，加载HBase2实例变量：

    **source HBase2/component\_env**

6.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户，当前用户需要具有创建HBase表的权限，具体请参见[创建角色](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0343.html)配置拥有对应权限的角色，参考[创建用户](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0345.html)章节，为用户绑定对应角色。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** _组件业务用户_

    例如，**kinit** **hbaseuser**。

7.  直接执行HBase组件的客户端命令。

    **hbase shell**


## HBase客户端常用命令<a name="zh-cn_topic_0264266039_section105048910387"></a>

常用的HBase客户端命令如下表所示。更多命令可参考[http://hbase.apache.org/2.2/book.html](http://hbase.apache.org/2.2/book.html)

**表 1**  HBase客户端命令

<a name="zh-cn_topic_0264266039_table25854914381"></a>
<table><thead align="left"><tr id="zh-cn_topic_0264266039_row558413963813"><th class="cellrowborder" valign="top" width="19.36%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0264266039_p458415973817"><a name="zh-cn_topic_0264266039_p458415973817"></a><a name="zh-cn_topic_0264266039_p458415973817"></a>命令</p>
</th>
<th class="cellrowborder" valign="top" width="80.64%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0264266039_p115847943810"><a name="zh-cn_topic_0264266039_p115847943810"></a><a name="zh-cn_topic_0264266039_p115847943810"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0264266039_row185847917385"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p155840910385"><a name="zh-cn_topic_0264266039_p155840910385"></a><a name="zh-cn_topic_0264266039_p155840910385"></a>create</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p175845943820"><a name="zh-cn_topic_0264266039_p175845943820"></a><a name="zh-cn_topic_0264266039_p175845943820"></a>创建一张表，例如<strong id="zh-cn_topic_0264266039_b13584139193813"><a name="zh-cn_topic_0264266039_b13584139193813"></a><a name="zh-cn_topic_0264266039_b13584139193813"></a>create 'test', 'f1', 'f2', 'f3'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row1358513910387"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p358439103812"><a name="zh-cn_topic_0264266039_p358439103812"></a><a name="zh-cn_topic_0264266039_p358439103812"></a>disable</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p155841199381"><a name="zh-cn_topic_0264266039_p155841199381"></a><a name="zh-cn_topic_0264266039_p155841199381"></a>停止指定的表，例如<strong id="zh-cn_topic_0264266039_b458417912388"><a name="zh-cn_topic_0264266039_b458417912388"></a><a name="zh-cn_topic_0264266039_b458417912388"></a>disable 'test'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row11585129193811"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p175854917387"><a name="zh-cn_topic_0264266039_p175854917387"></a><a name="zh-cn_topic_0264266039_p175854917387"></a>enable</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p165851097380"><a name="zh-cn_topic_0264266039_p165851097380"></a><a name="zh-cn_topic_0264266039_p165851097380"></a>启动指定的表，例如<strong id="zh-cn_topic_0264266039_b1358559123820"><a name="zh-cn_topic_0264266039_b1358559123820"></a><a name="zh-cn_topic_0264266039_b1358559123820"></a>enable 'test'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row45856911382"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p95852916383"><a name="zh-cn_topic_0264266039_p95852916383"></a><a name="zh-cn_topic_0264266039_p95852916383"></a>alter</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p75857915383"><a name="zh-cn_topic_0264266039_p75857915383"></a><a name="zh-cn_topic_0264266039_p75857915383"></a>更改表结构。可以通过alter命令增加、修改、删除列族信息以及表相关的参数值，例如<strong id="zh-cn_topic_0264266039_b15851999389"><a name="zh-cn_topic_0264266039_b15851999389"></a><a name="zh-cn_topic_0264266039_b15851999389"></a>alter 'test', {NAME =&gt; 'f3', METHOD =&gt; 'delete'}</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row1058515923811"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p55856933811"><a name="zh-cn_topic_0264266039_p55856933811"></a><a name="zh-cn_topic_0264266039_p55856933811"></a>describe</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p05851792382"><a name="zh-cn_topic_0264266039_p05851792382"></a><a name="zh-cn_topic_0264266039_p05851792382"></a>获取表的描述信息，例如<strong id="zh-cn_topic_0264266039_b05852918380"><a name="zh-cn_topic_0264266039_b05852918380"></a><a name="zh-cn_topic_0264266039_b05852918380"></a>describe 'test'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row558599203810"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p758599133812"><a name="zh-cn_topic_0264266039_p758599133812"></a><a name="zh-cn_topic_0264266039_p758599133812"></a>drop</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p17585993386"><a name="zh-cn_topic_0264266039_p17585993386"></a><a name="zh-cn_topic_0264266039_p17585993386"></a>删除指定表。删除前表必须已经是停止状态，例如<strong id="zh-cn_topic_0264266039_b125851195380"><a name="zh-cn_topic_0264266039_b125851195380"></a><a name="zh-cn_topic_0264266039_b125851195380"></a>drop 'test'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row1658510943814"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p15858916383"><a name="zh-cn_topic_0264266039_p15858916383"></a><a name="zh-cn_topic_0264266039_p15858916383"></a>put</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p1558516912386"><a name="zh-cn_topic_0264266039_p1558516912386"></a><a name="zh-cn_topic_0264266039_p1558516912386"></a>写入指定cell的value。Cell的定位由表、rowk、列组合起来唯一决定，例如<strong id="zh-cn_topic_0264266039_b135853914388"><a name="zh-cn_topic_0264266039_b135853914388"></a><a name="zh-cn_topic_0264266039_b135853914388"></a>put 'test','r1','f1:c1','myvalue1'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row125859913382"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p45854903813"><a name="zh-cn_topic_0264266039_p45854903813"></a><a name="zh-cn_topic_0264266039_p45854903813"></a>get</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p35851093384"><a name="zh-cn_topic_0264266039_p35851093384"></a><a name="zh-cn_topic_0264266039_p35851093384"></a>获取行的值或者行的指定cell的值。例如<strong id="zh-cn_topic_0264266039_b558549153819"><a name="zh-cn_topic_0264266039_b558549153819"></a><a name="zh-cn_topic_0264266039_b558549153819"></a>get 'test','r1'</strong>。</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266039_row16585129193817"><td class="cellrowborder" valign="top" width="19.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0264266039_p175859963812"><a name="zh-cn_topic_0264266039_p175859963812"></a><a name="zh-cn_topic_0264266039_p175859963812"></a>scan</p>
</td>
<td class="cellrowborder" valign="top" width="80.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0264266039_p65859983811"><a name="zh-cn_topic_0264266039_p65859983811"></a><a name="zh-cn_topic_0264266039_p65859983811"></a>查询表数据。参数中指定表名和scanner，例如<strong id="zh-cn_topic_0264266039_b358516919384"><a name="zh-cn_topic_0264266039_b358516919384"></a><a name="zh-cn_topic_0264266039_b358516919384"></a>scan 'test'</strong>。</p>
</td>
</tr>
</tbody>
</table>

