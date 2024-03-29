# OMS健康检查指标项说明<a name="mrs_01_0294"></a>

## OMS状态检查<a name="zh-cn_topic_0035251772_section53299896112957"></a>

**指标项名称**：OMS状态检查

**指标项含义**：OMS状态检查包括HA状态检查和资源状态检查。 HA状态取值为active、standby和NULL，分别表示主节点、备节点和未知。资源状态取值为normal、abnormal和NULL，分别表示正常、异常和未知。HA状态为NULL时，认为不健康；资源状态为NULL或abnormal时，认为不健康。

**表 1**  OMS状态说明表

<a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_table6449710413844"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_row1679551913844"><th class="cellrowborder" valign="top" width="37.230000000000004%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6365941215146"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6365941215146"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6365941215146"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="62.77%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1331465813844"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1331465813844"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1331465813844"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_row474554613844"><td class="cellrowborder" valign="top" width="37.230000000000004%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6412523413844"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6412523413844"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6412523413844"></a>HA状态</p>
</td>
<td class="cellrowborder" valign="top" width="62.77%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p165427113106"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p165427113106"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p165427113106"></a>active表示主节点</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1488844413106"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1488844413106"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1488844413106"></a>standby表示备节点</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6688714013106"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6688714013106"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6688714013106"></a>NULL表示未知</p>
</td>
</tr>
<tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_row5965719913844"><td class="cellrowborder" valign="top" width="37.230000000000004%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p3198841813844"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p3198841813844"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p3198841813844"></a>资源状态</p>
</td>
<td class="cellrowborder" valign="top" width="62.77%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6646373613111"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6646373613111"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6646373613111"></a>normal表示所有资源都正常</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6130271813111"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6130271813111"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p6130271813111"></a>abnormal表示有异常资源</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1485355513111"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1485355513111"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979617_p1485355513111"></a>NULL表示未知</p>
</td>
</tr>
</tbody>
</table>

**恢复指导：**

1.  登录主管理节点，执行**su - omm**切换到omm用户。执行**$\{CONTROLLER\_HOME\}/sbin/status-oms.sh**查看OMS状态。
2.  如果HA状态为NULL，可能是系统在重启，这个一般是中间状态，HA后续会自动调整为正常状态。
3.  如果资源状态异常，则说明有Manager的某些组件资源异常， 可具体查看acs、aos、cep、controller、feed\_watchdog、fms、guassDB、httpd、iam、ntp、okerberos、oldap、pms、tomcat等组件状态是否正常。
4.  如果Manager组件资源异常，参见Manager组件状态检查进行处理。

## Manager组件状态检查<a name="zh-cn_topic_0035251772_section53267853112958"></a>

**指标项名称**：Manager组件状态检查

**指标项含义**：Manager组件状态检查包括组件资源运行状态和资源HA状态。资源运行状态，取值为Normal、Abnormal等；资源HA状态，取值为Normal、Exception等。Manager组件包含acs、aos、cep、controller、feed\_watchdog、floatip、fms、gaussDB、heartBeatCheck、httpd、iam、ntp、okerberos、oldap、pms、tomcat等。当运行状态和HA状态不是Normal时，认为指标不健康。

**表 2**  Manager组件状态说明表

<a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_t441fe76cd1604ee6b5553e49e0a1aab1"></a>
<table><thead align="left"><tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_reaabe8c4d68b4509bf207935152caf07"><th class="cellrowborder" valign="top" width="37.230000000000004%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a762cc52c5dcc4d889b363dbc938fe9ec"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a762cc52c5dcc4d889b363dbc938fe9ec"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a762cc52c5dcc4d889b363dbc938fe9ec"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="62.77%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad4e245d15ee0458b8cc11b3a42e2f483"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad4e245d15ee0458b8cc11b3a42e2f483"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad4e245d15ee0458b8cc11b3a42e2f483"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_rd4d239eec7074d858fa527882d52a4bd"><td class="cellrowborder" valign="top" width="37.230000000000004%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ab2eced5111d94c3d991041c0c4897a55"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ab2eced5111d94c3d991041c0c4897a55"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ab2eced5111d94c3d991041c0c4897a55"></a>资源运行状态</p>
</td>
<td class="cellrowborder" valign="top" width="62.77%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a887649c269604368a1516101df6e15c0"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a887649c269604368a1516101df6e15c0"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a887649c269604368a1516101df6e15c0"></a>Normal表示正常运行</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p936536291738"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p936536291738"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p936536291738"></a>Abnormal表示运行异常</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a1ada10661b924b979de757d3dadd6b4b"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a1ada10661b924b979de757d3dadd6b4b"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a1ada10661b924b979de757d3dadd6b4b"></a>Stopped表示停止</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a731ce3261caa48f2b5fc13e60984f1d7"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a731ce3261caa48f2b5fc13e60984f1d7"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a731ce3261caa48f2b5fc13e60984f1d7"></a>Unknown表示状态未知</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ae96e586d79d6402594e4c1e06baedab1"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ae96e586d79d6402594e4c1e06baedab1"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ae96e586d79d6402594e4c1e06baedab1"></a>Starting表示正在启动</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aae6574bccb2442d981591d702b38ea67"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aae6574bccb2442d981591d702b38ea67"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aae6574bccb2442d981591d702b38ea67"></a>Stopping表示正在停止</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5323d9c68f1f49e9b0f3379a22af0975"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5323d9c68f1f49e9b0f3379a22af0975"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5323d9c68f1f49e9b0f3379a22af0975"></a>Active_normal表示主正常运行</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p879787891738"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p879787891738"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p879787891738"></a>Standby_normal表示备正常运行</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a276aee9da4a74279a54138988cf5c397"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a276aee9da4a74279a54138988cf5c397"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a276aee9da4a74279a54138988cf5c397"></a>Raising_active表示正在升主</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ac99e1e71426a4348839fc0cd708d46c6"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ac99e1e71426a4348839fc0cd708d46c6"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ac99e1e71426a4348839fc0cd708d46c6"></a>Lowing_standby表示正在降备</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a84f527bd9f804eaaa200abed83e72ef0"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a84f527bd9f804eaaa200abed83e72ef0"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a84f527bd9f804eaaa200abed83e72ef0"></a>No_action表示没有该动作</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p925535091738"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p925535091738"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p925535091738"></a>Repairing表示正在修复</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5b3861dc514642cfbfc6a4e6e341c82b"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5b3861dc514642cfbfc6a4e6e341c82b"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a5b3861dc514642cfbfc6a4e6e341c82b"></a>NULL表示未知</p>
</td>
</tr>
<tr id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_rd2d74278c93e4b3d962050d0934cc1cb"><td class="cellrowborder" valign="top" width="37.230000000000004%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad9f38fd21980434fa10ef06024d50ead"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad9f38fd21980434fa10ef06024d50ead"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_ad9f38fd21980434fa10ef06024d50ead"></a>资源HA状态</p>
</td>
<td class="cellrowborder" valign="top" width="62.77%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p187275091738"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p187275091738"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p187275091738"></a>Normal表示正常</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a2b4fe4e106454ce982e419ab665d5c7b"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a2b4fe4e106454ce982e419ab665d5c7b"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a2b4fe4e106454ce982e419ab665d5c7b"></a>Exception表示故障</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a9d6f36125da941adac53d4bcec10eb56"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a9d6f36125da941adac53d4bcec10eb56"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_a9d6f36125da941adac53d4bcec10eb56"></a>Non_steady表示非稳态</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aa6acb088007e429d969577951f73821a"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aa6acb088007e429d969577951f73821a"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_aa6acb088007e429d969577951f73821a"></a>Unknown表示未知</p>
<p id="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p619434191738"><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p619434191738"></a><a name="zh-cn_topic_0035251772_zh-cn_topic_0021979612_zh-cn_topic_0020558246_p619434191738"></a>NULL表示未知</p>
</td>
</tr>
</tbody>
</table>

**恢复指导：**

1.  登录主管理节点，执行**su - omm**切换到omm用户。执行**$\{CONTROLLER\_HOME\}/sbin/status-oms.sh**查看OMS状态。
2.  如果floatip、okerberos、oldap等异常，可参见告警ALM-12002、ALM-12004、ALM-12005分别进行处理。
3.  如果是其他资源异常，建议查看相关异常模块的日志。

    controller资源异常：查看异常节点的/var/log/Bigdata/controller/controller.log。

    cep资源异常：查看异常节点的/var/log/Bigdata/omm/oms/cep/cep.log。

    aos资源异常：查看异常节点的/var/log/Bigdata/controller/aos/aos.log。

    feed\_watchdog资源异常：查看异常节点的/var/log/Bigdata/watchdog/watchdog.log。

    httpd资源异常：查看异常节点的/var/log/Bigdata/httpd/error\_log。

    fms资源异常：查看异常节点的/var/log/Bigdata/omm/oms/fms/fms.log。

    pms资源异常：查看异常节点的/var/log/Bigdata/omm/oms/pms/pms.log。

    iam资源异常：查看异常节点的/var/log/Bigdata/omm/oms/iam/iam.log。

    gaussDB资源异常：查看异常节点的/var/log/Bigdata/omm/oms/db/omm\_gaussdba.log。

    ntp资源异常：查看异常节点的/var/log/Bigdata/omm/oms/ha/scriptlog/ha\_ntp.log。

    tomcat资源异常：查看异常节点的/var/log/Bigdata/tomcat/catalina.log。

4.  如果通过日志无法排除问题，请联系公有云运维人员处理，并发送已收集的故障日志信息。

## OMA运行状态<a name="zh-cn_topic_0035251772_section13384752112959"></a>

**指标项名称**：OMA运行状态

**指标项含义**：检查OMA的运行状态，状态结果包括运行和停止两种状态，如果OMA状态为停止，则认为不健康。

**恢复指导：**

1.  登录检查结果不健康的节点，然后执行**su - omm**切换到**omm**用户。
2.  执行**$\{OMA\_PATH\}/restart\_oma\_app**，手工启动OMA，然后重新检查。如果检查结果仍然不健康，则执行[3](#zh-cn_topic_0035251772_li62867080113130)。
3.  <a name="zh-cn_topic_0035251772_li62867080113130"></a>如果手工启动OMA无法恢复，建议查看分析OMA日志“/var/log/Bigdata/omm/oma/omm\_agent.log“。
4.  如果通过日志无法排除问题，请联系运维人员处理，并发送已收集的故障日志信息。

## 各节点与主管理节点之间SSH互信<a name="zh-cn_topic_0035251772_section20242671112959"></a>

**指标项名称：**各节点与主管理节点之间SSH互信

**指标项含义**：检查SSH互信是否正常。如果使用omm用户，在主管理节点可以通过SSH登录其他节点且不需要输入密码，则认为健康；否则，不健康。或者主管理节点SSH可以直接登录其他节点，但在其他节点无法通过SSH登录主管理节点，则也认为不健康。

**恢复指导：**

1.  如果该指标项检查异常，表示各节点与主管理节点之间SSH互信异常。SSH互信异常时，首先检查“/home/omm“目录的权限是否为**omm**。非**omm**的目录权限可能导致SSH互信异常，建议执行**chown omm:wheel**修改权限后重新检查。如果“/home/omm“目录权限正常，则执行[2](#zh-cn_topic_0035251772_li39886844113155)。
2.  <a name="zh-cn_topic_0035251772_li39886844113155"></a>SSH互信异常一般会导致Controller和NodeAgent之间心跳异常，进而出现节点故障的告警。这时可参见告警ALM-12006进行处理。

## 进程运行时间<a name="zh-cn_topic_0035251772_section2284678211300"></a>

**指标项名称：**NodeAgent运行时间、Controller运行时间和Tomcat运行时间

**指标项含义**：检查NodeAgent、Controller、Tomcat进程的运行时间。如果小于半小时（即1800s），则进程可能重启过，建议半小时后再检查。如果多次检查，进程的运行时间都小于半小时，说进程状态异常。

**恢复指导：**

1.  登录检查结果不健康的节点，执行**su - omm**切换到**omm**用户。
2.  根据进程名称查看进程pid，执行命令：

    **ps -ef | grep NodeAgent**

3.  根据pid查看进程启动时间，执行命令：

    **ps -p pid -o lstart**

4.  判断进程启动时间是否正常。如果进程一直反复重启，执行[5](#zh-cn_topic_0035251772_li38659710113226)
5.  <a name="zh-cn_topic_0035251772_li38659710113226"></a>查看对应模块日志，分析重启原因。

    NodeAgent运行时间异常，检查相关日志**/var/log/Bigdata/nodeagent/agentlog/agent.log**。

    Controller运行时间异常，检查相关日志**/var/log/Bigdata/controller/controller.log**。

    Tomcat运行时间异常，检查相关日志**/var/log/Bigdata/tomcat/web.log**。

6.  如果通过日志无法排除问题，请联系运维人员处理，并发送已收集的故障日志信息。

## 帐户及密码过期检查<a name="zh-cn_topic_0035251772_section3723151311300"></a>

**指标项名称**：账户及密码过期检查

**指标项含义**：该指标项检查MRS的两个操作系统用户**omm**和**ommdba**。对操作系统用户，同时检查账户及密码的过期时间。如果账户或密码有效期小于等于15天，则认为不健康。

**恢复指导**：如果账户或密码有效期小于等于15天，建议及时联系运维人员处理。

