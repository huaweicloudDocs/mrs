# 修改OMS服务配置参数<a name="admin_guide_000162"></a>

## 操作场景<a name="zh-cn_topic_0263899481_sc966349c08c44723996237c6b7e403d1"></a>

根据用户环境的安全要求，管理员可以在FusionInsight Manager修改OMS中Kerberos与LDAP配置。

## 对系统的影响<a name="zh-cn_topic_0263899481_sfc16142de0954095bb08beec3e7e3f69"></a>

修改OMS的服务配置参数后，需要重启对应的OMS模块，此时FusionInsight Manager将无法正常使用。

## 操作步骤<a name="zh-cn_topic_0263899481_section2053565583820"></a>

**修改okerberos配置**

1.  登录FusionInsight Manager，选择“系统 \> OMS“。

1.  在okerberos所在行，单击“修改配置“。

1.  根据[表1](#zh-cn_topic_0263899481_table19796438111412)所示的说明修改参数。

    **表 1**  okerberos参数配置一览表

    <a name="zh-cn_topic_0263899481_table19796438111412"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0263899481_row679817382146"><th class="cellrowborder" valign="top" width="17.87%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0263899481_p4798638161419"><a name="zh-cn_topic_0263899481_p4798638161419"></a><a name="zh-cn_topic_0263899481_p4798638161419"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="82.13000000000001%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0263899481_p7800153811142"><a name="zh-cn_topic_0263899481_p7800153811142"></a><a name="zh-cn_topic_0263899481_p7800153811142"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0263899481_row380123821413"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p1680215384145"><a name="zh-cn_topic_0263899481_p1680215384145"></a><a name="zh-cn_topic_0263899481_p1680215384145"></a>连接KDC最大时延（毫秒）</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p15802133871410"><a name="zh-cn_topic_0263899481_p15802133871410"></a><a name="zh-cn_topic_0263899481_p15802133871410"></a>应用连接到Kerberos的超时时间，单位为毫秒，请填写整数值。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row680318387148"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p118031038151419"><a name="zh-cn_topic_0263899481_p118031038151419"></a><a name="zh-cn_topic_0263899481_p118031038151419"></a>最大尝试次数</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p980473816145"><a name="zh-cn_topic_0263899481_p980473816145"></a><a name="zh-cn_topic_0263899481_p980473816145"></a>应用连接到Kerberos的最大重试次数，请填写整数值。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row168046388140"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p3805153811149"><a name="zh-cn_topic_0263899481_p3805153811149"></a><a name="zh-cn_topic_0263899481_p3805153811149"></a>操作Ldap最大时延（毫秒）</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p19806153891418"><a name="zh-cn_topic_0263899481_p19806153891418"></a><a name="zh-cn_topic_0263899481_p19806153891418"></a>Kerberos连接LDAP的超时时间，单位为毫秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row280663812145"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p13807183831410"><a name="zh-cn_topic_0263899481_p13807183831410"></a><a name="zh-cn_topic_0263899481_p13807183831410"></a>搜索Ldap最大时延（毫秒）</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p6807143841416"><a name="zh-cn_topic_0263899481_p6807143841416"></a><a name="zh-cn_topic_0263899481_p6807143841416"></a>Kerberos在LDAP查询用户信息的超时时间，单位为毫秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row980883820140"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p178082038131415"><a name="zh-cn_topic_0263899481_p178082038131415"></a><a name="zh-cn_topic_0263899481_p178082038131415"></a>Kadmin监听端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p180963861410"><a name="zh-cn_topic_0263899481_p180963861410"></a><a name="zh-cn_topic_0263899481_p180963861410"></a>kadmin服务的端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row68091638171419"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p14811538151420"><a name="zh-cn_topic_0263899481_p14811538151420"></a><a name="zh-cn_topic_0263899481_p14811538151420"></a>KDC监听端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p781216389148"><a name="zh-cn_topic_0263899481_p781216389148"></a><a name="zh-cn_topic_0263899481_p781216389148"></a>kinit服务的端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0263899481_row7812038111414"><td class="cellrowborder" valign="top" width="17.87%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p1281303811415"><a name="zh-cn_topic_0263899481_p1281303811415"></a><a name="zh-cn_topic_0263899481_p1281303811415"></a>Kpasswd监听端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.13000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p128141138171412"><a name="zh-cn_topic_0263899481_p128141138171412"></a><a name="zh-cn_topic_0263899481_p128141138171412"></a>kpasswd服务的端口。</p>
    </td>
    </tr>
    </tbody>
    </table>

2.  单击“确定”。

    在弹出窗口输入当前登录用户密码验证身份，单击“确定”，在确认重启的对话框中单击“确定”。


**修改oldap配置**

1.  在oldap所在行，单击“修改配置“。

1.  根据[表2](#zh-cn_topic_0263899481_table1696932817285)所示的说明修改参数。

    **表 2**  oldap参数配置一览表

    <a name="zh-cn_topic_0263899481_table1696932817285"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0263899481_row1697112802816"><th class="cellrowborder" valign="top" width="17.95%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0263899481_p209711286282"><a name="zh-cn_topic_0263899481_p209711286282"></a><a name="zh-cn_topic_0263899481_p209711286282"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="82.05%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0263899481_p1971182813281"><a name="zh-cn_topic_0263899481_p1971182813281"></a><a name="zh-cn_topic_0263899481_p1971182813281"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0263899481_row8918329172914"><td class="cellrowborder" valign="top" width="17.95%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0263899481_p28143905"><a name="zh-cn_topic_0263899481_p28143905"></a><a name="zh-cn_topic_0263899481_p28143905"></a>Ldap服务监听端口</p>
    </td>
    <td class="cellrowborder" valign="top" width="82.05%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0263899481_p65063845"><a name="zh-cn_topic_0263899481_p65063845"></a><a name="zh-cn_topic_0263899481_p65063845"></a>LDAP服务端口号。</p>
    </td>
    </tr>
    </tbody>
    </table>

2.  单击“确定”。

    在弹出窗口输入当前登录用户密码验证身份，单击“确定”，在确认重启的对话框中单击“确定”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果重置LDAP帐户口令需要重启ACS，操作步骤如下：
    >1.  使用PuTTY，以**omm**用户登录主管理节点，执行以下命令更新域配置：
    >    **sh $\{BIGDATA\_HOME\}/om-server/om/sbin/restart-RealmConfig.sh**
    >    提示以下信息表示命令执行成功：
    >    ```
    >    Modify realm successfully. Use the new password to log into FusionInsight again.
    >    ```
    >2.  执行**sh $CONTROLLER\_HOME/sbin/acs\_cmd.sh stop**，停止ACS。
    >3.  执行**sh $CONTROLLER\_HOME/sbin/acs\_cmd.sh start**，启动ACS。


**重启集群**

1.  登录FusionInsight Manager，参考[滚动重启集群](滚动重启集群.md#admin_guide_000012)章节，重启集群。

