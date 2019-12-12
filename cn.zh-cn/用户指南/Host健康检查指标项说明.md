# Host健康检查指标项说明<a name="ZH-CN_TOPIC_0173397586"></a>

## Swap使用率<a name="section2449280811212"></a>

**指标项名称**：Swap使用率

**指标项含义**：系统Swap使用率，计算方法：已用Swap大小/总共Swap大小。当前阈值设置为75.0%，如果使用率超过阈值，则认为不健康。

**恢复指导**：

1.  确认节点Swap使用率。

    登录检查结果不健康的节点，执行**free -m**查看swap总量和已使用量，如果swap使用率已超过阈值，则执行[2](#li6576720111231)。

2.  <a name="li6576720111231"></a>如果Swap使用率超过阈值，建议对系统进行扩容，如：增加节点。

## 主机文件句柄使用率<a name="section1560409611258"></a>

**指标项名称**：主机文件句柄使用率

**指标项含义**：系统中文件句柄的使用率，主机文件句柄使用率=已用句柄数/总共句柄数。如果使用率超过阈值，则认为不健康。

**恢复指导**：

1.  确认主机文件句柄使用率。

    登录检查结果不健康的节点，执行**cat /proc/sys/fs/file-nr**，输出结果的第一列和第三列分别表示系统已使用的句柄数和总句柄数，如果使用率超过阈值，则执行[2](#li3870258111327)。

2.  <a name="li3870258111327"></a>如果主机文件句柄使用率超过阈值，建议对系统进行排查，具体分析文件句柄的使用情况。

## NTP偏移量<a name="section257263621147"></a>

**指标项名称**：NTP偏移量

**指标项含义**：NTP时间偏差。如果时间偏差超过阈值，则认为不健康。

**恢复指导：**

1.  确认NTP时间偏差。

    登录检查结果不健康的节点，执行**/usr/sbin/ntpq -np**查看信息，其中offset列表示时间偏差。如果时间偏差大于阈值，则执行[2](#li4827260411417)。

2.  <a name="li4827260411417"></a>如果该指标项异常，则需要检查时钟源配置是否正确，请联系运维人员处理。

## 平均负载<a name="section6208777411520"></a>

**指标项名称：**平均负载

**指标项含义：**系统平均负载，表示特定时间段内运行队列中的平均进程数。这里系统平均负载是通过uptime命令中得到的负载值计算得到。计算方法：（1分钟负载 + 5分钟负载 + 15分钟负载）/\(3\*CPU个数\)。当前阈值设置为2，如果超过阈值，则认为不健康。

**恢复指导：**

1.  登录检查结果不健康的节点，执行**uptime**命令，命令输出的最后三列分别表示1分钟负载、5分钟负载和15分钟负载。根据系统平均负载的计算方法，如果负载超过阈值，则执行[2](#li1216080711528)。
2.  <a name="li1216080711528"></a>如果系统平均负载超过阈值，建议对系统进行扩容，如增加节点等。

## D状态进程<a name="section35806111163"></a>

**指标项名称**：D状态进程

**指标项含义**：不可中断的睡眠进程，即D状态进程。D状态通常是进程在等待IO，比如磁盘IO，网络IO等，但是此时IO出现异常。如果系统中出现D状态进程，则认为不健康。

**恢复指导**：如果该指标项异常，系统中会产生对应的告警，建议参见告警ALM-12028进行处理。

## 硬件状态<a name="section1214941911631"></a>

**指标项名称：**硬件状态

**指标项含义**：检查系统硬件状态，包括CPU、内存、磁盘、电源、风扇等。该检查项通过ipmitool sdr elist获取相关硬件信息。如果相关硬件状态异常，则认为不健康。

**恢复指导：**

1.  登录检查结果不健康的节点。执行**ipmitool sdr elist**查看系统硬件状态，命令输出的最后一列表示对应的硬件状态。如果提示的状态在下面的故障描述表中，则任务不健康。

    <a name="table3506092211640"></a>
    <table><thead align="left"><tr id="row2720766011640"><th class="cellrowborder" valign="top" width="47.36%" id="mcps1.1.3.1.1"><p id="p2888929111640"><a name="p2888929111640"></a><a name="p2888929111640"></a><strong id="b2451874311645"><a name="b2451874311645"></a><a name="b2451874311645"></a>模块</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="52.64%" id="mcps1.1.3.1.2"><p id="p5833121111640"><a name="p5833121111640"></a><a name="p5833121111640"></a><strong id="b3986117211645"><a name="b3986117211645"></a><a name="b3986117211645"></a>故障描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1315763911640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p5633685311640"><a name="p5633685311640"></a><a name="p5633685311640"></a>Processor</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p6699127911640"><a name="p6699127911640"></a><a name="p6699127911640"></a>IERR</p>
    <p id="p6605060611640"><a name="p6605060611640"></a><a name="p6605060611640"></a>Thermal Trip</p>
    <p id="p5758454611640"><a name="p5758454611640"></a><a name="p5758454611640"></a>FRB1/BIST failure</p>
    <p id="p4849886811640"><a name="p4849886811640"></a><a name="p4849886811640"></a>FRB2/Hang in POST failure</p>
    <p id="p3383662911640"><a name="p3383662911640"></a><a name="p3383662911640"></a>FRB3/Processor startup/init failure</p>
    <p id="p3609420611640"><a name="p3609420611640"></a><a name="p3609420611640"></a>Configuration Error</p>
    <p id="p5641240011640"><a name="p5641240011640"></a><a name="p5641240011640"></a>SM BIOS Uncorrectable CPU-complex Error</p>
    <p id="p3794955611640"><a name="p3794955611640"></a><a name="p3794955611640"></a>Disabled</p>
    <p id="p600169211640"><a name="p600169211640"></a><a name="p600169211640"></a>Throttled</p>
    <p id="p5401523211640"><a name="p5401523211640"></a><a name="p5401523211640"></a>Uncorrectable machine check exception</p>
    </td>
    </tr>
    <tr id="row2840418211640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p5130989311640"><a name="p5130989311640"></a><a name="p5130989311640"></a>Power Supply</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p6246069111640"><a name="p6246069111640"></a><a name="p6246069111640"></a>Failure detected</p>
    <p id="p2527530811640"><a name="p2527530811640"></a><a name="p2527530811640"></a>Predictive failure</p>
    <p id="p2615118511640"><a name="p2615118511640"></a><a name="p2615118511640"></a>Power Supply AC lost</p>
    <p id="p3403407311640"><a name="p3403407311640"></a><a name="p3403407311640"></a>AC lost or out-of-range</p>
    <p id="p3787120711640"><a name="p3787120711640"></a><a name="p3787120711640"></a>AC out-of-range, but present</p>
    <p id="p529654711640"><a name="p529654711640"></a><a name="p529654711640"></a>Config Error: Vendor Mismatch</p>
    <p id="p4766892611640"><a name="p4766892611640"></a><a name="p4766892611640"></a>Config Error: Revision Mismatch</p>
    <p id="p2636715311640"><a name="p2636715311640"></a><a name="p2636715311640"></a>Config Error: Processor Missing</p>
    <p id="p3597778911640"><a name="p3597778911640"></a><a name="p3597778911640"></a>Config Error: Power Supply Rating Mismatch</p>
    <p id="p5536465211640"><a name="p5536465211640"></a><a name="p5536465211640"></a>Config Error: Voltage Rating Mismatch</p>
    <p id="p2851982111640"><a name="p2851982111640"></a><a name="p2851982111640"></a>Config Error</p>
    </td>
    </tr>
    <tr id="row3366125511640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p5431104711640"><a name="p5431104711640"></a><a name="p5431104711640"></a>Power Unit</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p3711864711640"><a name="p3711864711640"></a><a name="p3711864711640"></a>240VA power down</p>
    <p id="p6563236811640"><a name="p6563236811640"></a><a name="p6563236811640"></a>Interlock power down</p>
    <p id="p5382040311640"><a name="p5382040311640"></a><a name="p5382040311640"></a>AC lost</p>
    <p id="p1462158611640"><a name="p1462158611640"></a><a name="p1462158611640"></a>Soft-power control failure</p>
    <p id="p6448541211640"><a name="p6448541211640"></a><a name="p6448541211640"></a>Failure detected</p>
    <p id="p4349780411640"><a name="p4349780411640"></a><a name="p4349780411640"></a>Predictive failure</p>
    </td>
    </tr>
    <tr id="row3940254711640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p3451584411640"><a name="p3451584411640"></a><a name="p3451584411640"></a>Memory</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p4432000311640"><a name="p4432000311640"></a><a name="p4432000311640"></a>Uncorrectable ECC</p>
    <p id="p6333571011640"><a name="p6333571011640"></a><a name="p6333571011640"></a>Parity</p>
    <p id="p3315048611640"><a name="p3315048611640"></a><a name="p3315048611640"></a>Memory Scrub Failed</p>
    <p id="p2991892311640"><a name="p2991892311640"></a><a name="p2991892311640"></a>Memory Device Disabled</p>
    <p id="p83485411640"><a name="p83485411640"></a><a name="p83485411640"></a>Correctable ECC logging limit reached</p>
    <p id="p751368811640"><a name="p751368811640"></a><a name="p751368811640"></a>Configuration Error</p>
    <p id="p51433011640"><a name="p51433011640"></a><a name="p51433011640"></a>Throttled</p>
    <p id="p462897311640"><a name="p462897311640"></a><a name="p462897311640"></a>Critical Overtemperature</p>
    </td>
    </tr>
    <tr id="row5289648511640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p1907860811640"><a name="p1907860811640"></a><a name="p1907860811640"></a>Drive Slot</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p186339311640"><a name="p186339311640"></a><a name="p186339311640"></a>Drive Fault</p>
    <p id="p1677054411640"><a name="p1677054411640"></a><a name="p1677054411640"></a>Predictive Failure</p>
    <p id="p1671717611640"><a name="p1671717611640"></a><a name="p1671717611640"></a>Parity Check In Progress</p>
    <p id="p1623685611640"><a name="p1623685611640"></a><a name="p1623685611640"></a>In Critical Array</p>
    <p id="p1191397811640"><a name="p1191397811640"></a><a name="p1191397811640"></a>In Failed Array</p>
    <p id="p4011694411640"><a name="p4011694411640"></a><a name="p4011694411640"></a>Rebuild In Progress</p>
    <p id="p2550817711640"><a name="p2550817711640"></a><a name="p2550817711640"></a>Rebuild Aborted</p>
    </td>
    </tr>
    <tr id="row6200181911640"><td class="cellrowborder" valign="top" width="47.36%" headers="mcps1.1.3.1.1 "><p id="p630632111640"><a name="p630632111640"></a><a name="p630632111640"></a>Battery</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.64%" headers="mcps1.1.3.1.2 "><p id="p4104999411640"><a name="p4104999411640"></a><a name="p4104999411640"></a>Low</p>
    <p id="p3390563411640"><a name="p3390563411640"></a><a name="p3390563411640"></a>Failed</p>
    </td>
    </tr>
    </tbody>
    </table>

2.  如果该指标项异常，建议联系运维人员解决处理。

## 主机名<a name="section1855193111725"></a>

**指标项名称：**主机名

**指标项含义：**检查是否设置了主机名。如果没有设置主机名，则认为不健康。如果该指标项异常，建议正确设置hostname。

**恢复指导：**

1.  登录检查结果不健康的节点。
2.  执行以下命令修改主机名，使节点主机名与规划的主机名保持一致：

    **hostname** _主机名_。例如，将主机名改为“Bigdata-OM-01”，请执行命令hostname Bigdata-OM-01。

3.  修改主机名配置文件。

    执行**vi /etc/HOSTNAME**命令编辑文件，修改文件内容为“Bigdata-OM-01”，并保存退出。


## Umask<a name="section1838129911750"></a>

**指标项名称：**Umask

**指标项含义**：检查omm用户的umask设置是否正确。如果umask设置不等于0077，则认为不健康。

**恢复指导：**

1.  如果该指标异常，建议将omm用户的umask设置为0077。登录检查结果不健康的节点，执行**su - omm**切换到omm用户。
2.  执行**vi $\{BIGDATA\_HOME\}/.om\_profile**，修改**umask=0077**，保存并退出。

## OMS的HA状态<a name="section2749505311810"></a>

**指标项名称**：OMS的HA状态

**指标项含义：**检查OMS的双机资源是否正常。OMS双机资源状态的详细信息可使用**$\{CONTROLLER\_HOME\}/sbin/status-oms.sh**查看。如果有模块状态异常，认为不健康。

**恢复指导：**

1.  登录主管理节点，执行**su - omm**切换到**omm**用户，然后执行**$\{CONTROLLER\_HOME\}/sbin/status-oms.sh**查看OMS状态。
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

4.  如果通过日志无法排除问题，请联系运维人员处理，并发送已收集的故障日志信息。

## 安装目录及数据目录检查<a name="section2634406711835"></a>

**指标项名称：**安装目录及数据目录检查

**指标项含义**：该指标项首先检查安装目录（默认为“/opt/Bigdata“）所在磁盘分区根目录下的lost+found目录。如果该目录下有**omm**用户的文件，则认为异常。节点异常时，会把相关的文件放入到“lost+found“目录。该检查主要是针对这类场景，检查文件是否丢失。然后，对安装目录（如：“/opt/Bigdata“）和数据目录（如：“/srv/BigData“）进行检查。如果目录下出现非**omm**用户的文件，则认为不健康。

**恢复指导：**

1.  登录检查结果不健康的节点，执行**su - omm**切换到**omm**用户。检查lost+found目录是否存在omm用户的文件或文件夹。

    如果有**omm**用户文件，建议对其进行恢复后重新检查；如果没有**omm**用户文件，则执行[2](#li557697581195)。

2.  <a name="li557697581195"></a>分别对安装目录和数据目录进行排查。查看目录下是否存在非**omm**用户是文件或文件夹。如果确认这些文件是手工生成的临时文件，建议对清理后重新检查。

## CPU使用率<a name="section4835272211846"></a>

**指标项名称：**CPU使用率

**指标项含义**：检查CPU使用率是否超过当前设定的阈值。如果超过阈值，则认为不健康。

**恢复指导：**如果该指标项异常，系统中会产生对应的告警，建议参见告警ALM-12016进行处理。

## 内存使用率<a name="section2798852511924"></a>

**指标项名称：**内存使用率

**指标项含义**：检查内存使用率是否超过当前设定的阈值。如果超过阈值，则认为不健康。

**恢复指导：**如果该指标项异常，系统中会产生对应的告警，建议参见告警ALM-12018进行处理。

## 主机磁盘使用率<a name="section277944511946"></a>

**指标项名称：**主机磁盘使用率

**指标项含义**：检查主机磁盘使用率是否超过当前设定的阈值。如果超过阈值，则认为不健康。

**恢复指导：**如果该指标项异常，系统中会产生对应的告警，建议参见告警ALM-12017进行处理。

## 主机磁盘写速率<a name="section43877412111017"></a>

**指标项名称：**主机磁盘写速率

**指标项含义**：检查主机磁盘写速率。根据业务场景不同，主机磁盘写速率大小可能存在差异，所以该指标项只反映具体的数值大小，用户需根据业务场景具体判断该指标是否健康。

**恢复指导：**用户根据具体的业务场景，判断当前磁盘写速率是否正常。

## 主机磁盘读速率<a name="section6914545111211"></a>

**指标项名称：**主机磁盘读速率

**指标项含义**：检查主机磁盘读速率。根据业务场景不同，主机磁盘读速率大小可能存在差异，所以该指标项只反映具体的数值大小，用户需根据业务场景具体判断该指标是否健康。

**恢复指导：**用户根据具体的业务场景，判断当前磁盘读速率是否正常。

## 主机业务平面网络状态<a name="section25333183111236"></a>

**指标项名称：**主机业务平面网络状态

**指标项含义**：检查集群主机业务平面网络连通性。如果出现无法连通的情况，则认为不健康。

**恢复指导：**如果是单平面组网，对应需检查单平面的IP。双平面组网排查恢复步骤如下：

1.  检查主备管理节点业务平面IP的网络连通性。

    如果网络异常，执行[3](#li45614056111343)。

    如果网络正常，执行[2](#li12524768111343)。

2.  <a name="li12524768111343"></a>检查主管理节点IP到集群内异常节点IP的网络连通性。
3.  <a name="li45614056111343"></a>如果网络不通，请联系运维人员排查网络问题，以保证满足业务使用。

## 主机状态<a name="section24273366111326"></a>

**指标项名称：**主机状态

**指标项含义**：检查主机状态是否正常。如果节点有故障，则认为不健康。

**恢复指导：**如果该指标项异常，建议参见告警ALM-12006进行处理。

## 检查告警<a name="section45605752111329"></a>

**指标项名称：**  检查告警

**指标项含义**：检查主机是否存在未清除的告警。如果存在，则认为不健康。

**恢复指导：**如果该指标项异常，建议参见告警进行处理。

