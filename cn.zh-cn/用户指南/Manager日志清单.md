# Manager日志清单<a name="mrs_01_1227"></a>

## 日志描述<a name="s913238bdbd904089818deaf8faec78a8"></a>

**日志存储路径**：Manager相关日志的默认存储路径为“/var/log/Bigdata/_Manager组件_”。

-   ControllerService：/var/log/Bigdata/controller/（OMS安装、运行日志）
-   Httpd：/var/log/Bigdata/httpd（httpd安装、运行日志）
-   logman：/var/log/Bigdata/logman（日志打包工具日志）
-   NodeAgent：/var/log/Bigdata/nodeagent（NodeAgent安装、运行日志）
-   okerberos：/var/log/Bigdata/okerberos（okerberos安装、运行日志）
-   oldapserver：/var/log/Bigdata/oldapserver（oldapserver安装、运行日志）
-   MetricAgent：/var/log/Bigdata/metric\_agent（MetricAgent运行日志）
-   omm：/var/log/Bigdata/omm（omm安装、运行日志）
-   timestamp：/var/log/Bigdata/timestamp（NodeAgent启动时间日志）
-   tomcat：/var/log/Bigdata/tomcat（Web进程日志）
-   patch：/var/log/Bigdata/patch（补丁安装日志）
-   Sudo：/var/log/Bigdata/sudo（sudo脚本执行日志）
-   OS：/var/log/_message文件_（OS系统日志）
-   OS Performance：/var/log/osperf（OS性能统计日志）
-   OS Statistics：/var/log/osinfo/statistics（OS参数配置信息日志）

**日志归档规则**：

Manager的日志启动了自动压缩归档功能，缺省情况下，当日志大小超过10MB的时候，会自动压缩，压缩后的日志文件名规则为：“<原有日志名\>-<yyyy-mm-dd\_hh-mm-ss\>.\[编号\].log.zip”。最多保留最近的20个压缩文件。

**表 1**  Manager日志列表

<a name="zh-cn_topic_0046736741_table64240649"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046736741_row13827559"><th class="cellrowborder" valign="top" width="33.07330733073307%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0046736741_p46290527"><a name="zh-cn_topic_0046736741_p46290527"></a><a name="zh-cn_topic_0046736741_p46290527"></a><strong id="zh-cn_topic_0046736741_b13961561"><a name="zh-cn_topic_0046736741_b13961561"></a><a name="zh-cn_topic_0046736741_b13961561"></a>日志类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="34.603460346034595%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0046736741_p57144672"><a name="zh-cn_topic_0046736741_p57144672"></a><a name="zh-cn_topic_0046736741_p57144672"></a><strong id="zh-cn_topic_0046736741_b44540007"><a name="zh-cn_topic_0046736741_b44540007"></a><a name="zh-cn_topic_0046736741_b44540007"></a>日志文件名</strong></p>
</th>
<th class="cellrowborder" valign="top" width="32.32323232323232%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0046736741_p50970824"><a name="zh-cn_topic_0046736741_p50970824"></a><a name="zh-cn_topic_0046736741_p50970824"></a><strong id="zh-cn_topic_0046736741_b56084236"><a name="zh-cn_topic_0046736741_b56084236"></a><a name="zh-cn_topic_0046736741_b56084236"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046736741_row46529281"><td class="cellrowborder" rowspan="31" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p10775402"><a name="zh-cn_topic_0046736741_p10775402"></a><a name="zh-cn_topic_0046736741_p10775402"></a>Controller运行日志</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p392368"><a name="zh-cn_topic_0046736741_p392368"></a><a name="zh-cn_topic_0046736741_p392368"></a>controller.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p31781818"><a name="zh-cn_topic_0046736741_p31781818"></a><a name="zh-cn_topic_0046736741_p31781818"></a>记录组件安装、升级、补丁、配置、监控、告警和日常运维操作日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row17600908"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p16387448"><a name="zh-cn_topic_0046736741_p16387448"></a><a name="zh-cn_topic_0046736741_p16387448"></a>controller_client.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p52314908"><a name="zh-cn_topic_0046736741_p52314908"></a><a name="zh-cn_topic_0046736741_p52314908"></a>Rest接口运行日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row1072131"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p19733807"><a name="zh-cn_topic_0046736741_p19733807"></a><a name="zh-cn_topic_0046736741_p19733807"></a>acs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p54934568"><a name="zh-cn_topic_0046736741_p54934568"></a><a name="zh-cn_topic_0046736741_p54934568"></a>Acs运行日志。</p>
</td>
</tr>
<tr id="row41019387142446"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p34236073142446"><a name="p34236073142446"></a><a name="p34236073142446"></a>acs_spnego.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p21658503142446"><a name="p21658503142446"></a><a name="p21658503142446"></a>acs中spnego用户日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row24649069"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p50417539"><a name="zh-cn_topic_0046736741_p50417539"></a><a name="zh-cn_topic_0046736741_p50417539"></a>aos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p57288858"><a name="zh-cn_topic_0046736741_p57288858"></a><a name="zh-cn_topic_0046736741_p57288858"></a>Aos运行日志。</p>
</td>
</tr>
<tr id="row5072124111019"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8188895111019"><a name="p8188895111019"></a><a name="p8188895111019"></a>plugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p59320767111019"><a name="p59320767111019"></a><a name="p59320767111019"></a>Aos插件日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row45837677"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p21864360"><a name="zh-cn_topic_0046736741_p21864360"></a><a name="zh-cn_topic_0046736741_p21864360"></a>backupplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p26182711"><a name="zh-cn_topic_0046736741_p26182711"></a><a name="zh-cn_topic_0046736741_p26182711"></a>备份恢复进程运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row34317810"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p28279195"><a name="zh-cn_topic_0046736741_p28279195"></a><a name="zh-cn_topic_0046736741_p28279195"></a>controller_config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p8913420"><a name="zh-cn_topic_0046736741_p8913420"></a><a name="zh-cn_topic_0046736741_p8913420"></a>配置运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row13111919"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p55432544"><a name="zh-cn_topic_0046736741_p55432544"></a><a name="zh-cn_topic_0046736741_p55432544"></a>controller_nodesetup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p60851118"><a name="zh-cn_topic_0046736741_p60851118"></a><a name="zh-cn_topic_0046736741_p60851118"></a>Controller加载任务日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row10789155"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p1506375"><a name="zh-cn_topic_0046736741_p1506375"></a><a name="zh-cn_topic_0046736741_p1506375"></a>controller_root.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p54907514"><a name="zh-cn_topic_0046736741_p54907514"></a><a name="zh-cn_topic_0046736741_p54907514"></a>Controller进程系统日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row24405586"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p30695458"><a name="zh-cn_topic_0046736741_p30695458"></a><a name="zh-cn_topic_0046736741_p30695458"></a>controller_trace.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p3304150"><a name="zh-cn_topic_0046736741_p3304150"></a><a name="zh-cn_topic_0046736741_p3304150"></a>Controller与NodeAgent之间RPC通信日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row29737353"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59915407"><a name="zh-cn_topic_0046736741_p59915407"></a><a name="zh-cn_topic_0046736741_p59915407"></a>controller_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p21309805"><a name="zh-cn_topic_0046736741_p21309805"></a><a name="zh-cn_topic_0046736741_p21309805"></a>监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row57570525"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p32700980"><a name="zh-cn_topic_0046736741_p32700980"></a><a name="zh-cn_topic_0046736741_p32700980"></a>controller_fsm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p31533686"><a name="zh-cn_topic_0046736741_p31533686"></a><a name="zh-cn_topic_0046736741_p31533686"></a>状态机日志</p>
</td>
</tr>
<tr id="row38164439142752"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p32590896142812"><a name="p32590896142812"></a><a name="p32590896142812"></a>controller_alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p24595814142839"><a name="p24595814142839"></a><a name="p24595814142839"></a>Controller发送告警日志</p>
</td>
</tr>
<tr id="row24767381142758"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p30178762142849"><a name="p30178762142849"></a><a name="p30178762142849"></a>controller_backup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14346244142858"><a name="p14346244142858"></a><a name="p14346244142858"></a>Controller备份恢复日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row15367724"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p36826108"><a name="zh-cn_topic_0046736741_p36826108"></a><a name="zh-cn_topic_0046736741_p36826108"></a>install.log，distributeAdapterFiles.log，install_os_optimization.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p30124781"><a name="zh-cn_topic_0046736741_p30124781"></a><a name="zh-cn_topic_0046736741_p30124781"></a>oms安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row2687577"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p16367198"><a name="zh-cn_topic_0046736741_p16367198"></a><a name="zh-cn_topic_0046736741_p16367198"></a>oms_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p50674647"><a name="zh-cn_topic_0046736741_p50674647"></a><a name="zh-cn_topic_0046736741_p50674647"></a>oms启停日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row53418643"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p31942806"><a name="zh-cn_topic_0046736741_p31942806"></a><a name="zh-cn_topic_0046736741_p31942806"></a>installntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p37230465"><a name="zh-cn_topic_0046736741_p37230465"></a><a name="zh-cn_topic_0046736741_p37230465"></a>ntp安装日志</p>
</td>
</tr>
<tr id="row1172406315957"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1012501415957"><a name="p1012501415957"></a><a name="p1012501415957"></a>modify_manager_param.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1481982615957"><a name="p1481982615957"></a><a name="p1481982615957"></a>修改Manager参数日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row66638733"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p29028329"><a name="zh-cn_topic_0046736741_p29028329"></a><a name="zh-cn_topic_0046736741_p29028329"></a>backup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p2484416"><a name="zh-cn_topic_0046736741_p2484416"></a><a name="zh-cn_topic_0046736741_p2484416"></a>OMS备份脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row22359750"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p66309348"><a name="zh-cn_topic_0046736741_p66309348"></a><a name="zh-cn_topic_0046736741_p66309348"></a>supressionAlarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p2348082"><a name="zh-cn_topic_0046736741_p2348082"></a><a name="zh-cn_topic_0046736741_p2348082"></a>告警脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row25200320"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p27960000"><a name="zh-cn_topic_0046736741_p27960000"></a><a name="zh-cn_topic_0046736741_p27960000"></a>om.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p50167500"><a name="zh-cn_topic_0046736741_p50167500"></a><a name="zh-cn_topic_0046736741_p50167500"></a>生成om证书日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row48854323"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p64886077"><a name="zh-cn_topic_0046736741_p64886077"></a><a name="zh-cn_topic_0046736741_p64886077"></a>backupplugin_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p21280904"><a name="zh-cn_topic_0046736741_p21280904"></a><a name="zh-cn_topic_0046736741_p21280904"></a>备份恢复插件进程启动日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row57310413"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p11631900"><a name="zh-cn_topic_0046736741_p11631900"></a><a name="zh-cn_topic_0046736741_p11631900"></a>getLogs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p2659839"><a name="zh-cn_topic_0046736741_p2659839"></a><a name="zh-cn_topic_0046736741_p2659839"></a>采集日志脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row23938556"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59974873"><a name="zh-cn_topic_0046736741_p59974873"></a><a name="zh-cn_topic_0046736741_p59974873"></a>backupAuditLogs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p26126526"><a name="zh-cn_topic_0046736741_p26126526"></a><a name="zh-cn_topic_0046736741_p26126526"></a>审计日志备份脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row33812148"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p54429433"><a name="zh-cn_topic_0046736741_p54429433"></a><a name="zh-cn_topic_0046736741_p54429433"></a>certStatus.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p46707930"><a name="zh-cn_topic_0046736741_p46707930"></a><a name="zh-cn_topic_0046736741_p46707930"></a>证书定期检查日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row17718193"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p25887561"><a name="zh-cn_topic_0046736741_p25887561"></a><a name="zh-cn_topic_0046736741_p25887561"></a>distribute.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p16517681"><a name="zh-cn_topic_0046736741_p16517681"></a><a name="zh-cn_topic_0046736741_p16517681"></a>证书分发日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14441402"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p28902942"><a name="zh-cn_topic_0046736741_p28902942"></a><a name="zh-cn_topic_0046736741_p28902942"></a>ficertgenetrate.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p59436966"><a name="zh-cn_topic_0046736741_p59436966"></a><a name="zh-cn_topic_0046736741_p59436966"></a>证书替换日志，包括生成二级证书、cas证书、httpd证书的日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row38237098"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p10197204"><a name="zh-cn_topic_0046736741_p10197204"></a><a name="zh-cn_topic_0046736741_p10197204"></a>genPwFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p20667178"><a name="zh-cn_topic_0046736741_p20667178"></a><a name="zh-cn_topic_0046736741_p20667178"></a>生成证书密码文件日志</p>
</td>
</tr>
<tr id="row566558016518"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5625881216518"><a name="p5625881216518"></a><a name="p5625881216518"></a>modifyproxyconf.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6066993316518"><a name="p6066993316518"></a><a name="p6066993316518"></a>修改HTTPD代理配置的日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row51786882"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p33987910"><a name="zh-cn_topic_0046736741_p33987910"></a><a name="zh-cn_topic_0046736741_p33987910"></a>importTar.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p1557355"><a name="zh-cn_topic_0046736741_p1557355"></a><a name="zh-cn_topic_0046736741_p1557355"></a>证书导入信任库日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14016201"><td class="cellrowborder" rowspan="2" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p61570530"><a name="zh-cn_topic_0046736741_p61570530"></a><a name="zh-cn_topic_0046736741_p61570530"></a>Httpd</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p21157039"><a name="zh-cn_topic_0046736741_p21157039"></a><a name="zh-cn_topic_0046736741_p21157039"></a>install.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p35998617"><a name="zh-cn_topic_0046736741_p35998617"></a><a name="zh-cn_topic_0046736741_p35998617"></a>Httpd安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row55552100"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p3426243"><a name="zh-cn_topic_0046736741_p3426243"></a><a name="zh-cn_topic_0046736741_p3426243"></a>access_log, error_log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p9090291"><a name="zh-cn_topic_0046736741_p9090291"></a><a name="zh-cn_topic_0046736741_p9090291"></a>Httpd运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14703761"><td class="cellrowborder" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p50153981"><a name="zh-cn_topic_0046736741_p50153981"></a><a name="zh-cn_topic_0046736741_p50153981"></a>logman</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p35940621"><a name="zh-cn_topic_0046736741_p35940621"></a><a name="zh-cn_topic_0046736741_p35940621"></a>logman.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p25509161"><a name="zh-cn_topic_0046736741_p25509161"></a><a name="zh-cn_topic_0046736741_p25509161"></a>日志打包工具日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row28255864"><td class="cellrowborder" rowspan="23" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p7023634"><a name="zh-cn_topic_0046736741_p7023634"></a><a name="zh-cn_topic_0046736741_p7023634"></a>NodeAgent</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p32043501"><a name="zh-cn_topic_0046736741_p32043501"></a><a name="zh-cn_topic_0046736741_p32043501"></a>install.log，install_os_optimization.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p45386801"><a name="zh-cn_topic_0046736741_p45386801"></a><a name="zh-cn_topic_0046736741_p45386801"></a>NodeAgent安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row5828025"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p2308012"><a name="zh-cn_topic_0046736741_p2308012"></a><a name="zh-cn_topic_0046736741_p2308012"></a>installntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p52731292"><a name="zh-cn_topic_0046736741_p52731292"></a><a name="zh-cn_topic_0046736741_p52731292"></a>ntp安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row4819582"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p54841843"><a name="zh-cn_topic_0046736741_p54841843"></a><a name="zh-cn_topic_0046736741_p54841843"></a>start_ntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p13004313"><a name="zh-cn_topic_0046736741_p13004313"></a><a name="zh-cn_topic_0046736741_p13004313"></a>ntp启动日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row49929958"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p17794775"><a name="zh-cn_topic_0046736741_p17794775"></a><a name="zh-cn_topic_0046736741_p17794775"></a>ntpChecker.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p32090702"><a name="zh-cn_topic_0046736741_p32090702"></a><a name="zh-cn_topic_0046736741_p32090702"></a>ntp检查日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row20380862"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p40237110"><a name="zh-cn_topic_0046736741_p40237110"></a><a name="zh-cn_topic_0046736741_p40237110"></a>ntpMonitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p37980454"><a name="zh-cn_topic_0046736741_p37980454"></a><a name="zh-cn_topic_0046736741_p37980454"></a>ntp监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row6279771"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p38899443"><a name="zh-cn_topic_0046736741_p38899443"></a><a name="zh-cn_topic_0046736741_p38899443"></a>heartbeat_trace.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p63847192"><a name="zh-cn_topic_0046736741_p63847192"></a><a name="zh-cn_topic_0046736741_p63847192"></a>NodeAgent与Controller心跳日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row37753818"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p38160445"><a name="zh-cn_topic_0046736741_p38160445"></a><a name="zh-cn_topic_0046736741_p38160445"></a>alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p3988320"><a name="zh-cn_topic_0046736741_p3988320"></a><a name="zh-cn_topic_0046736741_p3988320"></a>告警日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row35894881"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p21804231"><a name="zh-cn_topic_0046736741_p21804231"></a><a name="zh-cn_topic_0046736741_p21804231"></a>monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p21312323"><a name="zh-cn_topic_0046736741_p21312323"></a><a name="zh-cn_topic_0046736741_p21312323"></a>监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row57593179"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p34535952"><a name="zh-cn_topic_0046736741_p34535952"></a><a name="zh-cn_topic_0046736741_p34535952"></a>nodeagent_ctl.log，start-agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p45948750"><a name="zh-cn_topic_0046736741_p45948750"></a><a name="zh-cn_topic_0046736741_p45948750"></a>NodeAgent启动日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row10885567"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p9315740"><a name="zh-cn_topic_0046736741_p9315740"></a><a name="zh-cn_topic_0046736741_p9315740"></a>agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p16377494"><a name="zh-cn_topic_0046736741_p16377494"></a><a name="zh-cn_topic_0046736741_p16377494"></a>NodeAgent运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row13179721"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p60924472"><a name="zh-cn_topic_0046736741_p60924472"></a><a name="zh-cn_topic_0046736741_p60924472"></a>cert.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p35935224"><a name="zh-cn_topic_0046736741_p35935224"></a><a name="zh-cn_topic_0046736741_p35935224"></a>证书日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row54981566"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p24321850"><a name="zh-cn_topic_0046736741_p24321850"></a><a name="zh-cn_topic_0046736741_p24321850"></a>agentplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p23912794"><a name="zh-cn_topic_0046736741_p23912794"></a><a name="zh-cn_topic_0046736741_p23912794"></a>监控agent侧插件运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row13888555"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p51231165"><a name="zh-cn_topic_0046736741_p51231165"></a><a name="zh-cn_topic_0046736741_p51231165"></a>omaplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p56083687"><a name="zh-cn_topic_0046736741_p56083687"></a><a name="zh-cn_topic_0046736741_p56083687"></a>OMA插件运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row34991141"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p15710183"><a name="zh-cn_topic_0046736741_p15710183"></a><a name="zh-cn_topic_0046736741_p15710183"></a>diskhealth.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p64565334"><a name="zh-cn_topic_0046736741_p64565334"></a><a name="zh-cn_topic_0046736741_p64565334"></a>磁盘健康检查日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row44217097"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p24815142"><a name="zh-cn_topic_0046736741_p24815142"></a><a name="zh-cn_topic_0046736741_p24815142"></a>supressionAlarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p63869475"><a name="zh-cn_topic_0046736741_p63869475"></a><a name="zh-cn_topic_0046736741_p63869475"></a>告警脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row37954365"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p54404718"><a name="zh-cn_topic_0046736741_p54404718"></a><a name="zh-cn_topic_0046736741_p54404718"></a>updateHostFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p44706003"><a name="zh-cn_topic_0046736741_p44706003"></a><a name="zh-cn_topic_0046736741_p44706003"></a>更新主机列表日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row66809708"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p42877307"><a name="zh-cn_topic_0046736741_p42877307"></a><a name="zh-cn_topic_0046736741_p42877307"></a>collectLog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p50509875"><a name="zh-cn_topic_0046736741_p50509875"></a><a name="zh-cn_topic_0046736741_p50509875"></a>节点日志采集脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row51935693"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p46041620"><a name="zh-cn_topic_0046736741_p46041620"></a><a name="zh-cn_topic_0046736741_p46041620"></a>host_metric_collect.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p38383768"><a name="zh-cn_topic_0046736741_p38383768"></a><a name="zh-cn_topic_0046736741_p38383768"></a>主机指标采集运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row9909596"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p64479813"><a name="zh-cn_topic_0046736741_p64479813"></a><a name="zh-cn_topic_0046736741_p64479813"></a>checkfileconfig.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p55482399"><a name="zh-cn_topic_0046736741_p55482399"></a><a name="zh-cn_topic_0046736741_p55482399"></a>文件权限配置检查运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row29579550"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p47133348"><a name="zh-cn_topic_0046736741_p47133348"></a><a name="zh-cn_topic_0046736741_p47133348"></a>entropycheck.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p59704814"><a name="zh-cn_topic_0046736741_p59704814"></a><a name="zh-cn_topic_0046736741_p59704814"></a>熵值检查运行日志</p>
</td>
</tr>
<tr id="row4836868285942"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2554918985942"><a name="p2554918985942"></a><a name="p2554918985942"></a>timer.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p5621844185942"><a name="p5621844185942"></a><a name="p5621844185942"></a>节点定时调度日志</p>
</td>
</tr>
<tr id="row51660266142919"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p50107635143012"><a name="p50107635143012"></a><a name="p50107635143012"></a>pluginmonitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15723967143021"><a name="p15723967143021"></a><a name="p15723967143021"></a>组件监控插件日志</p>
</td>
</tr>
<tr id="row11895811142938"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p163018143032"><a name="p163018143032"></a><a name="p163018143032"></a>agent_alarm_py.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p30385516143047"><a name="p30385516143047"></a><a name="p30385516143047"></a>NodeAgent检查文件权限发送告警日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row472416"><td class="cellrowborder" rowspan="11" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p38265740"><a name="zh-cn_topic_0046736741_p38265740"></a><a name="zh-cn_topic_0046736741_p38265740"></a>okerberos</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p12517232"><a name="zh-cn_topic_0046736741_p12517232"></a><a name="zh-cn_topic_0046736741_p12517232"></a>addRealm.log，modifyKerberosRealm.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p7262901"><a name="zh-cn_topic_0046736741_p7262901"></a><a name="zh-cn_topic_0046736741_p7262901"></a>切域日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row65366115"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p60163996"><a name="zh-cn_topic_0046736741_p60163996"></a><a name="zh-cn_topic_0046736741_p60163996"></a>checkservice_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p41445513"><a name="zh-cn_topic_0046736741_p41445513"></a><a name="zh-cn_topic_0046736741_p41445513"></a>Okerberos健康检查日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row37465303"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p14790702"><a name="zh-cn_topic_0046736741_p14790702"></a><a name="zh-cn_topic_0046736741_p14790702"></a>genKeytab.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p57196205"><a name="zh-cn_topic_0046736741_p57196205"></a><a name="zh-cn_topic_0046736741_p57196205"></a>生成keytab日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row45003804"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p21429483"><a name="zh-cn_topic_0046736741_p21429483"></a><a name="zh-cn_topic_0046736741_p21429483"></a>KerberosAdmin_genConfigDetail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p58066551"><a name="zh-cn_topic_0046736741_p58066551"></a><a name="zh-cn_topic_0046736741_p58066551"></a>启动kadmin进程时，生成kadmin.conf的运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row52836911"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p51931360"><a name="zh-cn_topic_0046736741_p51931360"></a><a name="zh-cn_topic_0046736741_p51931360"></a>KerberosServer_genConfigDetail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p45690626"><a name="zh-cn_topic_0046736741_p45690626"></a><a name="zh-cn_topic_0046736741_p45690626"></a>启动krb5kdc进程时，生成krb5kdc.conf的运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row8562452"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p22470050"><a name="zh-cn_topic_0046736741_p22470050"></a><a name="zh-cn_topic_0046736741_p22470050"></a>oms-kadmind.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p8134772"><a name="zh-cn_topic_0046736741_p8134772"></a><a name="zh-cn_topic_0046736741_p8134772"></a>kadmin进程的运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row6104091"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p24669326"><a name="zh-cn_topic_0046736741_p24669326"></a><a name="zh-cn_topic_0046736741_p24669326"></a>oms_kerberos_install.log，postinstall_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p52058427"><a name="zh-cn_topic_0046736741_p52058427"></a><a name="zh-cn_topic_0046736741_p52058427"></a>okerberos安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row65872662"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p34085386"><a name="zh-cn_topic_0046736741_p34085386"></a><a name="zh-cn_topic_0046736741_p34085386"></a>oms-krb5kdc.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p9452875"><a name="zh-cn_topic_0046736741_p9452875"></a><a name="zh-cn_topic_0046736741_p9452875"></a>krbkdc运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row17967011"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p46041793"><a name="zh-cn_topic_0046736741_p46041793"></a><a name="zh-cn_topic_0046736741_p46041793"></a>start_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p38397792"><a name="zh-cn_topic_0046736741_p38397792"></a><a name="zh-cn_topic_0046736741_p38397792"></a>okerberos启动日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row10035816"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p7594730"><a name="zh-cn_topic_0046736741_p7594730"></a><a name="zh-cn_topic_0046736741_p7594730"></a>realmDataConfigProcess.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p11193409"><a name="zh-cn_topic_0046736741_p11193409"></a><a name="zh-cn_topic_0046736741_p11193409"></a>切域失败，回滚日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row33631824"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p39823233"><a name="zh-cn_topic_0046736741_p39823233"></a><a name="zh-cn_topic_0046736741_p39823233"></a>stop_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p4456442"><a name="zh-cn_topic_0046736741_p4456442"></a><a name="zh-cn_topic_0046736741_p4456442"></a>okerberos停止日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row40107986"><td class="cellrowborder" rowspan="10" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p27521419"><a name="zh-cn_topic_0046736741_p27521419"></a><a name="zh-cn_topic_0046736741_p27521419"></a>oldapserver</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p14642465"><a name="zh-cn_topic_0046736741_p14642465"></a><a name="zh-cn_topic_0046736741_p14642465"></a>ldapserver_backup.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p45188987"><a name="zh-cn_topic_0046736741_p45188987"></a><a name="zh-cn_topic_0046736741_p45188987"></a>Oldapserver备份日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row4047701"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59428369"><a name="zh-cn_topic_0046736741_p59428369"></a><a name="zh-cn_topic_0046736741_p59428369"></a>ldapserver_chk_service.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p48968581"><a name="zh-cn_topic_0046736741_p48968581"></a><a name="zh-cn_topic_0046736741_p48968581"></a>Oldapserver健康检查日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row38064052"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p63289392"><a name="zh-cn_topic_0046736741_p63289392"></a><a name="zh-cn_topic_0046736741_p63289392"></a>ldapserver_install.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p26167161"><a name="zh-cn_topic_0046736741_p26167161"></a><a name="zh-cn_topic_0046736741_p26167161"></a>Oldapserver安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row34177862"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p16943404"><a name="zh-cn_topic_0046736741_p16943404"></a><a name="zh-cn_topic_0046736741_p16943404"></a>ldapserver_start.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p30238483"><a name="zh-cn_topic_0046736741_p30238483"></a><a name="zh-cn_topic_0046736741_p30238483"></a>Oldapserver启动日志</p>
</td>
</tr>
<tr id="row1933129617146"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2233114217146"><a name="p2233114217146"></a><a name="p2233114217146"></a>ldapserver_status.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6399204817146"><a name="p6399204817146"></a><a name="p6399204817146"></a>Oldapserver进程状态检查日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row3710894"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p32147001"><a name="zh-cn_topic_0046736741_p32147001"></a><a name="zh-cn_topic_0046736741_p32147001"></a>ldapserver_stop.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p53770264"><a name="zh-cn_topic_0046736741_p53770264"></a><a name="zh-cn_topic_0046736741_p53770264"></a>Oldapserver停止日志</p>
</td>
</tr>
<tr id="row8292590171427"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p611223171427"><a name="p611223171427"></a><a name="p611223171427"></a>ldapserver_wrap.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p49509108171427"><a name="p49509108171427"></a><a name="p49509108171427"></a>Oldapserver服务管理日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14170331"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p6946132"><a name="zh-cn_topic_0046736741_p6946132"></a><a name="zh-cn_topic_0046736741_p6946132"></a>ldapserver_uninstall.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p25765781"><a name="zh-cn_topic_0046736741_p25765781"></a><a name="zh-cn_topic_0046736741_p25765781"></a>Oldapserver卸载日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row30565440"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59881601"><a name="zh-cn_topic_0046736741_p59881601"></a><a name="zh-cn_topic_0046736741_p59881601"></a>restart_service.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p18571551"><a name="zh-cn_topic_0046736741_p18571551"></a><a name="zh-cn_topic_0046736741_p18571551"></a>Oldapserver重启日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row32926236"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p49779472"><a name="zh-cn_topic_0046736741_p49779472"></a><a name="zh-cn_topic_0046736741_p49779472"></a>ldapserver_unlockUser.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p5605395"><a name="zh-cn_topic_0046736741_p5605395"></a><a name="zh-cn_topic_0046736741_p5605395"></a>记录解锁Ldap用户和管理帐户的日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row50448563"><td class="cellrowborder" rowspan="48" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59801811"><a name="zh-cn_topic_0046736741_p59801811"></a><a name="zh-cn_topic_0046736741_p59801811"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p12108503"><a name="zh-cn_topic_0046736741_p12108503"></a><a name="zh-cn_topic_0046736741_p12108503"></a>omsconfig.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p41264680"><a name="zh-cn_topic_0046736741_p41264680"></a><a name="zh-cn_topic_0046736741_p41264680"></a>OMS配置日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row35837800"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p17180694"><a name="zh-cn_topic_0046736741_p17180694"></a><a name="zh-cn_topic_0046736741_p17180694"></a>check_oms_heartbeat.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p49459013"><a name="zh-cn_topic_0046736741_p49459013"></a><a name="zh-cn_topic_0046736741_p49459013"></a>OMS心跳运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row42477941"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p18161159"><a name="zh-cn_topic_0046736741_p18161159"></a><a name="zh-cn_topic_0046736741_p18161159"></a>monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p61767790"><a name="zh-cn_topic_0046736741_p61767790"></a><a name="zh-cn_topic_0046736741_p61767790"></a>OMS监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row19039205"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p65780646"><a name="zh-cn_topic_0046736741_p65780646"></a><a name="zh-cn_topic_0046736741_p65780646"></a>ha_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p26632111"><a name="zh-cn_topic_0046736741_p26632111"></a><a name="zh-cn_topic_0046736741_p26632111"></a>HA_Monitor操作日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row38362415"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p20347896"><a name="zh-cn_topic_0046736741_p20347896"></a><a name="zh-cn_topic_0046736741_p20347896"></a>ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p37566878"><a name="zh-cn_topic_0046736741_p37566878"></a><a name="zh-cn_topic_0046736741_p37566878"></a>HA操作日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row2557583"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p5837642"><a name="zh-cn_topic_0046736741_p5837642"></a><a name="zh-cn_topic_0046736741_p5837642"></a>fms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p3086998"><a name="zh-cn_topic_0046736741_p3086998"></a><a name="zh-cn_topic_0046736741_p3086998"></a>告警日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row27782986"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p35829361"><a name="zh-cn_topic_0046736741_p35829361"></a><a name="zh-cn_topic_0046736741_p35829361"></a>fms_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p16497149"><a name="zh-cn_topic_0046736741_p16497149"></a><a name="zh-cn_topic_0046736741_p16497149"></a>告警的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14256621"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p13935627"><a name="zh-cn_topic_0046736741_p13935627"></a><a name="zh-cn_topic_0046736741_p13935627"></a>fms_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p55043969"><a name="zh-cn_topic_0046736741_p55043969"></a><a name="zh-cn_topic_0046736741_p55043969"></a>告警控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row25633677"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p63061947"><a name="zh-cn_topic_0046736741_p63061947"></a><a name="zh-cn_topic_0046736741_p63061947"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p7744086"><a name="zh-cn_topic_0046736741_p7744086"></a><a name="zh-cn_topic_0046736741_p7744086"></a>告警配置日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row2587911"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p8294256"><a name="zh-cn_topic_0046736741_p8294256"></a><a name="zh-cn_topic_0046736741_p8294256"></a>iam.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p746105"><a name="zh-cn_topic_0046736741_p746105"></a><a name="zh-cn_topic_0046736741_p746105"></a>IAM日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row6714945"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p7039645"><a name="zh-cn_topic_0046736741_p7039645"></a><a name="zh-cn_topic_0046736741_p7039645"></a>iam_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p33340398"><a name="zh-cn_topic_0046736741_p33340398"></a><a name="zh-cn_topic_0046736741_p33340398"></a>IAM控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row31628134"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p11742081"><a name="zh-cn_topic_0046736741_p11742081"></a><a name="zh-cn_topic_0046736741_p11742081"></a>iam_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p11584517"><a name="zh-cn_topic_0046736741_p11584517"></a><a name="zh-cn_topic_0046736741_p11584517"></a>IAM的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row37151789"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p56504928"><a name="zh-cn_topic_0046736741_p56504928"></a><a name="zh-cn_topic_0046736741_p56504928"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p13496464"><a name="zh-cn_topic_0046736741_p13496464"></a><a name="zh-cn_topic_0046736741_p13496464"></a>IAM配置日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row54359314"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p41028295"><a name="zh-cn_topic_0046736741_p41028295"></a><a name="zh-cn_topic_0046736741_p41028295"></a>operatelog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p34957613"><a name="zh-cn_topic_0046736741_p34957613"></a><a name="zh-cn_topic_0046736741_p34957613"></a>IAM操作日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row46183066"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p49840843"><a name="zh-cn_topic_0046736741_p49840843"></a><a name="zh-cn_topic_0046736741_p49840843"></a>heartbeatcheck_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p10576514"><a name="zh-cn_topic_0046736741_p10576514"></a><a name="zh-cn_topic_0046736741_p10576514"></a>OMS心跳的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row28079762"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p59868234"><a name="zh-cn_topic_0046736741_p59868234"></a><a name="zh-cn_topic_0046736741_p59868234"></a>install_oms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p17488762"><a name="zh-cn_topic_0046736741_p17488762"></a><a name="zh-cn_topic_0046736741_p17488762"></a>OMS安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row23181135"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p65732647"><a name="zh-cn_topic_0046736741_p65732647"></a><a name="zh-cn_topic_0046736741_p65732647"></a>pms_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p22744204"><a name="zh-cn_topic_0046736741_p22744204"></a><a name="zh-cn_topic_0046736741_p22744204"></a>监控的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row3371246"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p4635537"><a name="zh-cn_topic_0046736741_p4635537"></a><a name="zh-cn_topic_0046736741_p4635537"></a>pms_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p39934196"><a name="zh-cn_topic_0046736741_p39934196"></a><a name="zh-cn_topic_0046736741_p39934196"></a>监控控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row23863445"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p53890875"><a name="zh-cn_topic_0046736741_p53890875"></a><a name="zh-cn_topic_0046736741_p53890875"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p3084791"><a name="zh-cn_topic_0046736741_p3084791"></a><a name="zh-cn_topic_0046736741_p3084791"></a>监控配置日志</p>
</td>
</tr>
<tr id="row1887301515117"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5231928315117"><a name="p5231928315117"></a><a name="p5231928315117"></a>plugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1000349815117"><a name="p1000349815117"></a><a name="p1000349815117"></a>监控插件运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row27763119"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p34220196"><a name="zh-cn_topic_0046736741_p34220196"></a><a name="zh-cn_topic_0046736741_p34220196"></a>pms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p20372514"><a name="zh-cn_topic_0046736741_p20372514"></a><a name="zh-cn_topic_0046736741_p20372514"></a>监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row49134899"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p20503888"><a name="zh-cn_topic_0046736741_p20503888"></a><a name="zh-cn_topic_0046736741_p20503888"></a>ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p50202250"><a name="zh-cn_topic_0046736741_p50202250"></a><a name="zh-cn_topic_0046736741_p50202250"></a>HA运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row49167069"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p23109644"><a name="zh-cn_topic_0046736741_p23109644"></a><a name="zh-cn_topic_0046736741_p23109644"></a>cep_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p59941900"><a name="zh-cn_topic_0046736741_p59941900"></a><a name="zh-cn_topic_0046736741_p59941900"></a>CEP的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row2606194"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p9775150"><a name="zh-cn_topic_0046736741_p9775150"></a><a name="zh-cn_topic_0046736741_p9775150"></a>cep_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p53589646"><a name="zh-cn_topic_0046736741_p53589646"></a><a name="zh-cn_topic_0046736741_p53589646"></a>CEP控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row12544767"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p9493201"><a name="zh-cn_topic_0046736741_p9493201"></a><a name="zh-cn_topic_0046736741_p9493201"></a>cep.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p30751803"><a name="zh-cn_topic_0046736741_p30751803"></a><a name="zh-cn_topic_0046736741_p30751803"></a>CEP日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row8330777"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p3704347"><a name="zh-cn_topic_0046736741_p3704347"></a><a name="zh-cn_topic_0046736741_p3704347"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p31616714"><a name="zh-cn_topic_0046736741_p31616714"></a><a name="zh-cn_topic_0046736741_p31616714"></a>CEP配置日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row16114973"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p30244474"><a name="zh-cn_topic_0046736741_p30244474"></a><a name="zh-cn_topic_0046736741_p30244474"></a>omm_gaussdba.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p33883319"><a name="zh-cn_topic_0046736741_p33883319"></a><a name="zh-cn_topic_0046736741_p33883319"></a>gaussdb的HA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row36514417"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p4877794"><a name="zh-cn_topic_0046736741_p4877794"></a><a name="zh-cn_topic_0046736741_p4877794"></a>gaussdb-&lt;SERIAL&gt;.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p59556999"><a name="zh-cn_topic_0046736741_p59556999"></a><a name="zh-cn_topic_0046736741_p59556999"></a>gaussdb运行日志</p>
</td>
</tr>
<tr id="row11945706145430"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p28078126145430"><a name="p28078126145430"></a><a name="p28078126145430"></a>gs_ctl-&lt;DATE&gt;.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p59735763145430"><a name="p59735763145430"></a><a name="p59735763145430"></a>gaussdb控制日志的归档日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row66250944"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p64726287"><a name="zh-cn_topic_0046736741_p64726287"></a><a name="zh-cn_topic_0046736741_p64726287"></a>gs_ctl-current.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p8337927"><a name="zh-cn_topic_0046736741_p8337927"></a><a name="zh-cn_topic_0046736741_p8337927"></a>gaussdb控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row7932481"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p38551240"><a name="zh-cn_topic_0046736741_p38551240"></a><a name="zh-cn_topic_0046736741_p38551240"></a>gs_guc-current.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p35642764"><a name="zh-cn_topic_0046736741_p35642764"></a><a name="zh-cn_topic_0046736741_p35642764"></a>gaussdb操作日志</p>
</td>
</tr>
<tr id="row38574289145832"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p37509676145832"><a name="p37509676145832"></a><a name="p37509676145832"></a>encrypt.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18384920145832"><a name="p18384920145832"></a><a name="p18384920145832"></a>omm加密日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row52349424"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p12444953"><a name="zh-cn_topic_0046736741_p12444953"></a><a name="zh-cn_topic_0046736741_p12444953"></a>omm_agent_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p1408307"><a name="zh-cn_topic_0046736741_p1408307"></a><a name="zh-cn_topic_0046736741_p1408307"></a>OMA控制日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row12674770"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p20023448"><a name="zh-cn_topic_0046736741_p20023448"></a><a name="zh-cn_topic_0046736741_p20023448"></a>oma_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p11286562"><a name="zh-cn_topic_0046736741_p11286562"></a><a name="zh-cn_topic_0046736741_p11286562"></a>OMA监控日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row34470196"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p40622496"><a name="zh-cn_topic_0046736741_p40622496"></a><a name="zh-cn_topic_0046736741_p40622496"></a>install_oma.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p2087876"><a name="zh-cn_topic_0046736741_p2087876"></a><a name="zh-cn_topic_0046736741_p2087876"></a>OMA安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row18790891"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p45667223"><a name="zh-cn_topic_0046736741_p45667223"></a><a name="zh-cn_topic_0046736741_p45667223"></a>config_oma.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p8057616"><a name="zh-cn_topic_0046736741_p8057616"></a><a name="zh-cn_topic_0046736741_p8057616"></a>OMA配置日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row5409685"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p35531307"><a name="zh-cn_topic_0046736741_p35531307"></a><a name="zh-cn_topic_0046736741_p35531307"></a>omm_agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p59463618"><a name="zh-cn_topic_0046736741_p59463618"></a><a name="zh-cn_topic_0046736741_p59463618"></a>OMA运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row65410517"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p63760528"><a name="zh-cn_topic_0046736741_p63760528"></a><a name="zh-cn_topic_0046736741_p63760528"></a>acs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p64329119"><a name="zh-cn_topic_0046736741_p64329119"></a><a name="zh-cn_topic_0046736741_p64329119"></a>acs资源日志。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row42091162"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p53940931"><a name="zh-cn_topic_0046736741_p53940931"></a><a name="zh-cn_topic_0046736741_p53940931"></a>aos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p7139252"><a name="zh-cn_topic_0046736741_p7139252"></a><a name="zh-cn_topic_0046736741_p7139252"></a>aos资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row64253271"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p37132488"><a name="zh-cn_topic_0046736741_p37132488"></a><a name="zh-cn_topic_0046736741_p37132488"></a>controller.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p54941590"><a name="zh-cn_topic_0046736741_p54941590"></a><a name="zh-cn_topic_0046736741_p54941590"></a>controller资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row24712267"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p55536623"><a name="zh-cn_topic_0046736741_p55536623"></a><a name="zh-cn_topic_0046736741_p55536623"></a>feed_watchdog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p2172578"><a name="zh-cn_topic_0046736741_p2172578"></a><a name="zh-cn_topic_0046736741_p2172578"></a>feed_watchdog资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row19553210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p40306186"><a name="zh-cn_topic_0046736741_p40306186"></a><a name="zh-cn_topic_0046736741_p40306186"></a>floatip.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p43575614"><a name="zh-cn_topic_0046736741_p43575614"></a><a name="zh-cn_topic_0046736741_p43575614"></a>floatip资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row56636209"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p24130231"><a name="zh-cn_topic_0046736741_p24130231"></a><a name="zh-cn_topic_0046736741_p24130231"></a>ha_ntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p8391701"><a name="zh-cn_topic_0046736741_p8391701"></a><a name="zh-cn_topic_0046736741_p8391701"></a>ntp资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row8416453"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p10644124"><a name="zh-cn_topic_0046736741_p10644124"></a><a name="zh-cn_topic_0046736741_p10644124"></a>httpd.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p56867678"><a name="zh-cn_topic_0046736741_p56867678"></a><a name="zh-cn_topic_0046736741_p56867678"></a>httpd资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row42047060"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p50368676"><a name="zh-cn_topic_0046736741_p50368676"></a><a name="zh-cn_topic_0046736741_p50368676"></a>okerberos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p53330965"><a name="zh-cn_topic_0046736741_p53330965"></a><a name="zh-cn_topic_0046736741_p53330965"></a>okerberos资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row10216641"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p22241606"><a name="zh-cn_topic_0046736741_p22241606"></a><a name="zh-cn_topic_0046736741_p22241606"></a>oldap.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p56739647"><a name="zh-cn_topic_0046736741_p56739647"></a><a name="zh-cn_topic_0046736741_p56739647"></a>oldap资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row40894779"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p24142782"><a name="zh-cn_topic_0046736741_p24142782"></a><a name="zh-cn_topic_0046736741_p24142782"></a>tomcat.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p9408297"><a name="zh-cn_topic_0046736741_p9408297"></a><a name="zh-cn_topic_0046736741_p9408297"></a>tomcat资源日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row17565813"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p13544785"><a name="zh-cn_topic_0046736741_p13544785"></a><a name="zh-cn_topic_0046736741_p13544785"></a>send_alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p23385768"><a name="zh-cn_topic_0046736741_p23385768"></a><a name="zh-cn_topic_0046736741_p23385768"></a>管理节点HA告警发送脚本运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row9145326"><td class="cellrowborder" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p2573964"><a name="zh-cn_topic_0046736741_p2573964"></a><a name="zh-cn_topic_0046736741_p2573964"></a>timestamp</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p7164506"><a name="zh-cn_topic_0046736741_p7164506"></a><a name="zh-cn_topic_0046736741_p7164506"></a>restart_stamp</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p43454080"><a name="zh-cn_topic_0046736741_p43454080"></a><a name="zh-cn_topic_0046736741_p43454080"></a>NodeAgent启动时间</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row55542404"><td class="cellrowborder" rowspan="5" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p2640866"><a name="zh-cn_topic_0046736741_p2640866"></a><a name="zh-cn_topic_0046736741_p2640866"></a>tomcat</p>
<p id="p44392495142912"><a name="p44392495142912"></a><a name="p44392495142912"></a></p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p12583597"><a name="zh-cn_topic_0046736741_p12583597"></a><a name="zh-cn_topic_0046736741_p12583597"></a>cas.log，localhost_access_cas_log.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p12638412"><a name="zh-cn_topic_0046736741_p12638412"></a><a name="zh-cn_topic_0046736741_p12638412"></a>cas运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row46636847"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p19488232"><a name="zh-cn_topic_0046736741_p19488232"></a><a name="zh-cn_topic_0046736741_p19488232"></a>catalina.log，catalina.out，host-manager.log，localhost.log，manager.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p35042921"><a name="zh-cn_topic_0046736741_p35042921"></a><a name="zh-cn_topic_0046736741_p35042921"></a>tomcat运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row46950836"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p44921397"><a name="zh-cn_topic_0046736741_p44921397"></a><a name="zh-cn_topic_0046736741_p44921397"></a>localhost_access_web_log.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p14754579"><a name="zh-cn_topic_0046736741_p14754579"></a><a name="zh-cn_topic_0046736741_p14754579"></a>记录访问FusionInsight Manager系统REST接口的日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row65682352"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p18670308"><a name="zh-cn_topic_0046736741_p18670308"></a><a name="zh-cn_topic_0046736741_p18670308"></a>web.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p35899943"><a name="zh-cn_topic_0046736741_p35899943"></a><a name="zh-cn_topic_0046736741_p35899943"></a>web进程运行日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row54664039"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p65711047"><a name="zh-cn_topic_0046736741_p65711047"></a><a name="zh-cn_topic_0046736741_p65711047"></a>northbound_ftp_sftp.log，snmp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p20994571"><a name="zh-cn_topic_0046736741_p20994571"></a><a name="zh-cn_topic_0046736741_p20994571"></a>北向日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row57621698"><td class="cellrowborder" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p36845993"><a name="zh-cn_topic_0046736741_p36845993"></a><a name="zh-cn_topic_0046736741_p36845993"></a>watchdog</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p31735419"><a name="zh-cn_topic_0046736741_p31735419"></a><a name="zh-cn_topic_0046736741_p31735419"></a>watchdog.log，feed_watchdog.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p20432162"><a name="zh-cn_topic_0046736741_p20432162"></a><a name="zh-cn_topic_0046736741_p20432162"></a>watchdog.log运行日志</p>
</td>
</tr>
<tr id="row57476204163118"><td class="cellrowborder" rowspan="13" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="p13837878163131"><a name="p13837878163131"></a><a name="p13837878163131"></a>patch</p>
<p id="p54324817175730"><a name="p54324817175730"></a><a name="p54324817175730"></a></p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="p50171400163118"><a name="p50171400163118"></a><a name="p50171400163118"></a>oms_installPatch.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p904418163118"><a name="p904418163118"></a><a name="p904418163118"></a>OMS补丁安装日志</p>
</td>
</tr>
<tr id="row26752416163124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p32417940163124"><a name="p32417940163124"></a><a name="p32417940163124"></a>agent_installPatch.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p45899290163124"><a name="p45899290163124"></a><a name="p45899290163124"></a>Agent补丁安装日志</p>
</td>
</tr>
<tr id="row43220101175346"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p32133401175346"><a name="p32133401175346"></a><a name="p32133401175346"></a>agent_uninstallPatch.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p52668688175346"><a name="p52668688175346"></a><a name="p52668688175346"></a>agent补丁卸载日志</p>
</td>
</tr>
<tr id="row47201177175351"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p46630067175351"><a name="p46630067175351"></a><a name="p46630067175351"></a>NODE_AGENT_restoreFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18939064175351"><a name="p18939064175351"></a><a name="p18939064175351"></a>agent补丁恢复文件日志</p>
</td>
</tr>
<tr id="row66659669175356"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5621838175356"><a name="p5621838175356"></a><a name="p5621838175356"></a>NODE_AGENT_updateFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p52715762175356"><a name="p52715762175356"></a><a name="p52715762175356"></a>agent补丁更新文件日志</p>
</td>
</tr>
<tr id="row3339908217540"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2093636217540"><a name="p2093636217540"></a><a name="p2093636217540"></a>OMA_restoreFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1812375117540"><a name="p1812375117540"></a><a name="p1812375117540"></a>OMA补丁恢复文件日志</p>
</td>
</tr>
<tr id="row62323302183510"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15022702183510"><a name="p15022702183510"></a><a name="p15022702183510"></a>OMA_updateFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8879363183510"><a name="p8879363183510"></a><a name="p8879363183510"></a>OMA补丁更新文件日志</p>
</td>
</tr>
<tr id="row27909216175512"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p39388169175512"><a name="p39388169175512"></a><a name="p39388169175512"></a>CONTROLLER_restoreFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p36325143175512"><a name="p36325143175512"></a><a name="p36325143175512"></a>CONTROLLER补丁恢复文件日志</p>
</td>
</tr>
<tr id="row51469382175516"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p65920735175516"><a name="p65920735175516"></a><a name="p65920735175516"></a>CONTROLLER_updateFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p37979347175516"><a name="p37979347175516"></a><a name="p37979347175516"></a>CONTROLLER补丁更新文件日志</p>
</td>
</tr>
<tr id="row36484699175559"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p65906151175559"><a name="p65906151175559"></a><a name="p65906151175559"></a>OMS_restoreFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p36797981175559"><a name="p36797981175559"></a><a name="p36797981175559"></a>OMS补丁恢复文件日志</p>
</td>
</tr>
<tr id="row6198352317563"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6129277017563"><a name="p6129277017563"></a><a name="p6129277017563"></a>oms_uninstallPatch.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6576734817563"><a name="p6576734817563"></a><a name="p6576734817563"></a>OMS补丁卸载日志</p>
</td>
</tr>
<tr id="row968891717567"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1689249717567"><a name="p1689249717567"></a><a name="p1689249717567"></a>OMS_updateFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2611498917567"><a name="p2611498917567"></a><a name="p2611498917567"></a>OMS补丁更新文件日志</p>
</td>
</tr>
<tr id="row29668334175730"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p38234094175730"><a name="p38234094175730"></a><a name="p38234094175730"></a>createStackConf.log，decompress.log，decompress_OMS.log ，distrExtractPatchOnOMS.log，slimReduction.log，switch_adapter.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p9953899175730"><a name="p9953899175730"></a><a name="p9953899175730"></a>补丁安装日志</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row12969758"><td class="cellrowborder" valign="top" width="33.07330733073307%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0046736741_p43917482"><a name="zh-cn_topic_0046736741_p43917482"></a><a name="zh-cn_topic_0046736741_p43917482"></a>sudo</p>
</td>
<td class="cellrowborder" valign="top" width="34.603460346034595%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0046736741_p546286"><a name="zh-cn_topic_0046736741_p546286"></a><a name="zh-cn_topic_0046736741_p546286"></a>sudo.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0046736741_p44249235"><a name="zh-cn_topic_0046736741_p44249235"></a><a name="zh-cn_topic_0046736741_p44249235"></a>sudo脚本执行日志</p>
</td>
</tr>
</tbody>
</table>

## 日志级别<a name="section128471159072"></a>

Manager中提供了如[表2](#tce0bb52db5fc4d53a43987beff277cb7)所示的日志级别。日志级别优先级从高到低分别是FATAL、ERROR、WARN、INFO、DEBUG。程序会打印高于或等于所设置级别的日志，设置的日志等级越高，打印出来的日志就越少。

**表 2**  日志级别

<a name="tce0bb52db5fc4d53a43987beff277cb7"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046736741_row47207275"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0046736741_p65692955"><a name="zh-cn_topic_0046736741_p65692955"></a><a name="zh-cn_topic_0046736741_p65692955"></a><strong id="zh-cn_topic_0046736741_b54365689"><a name="zh-cn_topic_0046736741_b54365689"></a><a name="zh-cn_topic_0046736741_b54365689"></a>级别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0046736741_p41544677"><a name="zh-cn_topic_0046736741_p41544677"></a><a name="zh-cn_topic_0046736741_p41544677"></a><strong id="zh-cn_topic_0046736741_b38357773"><a name="zh-cn_topic_0046736741_b38357773"></a><a name="zh-cn_topic_0046736741_b38357773"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046736741_row19971870"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p7108768"><a name="zh-cn_topic_0046736741_p7108768"></a><a name="zh-cn_topic_0046736741_p7108768"></a>FATAL</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p38939322"><a name="zh-cn_topic_0046736741_p38939322"></a><a name="zh-cn_topic_0046736741_p38939322"></a>FATAL表示当前事件处理出现严重错误信息，可能导致系统崩溃。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row14909584"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p66825666"><a name="zh-cn_topic_0046736741_p66825666"></a><a name="zh-cn_topic_0046736741_p66825666"></a>ERROR</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p44169889"><a name="zh-cn_topic_0046736741_p44169889"></a><a name="zh-cn_topic_0046736741_p44169889"></a>ERROR表示当前事件处理出现错误信息，系统运行出错。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row61984684"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p54703545"><a name="zh-cn_topic_0046736741_p54703545"></a><a name="zh-cn_topic_0046736741_p54703545"></a>WARN</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p1802150"><a name="zh-cn_topic_0046736741_p1802150"></a><a name="zh-cn_topic_0046736741_p1802150"></a>WARN表示当前事件处理存在异常信息，但认为是正常范围，不会导致系统出错。</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row16219352"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p38699129"><a name="zh-cn_topic_0046736741_p38699129"></a><a name="zh-cn_topic_0046736741_p38699129"></a>INFO</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p47621710"><a name="zh-cn_topic_0046736741_p47621710"></a><a name="zh-cn_topic_0046736741_p47621710"></a>INFO表示记录系统及各事件正常运行状态信息</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row25942207"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p20944062"><a name="zh-cn_topic_0046736741_p20944062"></a><a name="zh-cn_topic_0046736741_p20944062"></a>DEBUG</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p18747494"><a name="zh-cn_topic_0046736741_p18747494"></a><a name="zh-cn_topic_0046736741_p18747494"></a>DEBUG表示记录系统及系统的调试信息。</p>
</td>
</tr>
</tbody>
</table>

## 日志格式<a name="s4b62a749ccb842f7a27cda0c50bd620f"></a>

Manager的日志格式如下所示：

**表 3**  日志格式

<a name="zh-cn_topic_0046736741_table65514185"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046736741_row34287870"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0046736741_p25854119"><a name="zh-cn_topic_0046736741_p25854119"></a><a name="zh-cn_topic_0046736741_p25854119"></a><strong id="zh-cn_topic_0046736741_b31360484"><a name="zh-cn_topic_0046736741_b31360484"></a><a name="zh-cn_topic_0046736741_b31360484"></a>日志类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0046736741_p57171242"><a name="zh-cn_topic_0046736741_p57171242"></a><a name="zh-cn_topic_0046736741_p57171242"></a><strong id="zh-cn_topic_0046736741_b44779134"><a name="zh-cn_topic_0046736741_b44779134"></a><a name="zh-cn_topic_0046736741_b44779134"></a>组件</strong></p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0046736741_p3231228"><a name="zh-cn_topic_0046736741_p3231228"></a><a name="zh-cn_topic_0046736741_p3231228"></a><strong id="zh-cn_topic_0046736741_b29081056"><a name="zh-cn_topic_0046736741_b29081056"></a><a name="zh-cn_topic_0046736741_b29081056"></a>格式</strong></p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0046736741_p6755360"><a name="zh-cn_topic_0046736741_p6755360"></a><a name="zh-cn_topic_0046736741_p6755360"></a><strong id="zh-cn_topic_0046736741_b60798246"><a name="zh-cn_topic_0046736741_b60798246"></a><a name="zh-cn_topic_0046736741_b60798246"></a>示例</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046736741_row25710882"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0046736741_p2206658"><a name="zh-cn_topic_0046736741_p2206658"></a><a name="zh-cn_topic_0046736741_p2206658"></a>Controller，Httpd，logman，NodeAgent，okerberos，oldapserver，omm，tomcat，upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0046736741_p44521582"><a name="zh-cn_topic_0046736741_p44521582"></a><a name="zh-cn_topic_0046736741_p44521582"></a>Controller，Httpd，logman，NodeAgent，okerberos，oldapserver，omm，tomcat，upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0046736741_p49478415"><a name="zh-cn_topic_0046736741_p49478415"></a><a name="zh-cn_topic_0046736741_p49478415"></a>&lt;yyyy-MM-dd HH:mm:ss,SSS&gt;|&lt;Log Level&gt;|&lt;产生该日志的线程名字&gt;|&lt;log中的message&gt;|&lt;日志事件的发生位置&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0046736741_p48328717"><a name="zh-cn_topic_0046736741_p48328717"></a><a name="zh-cn_topic_0046736741_p48328717"></a>2015-06-30 00:37:09,067 INFO [pool-1-thread-1] Completed Discovering Node. com.huawei.hadoop.om.controller.tasks.nodesetup.DiscoverNodeTask.execute(DiscoverNodeTask.java:299)</p>
</td>
</tr>
</tbody>
</table>

