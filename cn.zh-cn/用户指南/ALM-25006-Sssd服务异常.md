# ALM-25006 Sssd服务异常<a name="ALM-25006"></a>

## 告警解释<a name="section6427584"></a>

系统每60秒周期性检测sssd服务的状态，如果连续4次（3分钟）查询不到sssd进程或者无法获取LdapServer中的用户时，产生该告警。

当进程恢复且可以获取LdapServer中的用户时，告警恢复。

## 告警属性<a name="section57848263"></a>

<a name="table53988588"></a>
<table><thead align="left"><tr id="row25963404"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p22660970"><a name="p22660970"></a><a name="p22660970"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p23599285"><a name="p23599285"></a><a name="p23599285"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p32493908"><a name="p32493908"></a><a name="p32493908"></a>是否自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="row14760880"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p54780592"><a name="p54780592"></a><a name="p54780592"></a>25006</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p8042940"><a name="p8042940"></a><a name="p8042940"></a>重要</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p47498429"><a name="p47498429"></a><a name="p47498429"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="section50872323"></a>

<a name="table22167579"></a>
<table><thead align="left"><tr id="row15017071"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p8423276"><a name="p8423276"></a><a name="p8423276"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p11196745"><a name="p11196745"></a><a name="p11196745"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="row1756114464143"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p13858113752316"><a name="p13858113752316"></a><a name="p13858113752316"></a>来源</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p187931338134115"><a name="p187931338134115"></a><a name="p187931338134115"></a>产生告警的集群名称。</p>
</td>
</tr>
<tr id="row34521134"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p39123317"><a name="p39123317"></a><a name="p39123317"></a>服务名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p748594"><a name="p748594"></a><a name="p748594"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="row6737354"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p66118565"><a name="p66118565"></a><a name="p66118565"></a>主机名</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p46152835"><a name="p46152835"></a><a name="p46152835"></a>产生告警的主机节点信息。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="section55197725"></a>

sssd服务不可用时，可能会影响该节点从LdapServer上同步数据，此时，使用**id**命令可能会获取不到ldap中的数据，影响上层业务。

## 可能原因<a name="section27017478"></a>

-   sssd服务未启动或启动错误。
-   网络故障，无法访问Ldap服务器。
-   Name Service服务异常。
-   OS执行命令慢导致无法查询用户。

## 处理步骤<a name="section41830711"></a>

**检查sssd服务是否启动或启动错误。**

1.  在FusionInsight Manager界面，选择“运维 \> 告警 \> 告警”。记录该告警定位信息中的“主机名”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1、IP2、IP3等）。
2.  <a name="li932573144835"></a>联系运维人员，以**root**用户登录IP1节点，用户密码为安装前用户自定义，请咨询系统管理员，在该节点执行**ps -ef | grep sssd**命令，查看是否有/usr/sbin/sssd进程启动。

    ```
    root       6893  12764  0 20:20 pts/2    00:00:00 grep sssd
    root       8480      1  0 Jun13 ?        00:33:19 /usr/sbin/sssd
    ```

    -   是，执行[3](#li159597144835)。
    -   否，执行[4](#li13136781144835)。

3.  <a name="li159597144835"></a>查看[2](#li932573144835)中查询的sssd进程是否有三个子进程。
    -   是，执行[5](#li55692079144835)。
    -   否，执行[4](#li13136781144835)。

4.  <a name="li13136781144835"></a>以**root**用户执行**service sssd restart**命令重启sssd服务，执行**ps -ef | grep sssd**命令，查看sssd进程是否正常。

    正常状态为：存在/usr/sbin/sssd进程和三个子进程/usr/libexec/sssd/sssd\_be、/usr/libexec/sssd/sssd\_nss、/usr/libexec/sssd/sssd\_pam。

    -   是，执行[9](#li51651957144835)。
    -   否，执行[13](#li51012442144835)。


**检查网络是否故障，无法访问ldap服务器。**

1.  <a name="li55692079144835"></a>用**root**用户登录故障节点，在这个节点上使用**ping**命令检查该节点与LdapServer节点的网络是否畅通。
    -   是，执行[6](#li61764950144835)。
    -   否，请联系网络管理员，解决网络故障。


**检查Name Service服务是否异常。**

1.  <a name="li61764950144835"></a>用**root**用户登录故障节点，执行命令**cat /etc/nsswitch.conf**，查看NameService配置中的“passwd”、“group”两项配置是否正确。

    正确配置请参照：“passwd: files sss”、“group:  files sss”。

    -   是，执行[7](#li14892428144835)。
    -   否，执行[8](#li49843606144835)。

2.  <a name="li14892428144835"></a>用**root**用户执行**/usr/sbin/sss\_cache -G**和**/usr/sbin/sss\_cache -U**命令，等待2分钟，执行**id admin**和**id backup/manager**命令，查看是否能查询到结果。
    -   是，执行[9](#li51651957144835)。
    -   否，执行[13](#li51012442144835)。

3.  <a name="li49843606144835"></a>以root用户执行**vi /etc/nsswitch.conf**命令，将[6](#li61764950144835)中的两项配置项改成正确配置，保存后执行**service sssd restart**命令重启sssd服务，等待2分钟，执行**id admin**和**id backup/manager**命令，查看是否能查询到结果。

    ```
    host07:~ # id admin
    uid=20000(admin) gid=9998(ficommon) groups=9998(ficommon),8000(Manager_administrator_180)
    host07:~ # id backup/manager
    uid=20002(backup/manager) gid=10001(supergroup) groups=10001(supergroup)
    ```

    -   是，执行[9](#li51651957144835)。
    -   否，执行[13](#li51012442144835)。

4.  <a name="li51651957144835"></a>登录FusionInsight Manager界面，等待5分钟，然后查看“Sssd服务异常”告警是否恢复。
    -   是，处理完毕。
    -   否，执行[10](#li6618403710103)。


**检查操作系统执行命令是否卡顿。**

1.  <a name="li6618403710103"></a>用**root**用户登录故障节点，执行命令**id admin**，观察命令返回结果时长，观察执行命令是否缓慢（超过3s即可认为执行命令慢）。
    -   是，执行[11](#li25024858101018)。
    -   否，执行[13](#li51012442144835)。

2.  <a name="li25024858101018"></a>执行命令**cat /var/log/messages**，查看sssd是否频繁重启或者存在Can't contact LDAP server的异常信息。

    sssd重启样例

    ```
    Feb  7 11:38:16 10-132-190-105 sssd[pam]: Shutting down
    Feb  7 11:38:16 10-132-190-105 sssd[nss]: Shutting down
    Feb  7 11:38:16 10-132-190-105 sssd[nss]: Shutting down
    Feb  7 11:38:16 10-132-190-105 sssd[be[default]]: Shutting down
    Feb  7 11:38:16 10-132-190-105 sssd: Starting up
    Feb  7 11:38:16 10-132-190-105 sssd[be[default]]: Starting up
    Feb  7 11:38:16 10-132-190-105 sssd[nss]: Starting up
    Feb  7 11:38:16 10-132-190-105 sssd[pam]: Starting up
    ```

    -   是，执行[12](#li64758911101029)。
    -   否，执行[13](#li51012442144835)。

3.  <a name="li64758911101029"></a>执行命令**vi $BIGDATA\_HOME/tmp/random\_ldap\_ip\_order**，修改末尾数字，若原本为奇数则改为偶数，若原本为偶数则修改为奇数。

    执行命令**vi /etc/sssd/sssd.conf**，将ldap\_uri配置项的前两个IP进行颠倒，保存退出。

    执行命令**ps -ef | grep sssd**查询sssd进程id，并将其kill掉，执**行/usr/sbin/sssd -D -f**，重启sssd服务，等待5分钟，再次执行**id admin**命令。

    观察返回结果时长，观察执行命令是否缓慢。

    -   是，执行[13](#li51012442144835)。
    -   否，登录其他故障节点执行[10](#li6618403710103)至[12](#li64758911101029)；收集日志，并排查“/etc/sssd/sssd.conf”修改前ldap\_uri中第一个ldapserver节点是否故障，例如业务IP不可达、网络延时过长或者部署其他异常的软件。


**收集故障信息。**

1.  <a name="li51012442144835"></a>在FusionInsight Manager界面，选择“运维 \> 日志 \> 下载”。
2.  在“服务”中勾选待操作集群的“LdapClient”。
3.  单击右上角的![](figures/zh-cn_image_0263895532.png)设置日志收集的“开始时间”和“结束时间”分别为告警产生时间的前后1小时，单击“下载”。
4.  请联系运维人员，并发送已收集的故障日志信息。

## 告警清除<a name="section169311343318"></a>

此告警修复后，系统会自动清除此告警，无需手工清除。

## 参考信息<a name="section40932081"></a>

无。

