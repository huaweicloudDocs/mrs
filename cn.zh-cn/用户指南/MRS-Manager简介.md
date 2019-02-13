# MRS Manager简介<a name="ZH-CN_TOPIC_0035209593"></a>

## 概述<a name="section1737211712858"></a>

MRS为用户提供海量数据的管理及分析功能，快速从结构化和非结构化的海量数据中挖掘您所需要的价值数据。开源组件结构复杂，安装、配置、管理过程费时费力，MRS Manager提供了企业级的大数据集群的统一管理平台：

-   提供集群状态的监控功能，您能快速掌握服务及主机的健康状态。
-   提供图形化的指标监控及定制，您能及时的获取系统的关键信息。
-   提供服务属性的配置功能，满足您实际业务的性能需求。
-   提供集群、服务、角色实例的操作功能，满足您一键启停等操作需求。

## 系统界面简介<a name="section44171021121413"></a>

MRS Manager提供统一的集群管理平台，帮助用户快捷、直观的完成集群的运行维护。

各操作入口的详细功能如[表1](#table13549662121428)所示。

**表 1**  界面操作入口功能描述

<a name="table13549662121428"></a>
<table><thead align="left"><tr id="row22155541121428"><th class="cellrowborder" valign="top" width="24.5%" id="mcps1.2.3.1.1"><p id="p49768398121428"><a name="p49768398121428"></a><a name="p49768398121428"></a>界面</p>
</th>
<th class="cellrowborder" valign="top" width="75.5%" id="mcps1.2.3.1.2"><p id="p4708472121428"><a name="p4708472121428"></a><a name="p4708472121428"></a>功能描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row45841979121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p22212798121428"><a name="p22212798121428"></a><a name="p22212798121428"></a>系统概览</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p19893621121428"><a name="p19893621121428"></a><a name="p19893621121428"></a>提供柱状图、折线图、表格等多种图表方式展示所有服务的状态、各服务的主要监控指标、主机的状态统计。用户可以定制关键监控信息面板，并拖动到任意位置。系统概览支持数据自动刷新。</p>
</td>
</tr>
<tr id="row44824869121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p6935769121428"><a name="p6935769121428"></a><a name="p6935769121428"></a>服务管理</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p23011428121428"><a name="p23011428121428"></a><a name="p23011428121428"></a>提供服务监控、服务操作向导以及服务配置，帮助用户对服务进行统一管理。</p>
</td>
</tr>
<tr id="row51986413121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p50149930121428"><a name="p50149930121428"></a><a name="p50149930121428"></a>主机管理</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p52077479121428"><a name="p52077479121428"></a><a name="p52077479121428"></a>提供主机监控、主机操作向导，帮助用户对主机进行统一管理。</p>
</td>
</tr>
<tr id="row57526262121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p29115670121428"><a name="p29115670121428"></a><a name="p29115670121428"></a>告警管理</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p18922920121428"><a name="p18922920121428"></a><a name="p18922920121428"></a>提供告警查询、告警处理指导功能。帮助用户及时发现产品故障及潜在隐患，并进行定位排除，以保证系统正常运行。</p>
</td>
</tr>
<tr id="row56361512121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p1879732121428"><a name="p1879732121428"></a><a name="p1879732121428"></a>审计管理</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p28147941121428"><a name="p28147941121428"></a><a name="p28147941121428"></a>提供审计日志查询及导出功能。帮助用户查阅所有用户活动及操作。</p>
</td>
</tr>
<tr id="row42645073202928"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p31698894202928"><a name="p31698894202928"></a><a name="p31698894202928"></a>租户管理</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p17473640202928"><a name="p17473640202928"></a><a name="p17473640202928"></a>提供统一租户管理平台。</p>
</td>
</tr>
<tr id="row17780935121428"><td class="cellrowborder" valign="top" width="24.5%" headers="mcps1.2.3.1.1 "><p id="p30969611121428"><a name="p30969611121428"></a><a name="p30969611121428"></a>系统设置</p>
</td>
<td class="cellrowborder" valign="top" width="75.5%" headers="mcps1.2.3.1.2 "><p id="p28268412121428"><a name="p28268412121428"></a><a name="p28268412121428"></a>用户可以进行监控和告警配置管理、备份管理。</p>
</td>
</tr>
</tbody>
</table>

当用户进入到“系统设置”的各子功能页面后，提供快捷方式跳转到其他System子功能页面。

-   普通集群的“系统设置“快捷菜单提供的跳转链接项如[表2](#table6784789113859)所示。
-   安全集群的“系统设置“快捷菜单提供的跳转链接项如[表3](#table5212148312126)所示。

快捷跳转操作示例如下所示。

1.  在MRS Manager，单击“系统设置”。
2.  在“系统设置”界面，任意单击一个功能链接，进入具体功能界面。

    例如在“备份恢复管理”区域中单击“备份管理”，进入到“备份管理”界面。

3.  将鼠标移动到浏览器窗口的左边界，弹出“系统设置“黑色快捷菜单。鼠标移出该菜单后，该菜单收起。
4.  在弹出的快捷菜单上，可以单击某个功能链接直接跳转到对应的功能界面。

    例如选择“维护 \> 日志导出“，进入“日志导出”界面。


**表 2**  普通集群的系统设置快捷菜单

<a name="table6784789113859"></a>
<table><thead align="left"><tr id="row9016418113859"><th class="cellrowborder" valign="top" width="49.94%" id="mcps1.2.3.1.1"><p id="p31770041114142"><a name="p31770041114142"></a><a name="p31770041114142"></a>菜单子标题</p>
</th>
<th class="cellrowborder" valign="top" width="50.06%" id="mcps1.2.3.1.2"><p id="p35878009113859"><a name="p35878009113859"></a><a name="p35878009113859"></a>功能链接</p>
</th>
</tr>
</thead>
<tbody><tr id="row40090469114312"><td class="cellrowborder" rowspan="2" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p874840113859"><a name="p874840113859"></a><a name="p874840113859"></a>备份恢复管理</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p33932283114312"><a name="p33932283114312"></a><a name="p33932283114312"></a>备份管理</p>
</td>
</tr>
<tr id="row49721070113859"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p3753198113859"><a name="p3753198113859"></a><a name="p3753198113859"></a>恢复管理</p>
</td>
</tr>
<tr id="row51727466113859"><td class="cellrowborder" rowspan="3" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p29175247113859"><a name="p29175247113859"></a><a name="p29175247113859"></a>维护</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p14384829113859"><a name="p14384829113859"></a><a name="p14384829113859"></a>日志导出</p>
</td>
</tr>
<tr id="row6039639811437"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p5003423411437"><a name="p5003423411437"></a><a name="p5003423411437"></a>审计日志导出</p>
</td>
</tr>
<tr id="row39138137114343"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p26804948114343"><a name="p26804948114343"></a><a name="p26804948114343"></a>健康检查</p>
</td>
</tr>
<tr id="row17557683113859"><td class="cellrowborder" rowspan="5" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p12886237113859"><a name="p12886237113859"></a><a name="p12886237113859"></a>监控和告警配置</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p14412701695"><a name="p14412701695"></a><a name="p14412701695"></a>Syslog配置</p>
</td>
</tr>
<tr id="row25194038114350"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p440528941695"><a name="p440528941695"></a><a name="p440528941695"></a>阈值管理</p>
</td>
</tr>
<tr id="row34875773114358"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p45831442114358"><a name="p45831442114358"></a><a name="p45831442114358"></a>SNMP配置</p>
</td>
</tr>
<tr id="row2324405311443"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p3289345511443"><a name="p3289345511443"></a><a name="p3289345511443"></a>监控指标转储配置</p>
</td>
</tr>
<tr id="row56483703114417"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p14433103114417"><a name="p14433103114417"></a><a name="p14433103114417"></a>资源贡献排名配置</p>
</td>
</tr>
<tr id="row39130839113859"><td class="cellrowborder" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p15481408113859"><a name="p15481408113859"></a><a name="p15481408113859"></a>资源管理</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p46034505113859"><a name="p46034505113859"></a><a name="p46034505113859"></a>静态服务池</p>
</td>
</tr>
<tr id="row101186259472"><td class="cellrowborder" rowspan="4" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p46950462113859"><a name="p46950462113859"></a><a name="p46950462113859"></a>权限配置</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p86652164818"><a name="p86652164818"></a><a name="p86652164818"></a>用户管理</p>
</td>
</tr>
<tr id="row462711223471"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1466731114818"><a name="p1466731114818"></a><a name="p1466731114818"></a>用户组管理</p>
</td>
</tr>
<tr id="row1268710198479"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p8822579483"><a name="p8822579483"></a><a name="p8822579483"></a>密码策略配置</p>
</td>
</tr>
<tr id="row4722157113859"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p44891116113859"><a name="p44891116113859"></a><a name="p44891116113859"></a>OMS数据库密码修改</p>
</td>
</tr>
<tr id="row43607253113859"><td class="cellrowborder" valign="top" width="49.94%" headers="mcps1.2.3.1.1 "><p id="p42526568113859"><a name="p42526568113859"></a><a name="p42526568113859"></a>补丁管理</p>
</td>
<td class="cellrowborder" valign="top" width="50.06%" headers="mcps1.2.3.1.2 "><p id="p22100021113859"><a name="p22100021113859"></a><a name="p22100021113859"></a>补丁管理</p>
</td>
</tr>
</tbody>
</table>

**表 3**  安全集群的System快捷菜单

<a name="table5212148312126"></a>
<table><thead align="left"><tr id="row4143668412126"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p835423612126"><a name="p835423612126"></a><a name="p835423612126"></a>菜单子标题</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p560448312126"><a name="p560448312126"></a><a name="p560448312126"></a>功能链接</p>
</th>
</tr>
</thead>
<tbody><tr id="row5044035312126"><td class="cellrowborder" rowspan="2" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5913681512126"><a name="p5913681512126"></a><a name="p5913681512126"></a>备份恢复管理</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p51047573154936"><a name="p51047573154936"></a><a name="p51047573154936"></a>备份管理</p>
</td>
</tr>
<tr id="row2684757312126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p35370461154936"><a name="p35370461154936"></a><a name="p35370461154936"></a>恢复管理</p>
</td>
</tr>
<tr id="row968636112126"><td class="cellrowborder" rowspan="3" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4639780112126"><a name="p4639780112126"></a><a name="p4639780112126"></a>维护</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p16092857154947"><a name="p16092857154947"></a><a name="p16092857154947"></a>日志导出</p>
</td>
</tr>
<tr id="row112998712126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p54750612154947"><a name="p54750612154947"></a><a name="p54750612154947"></a>审计日志导出</p>
</td>
</tr>
<tr id="row1839166212126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p50530978154947"><a name="p50530978154947"></a><a name="p50530978154947"></a>健康检查</p>
</td>
</tr>
<tr id="row5363168012126"><td class="cellrowborder" rowspan="5" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4919884712126"><a name="p4919884712126"></a><a name="p4919884712126"></a>监控和告警配置</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p5501854121332"><a name="p5501854121332"></a><a name="p5501854121332"></a>Syslog配置</p>
</td>
</tr>
<tr id="row2982640712126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p51429217121332"><a name="p51429217121332"></a><a name="p51429217121332"></a>阈值管理</p>
</td>
</tr>
<tr id="row1450146312126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p66993806155414"><a name="p66993806155414"></a><a name="p66993806155414"></a>SNMP配置</p>
</td>
</tr>
<tr id="row5489671612126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p50340891155414"><a name="p50340891155414"></a><a name="p50340891155414"></a>监控指标转储配置</p>
</td>
</tr>
<tr id="row3677799712126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p57070274155414"><a name="p57070274155414"></a><a name="p57070274155414"></a>资源贡献排名配置</p>
</td>
</tr>
<tr id="row6115575012126"><td class="cellrowborder" rowspan="5" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p5466875212126"><a name="p5466875212126"></a><a name="p5466875212126"></a>权限配置</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6609281912126"><a name="p6609281912126"></a><a name="p6609281912126"></a>用户管理</p>
</td>
</tr>
<tr id="row5796446112126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p6600602912126"><a name="p6600602912126"></a><a name="p6600602912126"></a>用户组管理</p>
</td>
</tr>
<tr id="row5718335712126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p4145850212126"><a name="p4145850212126"></a><a name="p4145850212126"></a>角色管理</p>
</td>
</tr>
<tr id="row3758220412126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p1888006612126"><a name="p1888006612126"></a><a name="p1888006612126"></a>密码策略配置</p>
</td>
</tr>
<tr id="row3570287212126"><td class="cellrowborder" valign="top" headers="mcps1.2.3.1.1 "><p id="p3661102212126"><a name="p3661102212126"></a><a name="p3661102212126"></a>OMS数据库密码修改</p>
</td>
</tr>
<tr id="row6106374912126"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p4721661212126"><a name="p4721661212126"></a><a name="p4721661212126"></a>补丁管理</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p6435483616116"><a name="p6435483616116"></a><a name="p6435483616116"></a>补丁管理</p>
</td>
</tr>
</tbody>
</table>

## 参考信息<a name="section5822925105428"></a>

MapReduce服务是公有云的一项数据分析服务，用于海量数据的管理和分析，简称MRS。

MRS通过MRS Manager管理大数据组件，例如Hadoop生态体系中的组件。因此，公有云MRS和MRS Manager管理界面上的部分概念需要区别，具体解释如[表4](#table39303837105524)：

**表 4**  差异对比参考

<a name="table39303837105524"></a>
<table><thead align="left"><tr id="row36661318105524"><th class="cellrowborder" valign="top" width="25.542554255425543%" id="mcps1.2.4.1.1"><p id="p16776821105524"><a name="p16776821105524"></a><a name="p16776821105524"></a>名词概念</p>
</th>
<th class="cellrowborder" valign="top" width="39.31393139313931%" id="mcps1.2.4.1.2"><p id="p16745293105524"><a name="p16745293105524"></a><a name="p16745293105524"></a>公有云MRS</p>
</th>
<th class="cellrowborder" valign="top" width="35.14351435143514%" id="mcps1.2.4.1.3"><p id="p14191477105524"><a name="p14191477105524"></a><a name="p14191477105524"></a>MRS Manager</p>
</th>
</tr>
</thead>
<tbody><tr id="row60614430105524"><td class="cellrowborder" valign="top" width="25.542554255425543%" headers="mcps1.2.4.1.1 "><p id="p10821826105524"><a name="p10821826105524"></a><a name="p10821826105524"></a>MapReduce服务</p>
</td>
<td class="cellrowborder" valign="top" width="39.31393139313931%" headers="mcps1.2.4.1.2 "><p id="p4152714105524"><a name="p4152714105524"></a><a name="p4152714105524"></a>表示公有云上的数据分析云服务，简称为MRS，包括Hive、Spark、Yarn、HDFS和ZooKeeper等组件。</p>
</td>
<td class="cellrowborder" valign="top" width="35.14351435143514%" headers="mcps1.2.4.1.3 "><p id="p825567105524"><a name="p825567105524"></a><a name="p825567105524"></a>为租户集群中的大数据组件提供的统一管理平台。</p>
</td>
</tr>
</tbody>
</table>

