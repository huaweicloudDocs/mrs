# ALM-25004 LdapServer数据同步异常<a name="ZH-CN_TOPIC_0093195069"></a>

## 告警解释<a name="zh-cn_topic_0035998743_section47176343"></a>

当Manager中LdapServer数据内容不一致时，产生该告警，当两者的数据一致时，对应告警恢复。

当集群中LdapServer与Manager中的LdapServer数据内容不一致时，产生该告警，当两者的数据一致时，对应告警恢复。

## 告警属性<a name="zh-cn_topic_0035998743_section21933905"></a>

<a name="zh-cn_topic_0035998743_table53406450"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998743_row25792371"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0035998743_p8807292"><a name="zh-cn_topic_0035998743_p8807292"></a><a name="zh-cn_topic_0035998743_p8807292"></a>告警ID</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0035998743_p42302050"><a name="zh-cn_topic_0035998743_p42302050"></a><a name="zh-cn_topic_0035998743_p42302050"></a>告警级别</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0035998743_p3913996"><a name="zh-cn_topic_0035998743_p3913996"></a><a name="zh-cn_topic_0035998743_p3913996"></a>可自动清除</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998743_row48598242"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0035998743_p44143566"><a name="zh-cn_topic_0035998743_p44143566"></a><a name="zh-cn_topic_0035998743_p44143566"></a>25004</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0035998743_p18859061"><a name="zh-cn_topic_0035998743_p18859061"></a><a name="zh-cn_topic_0035998743_p18859061"></a>致命</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0035998743_p51188993"><a name="zh-cn_topic_0035998743_p51188993"></a><a name="zh-cn_topic_0035998743_p51188993"></a>是</p>
</td>
</tr>
</tbody>
</table>

## 告警参数<a name="zh-cn_topic_0035998743_section63187419"></a>

<a name="zh-cn_topic_0035998743_table52667802"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035998743_row22098140"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0035998743_p45118907"><a name="zh-cn_topic_0035998743_p45118907"></a><a name="zh-cn_topic_0035998743_p45118907"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0035998743_p30752875"><a name="zh-cn_topic_0035998743_p30752875"></a><a name="zh-cn_topic_0035998743_p30752875"></a>参数含义</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035998743_row7954964"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998743_p40372317"><a name="zh-cn_topic_0035998743_p40372317"></a><a name="zh-cn_topic_0035998743_p40372317"></a>ServiceName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998743_p48932206"><a name="zh-cn_topic_0035998743_p48932206"></a><a name="zh-cn_topic_0035998743_p48932206"></a>产生告警的服务名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998743_row37736673"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998743_p36771698"><a name="zh-cn_topic_0035998743_p36771698"></a><a name="zh-cn_topic_0035998743_p36771698"></a>RoleName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998743_p25717600"><a name="zh-cn_topic_0035998743_p25717600"></a><a name="zh-cn_topic_0035998743_p25717600"></a>产生告警的角色名称。</p>
</td>
</tr>
<tr id="zh-cn_topic_0035998743_row30131813"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0035998743_p24757801"><a name="zh-cn_topic_0035998743_p24757801"></a><a name="zh-cn_topic_0035998743_p24757801"></a>HostName</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0035998743_p59224828"><a name="zh-cn_topic_0035998743_p59224828"></a><a name="zh-cn_topic_0035998743_p59224828"></a>产生告警的主机节点信息。</p>
</td>
</tr>
</tbody>
</table>

## 对系统的影响<a name="zh-cn_topic_0035998743_section31815862"></a>

LdapServer数据不一致时，有可能是Manager上的LdapServer数据损坏，也有可能是集群上的LdapServer数据损坏，此时数据损坏的LdapServer进程将无法对外提供服务，影响Manager和集群的认证功能。

## 可能原因<a name="zh-cn_topic_0035998743_section17907308"></a>

-   LdapServer进程所在的节点网络故障。
-   LdapServer进程异常。
-   OS重启导致的LdapServer数据损坏。

## 处理步骤<a name="zh-cn_topic_0035998743_section26948044"></a>

1.  检查LdapServer所在的节点网络是否故障。
    1.  在MRS Manager界面，单击“告警管理”。记录该告警定位信息中的“HostName”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1、IP2、IP3等）。
    2.  联系运维人员，登录IP1节点，在这个节点上使用**ping**命令检查该节点与主oms节点的管理平面IP是否可达。
        -   是，执行[1.c](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step3)。
        -   否，执行[2.a](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step4)。

    3.  <a name="zh-cn_topic_0035998743_aalm-25004_mmccppss_step3"></a>联系公有云运维人员恢复网络，然后查看“ALM-25004 LdapServer数据同步异常”告警是否恢复。
        -   是，处理完毕。
        -   否，执行[2.a](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step4)。


2.  检查LdapServer进程是否正常。
    1.  <a name="zh-cn_topic_0035998743_aalm-25004_mmccppss_step4"></a>在MRS Manager的“告警管理”页面，查看是否有LdapServer的ALM-12004 OLdap资源异常告警产生。
        -   是，执行[2.b](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step5)。
        -   否，执行[2.d](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step7)。

    2.  <a name="zh-cn_topic_0035998743_aalm-25004_mmccppss_step5"></a>按照ALM-12004 OLdap资源异常提供的步骤处理该告警。
    3.  在告警列表中查看“ALM-25004 LdapServer数据同步异常”告警是否清除。
        -   是，处理完毕。
        -   否，执行[2.d](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step7)。

    4.  <a name="zh-cn_topic_0035998743_aalm-25004_mmccppss_step7"></a>在MRS Manager的“告警管理”页面，查看是否有LdapServer的ALM-12007 进程故障告警产生。
        -   是，执行[2.e](#zh-cn_topic_0035998743_step8)。
        -   否，执行[3.a](#zh-cn_topic_0035998743_step10)。

    5.  <a name="zh-cn_topic_0035998743_step8"></a>按照ALM-12007 进程故障提供的步骤处理该告警。
    6.  在告警列表中查看“ALM-25004 LdapServer数据同步异常”告警是否清除。
        -   是，处理完毕。
        -   否，执行[3.a](#zh-cn_topic_0035998743_step10)。


3.  检查是否存在因为OS重启导致LdapServer数据损坏。
    1.  <a name="zh-cn_topic_0035998743_step10"></a>在MRS Manager界面，单击“告警管理”。记录该告警定位信息中的“HostName”的IP地址为IP1（若出现多个告警，则分别记录其中的IP地址为IP1，IP2，IP3等）。单击“服务管理 \> LdapServer \> 服务配置”，记录LdapServer的端口号为PORT\(若告警定位信息中的IP地址为oms备节点IP地址，则端口号为默认端口21750\)。
    2.  以**omm**用户登录IP1节点，分别执行**ldapsearch -H ldaps://IP1:PORT -x -LLL -b dc=hadoop,dc=com**命令（如果该IP为OMS备节点IP地址，执行该命令之前先执行**export LDAPCONF=$\{CONTROLLER\_HOME\}/ldapserver/ldapserver/local/conf/ldap.conf**命令），观察查询出来的内容是否提示有error错误信息。
        -   是，执行[3.c](#zh-cn_topic_0035998743_aalm-25004_mmccppss_step12)。
        -   否，执行[4](#zh-cn_topic_0035998743_li39608838151323)。

    3.  <a name="zh-cn_topic_0035998743_aalm-25004_mmccppss_step12"></a>参考“恢复元数据”章节，使用告警出现日期之前的备份包进行LdapServer恢复和OMS恢复。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >必须使用同一时间点的OMS和LdapServer备份数据进行恢复，否则可能造成业务和操作失败。当业务正常时需要恢复数据，建议手动备份最新管理数据后，再执行恢复数据操作，否则会丢失从备份时刻到恢复时刻之间的Manager数据。  

    4.  在告警列表中查看“ALM-25004 LdapServer数据同步异常”告警是否清除。
        -   是，处理完毕。
        -   否，执行[4](#zh-cn_topic_0035998743_li39608838151323)。


4.  <a name="zh-cn_topic_0035998743_li39608838151323"></a>收集故障信息。
    1.  在MRS Manager界面，单击“系统设置 \> 日志导出”。
    2.  请联系运维人员，并发送已收集的故障日志信息。


## 参考信息<a name="zh-cn_topic_0035998743_section41205809"></a>

无。

