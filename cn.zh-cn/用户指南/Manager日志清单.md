# Manager日志清单<a name="admin_guide_000194"></a>

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
-   watchdog：/var/log/Bigdata/watchdog（watchdog日志）
-   upgrade：/var/log/Bigdata/upgrade（升级OMS日志）
-   UpdateService：/var/log/Bigdata/update-service（升级服务日志）
-   Sudo：/var/log/Bigdata/sudo（sudo脚本执行日志）
-   OS：/var/log/_message文件_（OS系统日志）
-   OS Performance：/var/log/osperf（OS性能统计日志）
-   OS Statistics：/var/log/osinfo/statistics（OS参数配置信息日志）

**日志归档规则**：

Manager的日志启动了自动压缩归档功能，缺省情况下，当日志大小超过10MB的时候，会自动压缩，压缩后的日志文件名规则为：“<原有日志名\>-<yyyy-mm-dd\_hh-mm-ss\>.\[编号\].log.zip”。最多保留最近的20个压缩文件。

**表 1**  Manager日志列表

<a name="table1181918461127"></a>
<table><thead align="left"><tr id="row88191846191219"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p1819346161216"><a name="p1819346161216"></a><a name="p1819346161216"></a><strong id="b28195461121"><a name="b28195461121"></a><a name="b28195461121"></a>日志类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="34.34343434343434%" id="mcps1.2.4.1.2"><p id="p1781934661212"><a name="p1781934661212"></a><a name="p1781934661212"></a><strong id="b178191146121219"><a name="b178191146121219"></a><a name="b178191146121219"></a>日志文件名</strong></p>
</th>
<th class="cellrowborder" valign="top" width="32.32323232323232%" id="mcps1.2.4.1.3"><p id="p16819346131212"><a name="p16819346131212"></a><a name="p16819346131212"></a><strong id="b1881994631212"><a name="b1881994631212"></a><a name="b1881994631212"></a>描述</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="row58201946121210"><td class="cellrowborder" rowspan="32" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p14820104691215"><a name="p14820104691215"></a><a name="p14820104691215"></a>Controller运行日志</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p682074611123"><a name="p682074611123"></a><a name="p682074611123"></a>controller.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p18201546121213"><a name="p18201546121213"></a><a name="p18201546121213"></a>记录组件安装、升级、配置、监控、告警和日常运维操作日志。</p>
</td>
</tr>
<tr id="row19820104671218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p148201846151214"><a name="p148201846151214"></a><a name="p148201846151214"></a>controller_client.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p482064610126"><a name="p482064610126"></a><a name="p482064610126"></a>Rest接口运行日志。</p>
</td>
</tr>
<tr id="row482024651216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p148201146161220"><a name="p148201146161220"></a><a name="p148201146161220"></a>acs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p182004611128"><a name="p182004611128"></a><a name="p182004611128"></a>Acs运行日志。</p>
</td>
</tr>
<tr id="row7820104611122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p208201346181211"><a name="p208201346181211"></a><a name="p208201346181211"></a>acs_spnego.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p582064618120"><a name="p582064618120"></a><a name="p582064618120"></a>acs中spnego用户日志</p>
</td>
</tr>
<tr id="row1982094631210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1682034631213"><a name="p1682034631213"></a><a name="p1682034631213"></a>aos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16820204671211"><a name="p16820204671211"></a><a name="p16820204671211"></a>Aos运行日志。</p>
</td>
</tr>
<tr id="row10820184617126"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p158204468129"><a name="p158204468129"></a><a name="p158204468129"></a>plugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15820946121213"><a name="p15820946121213"></a><a name="p15820946121213"></a>Aos插件日志</p>
</td>
</tr>
<tr id="row15820164651214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p982084618120"><a name="p982084618120"></a><a name="p982084618120"></a>backupplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1582016467127"><a name="p1582016467127"></a><a name="p1582016467127"></a>备份恢复进程运行日志</p>
</td>
</tr>
<tr id="row1882010460127"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p482074651218"><a name="p482074651218"></a><a name="p482074651218"></a>controller_config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16820144611123"><a name="p16820144611123"></a><a name="p16820144611123"></a>配置运行日志</p>
</td>
</tr>
<tr id="row1682034619129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p382094611121"><a name="p382094611121"></a><a name="p382094611121"></a>controller_nodesetup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8820184618121"><a name="p8820184618121"></a><a name="p8820184618121"></a>Controller加载任务日志</p>
</td>
</tr>
<tr id="row7820646171217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p38201946191210"><a name="p38201946191210"></a><a name="p38201946191210"></a>controller_root.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p38201846121219"><a name="p38201846121219"></a><a name="p38201846121219"></a>Controller进程系统日志</p>
</td>
</tr>
<tr id="row148201246181219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p11820144620124"><a name="p11820144620124"></a><a name="p11820144620124"></a>controller_trace.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p168207467129"><a name="p168207467129"></a><a name="p168207467129"></a>Controller与NodeAgent之间RPC通信日志</p>
</td>
</tr>
<tr id="row782015461126"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1982174610128"><a name="p1982174610128"></a><a name="p1982174610128"></a>controller_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10821846121218"><a name="p10821846121218"></a><a name="p10821846121218"></a>监控日志</p>
</td>
</tr>
<tr id="row1782113468123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p7821646121217"><a name="p7821646121217"></a><a name="p7821646121217"></a>controller_fsm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19821174661219"><a name="p19821174661219"></a><a name="p19821174661219"></a>状态机日志</p>
</td>
</tr>
<tr id="row168213464122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8821104601214"><a name="p8821104601214"></a><a name="p8821104601214"></a>controller_alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p68211946161220"><a name="p68211946161220"></a><a name="p68211946161220"></a>Controller发送告警日志</p>
</td>
</tr>
<tr id="row7821124610125"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4821194616129"><a name="p4821194616129"></a><a name="p4821194616129"></a>controller_backup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8821164601216"><a name="p8821164601216"></a><a name="p8821164601216"></a>Controller备份恢复日志</p>
</td>
</tr>
<tr id="row2821134621219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12821546191212"><a name="p12821546191212"></a><a name="p12821546191212"></a>install.log，restore_package.log，installPack.log，distributeAdapterFiles.log，install_os_optimization.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p982118465128"><a name="p982118465128"></a><a name="p982118465128"></a>oms安装日志</p>
</td>
</tr>
<tr id="row15821134611217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p178219464122"><a name="p178219464122"></a><a name="p178219464122"></a>oms_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16821746161216"><a name="p16821746161216"></a><a name="p16821746161216"></a>oms启停日志</p>
</td>
</tr>
<tr id="row3821114631212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6821946101216"><a name="p6821946101216"></a><a name="p6821946101216"></a>preInstall_client.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p882114691218"><a name="p882114691218"></a><a name="p882114691218"></a>客户端安装前预处理日志</p>
</td>
</tr>
<tr id="row2821746151219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1582164661211"><a name="p1582164661211"></a><a name="p1582164661211"></a>installntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p78214463122"><a name="p78214463122"></a><a name="p78214463122"></a>ntp安装日志</p>
</td>
</tr>
<tr id="row3821134617122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p382174621211"><a name="p382174621211"></a><a name="p382174621211"></a>modify_manager_param.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p682184681213"><a name="p682184681213"></a><a name="p682184681213"></a>修改Manager参数日志</p>
</td>
</tr>
<tr id="row1682113464123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1821194681211"><a name="p1821194681211"></a><a name="p1821194681211"></a>backup.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p188211746101216"><a name="p188211746101216"></a><a name="p188211746101216"></a>OMS备份脚本运行日志</p>
</td>
</tr>
<tr id="row1382134615121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1821184651212"><a name="p1821184651212"></a><a name="p1821184651212"></a>supressionAlarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p0821746151219"><a name="p0821746151219"></a><a name="p0821746151219"></a>告警脚本运行日志</p>
</td>
</tr>
<tr id="row882174611121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1821746111213"><a name="p1821746111213"></a><a name="p1821746111213"></a>om.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p98211464129"><a name="p98211464129"></a><a name="p98211464129"></a>生成om证书日志</p>
</td>
</tr>
<tr id="row1182184614121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p58221646181210"><a name="p58221646181210"></a><a name="p58221646181210"></a>backupplugin_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16822134631211"><a name="p16822134631211"></a><a name="p16822134631211"></a>备份恢复插件进程启动日志</p>
</td>
</tr>
<tr id="row1082284651210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15822646171210"><a name="p15822646171210"></a><a name="p15822646171210"></a>getLogs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p68223467123"><a name="p68223467123"></a><a name="p68223467123"></a>采集日志脚本运行日志</p>
</td>
</tr>
<tr id="row98221646111216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2082254611127"><a name="p2082254611127"></a><a name="p2082254611127"></a>backupAuditLogs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p682219460122"><a name="p682219460122"></a><a name="p682219460122"></a>审计日志备份脚本运行日志</p>
</td>
</tr>
<tr id="row48221146121212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1982274617122"><a name="p1982274617122"></a><a name="p1982274617122"></a>certStatus.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14822144612128"><a name="p14822144612128"></a><a name="p14822144612128"></a>证书定期检查日志</p>
</td>
</tr>
<tr id="row18822204616121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2822154681211"><a name="p2822154681211"></a><a name="p2822154681211"></a>distribute.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p198221464120"><a name="p198221464120"></a><a name="p198221464120"></a>证书分发日志</p>
</td>
</tr>
<tr id="row118221469127"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6822446131218"><a name="p6822446131218"></a><a name="p6822446131218"></a>ficertgenetrate.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19822346111218"><a name="p19822346111218"></a><a name="p19822346111218"></a>证书替换日志，包括生成二级证书、cas证书、httpd证书的日志。</p>
</td>
</tr>
<tr id="row128227465124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1082274641216"><a name="p1082274641216"></a><a name="p1082274641216"></a>genPwFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p148229467128"><a name="p148229467128"></a><a name="p148229467128"></a>生成证书密码文件日志</p>
</td>
</tr>
<tr id="row9822134691219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p88221846191214"><a name="p88221846191214"></a><a name="p88221846191214"></a>modifyproxyconf.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1082254661215"><a name="p1082254661215"></a><a name="p1082254661215"></a>修改HTTPD代理配置的日志</p>
</td>
</tr>
<tr id="row6822114612128"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p38221546141211"><a name="p38221546141211"></a><a name="p38221546141211"></a>importTar.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19822134651219"><a name="p19822134651219"></a><a name="p19822134651219"></a>证书导入信任库日志</p>
</td>
</tr>
<tr id="row158226468123"><td class="cellrowborder" rowspan="2" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1782284616123"><a name="p1782284616123"></a><a name="p1782284616123"></a>Httpd</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p682234621217"><a name="p682234621217"></a><a name="p682234621217"></a>install.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p1882214616126"><a name="p1882214616126"></a><a name="p1882214616126"></a>Httpd安装日志</p>
</td>
</tr>
<tr id="row08221946141212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p882294619129"><a name="p882294619129"></a><a name="p882294619129"></a>access_log, error_log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p10822446101212"><a name="p10822446101212"></a><a name="p10822446101212"></a>Httpd运行日志</p>
</td>
</tr>
<tr id="row98231446131210"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p11823104611215"><a name="p11823104611215"></a><a name="p11823104611215"></a>logman</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p5823946141212"><a name="p5823946141212"></a><a name="p5823946141212"></a>logman.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p1582324661219"><a name="p1582324661219"></a><a name="p1582324661219"></a>日志打包工具日志。</p>
</td>
</tr>
<tr id="row19823104614128"><td class="cellrowborder" rowspan="23" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p14823154671219"><a name="p14823154671219"></a><a name="p14823154671219"></a>NodeAgent</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p382310466121"><a name="p382310466121"></a><a name="p382310466121"></a>install.log，install_os_optimization.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p108232464126"><a name="p108232464126"></a><a name="p108232464126"></a>NodeAgent安装日志</p>
</td>
</tr>
<tr id="row1082316467124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p58237465124"><a name="p58237465124"></a><a name="p58237465124"></a>installntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p982394671210"><a name="p982394671210"></a><a name="p982394671210"></a>ntp安装日志</p>
</td>
</tr>
<tr id="row9823184615123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p19823164614129"><a name="p19823164614129"></a><a name="p19823164614129"></a>start_ntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p12823184691215"><a name="p12823184691215"></a><a name="p12823184691215"></a>ntp启动日志</p>
</td>
</tr>
<tr id="row382394612129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4823174661210"><a name="p4823174661210"></a><a name="p4823174661210"></a>ntpChecker.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1823154671217"><a name="p1823154671217"></a><a name="p1823154671217"></a>ntp检查日志</p>
</td>
</tr>
<tr id="row582318460121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p178230467123"><a name="p178230467123"></a><a name="p178230467123"></a>ntpMonitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p582394611124"><a name="p582394611124"></a><a name="p582394611124"></a>ntp监控日志</p>
</td>
</tr>
<tr id="row1982364661219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1782304641211"><a name="p1782304641211"></a><a name="p1782304641211"></a>heartbeat_trace.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1823134620125"><a name="p1823134620125"></a><a name="p1823134620125"></a>NodeAgent与Controller心跳日志</p>
</td>
</tr>
<tr id="row1682344651211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1482354621217"><a name="p1482354621217"></a><a name="p1482354621217"></a>alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18823846191217"><a name="p18823846191217"></a><a name="p18823846191217"></a>告警日志</p>
</td>
</tr>
<tr id="row482344610121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4823144612128"><a name="p4823144612128"></a><a name="p4823144612128"></a>monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p88243463127"><a name="p88243463127"></a><a name="p88243463127"></a>监控日志</p>
</td>
</tr>
<tr id="row2824144613124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4824546121216"><a name="p4824546121216"></a><a name="p4824546121216"></a>nodeagent_ctl.log，start-agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p208249462129"><a name="p208249462129"></a><a name="p208249462129"></a>NodeAgent启动日志</p>
</td>
</tr>
<tr id="row78241646191215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p782434610126"><a name="p782434610126"></a><a name="p782434610126"></a>agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18824246141216"><a name="p18824246141216"></a><a name="p18824246141216"></a>NodeAgent运行日志</p>
</td>
</tr>
<tr id="row1482434618123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p582464641210"><a name="p582464641210"></a><a name="p582464641210"></a>cert.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17824204611216"><a name="p17824204611216"></a><a name="p17824204611216"></a>证书日志</p>
</td>
</tr>
<tr id="row1582474614124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p28241946191215"><a name="p28241946191215"></a><a name="p28241946191215"></a>agentplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p28241546111218"><a name="p28241546111218"></a><a name="p28241546111218"></a>监控agent侧插件运行日志</p>
</td>
</tr>
<tr id="row382444615129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p17824114691213"><a name="p17824114691213"></a><a name="p17824114691213"></a>omaplugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p082424681219"><a name="p082424681219"></a><a name="p082424681219"></a>OMA插件运行日志</p>
</td>
</tr>
<tr id="row13824104610122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p982414465123"><a name="p982414465123"></a><a name="p982414465123"></a>diskhealth.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14824114611216"><a name="p14824114611216"></a><a name="p14824114611216"></a>磁盘健康检查日志</p>
</td>
</tr>
<tr id="row148241646101210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13824114691218"><a name="p13824114691218"></a><a name="p13824114691218"></a>supressionAlarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p782494611125"><a name="p782494611125"></a><a name="p782494611125"></a>告警脚本运行日志</p>
</td>
</tr>
<tr id="row38241646151215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p138241946141215"><a name="p138241946141215"></a><a name="p138241946141215"></a>updateHostFile.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18241446141216"><a name="p18241446141216"></a><a name="p18241446141216"></a>更新主机列表日志</p>
</td>
</tr>
<tr id="row5824446161216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12825646131216"><a name="p12825646131216"></a><a name="p12825646131216"></a>collectLog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14825164631217"><a name="p14825164631217"></a><a name="p14825164631217"></a>节点日志采集脚本运行日志</p>
</td>
</tr>
<tr id="row982594671211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1682554611216"><a name="p1682554611216"></a><a name="p1682554611216"></a>host_metric_collect.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p482594641214"><a name="p482594641214"></a><a name="p482594641214"></a>主机指标采集运行日志</p>
</td>
</tr>
<tr id="row382594631217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4825154618120"><a name="p4825154618120"></a><a name="p4825154618120"></a>checkfileconfig.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p4825194618124"><a name="p4825194618124"></a><a name="p4825194618124"></a>文件权限配置检查运行日志</p>
</td>
</tr>
<tr id="row11825746191215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p98256461127"><a name="p98256461127"></a><a name="p98256461127"></a>entropycheck.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6825746191213"><a name="p6825746191213"></a><a name="p6825746191213"></a>熵值检查运行日志</p>
</td>
</tr>
<tr id="row5825146171212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p78259463124"><a name="p78259463124"></a><a name="p78259463124"></a>timer.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19825846161216"><a name="p19825846161216"></a><a name="p19825846161216"></a>节点定时调度日志</p>
</td>
</tr>
<tr id="row108258464125"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1182554616122"><a name="p1182554616122"></a><a name="p1182554616122"></a>pluginmonitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p168259461128"><a name="p168259461128"></a><a name="p168259461128"></a>组件监控插件日志</p>
</td>
</tr>
<tr id="row158251846151212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13825946101215"><a name="p13825946101215"></a><a name="p13825946101215"></a>agent_alarm_py.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p282513467129"><a name="p282513467129"></a><a name="p282513467129"></a>NodeAgent检查文件权限发送告警日志</p>
</td>
</tr>
<tr id="row1682511468128"><td class="cellrowborder" rowspan="11" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p16825146181213"><a name="p16825146181213"></a><a name="p16825146181213"></a>okerberos</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p17825246181220"><a name="p17825246181220"></a><a name="p17825246181220"></a>addRealm.log，modifyKerberosRealm.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p1382518465127"><a name="p1382518465127"></a><a name="p1382518465127"></a>切域日志</p>
</td>
</tr>
<tr id="row9825134641214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p168261146181215"><a name="p168261146181215"></a><a name="p168261146181215"></a>checkservice_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p13826146111217"><a name="p13826146111217"></a><a name="p13826146111217"></a>Okerberos健康检查日志</p>
</td>
</tr>
<tr id="row6826174614121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16826134612123"><a name="p16826134612123"></a><a name="p16826134612123"></a>genKeytab.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1682674641213"><a name="p1682674641213"></a><a name="p1682674641213"></a>生成keytab日志</p>
</td>
</tr>
<tr id="row14826846171214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13826646181214"><a name="p13826646181214"></a><a name="p13826646181214"></a>KerberosAdmin_genConfigDetail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p12826194651212"><a name="p12826194651212"></a><a name="p12826194651212"></a>启动kadmin进程时，生成kadmin.conf的运行日志</p>
</td>
</tr>
<tr id="row1882654641214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12826124619125"><a name="p12826124619125"></a><a name="p12826124619125"></a>KerberosServer_genConfigDetail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p188261946121213"><a name="p188261946121213"></a><a name="p188261946121213"></a>启动krb5kdc进程时，生成krb5kdc.conf的运行日志</p>
</td>
</tr>
<tr id="row18826646121215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p178261146121212"><a name="p178261146121212"></a><a name="p178261146121212"></a>oms-kadmind.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1182624661216"><a name="p1182624661216"></a><a name="p1182624661216"></a>kadmin进程的运行日志</p>
</td>
</tr>
<tr id="row188269469129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p10826184617120"><a name="p10826184617120"></a><a name="p10826184617120"></a>oms_kerberos_install.log，postinstall_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17826144631216"><a name="p17826144631216"></a><a name="p17826144631216"></a>okerberos安装日志</p>
</td>
</tr>
<tr id="row1682624611128"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p3826104691211"><a name="p3826104691211"></a><a name="p3826104691211"></a>oms-krb5kdc.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p138261246111216"><a name="p138261246111216"></a><a name="p138261246111216"></a>krbkdc运行日志</p>
</td>
</tr>
<tr id="row16826184661211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1782694614127"><a name="p1782694614127"></a><a name="p1782694614127"></a>start_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6827194611126"><a name="p6827194611126"></a><a name="p6827194611126"></a>okerberos启动日志</p>
</td>
</tr>
<tr id="row9827144671214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12827134611121"><a name="p12827134611121"></a><a name="p12827134611121"></a>realmDataConfigProcess.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1382720463128"><a name="p1382720463128"></a><a name="p1382720463128"></a>切域失败，回滚日志</p>
</td>
</tr>
<tr id="row178271146151211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p782794621220"><a name="p782794621220"></a><a name="p782794621220"></a>stop_detail.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p3827104620120"><a name="p3827104620120"></a><a name="p3827104620120"></a>okerberos停止日志</p>
</td>
</tr>
<tr id="row58271146141211"><td class="cellrowborder" rowspan="10" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p182774671211"><a name="p182774671211"></a><a name="p182774671211"></a>oldapserver</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p15827194691211"><a name="p15827194691211"></a><a name="p15827194691211"></a>ldapserver_backup.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p1827154661219"><a name="p1827154661219"></a><a name="p1827154661219"></a>Oldapserver备份日志</p>
</td>
</tr>
<tr id="row1382719468124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p168271246201214"><a name="p168271246201214"></a><a name="p168271246201214"></a>ldapserver_chk_service.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p78276468125"><a name="p78276468125"></a><a name="p78276468125"></a>Oldapserver健康检查日志</p>
</td>
</tr>
<tr id="row7827846101218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p118271846111214"><a name="p118271846111214"></a><a name="p118271846111214"></a>ldapserver_install.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p98276466123"><a name="p98276466123"></a><a name="p98276466123"></a>Oldapserver安装日志</p>
</td>
</tr>
<tr id="row118277468123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p168271146151217"><a name="p168271146151217"></a><a name="p168271146151217"></a>ldapserver_start.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p782774621218"><a name="p782774621218"></a><a name="p782774621218"></a>Oldapserver启动日志</p>
</td>
</tr>
<tr id="row14827346111216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18828164631218"><a name="p18828164631218"></a><a name="p18828164631218"></a>ldapserver_status.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p58285466120"><a name="p58285466120"></a><a name="p58285466120"></a>Oldapserver进程状态检查日志。</p>
</td>
</tr>
<tr id="row1782884613123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1682812463126"><a name="p1682812463126"></a><a name="p1682812463126"></a>ldapserver_stop.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p118281746181218"><a name="p118281746181218"></a><a name="p118281746181218"></a>Oldapserver停止日志</p>
</td>
</tr>
<tr id="row382818464123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p682884681215"><a name="p682884681215"></a><a name="p682884681215"></a>ldapserver_wrap.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1782824620123"><a name="p1782824620123"></a><a name="p1782824620123"></a>Oldapserver服务管理日志。</p>
</td>
</tr>
<tr id="row13828104631220"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1682844671218"><a name="p1682844671218"></a><a name="p1682844671218"></a>ldapserver_uninstall.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1982864612129"><a name="p1982864612129"></a><a name="p1982864612129"></a>Oldapserver卸载日志</p>
</td>
</tr>
<tr id="row1282824671218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p158287462121"><a name="p158287462121"></a><a name="p158287462121"></a>restart_service.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1182874610121"><a name="p1182874610121"></a><a name="p1182874610121"></a>Oldapserver重启日志</p>
</td>
</tr>
<tr id="row682844619127"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p882854612124"><a name="p882854612124"></a><a name="p882854612124"></a>ldapserver_unlockUser.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1482894631218"><a name="p1482894631218"></a><a name="p1482894631218"></a>记录解锁Ldap用户和管理帐户的日志</p>
</td>
</tr>
<tr id="row1382894681213"><td class="cellrowborder" rowspan="5" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p8828174612122"><a name="p8828174612122"></a><a name="p8828174612122"></a>metric_agent</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p16829164611212"><a name="p16829164611212"></a><a name="p16829164611212"></a>gc.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p208292465126"><a name="p208292465126"></a><a name="p208292465126"></a>MetricAgent JAVA虚拟机gc日志</p>
</td>
</tr>
<tr id="row16829194613128"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p118298468125"><a name="p118298468125"></a><a name="p118298468125"></a>metric_agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p98291746171218"><a name="p98291746171218"></a><a name="p98291746171218"></a>MetricAgent运行日志</p>
</td>
</tr>
<tr id="row9829144611217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p98291146161220"><a name="p98291146161220"></a><a name="p98291146161220"></a>metric_agent_qps.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1782944619123"><a name="p1782944619123"></a><a name="p1782944619123"></a>MetricAgent内部队列长度及qps信息记录日志</p>
</td>
</tr>
<tr id="row2829146181211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p382918462124"><a name="p382918462124"></a><a name="p382918462124"></a>metric_agent_root.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15829124691213"><a name="p15829124691213"></a><a name="p15829124691213"></a>MetricAgent所有运行日志</p>
</td>
</tr>
<tr id="row2829134619120"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2082944616126"><a name="p2082944616126"></a><a name="p2082944616126"></a>start.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p28291146101214"><a name="p28291146101214"></a><a name="p28291146101214"></a>MetricAgent启停信息日志</p>
</td>
</tr>
<tr id="row128292463129"><td class="cellrowborder" rowspan="48" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p982911464128"><a name="p982911464128"></a><a name="p982911464128"></a>omm</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p1082944614124"><a name="p1082944614124"></a><a name="p1082944614124"></a>omsconfig.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p12829184611121"><a name="p12829184611121"></a><a name="p12829184611121"></a>OMS配置日志</p>
</td>
</tr>
<tr id="row08299466128"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p19829144618121"><a name="p19829144618121"></a><a name="p19829144618121"></a>check_oms_heartbeat.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p118291846161219"><a name="p118291846161219"></a><a name="p118291846161219"></a>OMS心跳运行日志</p>
</td>
</tr>
<tr id="row108291465123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p14830184631214"><a name="p14830184631214"></a><a name="p14830184631214"></a>monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p78301646121211"><a name="p78301646121211"></a><a name="p78301646121211"></a>OMS监控日志</p>
</td>
</tr>
<tr id="row15830134671212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1830134616126"><a name="p1830134616126"></a><a name="p1830134616126"></a>ha_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p88301246151210"><a name="p88301246151210"></a><a name="p88301246151210"></a>HA_Monitor操作日志</p>
</td>
</tr>
<tr id="row14830194615124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16830346151211"><a name="p16830346151211"></a><a name="p16830346151211"></a>ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p783012465127"><a name="p783012465127"></a><a name="p783012465127"></a>HA操作日志</p>
</td>
</tr>
<tr id="row3830164681217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2083011466125"><a name="p2083011466125"></a><a name="p2083011466125"></a>fms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p9830164671210"><a name="p9830164671210"></a><a name="p9830164671210"></a>告警日志</p>
</td>
</tr>
<tr id="row383054601212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1183014681217"><a name="p1183014681217"></a><a name="p1183014681217"></a>fms_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2830946181210"><a name="p2830946181210"></a><a name="p2830946181210"></a>告警的HA监控日志</p>
</td>
</tr>
<tr id="row14830134631210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13830846141219"><a name="p13830846141219"></a><a name="p13830846141219"></a>fms_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1783054641211"><a name="p1783054641211"></a><a name="p1783054641211"></a>告警控制日志</p>
</td>
</tr>
<tr id="row28304466129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p11830164610122"><a name="p11830164610122"></a><a name="p11830164610122"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17830246111217"><a name="p17830246111217"></a><a name="p17830246111217"></a>告警配置日志</p>
</td>
</tr>
<tr id="row183064611212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p9830646131215"><a name="p9830646131215"></a><a name="p9830646131215"></a>iam.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p7831946101212"><a name="p7831946101212"></a><a name="p7831946101212"></a>IAM日志</p>
</td>
</tr>
<tr id="row1583118460129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1583113463127"><a name="p1583113463127"></a><a name="p1583113463127"></a>iam_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p583117465122"><a name="p583117465122"></a><a name="p583117465122"></a>IAM控制日志</p>
</td>
</tr>
<tr id="row28311946171212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6831146161216"><a name="p6831146161216"></a><a name="p6831146161216"></a>iam_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1983124661217"><a name="p1983124661217"></a><a name="p1983124661217"></a>IAM的HA监控日志</p>
</td>
</tr>
<tr id="row11831446151210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16831144651210"><a name="p16831144651210"></a><a name="p16831144651210"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p0831184671215"><a name="p0831184671215"></a><a name="p0831184671215"></a>IAM配置日志</p>
</td>
</tr>
<tr id="row08311346181213"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18831124641219"><a name="p18831124641219"></a><a name="p18831124641219"></a>operatelog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p11831184671212"><a name="p11831184671212"></a><a name="p11831184671212"></a>IAM操作日志</p>
</td>
</tr>
<tr id="row88311546141218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p683194612121"><a name="p683194612121"></a><a name="p683194612121"></a>heartbeatcheck_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p983194611126"><a name="p983194611126"></a><a name="p983194611126"></a>OMS心跳的HA监控日志</p>
</td>
</tr>
<tr id="row083111460126"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p14831646161219"><a name="p14831646161219"></a><a name="p14831646161219"></a>install_oms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p583154611124"><a name="p583154611124"></a><a name="p583154611124"></a>OMS安装日志</p>
</td>
</tr>
<tr id="row158311463127"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p168311246171211"><a name="p168311246171211"></a><a name="p168311246171211"></a>pms_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8831204641216"><a name="p8831204641216"></a><a name="p8831204641216"></a>监控的HA监控日志</p>
</td>
</tr>
<tr id="row383212468122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p383234631212"><a name="p383234631212"></a><a name="p383234631212"></a>pms_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1883218469127"><a name="p1883218469127"></a><a name="p1883218469127"></a>监控控制日志</p>
</td>
</tr>
<tr id="row1683204601214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p883218461129"><a name="p883218461129"></a><a name="p883218461129"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1083224621218"><a name="p1083224621218"></a><a name="p1083224621218"></a>监控配置日志</p>
</td>
</tr>
<tr id="row18832134614123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p183213469121"><a name="p183213469121"></a><a name="p183213469121"></a>plugin.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1083210461122"><a name="p1083210461122"></a><a name="p1083210461122"></a>监控插件运行日志</p>
</td>
</tr>
<tr id="row2083274610122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p683234617129"><a name="p683234617129"></a><a name="p683234617129"></a>pms.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1583234661213"><a name="p1583234661213"></a><a name="p1583234661213"></a>监控日志</p>
</td>
</tr>
<tr id="row783211464120"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p78321464122"><a name="p78321464122"></a><a name="p78321464122"></a>ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8832154611129"><a name="p8832154611129"></a><a name="p8832154611129"></a>HA运行日志</p>
</td>
</tr>
<tr id="row2832046131220"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1183219462125"><a name="p1183219462125"></a><a name="p1183219462125"></a>cep_ha.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p11832184613124"><a name="p11832184613124"></a><a name="p11832184613124"></a>CEP的HA监控日志</p>
</td>
</tr>
<tr id="row983219462124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2832114661212"><a name="p2832114661212"></a><a name="p2832114661212"></a>cep_script.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p983354617127"><a name="p983354617127"></a><a name="p983354617127"></a>CEP控制日志</p>
</td>
</tr>
<tr id="row983334671213"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2833046151217"><a name="p2833046151217"></a><a name="p2833046151217"></a>cep.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p183374641217"><a name="p183374641217"></a><a name="p183374641217"></a>CEP日志</p>
</td>
</tr>
<tr id="row6833104631219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p14833146121216"><a name="p14833146121216"></a><a name="p14833146121216"></a>config.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p083374616129"><a name="p083374616129"></a><a name="p083374616129"></a>CEP配置日志</p>
</td>
</tr>
<tr id="row148336462125"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p7833146121216"><a name="p7833146121216"></a><a name="p7833146121216"></a>omm_gaussdba.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p19833164618121"><a name="p19833164618121"></a><a name="p19833164618121"></a>gaussdb的HA监控日志</p>
</td>
</tr>
<tr id="row10833184661215"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1833164611129"><a name="p1833164611129"></a><a name="p1833164611129"></a>gaussdb-&lt;SERIAL&gt;.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p4833124611123"><a name="p4833124611123"></a><a name="p4833124611123"></a>gaussdb运行日志</p>
</td>
</tr>
<tr id="row1833154601213"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8833846181216"><a name="p8833846181216"></a><a name="p8833846181216"></a>gs_ctl-&lt;DATE&gt;.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p118330465125"><a name="p118330465125"></a><a name="p118330465125"></a>gaussdb控制日志的归档日志</p>
</td>
</tr>
<tr id="row2083364691212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p483314464122"><a name="p483314464122"></a><a name="p483314464122"></a>gs_ctl-current.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p783364611215"><a name="p783364611215"></a><a name="p783364611215"></a>gaussdb控制日志</p>
</td>
</tr>
<tr id="row188331146151216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5834104618122"><a name="p5834104618122"></a><a name="p5834104618122"></a>gs_guc-current.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1883419464125"><a name="p1883419464125"></a><a name="p1883419464125"></a>gaussdb操作日志</p>
</td>
</tr>
<tr id="row138341746171218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4834144610121"><a name="p4834144610121"></a><a name="p4834144610121"></a>encrypt.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18834246111216"><a name="p18834246111216"></a><a name="p18834246111216"></a>omm加密日志</p>
</td>
</tr>
<tr id="row68344468129"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p483404612120"><a name="p483404612120"></a><a name="p483404612120"></a>omm_agent_ctl.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p6834174612124"><a name="p6834174612124"></a><a name="p6834174612124"></a>OMA控制日志</p>
</td>
</tr>
<tr id="row20834746131217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13834164651217"><a name="p13834164651217"></a><a name="p13834164651217"></a>oma_monitor.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p7834646101213"><a name="p7834646101213"></a><a name="p7834646101213"></a>OMA监控日志</p>
</td>
</tr>
<tr id="row19834154618128"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1683454617127"><a name="p1683454617127"></a><a name="p1683454617127"></a>install_oma.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p483414620121"><a name="p483414620121"></a><a name="p483414620121"></a>OMA安装日志</p>
</td>
</tr>
<tr id="row3834134681218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1834184610122"><a name="p1834184610122"></a><a name="p1834184610122"></a>config_oma.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p5834144615129"><a name="p5834144615129"></a><a name="p5834144615129"></a>OMA配置日志</p>
</td>
</tr>
<tr id="row1983434611123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2083418464128"><a name="p2083418464128"></a><a name="p2083418464128"></a>omm_agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p208341646121216"><a name="p208341646121216"></a><a name="p208341646121216"></a>OMA运行日志</p>
</td>
</tr>
<tr id="row383444617122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p148354460122"><a name="p148354460122"></a><a name="p148354460122"></a>acs.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p883514611212"><a name="p883514611212"></a><a name="p883514611212"></a>acs资源日志。</p>
</td>
</tr>
<tr id="row138351946101210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1383564621219"><a name="p1383564621219"></a><a name="p1383564621219"></a>aos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p148354469123"><a name="p148354469123"></a><a name="p148354469123"></a>aos资源日志</p>
</td>
</tr>
<tr id="row083511460125"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6835114610121"><a name="p6835114610121"></a><a name="p6835114610121"></a>controller.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2835194671215"><a name="p2835194671215"></a><a name="p2835194671215"></a>controller资源日志</p>
</td>
</tr>
<tr id="row15835194641219"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p13835194691219"><a name="p13835194691219"></a><a name="p13835194691219"></a>feed_watchdog.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p78350468121"><a name="p78350468121"></a><a name="p78350468121"></a>feed_watchdog资源日志</p>
</td>
</tr>
<tr id="row5835204612121"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p178358468124"><a name="p178358468124"></a><a name="p178358468124"></a>floatip.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18351046161214"><a name="p18351046161214"></a><a name="p18351046161214"></a>floatip资源日志</p>
</td>
</tr>
<tr id="row1835164631211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8835164661219"><a name="p8835164661219"></a><a name="p8835164661219"></a>ha_ntp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p118351346141217"><a name="p118351346141217"></a><a name="p118351346141217"></a>ntp资源日志</p>
</td>
</tr>
<tr id="row198351646121214"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1683517465127"><a name="p1683517465127"></a><a name="p1683517465127"></a>httpd.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p148358466125"><a name="p148358466125"></a><a name="p148358466125"></a>httpd资源日志</p>
</td>
</tr>
<tr id="row16835124614123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6836104615124"><a name="p6836104615124"></a><a name="p6836104615124"></a>okerberos.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1583654614129"><a name="p1583654614129"></a><a name="p1583654614129"></a>okerberos资源日志</p>
</td>
</tr>
<tr id="row188361446151210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6836154619125"><a name="p6836154619125"></a><a name="p6836154619125"></a>oldap.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2836114691218"><a name="p2836114691218"></a><a name="p2836114691218"></a>oldap资源日志</p>
</td>
</tr>
<tr id="row3836104613122"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1836144641210"><a name="p1836144641210"></a><a name="p1836144641210"></a>tomcat.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1483664619124"><a name="p1483664619124"></a><a name="p1483664619124"></a>tomcat资源日志</p>
</td>
</tr>
<tr id="row383654612126"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15836194681219"><a name="p15836194681219"></a><a name="p15836194681219"></a>send_alarm.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1583616465128"><a name="p1583616465128"></a><a name="p1583616465128"></a>管理节点HA告警发送脚本运行日志</p>
</td>
</tr>
<tr id="row4836174615125"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p11836184616124"><a name="p11836184616124"></a><a name="p11836184616124"></a>timestamp</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p108361446171215"><a name="p108361446171215"></a><a name="p108361446171215"></a>restart_stamp</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p19836134613121"><a name="p19836134613121"></a><a name="p19836134613121"></a>NodeAgent启动时间</p>
</td>
</tr>
<tr id="row38361546181218"><td class="cellrowborder" rowspan="6" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p12836446111211"><a name="p12836446111211"></a><a name="p12836446111211"></a>tomcat</p>
<p id="p1783613466122"><a name="p1783613466122"></a><a name="p1783613466122"></a></p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p3837174661215"><a name="p3837174661215"></a><a name="p3837174661215"></a>cas.log，localhost_access_cas_log.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p78371646101216"><a name="p78371646101216"></a><a name="p78371646101216"></a>cas运行日志</p>
</td>
</tr>
<tr id="row883744610123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p983764610123"><a name="p983764610123"></a><a name="p983764610123"></a>catalina.log，catalina.out，host-manager.log，localhost.log，manager.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p683704612121"><a name="p683704612121"></a><a name="p683704612121"></a>tomcat运行日志</p>
</td>
</tr>
<tr id="row883724641218"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p118378460124"><a name="p118378460124"></a><a name="p118378460124"></a>localhost_access_web_log.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1683715468121"><a name="p1683715468121"></a><a name="p1683715468121"></a>记录访问FusionInsight Manager系统REST接口的日志</p>
</td>
</tr>
<tr id="row1283784691211"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12837194661213"><a name="p12837194661213"></a><a name="p12837194661213"></a>web.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17837104614128"><a name="p17837104614128"></a><a name="p17837104614128"></a>web进程运行日志</p>
</td>
</tr>
<tr id="row98371746161217"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1983724613129"><a name="p1983724613129"></a><a name="p1983724613129"></a>northbound_ftp_sftp.log，snmp.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p183754619127"><a name="p183754619127"></a><a name="p183754619127"></a>北向日志</p>
</td>
</tr>
<tr id="row16837154618123"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5837746131213"><a name="p5837746131213"></a><a name="p5837746131213"></a>perfStats.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p3837204651220"><a name="p3837204651220"></a><a name="p3837204651220"></a>性能数据统计日志</p>
</td>
</tr>
<tr id="row1283854614122"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p108381946121218"><a name="p108381946121218"></a><a name="p108381946121218"></a>watchdog</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p10838174691220"><a name="p10838174691220"></a><a name="p10838174691220"></a>watchdog.log，feed_watchdog.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p48381246131218"><a name="p48381246131218"></a><a name="p48381246131218"></a>watchdog.log运行日志</p>
</td>
</tr>
<tr id="row12838546181217"><td class="cellrowborder" rowspan="6" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p128381746101211"><a name="p128381746101211"></a><a name="p128381746101211"></a>update-service</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p68384467129"><a name="p68384467129"></a><a name="p68384467129"></a>omm_upd_server.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p138381546111216"><a name="p138381546111216"></a><a name="p138381546111216"></a>updserver的运行日志</p>
</td>
</tr>
<tr id="row1183811464127"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p68382464122"><a name="p68382464122"></a><a name="p68382464122"></a>omm_upd_agent.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p383884671215"><a name="p383884671215"></a><a name="p383884671215"></a>updagent的运行日志</p>
</td>
</tr>
<tr id="row16838946121212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1683884617128"><a name="p1683884617128"></a><a name="p1683884617128"></a>update-manager.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p13838104616126"><a name="p13838104616126"></a><a name="p13838104616126"></a>updmanager的运行日志</p>
</td>
</tr>
<tr id="row1383814681212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p158391646131217"><a name="p158391646131217"></a><a name="p158391646131217"></a>install.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p7839144616127"><a name="p7839144616127"></a><a name="p7839144616127"></a>升级服务安装日志</p>
</td>
</tr>
<tr id="row0839746141210"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p158391646121211"><a name="p158391646121211"></a><a name="p158391646121211"></a>uninstall.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1083964617124"><a name="p1083964617124"></a><a name="p1083964617124"></a>升级服务卸载日志</p>
</td>
</tr>
<tr id="row18391746141212"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2839194610124"><a name="p2839194610124"></a><a name="p2839194610124"></a>catalina.&lt;时间&gt;.log，catalina.out，host-manager.&lt;时间&gt;.log，localhost.&lt;时间&gt;.log，manager.&lt;时间&gt;.log，manager_access_log.&lt;时间&gt;.txt，web_service_access_log.&lt;时间&gt;.txt，catalina.log，gc-update-service.log.0.current，update-manager.controller，update-web-service.controller，update-web-service.log，commit_rm_distributed.log ，commit_rm_upload_package.log，common_omagent_operator.log，forbid_monitor.log，initialize_package_atoms.log，initialize_unzip_pack.log，omm-upd.log，register_patch_pack.log，resume_monitor.logrollback_clear_patch.log，unregister_patch_pack.log，update-rcommupd.log，update-rcupdatemanager.log，update-service.log</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p98397463127"><a name="p98397463127"></a><a name="p98397463127"></a>升级服务运行日志</p>
</td>
</tr>
<tr id="row1783984681214"><td class="cellrowborder" rowspan="2" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p168395464129"><a name="p168395464129"></a><a name="p168395464129"></a>upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p128391446131213"><a name="p128391446131213"></a><a name="p128391446131213"></a>upgrade.log_&lt;时间&gt;</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p10839144661216"><a name="p10839144661216"></a><a name="p10839144661216"></a>升级OMS日志</p>
</td>
</tr>
<tr id="row118393460124"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p148392468125"><a name="p148392468125"></a><a name="p148392468125"></a>rollback.log_&lt;时间&gt;</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p38391046181217"><a name="p38391046181217"></a><a name="p38391046181217"></a>回滚OMS日志</p>
</td>
</tr>
<tr id="row78421467120"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1384219469122"><a name="p1384219469122"></a><a name="p1384219469122"></a>sudo</p>
</td>
<td class="cellrowborder" valign="top" width="34.34343434343434%" headers="mcps1.2.4.1.2 "><p id="p484224618128"><a name="p484224618128"></a><a name="p484224618128"></a>sudo.log</p>
</td>
<td class="cellrowborder" valign="top" width="32.32323232323232%" headers="mcps1.2.4.1.3 "><p id="p384214611220"><a name="p384214611220"></a><a name="p384214611220"></a>sudo脚本执行日志</p>
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
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p47621710"><a name="zh-cn_topic_0046736741_p47621710"></a><a name="zh-cn_topic_0046736741_p47621710"></a>INFO记录系统及各事件正常运行状态信息</p>
</td>
</tr>
<tr id="zh-cn_topic_0046736741_row25942207"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0046736741_p20944062"><a name="zh-cn_topic_0046736741_p20944062"></a><a name="zh-cn_topic_0046736741_p20944062"></a>DEBUG</p>
</td>
<td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0046736741_p18747494"><a name="zh-cn_topic_0046736741_p18747494"></a><a name="zh-cn_topic_0046736741_p18747494"></a>DEBUG记录系统及系统的调试信息。</p>
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
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0046736741_p48328717"><a name="zh-cn_topic_0046736741_p48328717"></a><a name="zh-cn_topic_0046736741_p48328717"></a>2020-06-30 00:37:09,067 INFO [pool-1-thread-1] Completed Discovering Node. com.xxx.hadoop.om.controller.tasks.nodesetup.DiscoverNodeTask.execute(DiscoverNodeTask.java:299)</p>
</td>
</tr>
</tbody>
</table>

