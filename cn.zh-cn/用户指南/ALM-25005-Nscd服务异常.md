# ALM-25005 Nscd服务异常<a name="ALM-25005"></a>

## 告警解释<a name="section50910190"></a>

系统每60秒周期性检测nscd服务的状态，如果连续4次（3分钟）查询不到nscd进程或者无法获取ldapserver中的用户时，产生该告警。

当进程恢复且可以获取ldapserver中的用户时，告警恢复。

## 告警属性<a name="section55538530"></a>

<a name="table26122451"></a>
<table><thead align="left"><tr id="row66613897"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p27016537"><a name="p27016537"></a><a name="p27016537"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p40855861"><a name="p40855861"></a><a name="p40855861"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p20990470"><a name="p20990470"></a><a name="p20990470"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row22506548"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p11091110"><a name="p11091110"></a><a name="p11091110"></a>25005</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p25964741"><a name="p25964741"></a><a name="p25964741"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p22769272"><a name="p22769272"></a><a name="p22769272"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section30084722"></a>

<a name="table32371752"></a>
<table><thead align="left"><tr id="row57825413"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p53346883"><a name="p53346883"></a><a name="p53346883"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p26130306"><a name="p26130306"></a><a name="p26130306"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row105875515147"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row36180074"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p13415506"><a name="p13415506"></a><a name="p13415506"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row53630695"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p19219236"><a name="p19219236"></a><a name="p19219236"></a>产生告警的主机节点信息。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section2327049"></a>

nscd服务不可用时，可能会影响该节点从LdapServer上同步数据，此时，使用**id**命令可能会获取不到ldap中的数据，影响上层业务。

## 可能原因<a name="section20943447"></a>

-   nscd服务未启动。
-   网络故障，无法访问ldap服务器。
-   Name Service服务异常。
-   OS执行命令慢导致无法查询用户。

## 处理步骤<a name="section54273301"></a>

**检查nscd服务是否启动。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”。记录该告警定位信息中的“主机名”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1、IP2、IP3等）。
2.  联系运维人员，以**root**用户登录IP1节点，用户密码为安装前用户自定义，请咨询系统管理员，在该节点上执行**ps -ef | grep nscd**命令，查看是否有/usr/sbin/nscd进程启动。

    ```
    root       6893  12764  0 20:20 pts/2    00:00:00 grep nscd
    root       8480      1  0 Jun13 ?        00:31:49 /usr/sbin/nscd
    ```

    -   是，执行[5](#li423153448513)。
    -   否，执行[3](#li600689958513)。

3.  <a name="li600689958513"></a>以**root**用户执行**service nscd restart**命令，重启nscd服务，执行**ps -ef | grep nscd**命令，查看服务是否启动。
    -   是，执行[4](#li67767558513)。
    -   否，执行[15](#li265529978513)。

4.  <a name="li67767558513"></a>5分钟后，以**root**用户再次执行命令，查看服务是否存在。
    -   是，执行[11](#li551461168513)。
    -   否，执行[15](#li265529978513)。


**检查网络是否故障，无法访问ldap服务器。**

1.  <a name="li423153448513"></a>用**root**用户登录故障节点，在这个节点上使用**ping**命令检查该节点与LdapServer节点的网络是否畅通。
    -   是，执行[6](#li297764118513)。
    -   否，请联系网络管理员，解决网络故障。


**检查Name Service服务是否异常。**

1.  <a name="li297764118513"></a>用**root**用户登录故障节点，执行**cat /etc/nsswitch.conf**命令，查看NameService配置中的“passwd”、“group”、“services”、“netgroup”、“aliases”五项配置是否正确。

    正确配置请参照：“passwd: compat ldap”、“group:  compat ldap”、“services: files ldap”、“netgroup: files ldap”、“aliases:  files ldap”。

    -   是，执行[7](#li11806553308)。
    -   否，执行[9](#li195824098513)。

2.  <a name="li11806553308"></a>用**root**用户登录故障节点，执行**cat /etc/nscd.conf**命令，查看配置文件中“enable-cache passwd”、“positive-time-to-live passwd”、“enable-cache group”、“positive-time-to-live  group”四项配置是否正确。

    正确配置请参照： “enable-cache passwd yes ”、“positive-time-to-live  passwd 600”、“enable-cache group yes”、“positive-time-to-live group 3600”。

    -   是，执行[8](#li389947948513)。
    -   否，执行[10](#li1648032715218)。

3.  <a name="li389947948513"></a>用**root**用户执行**/usr/sbin/nscd -i group**和**/usr/sbin/nscd -i passwd**命令，等待2分钟，继续执行**id admin**和**id backup/manager**命令，查看是否能查询到结果。

    ```
    host07:~ # id admin
    uid=20000(admin) gid=9998(ficommon) groups=9998(ficommon),8000(Manager_administrator_180)
    host07:~ # id backup/manager
    uid=20002(backup/manager) gid=10001(supergroup) groups=10001(supergroup)
    ```

    -   是，执行[11](#li551461168513)。
    -   否，执行[15](#li265529978513)。

4.  <a name="li195824098513"></a>以**root**用户执行**vi /etc/nsswitch.conf**命令，将[6](#li297764118513)中的五项配置项改成正确配置，保存后执行**service nscd restart**命令重启nscd服务，等待2分钟，执行**id admin**和**id backup/manager**命令，查看是否能查询到结果。
    -   是，执行[11](#li551461168513)。
    -   否，执行[15](#li265529978513)。

5.  <a name="li1648032715218"></a>以**root**用户执行**vi /etc/**nscd**.conf**命令，将[7](#li11806553308)中的四项配置项改成正确配置，保存后执行**service nscd restart**命令重启nscd服务，等待2分钟，执行**id admin**和**id backup/manager**命令，查看是否能查询到结果。
    -   是，执行[11](#li551461168513)。
    -   否，执行[15](#li265529978513)。

6.  <a name="li551461168513"></a>登录FusionInsight Manager界面，等待5分钟，然后查看“Nscd服务异常”告警是否恢复。
    -   是，处理完毕。
    -   否，执行[12](#li1693832195142)。


**检查操作系统执行命令是否卡顿。**

1.  <a name="li1693832195142"></a>用**root**用户登录故障节点，执行命令**id admin**，观察命令返回结果时长，观察执行命令是否缓慢（超过3s即可认为执行命令慢）。
    -   是，执行[13](#li97084049527)。
    -   否，执行[15](#li265529978513)。

2.  <a name="li97084049527"></a>执行命令**cat /var/log/messages**，查看nscd是否频繁重启或者存在Can't contact LDAP server的异常信息。

    nscd异常信息样例：

    ```
    Feb 11 11:44:42 10-120-205-33 nscd: nss_ldap: failed to bind to LDAP server ldaps://10.120.205.55:21780: Can't contact LDAP server
    Feb 11 11:44:43 10-120-205-33 ntpq: nss_ldap: failed to bind to LDAP server ldaps://10.120.205.55:21780: Can't contact LDAP server
    Feb 11 11:44:44 10-120-205-33 ntpq: nss_ldap: failed to bind to LDAP server ldaps://10.120.205.92:21780: Can't contact LDAP server
    ```

    -   是，执行[14](#li3335145595227)。
    -   否，执行[15](#li265529978513)。

3.  <a name="li3335145595227"></a>执行命令**vi $BIGDATA\_HOME/tmp/random\_ldap\_ip\_order**，修改末尾数字，若原本为奇数则改为偶数，若原本为偶数则修改为奇数；

    执行命令**vi /etc/ldap.conf**进入编辑模式，按“Insert”键开始编辑，然后将URI配置项的前两个IP进行调换。

    修改完成后按“Esc”键退出编辑模式，并输入**:wq**保存退出。

    执行命令**service nscd restart**，重启nscd服务，等待5分钟，再次执行**id admin**命令，观察返回结果时长，观察执行命令是否缓慢。

    -   是，执行[15](#li265529978513)。
    -   否，登录其他故障节点执行[12](#li1693832195142)至[14](#li3335145595227)；排查“/etc/ldap.conf”修改前URI中第一个ldapserver节点，是否故障，例如业务IP不可达、网络延时过长或者部署其他异常的软件。


**收集故障信息。**

1.  <a name="li265529978513"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“LdapClient”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section18697669"></a>

无。

