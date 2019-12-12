# 配置管理Flink<a name="ZH-CN_TOPIC_0176678779"></a>

## 配置参数路径<a name="section4819172518615"></a>

Flink所有的配置参数都需要在客户端侧进行配置，配置文件路径：“客户端安装路径/Flink/flink/conf/flink-conf.yaml”。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   建议用户直接修改客户端的“flink-conf.yaml”配置文件进行配置，YAML文件配置格式为**key: value**。  
>    例：**taskmanager.heap.mb: 512**  
>    注意配置项**key:**与**value**之间需有空格分隔。  
>-   如果在Flink的“服务配置”修改参数，配置完成之后需要重新下载安装客户端。  

## 配置JobManager & TaskManager<a name="section4452655171416"></a>

JobManager和TaskManager是Flink的主要组件，针对各种安全场景和性能场景，可以在客户端侧配置相关参数。

主要配置项包括通信端口，内存管理，连接重试等。

**表 1**  参数说明

<a name="table91792019191713"></a>
<table><thead align="left"><tr id="row91791919191719"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p5179111941713"><a name="p5179111941713"></a><a name="p5179111941713"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p101796192178"><a name="p101796192178"></a><a name="p101796192178"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p13179111951711"><a name="p13179111951711"></a><a name="p13179111951711"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p61791419191711"><a name="p61791419191711"></a><a name="p61791419191711"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row18179121931710"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p27068241192"><a name="p27068241192"></a><a name="p27068241192"></a>taskmanager.rpc.port</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p14805194821916"><a name="p14805194821916"></a><a name="p14805194821916"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p7931104141917"><a name="p7931104141917"></a><a name="p7931104141917"></a>默认值为32326-32390。</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p191319325196"><a name="p191319325196"></a><a name="p191319325196"></a>TaskManager上Akka system监听端口。</p>
</td>
</tr>
<tr id="row1318010197178"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p12707152413197"><a name="p12707152413197"></a><a name="p12707152413197"></a>taskmanager.data.port</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p08051848141916"><a name="p08051848141916"></a><a name="p08051848141916"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p6932124114198"><a name="p6932124114198"></a><a name="p6932124114198"></a>默认值为32391-32455。</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1013183214194"><a name="p1013183214194"></a><a name="p1013183214194"></a>TaskManager之间数据传输NettyServer的监听端口。</p>
</td>
</tr>
<tr id="row1518091921713"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4707324151912"><a name="p4707324151912"></a><a name="p4707324151912"></a>taskmanager.data.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p168057488199"><a name="p168057488199"></a><a name="p168057488199"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p793215413197"><a name="p793215413197"></a><a name="p793215413197"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p15131432131912"><a name="p15131432131912"></a><a name="p15131432131912"></a>TaskManager之间数据传输是否使用SSL加密，仅在全局开关security.ssl开启时有效。</p>
</td>
</tr>
<tr id="row1573125391914"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p183181422014"><a name="p183181422014"></a><a name="p183181422014"></a>taskmanager.numberOfTaskSlots</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1435613268202"><a name="p1435613268202"></a><a name="p1435613268202"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p13588161916209"><a name="p13588161916209"></a><a name="p13588161916209"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1642051219208"><a name="p1642051219208"></a><a name="p1642051219208"></a>TaskManager占用的slot数，一般配置成物理机的核数，yarn-session模式下只能使用-s参数传递，yarn-cluster模式下只能使用-ys参数传递。</p>
</td>
</tr>
<tr id="row989714536194"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4402174222019"><a name="p4402174222019"></a><a name="p4402174222019"></a>parallelism.default</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p192878302119"><a name="p192878302119"></a><a name="p192878302119"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1296485510203"><a name="p1296485510203"></a><a name="p1296485510203"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1658184920204"><a name="p1658184920204"></a><a name="p1658184920204"></a>Job各个算子运行的并发数。</p>
</td>
</tr>
<tr id="row642515491913"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p12402142162018"><a name="p12402142162018"></a><a name="p12402142162018"></a>taskmanager.memory.size</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p14287139218"><a name="p14287139218"></a><a name="p14287139218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p7964205582016"><a name="p7964205582016"></a><a name="p7964205582016"></a>0</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p14581204917204"><a name="p14581204917204"></a><a name="p14581204917204"></a>TaskManager在JVM堆内存中保留空间的大小，此内存用于排序，哈希表和中间状态的缓存。如果未指定，则会使用JVM堆内存乘以比例taskmanager.memory.fraction。单位：MB。</p>
</td>
</tr>
<tr id="row058545431917"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p11402114211204"><a name="p11402114211204"></a><a name="p11402114211204"></a>taskmanager.memory.fraction</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p328716372110"><a name="p328716372110"></a><a name="p328716372110"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p14964755192019"><a name="p14964755192019"></a><a name="p14964755192019"></a>0.7</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p17581134915204"><a name="p17581134915204"></a><a name="p17581134915204"></a>TaskManager在JVM堆内存中保留空间的比例，此内存用于排序，哈希表和中间状态的缓存。</p>
</td>
</tr>
<tr id="row1291515543199"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p340284282015"><a name="p340284282015"></a><a name="p340284282015"></a>taskmanager.memory.off-heap</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p228719313215"><a name="p228719313215"></a><a name="p228719313215"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p11964955192012"><a name="p11964955192012"></a><a name="p11964955192012"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p5581104992012"><a name="p5581104992012"></a><a name="p5581104992012"></a>TaskManager是否使用堆外内存，此内存用于排序，哈希表和中间状态的缓存。建议对于大内存，开启此配置提高内存操作的效率。</p>
</td>
</tr>
<tr id="row11180119121715"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1248825152110"><a name="p1248825152110"></a><a name="p1248825152110"></a>taskmanager.memory.segment-size</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p467918434213"><a name="p467918434213"></a><a name="p467918434213"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p8544123719210"><a name="p8544123719210"></a><a name="p8544123719210"></a>32768</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p128293116218"><a name="p128293116218"></a><a name="p128293116218"></a>TaskManager中memory segment大小，这是保留内存空间的基本单位，以及用于配置网络缓存栈。单位：bytes。</p>
</td>
</tr>
<tr id="row126421921102118"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5481825162119"><a name="p5481825162119"></a><a name="p5481825162119"></a>taskmanager.memory.preallocate</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1567924314215"><a name="p1567924314215"></a><a name="p1567924314215"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p7544537122117"><a name="p7544537122117"></a><a name="p7544537122117"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p7282173110219"><a name="p7282173110219"></a><a name="p7282173110219"></a>TaskManager是否在启动时分配保留内存空间。当开启堆外内存是，建议开启此配置项。</p>
</td>
</tr>
<tr id="row6418222102114"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p310114802216"><a name="p310114802216"></a><a name="p310114802216"></a>taskmanager.registration.initial-backoff</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p157412562211"><a name="p157412562211"></a><a name="p157412562211"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p640731912215"><a name="p640731912215"></a><a name="p640731912215"></a>500 ms</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p5189101462212"><a name="p5189101462212"></a><a name="p5189101462212"></a>两次连续注册的初始间隔时间。单位：ms/s/m/h/d。</p>
<div class="note" id="note397143972210"><a name="note397143972210"></a><a name="note397143972210"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p3971939202218"><a name="p3971939202218"></a><a name="p3971939202218"></a>时间数值和单位之间有半角字符空格。ms/s/m/h/d表示毫秒、秒、分钟、小时、天。</p>
</div></div>
</td>
</tr>
<tr id="row1160062212111"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p11021185225"><a name="p11021185225"></a><a name="p11021185225"></a>taskmanager.registration.refused-backoff</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p574182582218"><a name="p574182582218"></a><a name="p574182582218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p540711198226"><a name="p540711198226"></a><a name="p540711198226"></a>5 min</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p18190614172219"><a name="p18190614172219"></a><a name="p18190614172219"></a>JobManager拒绝注册后到允许再次注册的间隔时间。</p>
</td>
</tr>
<tr id="row7534193714615"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p65352371662"><a name="p65352371662"></a><a name="p65352371662"></a>task.cancellation.interval</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1553514371964"><a name="p1553514371964"></a><a name="p1553514371964"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1535537569"><a name="p1535537569"></a><a name="p1535537569"></a>30000</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p953513715610"><a name="p953513715610"></a><a name="p953513715610"></a>两次连续任务取消操作的间隔时间。</p>
</td>
</tr>
</tbody>
</table>

## 配置Blob<a name="section193756481261"></a>

JobManager节点上的Blob服务端是用于接收用户在客户端上传的Jar包，或将Jar包发送给TaskManager，传输log文件等。Flink提供配置Blob服务端的一些配置项，用户请在“flink-conf.yaml”配置文件中进行配置。

用户可以配置端口，SSL，重试次数，并发等配置项。

**表 2**  参数说明

<a name="table199651434182719"></a>
<table><thead align="left"><tr id="row796693412712"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p119661134122720"><a name="p119661134122720"></a><a name="p119661134122720"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p7966183413275"><a name="p7966183413275"></a><a name="p7966183413275"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p18966173412273"><a name="p18966173412273"></a><a name="p18966173412273"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p1196663412279"><a name="p1196663412279"></a><a name="p1196663412279"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6966143452716"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p116661421152811"><a name="p116661421152811"></a><a name="p116661421152811"></a>blob.server.port</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2082059182911"><a name="p2082059182911"></a><a name="p2082059182911"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p113171527202911"><a name="p113171527202911"></a><a name="p113171527202911"></a>默认值为32456-32520。</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p14706136142911"><a name="p14706136142911"></a><a name="p14706136142911"></a>blob服务器端口。</p>
</td>
</tr>
<tr id="row35761553284"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1866692118284"><a name="p1866692118284"></a><a name="p1866692118284"></a>blob.service.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p482012922915"><a name="p482012922915"></a><a name="p482012922915"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p143171271294"><a name="p143171271294"></a><a name="p143171271294"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p18706136132916"><a name="p18706136132916"></a><a name="p18706136132916"></a>blob传输通道是否加密传输，仅在全局开关security.ssl开启时有。</p>
</td>
</tr>
<tr id="row1114169281"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p146661221202816"><a name="p146661221202816"></a><a name="p146661221202816"></a>blob.fetch.retries</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1582016992917"><a name="p1582016992917"></a><a name="p1582016992917"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p131732752919"><a name="p131732752919"></a><a name="p131732752919"></a>50</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p20707336162915"><a name="p20707336162915"></a><a name="p20707336162915"></a>TaskManager从JobManager下载blob文件的重试次数。</p>
</td>
</tr>
<tr id="row12966123411274"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p266612215289"><a name="p266612215289"></a><a name="p266612215289"></a>blob.fetch.num-concurrent</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p582018914290"><a name="p582018914290"></a><a name="p582018914290"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p431720275295"><a name="p431720275295"></a><a name="p431720275295"></a>50</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p10707036142919"><a name="p10707036142919"></a><a name="p10707036142919"></a>JobManager支持的下载blob的并发数。</p>
</td>
</tr>
<tr id="row596633462714"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p513913132919"><a name="p513913132919"></a><a name="p513913132919"></a>blob.fetch.backlog</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p351191682915"><a name="p351191682915"></a><a name="p351191682915"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p855072072910"><a name="p855072072910"></a><a name="p855072072910"></a>1000</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p09461442112917"><a name="p09461442112917"></a><a name="p09461442112917"></a>JobManager支持的blob下载队列大小，比如下载Jar包等。单位：个。</p>
</td>
</tr>
</tbody>
</table>

## 配置Distributed Coordination \(via Akka\)<a name="section10197757112916"></a>

Flink客户端与JobManager的通信，JobManager与TaskManager的通信和TaskManager与TaskManager的通信都基于Akka actor模型。Flink提供Akka连接参数的配置项，配置项请在“flink-conf.yaml”配置文件中进行配置，用户可以根据网络环境或调优策略在进行配置。

配置项包括消息发送和等待的超时设置，akka监听机制Deathwatch的相关配置等。

**表 3**  参数说明

<a name="table8198157172919"></a>
<table><thead align="left"><tr id="row12198757192914"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p9198145720293"><a name="p9198145720293"></a><a name="p9198145720293"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p51981857102912"><a name="p51981857102912"></a><a name="p51981857102912"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p12198557152912"><a name="p12198557152912"></a><a name="p12198557152912"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p11981957142915"><a name="p11981957142915"></a><a name="p11981957142915"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1198115762915"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p62145455513"><a name="p62145455513"></a><a name="p62145455513"></a>akka.ask.timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p13197987564"><a name="p13197987564"></a><a name="p13197987564"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5121164135617"><a name="p5121164135617"></a><a name="p5121164135617"></a>10 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p485535814552"><a name="p485535814552"></a><a name="p485535814552"></a>akka所有异步请求和阻塞请求的超时时间。如果Flink发生超时失败，可以增大这个值。当机器处理速度慢或者网络阻塞时会发生超时。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row1719985762912"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p112554125512"><a name="p112554125512"></a><a name="p112554125512"></a>akka.lookup.timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p81983835613"><a name="p81983835613"></a><a name="p81983835613"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p612111417564"><a name="p612111417564"></a><a name="p612111417564"></a>10 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p138556589553"><a name="p138556589553"></a><a name="p138556589553"></a>查找JobManager actor对象的超时时间。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row519985712915"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1721554105514"><a name="p1721554105514"></a><a name="p1721554105514"></a>akka.framesize</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p4198188155611"><a name="p4198188155611"></a><a name="p4198188155611"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p3121144562"><a name="p3121144562"></a><a name="p3121144562"></a>10485760b</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p885575845510"><a name="p885575845510"></a><a name="p885575845510"></a>JobManager和TaskManager间最大消息传输大小。当Flink出现消息大小超过限制的错误时，可以增大这个值。单位：b/B/KB/MB。</p>
</td>
</tr>
<tr id="row5199857192912"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p662721515561"><a name="p662721515561"></a><a name="p662721515561"></a>akka.watch.heartbeat.interval</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p171973315569"><a name="p171973315569"></a><a name="p171973315569"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p178702710567"><a name="p178702710567"></a><a name="p178702710567"></a>10 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p62841820185610"><a name="p62841820185610"></a><a name="p62841820185610"></a>Akka DeathWatch机制检测失联TaskManager的心跳间隔。如果TaskManager经常发生由于心跳消息丢失或延误而被错误标记为失联的情况，可以增大这个值。单位：ms/s/m/h/d。</p>
<div class="note" id="note1542393885610"><a name="note1542393885610"></a><a name="note1542393885610"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p15424538105615"><a name="p15424538105615"></a><a name="p15424538105615"></a>DeathWatch的详细解释可以参考akka官网：<a href="http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector" target="_blank" rel="noopener noreferrer">http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector</a>。</p>
</div></div>
</td>
</tr>
<tr id="row82003573299"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p7627141511561"><a name="p7627141511561"></a><a name="p7627141511561"></a>akka.watch.heartbeat.pause</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p117191133145617"><a name="p117191133145617"></a><a name="p117191133145617"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p987927165611"><a name="p987927165611"></a><a name="p987927165611"></a>60 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p122843206562"><a name="p122843206562"></a><a name="p122843206562"></a>Akka DeathWatch可接受的心跳暂停时间，较小的数值表示不允许不规律的心跳。单位：ms/s/m/h/d。</p>
<div class="note" id="note28881951135617"><a name="note28881951135617"></a><a name="note28881951135617"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p48900519565"><a name="p48900519565"></a><a name="p48900519565"></a>DeathWatch的详细解释可以参考akka官网：<a href="http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector" target="_blank" rel="noopener noreferrer">http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector</a>。</p>
</div></div>
</td>
</tr>
<tr id="row3200125742911"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1657712548571"><a name="p1657712548571"></a><a name="p1657712548571"></a>akka.watch.threshold</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p99629169587"><a name="p99629169587"></a><a name="p99629169587"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p17661013583"><a name="p17661013583"></a><a name="p17661013583"></a>12</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p62761659105717"><a name="p62761659105717"></a><a name="p62761659105717"></a>DeathWatch失败检测阈值，较小的数值容易把正常TaskManager标记为失败，较大的值增加了失败检测的时间。</p>
<div class="note" id="note0806521165812"><a name="note0806521165812"></a><a name="note0806521165812"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p027616591576"><a name="p027616591576"></a><a name="p027616591576"></a>DeathWatch的详细解释可以参考akka官网：<a href="http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector" target="_blank" rel="noopener noreferrer">http://doc.akka.io/docs/akka/snapshot/scala/remoting.html#failure-detector</a>。</p>
</div></div>
</td>
</tr>
<tr id="row1278412518579"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p10577654165714"><a name="p10577654165714"></a><a name="p10577654165714"></a>akka.tcp.timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p18962131615817"><a name="p18962131615817"></a><a name="p18962131615817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p568100588"><a name="p568100588"></a><a name="p568100588"></a>20 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p192774598574"><a name="p192774598574"></a><a name="p192774598574"></a>发送连接TCP超时时间，如果经常发生满网络环境下连接TaskManager超时，可以增大这个值。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row1996655114579"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p457735415712"><a name="p457735415712"></a><a name="p457735415712"></a>akka.throughput</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p159623161587"><a name="p159623161587"></a><a name="p159623161587"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p12661035815"><a name="p12661035815"></a><a name="p12661035815"></a>15</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p027711599579"><a name="p027711599579"></a><a name="p027711599579"></a>Akka批量处理消息的数量，一次操作完后把处理线程归还线程池。较小的数值代表actor消息处理的公平调度，较大的值以牺牲调度公平的代价提高整体性能。</p>
</td>
</tr>
<tr id="row715211529576"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p689014019581"><a name="p689014019581"></a><a name="p689014019581"></a>akka.log.lifecycle.events</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p515112165912"><a name="p515112165912"></a><a name="p515112165912"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p124581561583"><a name="p124581561583"></a><a name="p124581561583"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1396295065813"><a name="p1396295065813"></a><a name="p1396295065813"></a>Akka远程时间日志开关，当需要调试时可打开此开关。</p>
</td>
</tr>
<tr id="row532715214576"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p138902040135813"><a name="p138902040135813"></a><a name="p138902040135813"></a>akka.startup-timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1015120115912"><a name="p1015120115912"></a><a name="p1015120115912"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p34583565582"><a name="p34583565582"></a><a name="p34583565582"></a>默认与akka.ask.timeout的值一致</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p18962750195818"><a name="p18962750195818"></a><a name="p18962750195818"></a>Akka启动remote组件的超时时间。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row95187522578"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p6890940145815"><a name="p6890940145815"></a><a name="p6890940145815"></a>akka.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1215119165913"><a name="p1215119165913"></a><a name="p1215119165913"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1845825613583"><a name="p1845825613583"></a><a name="p1845825613583"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p16963115016585"><a name="p16963115016585"></a><a name="p16963115016585"></a>Akka通信SSL开关，仅在全局开关security.ssl开启时有。</p>
</td>
</tr>
</tbody>
</table>

## 配置SSL<a name="section8618438178"></a>

当需要配置安全Flink集群时，需要配置SSL相关配置项。

配置项包括SSL开关，证书，密码，加密算法等。

**表 4**  参数说明

<a name="table956544414184"></a>
<table><thead align="left"><tr id="row65654448188"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p125657441185"><a name="p125657441185"></a><a name="p125657441185"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15.02%" id="mcps1.2.5.1.2"><p id="p2056564431818"><a name="p2056564431818"></a><a name="p2056564431818"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.979999999999999%" id="mcps1.2.5.1.3"><p id="p13566644111819"><a name="p13566644111819"></a><a name="p13566644111819"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p20566644111819"><a name="p20566644111819"></a><a name="p20566644111819"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row175661544171818"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p81073617194"><a name="p81073617194"></a><a name="p81073617194"></a>security.ssl.internal.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p14385122514194"><a name="p14385122514194"></a><a name="p14385122514194"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p3514121911910"><a name="p3514121911910"></a><a name="p3514121911910"></a>按照集群的安装模式自动配置。</p>
<a name="ul1251481921919"></a><a name="ul1251481921919"></a><ul id="ul1251481921919"><li>安全模式：默认为true。</li><li>普通模式：默认为false。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p49151910101915"><a name="p49151910101915"></a><a name="p49151910101915"></a>内部通信SSL总开关。</p>
</td>
</tr>
<tr id="row145662044171818"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p310712613195"><a name="p310712613195"></a><a name="p310712613195"></a>security.ssl.internal.keystore</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p10385025161918"><a name="p10385025161918"></a><a name="p10385025161918"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p115141819191915"><a name="p115141819191915"></a><a name="p115141819191915"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p17915201041917"><a name="p17915201041917"></a><a name="p17915201041917"></a>Java keystore文件。</p>
</td>
</tr>
<tr id="row2566124421810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1410716171910"><a name="p1410716171910"></a><a name="p1410716171910"></a>security.ssl.internal.keystore-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p2038522514193"><a name="p2038522514193"></a><a name="p2038522514193"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p85141219201914"><a name="p85141219201914"></a><a name="p85141219201914"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p109154103190"><a name="p109154103190"></a><a name="p109154103190"></a>keystore文件解密密码。</p>
</td>
</tr>
<tr id="row2566044141812"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p8666743171916"><a name="p8666743171916"></a><a name="p8666743171916"></a>security.ssl.internal.key-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p1243982122017"><a name="p1243982122017"></a><a name="p1243982122017"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p122986550192"><a name="p122986550192"></a><a name="p122986550192"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p8390124917196"><a name="p8390124917196"></a><a name="p8390124917196"></a>keystore文件中服务端key的解密密码。</p>
</td>
</tr>
<tr id="row556784451810"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p16666114317195"><a name="p16666114317195"></a><a name="p16666114317195"></a>security.ssl.internal.truststore</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p8439828207"><a name="p8439828207"></a><a name="p8439828207"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p1629816553190"><a name="p1629816553190"></a><a name="p1629816553190"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1239054951910"><a name="p1239054951910"></a><a name="p1239054951910"></a>truststore文件包含公共CA证书。</p>
</td>
</tr>
<tr id="row656754451819"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4666543191910"><a name="p4666543191910"></a><a name="p4666543191910"></a>security.ssl.internal.truststore-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p94393212012"><a name="p94393212012"></a><a name="p94393212012"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p1329811556193"><a name="p1329811556193"></a><a name="p1329811556193"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p193904495195"><a name="p193904495195"></a><a name="p193904495195"></a>truststore文件解密密码。</p>
</td>
</tr>
<tr id="row3567114491814"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p186661643151916"><a name="p186661643151916"></a><a name="p186661643151916"></a>security.ssl.protocol</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p7440423206"><a name="p7440423206"></a><a name="p7440423206"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p62991555201916"><a name="p62991555201916"></a><a name="p62991555201916"></a>TLSv1.2</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1039010497199"><a name="p1039010497199"></a><a name="p1039010497199"></a>SSL传输的协议版本。</p>
</td>
</tr>
<tr id="row656817442185"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p19666443201915"><a name="p19666443201915"></a><a name="p19666443201915"></a>security.ssl.algorithms</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p14440923204"><a name="p14440923204"></a><a name="p14440923204"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p1829955515198"><a name="p1829955515198"></a><a name="p1829955515198"></a>默认值为“TLS_RSA_WITH_AES_128_CBC_SHA256,TLS_DHE_RSA_WITH_AES_128_CBC_SHA256,TLS_DHE_DSS_WITH_AES_128_CBC_SHA256”</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1139018493198"><a name="p1139018493198"></a><a name="p1139018493198"></a>支持的SSL标准算法，具体可参考java官网：<a href="http://docs.oracle.com/javase/8/docs/technotes/guides/security/StandardNames.html#ciphersuites" target="_blank" rel="noopener noreferrer">http://docs.oracle.com/javase/8/docs/technotes/guides/security/StandardNames.html#ciphersuites</a>。</p>
</td>
</tr>
<tr id="row136382191219"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p6600113810141"><a name="p6600113810141"></a><a name="p6600113810141"></a>security.ssl.rest.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p1260013818147"><a name="p1260013818147"></a><a name="p1260013818147"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p56001538111419"><a name="p56001538111419"></a><a name="p56001538111419"></a>按照集群的安装模式自动配置。</p>
<a name="ul760019381146"></a><a name="ul760019381146"></a><ul id="ul760019381146"><li>安全模式：默认为true。</li><li>普通模式：默认为false。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p19600123817149"><a name="p19600123817149"></a><a name="p19600123817149"></a>外部通信SSL总开关。</p>
</td>
</tr>
<tr id="row1243418413138"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p2601638181411"><a name="p2601638181411"></a><a name="p2601638181411"></a>security.ssl.rest.keystore</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p1560117384142"><a name="p1560117384142"></a><a name="p1560117384142"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p8601193811419"><a name="p8601193811419"></a><a name="p8601193811419"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1660117384144"><a name="p1660117384144"></a><a name="p1660117384144"></a>Java keystore文件。</p>
</td>
</tr>
<tr id="row44761023191416"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1660115387148"><a name="p1660115387148"></a><a name="p1660115387148"></a>security.ssl.rest.keystore-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p6601203811145"><a name="p6601203811145"></a><a name="p6601203811145"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p18601103811142"><a name="p18601103811142"></a><a name="p18601103811142"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p6601133812144"><a name="p6601133812144"></a><a name="p6601133812144"></a>keystore文件解密密码。</p>
</td>
</tr>
<tr id="row9427926201417"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p76012386145"><a name="p76012386145"></a><a name="p76012386145"></a>security.ssl.rest.key-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p3601183801413"><a name="p3601183801413"></a><a name="p3601183801413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p12601103819146"><a name="p12601103819146"></a><a name="p12601103819146"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p106013387143"><a name="p106013387143"></a><a name="p106013387143"></a>keystore文件中服务端key的解密密码。</p>
</td>
</tr>
<tr id="row4324153081417"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1760193861412"><a name="p1760193861412"></a><a name="p1760193861412"></a>security.ssl.rest.truststore</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p8602438191412"><a name="p8602438191412"></a><a name="p8602438191412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p7602338161418"><a name="p7602338161418"></a><a name="p7602338161418"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p19602938161410"><a name="p19602938161410"></a><a name="p19602938161410"></a>truststore文件包含公共CA证书。</p>
</td>
</tr>
<tr id="row2245183321413"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p19602438111420"><a name="p19602438111420"></a><a name="p19602438111420"></a>security.ssl.rest.truststore-password</p>
</td>
<td class="cellrowborder" valign="top" width="15.02%" headers="mcps1.2.5.1.2 "><p id="p96021738151412"><a name="p96021738151412"></a><a name="p96021738151412"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.979999999999999%" headers="mcps1.2.5.1.3 "><p id="p1760233813148"><a name="p1760233813148"></a><a name="p1760233813148"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p560283812149"><a name="p560283812149"></a><a name="p560283812149"></a>truststore文件解密密码。</p>
</td>
</tr>
</tbody>
</table>

## 配置Network communication \(via Netty\)<a name="section510792792019"></a>

Flink运行Job时，Task之间的数据传输和反压检测都依赖Netty，某些环境下可能需要对Netty参数进行配置。

对于高级调优，可调整以下Netty配置项，默认配置已可满足大规模集群并发高吞吐量的任务，参数详情可参考Netty官网：[http://netty.io/](http://netty.io/)。

**表 5**  参数说明

<a name="table151072027112015"></a>
<table><thead align="left"><tr id="row2010720276207"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p910842792012"><a name="p910842792012"></a><a name="p910842792012"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p9108827162020"><a name="p9108827162020"></a><a name="p9108827162020"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p1410817274200"><a name="p1410817274200"></a><a name="p1410817274200"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p410822712203"><a name="p410822712203"></a><a name="p410822712203"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1310811274206"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1631132952313"><a name="p1631132952313"></a><a name="p1631132952313"></a>taskmanager.network.netty.num-arenas</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1527516483234"><a name="p1527516483234"></a><a name="p1527516483234"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p10785114014230"><a name="p10785114014230"></a><a name="p10785114014230"></a>taskmanager.numberOfTaskSlots</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p6703520234"><a name="p6703520234"></a><a name="p6703520234"></a>Netty arenas的数量。</p>
</td>
</tr>
<tr id="row7108142712013"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1311142982317"><a name="p1311142982317"></a><a name="p1311142982317"></a>taskmanager.network.netty.server.numThreads</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p227510486230"><a name="p227510486230"></a><a name="p227510486230"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p18785154020239"><a name="p18785154020239"></a><a name="p18785154020239"></a>taskmanager.numberOfTaskSlots</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p8743518232"><a name="p8743518232"></a><a name="p8743518232"></a>Netty服务器线程的数量。</p>
</td>
</tr>
<tr id="row31091127192018"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p731113291231"><a name="p731113291231"></a><a name="p731113291231"></a>taskmanager.network.netty.client.numThreads</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1275134862316"><a name="p1275134862316"></a><a name="p1275134862316"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p117851840132310"><a name="p117851840132310"></a><a name="p117851840132310"></a>taskmanager.numberOfTaskSlots</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p117935112317"><a name="p117935112317"></a><a name="p117935112317"></a>Netty客户端线程数。</p>
</td>
</tr>
<tr id="row171101227202014"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1731132914235"><a name="p1731132914235"></a><a name="p1731132914235"></a>taskmanager.network.netty.client.connectTimeoutSec</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p82757488236"><a name="p82757488236"></a><a name="p82757488236"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p678504015230"><a name="p678504015230"></a><a name="p678504015230"></a>120</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1871435172310"><a name="p1871435172310"></a><a name="p1871435172310"></a>Netty客户端连接超时。单位：s。</p>
</td>
</tr>
<tr id="row11103272204"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p113111629152317"><a name="p113111629152317"></a><a name="p113111629152317"></a>taskmanager.network.netty.sendReceiveBufferSize</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p327511480236"><a name="p327511480236"></a><a name="p327511480236"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p13785104010235"><a name="p13785104010235"></a><a name="p13785104010235"></a>4096</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p471335152318"><a name="p471335152318"></a><a name="p471335152318"></a>Netty发送和接收缓冲区大小。 默认为系统缓冲区大小（cat /proc/sys/net/ipv4/tcp_[rw] mem），在现代Linux中为4MB。单位：bytes。</p>
</td>
</tr>
<tr id="row1111011279201"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p9159164718209"><a name="p9159164718209"></a><a name="p9159164718209"></a>taskmanager.network.netty.transport</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p51581947152015"><a name="p51581947152015"></a><a name="p51581947152015"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1415717478209"><a name="p1415717478209"></a><a name="p1415717478209"></a>nio</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p18156147182016"><a name="p18156147182016"></a><a name="p18156147182016"></a>Netty传输类型，“nio”或“epoll”。</p>
</td>
</tr>
</tbody>
</table>

## 配置JobManager Web Frontend<a name="section51271561248"></a>

JobManager启动时，会在同一进程内启动web服务器。

-   用户可以访问web服务器获取当前Flink集群的信息，包括JobManager，TaskManager及集群内运行的Job。
-   用户可以对web服务器参数进行配置。

配置包括端口，临时目录，显示项目，错误重定向，安全相关等。

**表 6**  参数说明

<a name="table812755682411"></a>
<table><thead align="left"><tr id="row161286561240"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p7128556192419"><a name="p7128556192419"></a><a name="p7128556192419"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p1128856122419"><a name="p1128856122419"></a><a name="p1128856122419"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p19128125602412"><a name="p19128125602412"></a><a name="p19128125602412"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p4128185610247"><a name="p4128185610247"></a><a name="p4128185610247"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1712865672420"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3627925202618"><a name="p3627925202618"></a><a name="p3627925202618"></a>jobmanager.web.port</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1539124613267"><a name="p1539124613267"></a><a name="p1539124613267"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1886718402267"><a name="p1886718402267"></a><a name="p1886718402267"></a>32261-32325</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p175673412618"><a name="p175673412618"></a><a name="p175673412618"></a>web端口，支持范围：32261-32325。</p>
</td>
</tr>
<tr id="row055212279"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p11873743142718"><a name="p11873743142718"></a><a name="p11873743142718"></a>jobmanager.web.allow-access-address</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p7997172192820"><a name="p7997172192820"></a><a name="p7997172192820"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p166814569275"><a name="p166814569275"></a><a name="p166814569275"></a>*</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p165032515277"><a name="p165032515277"></a><a name="p165032515277"></a>web访问白名单，ip以逗号隔开。只有在白名单中的ip才能访问web。</p>
</td>
</tr>
</tbody>
</table>

## 配置File Systems<a name="section795833918285"></a>

task运行中会创建结果文件，Flink支持对文件创建行为进行配置。

配置项包括文件覆盖策略，目录创建。

**表 7**  参数说明

<a name="table1454185635918"></a>
<table><thead align="left"><tr id="row1455656185916"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p34551256165913"><a name="p34551256165913"></a><a name="p34551256165913"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p34555565596"><a name="p34555565596"></a><a name="p34555565596"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p545515561598"><a name="p545515561598"></a><a name="p545515561598"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p194551656135914"><a name="p194551656135914"></a><a name="p194551656135914"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15455175618598"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p544415222017"><a name="p544415222017"></a><a name="p544415222017"></a>fs.overwrite-files</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p127041545101"><a name="p127041545101"></a><a name="p127041545101"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p25288391705"><a name="p25288391705"></a><a name="p25288391705"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p17182103111012"><a name="p17182103111012"></a><a name="p17182103111012"></a>是否覆盖文件。</p>
</td>
</tr>
<tr id="row12456145615593"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p154444221002"><a name="p154444221002"></a><a name="p154444221002"></a>fs.output.always-create-directory</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1670474517014"><a name="p1670474517014"></a><a name="p1670474517014"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p145291039803"><a name="p145291039803"></a><a name="p145291039803"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1918219311905"><a name="p1918219311905"></a><a name="p1918219311905"></a>当文件写入程序的并行度大于1时，输出文件的路径下会创建一个目录，并将不同的结果文件（每个并行写程序任务一个）放入该目录。</p>
<a name="ul618213311903"></a><a name="ul618213311903"></a><ul id="ul618213311903"><li>如果此选项设置为true，那么并行度为1的写入程序也将创建一个目录并将一个结果文件放入其中。</li><li>如果该选项设置为false，则并行度为1的写入程序将直接在输出路径中创建文件，而不再创建目录。</li></ul>
</td>
</tr>
</tbody>
</table>

## 配置State Backend<a name="section5704059307"></a>

Flink提供了HA和作业的异常恢复，并且提供版本升级时作业的暂停恢复。对于作业状态的存储，FLink依赖于state backend，作业的重启依赖于重启策略，用户可以对这两部分进行配置。

配置项包括state  backend类型，存储路径，重启策略等。

**表 8**  参数说明

<a name="table8462851313"></a>
<table><thead align="left"><tr id="row134629518113"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p14637519120"><a name="p14637519120"></a><a name="p14637519120"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p164631451519"><a name="p164631451519"></a><a name="p164631451519"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p204638511515"><a name="p204638511515"></a><a name="p204638511515"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p2463105116117"><a name="p2463105116117"></a><a name="p2463105116117"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row84631251613"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p98851230425"><a name="p98851230425"></a><a name="p98851230425"></a>state.checkpoints.dir</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p6871152924"><a name="p6871152924"></a><a name="p6871152924"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p119898471928"><a name="p119898471928"></a><a name="p119898471928"></a>hdfs:///flink/checkpoints</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p17673339522"><a name="p17673339522"></a><a name="p17673339522"></a>当backend为filesystem时的路径，路径必须能够被JobManager访问到，本地路径只支持local模式，集群模式下请使用HDFS路径。</p>
</td>
</tr>
<tr id="row94242586114"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1885130424"><a name="p1885130424"></a><a name="p1885130424"></a>state.savepoints.dir</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p198714527216"><a name="p198714527216"></a><a name="p198714527216"></a>安全模式下必配</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p698954711215"><a name="p698954711215"></a><a name="p698954711215"></a>hdfs:///flink/savepoint</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p5673439123"><a name="p5673439123"></a><a name="p5673439123"></a>用户存储save point的路径。</p>
<p id="p367393917212"><a name="p367393917212"></a><a name="p367393917212"></a>用户可以在保存savepoint时指定HDFS路径，如果没有指定，使用该配置项。</p>
</td>
</tr>
<tr id="row1876205820115"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p188513016214"><a name="p188513016214"></a><a name="p188513016214"></a>restart-strategy</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p887116521022"><a name="p887116521022"></a><a name="p887116521022"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p139897471726"><a name="p139897471726"></a><a name="p139897471726"></a>fixed-delay</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p9673113910214"><a name="p9673113910214"></a><a name="p9673113910214"></a>重启策略，三个值可选：</p>
<a name="ul8673193914215"></a><a name="ul8673193914215"></a><ul id="ul8673193914215"><li>fixed-delay</li><li>failure-rate</li><li>none</li></ul>
</td>
</tr>
<tr id="row1549591112"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p16324157315"><a name="p16324157315"></a><a name="p16324157315"></a>restart-strategy.fixed-delay.attempts</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p673913286318"><a name="p673913286318"></a><a name="p673913286318"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><a name="ul58332197311"></a><a name="ul58332197311"></a><ul id="ul58332197311"><li>作业中开启了checkpoint，则默认值为Integer.MAX_VALUE。</li><li>作业中未开启checkpoint，默认值为3。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p92519141730"><a name="p92519141730"></a><a name="p92519141730"></a>fixed-delay策略重试次数，具体策略的介绍请参见：<a href="https://ci.apache.org/projects/flink/flink-docs-release-1.7/dev/restart_strategies.html" target="_blank" rel="noopener noreferrer">https://ci.apache.org/projects/flink/flink-docs-release-1.7/dev/restart_strategies.html</a>。</p>
</td>
</tr>
<tr id="row1923419591214"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4324145937"><a name="p4324145937"></a><a name="p4324145937"></a>restart-strategy.fixed-delay.delay</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p77394288319"><a name="p77394288319"></a><a name="p77394288319"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><a name="ul88331119535"></a><a name="ul88331119535"></a><ul id="ul88331119535"><li>作业中开启了checkpoint，默认值是10 s。</li><li>作业中不开启checkpoint，默认值和配置项akka.ask.timeout的值一致。</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p11256149316"><a name="p11256149316"></a><a name="p11256149316"></a>fixed-delay策略重试间隔时间。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row1450111592012"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1310116478313"><a name="p1310116478313"></a><a name="p1310116478313"></a>restart-strategy.failure-rate.max-failures-per-interval</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p145273412418"><a name="p145273412418"></a><a name="p145273412418"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p17012581631"><a name="p17012581631"></a><a name="p17012581631"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p167541529313"><a name="p167541529313"></a><a name="p167541529313"></a>failure-rate策略重试次数，具体策略的介绍请参见：<a href="https://ci.apache.org/projects/flink/flink-docs-release-1.7/dev/restart_strategies.html" target="_blank" rel="noopener noreferrer">https://ci.apache.org/projects/flink/flink-docs-release-1.7/dev/restart_strategies.html</a>。</p>
</td>
</tr>
<tr id="row18825135911114"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p61019473311"><a name="p61019473311"></a><a name="p61019473311"></a>restart-strategy.failure-rate.failure-rate-interval</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1352716411413"><a name="p1352716411413"></a><a name="p1352716411413"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p3701105815310"><a name="p3701105815310"></a><a name="p3701105815310"></a>60 s</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p87549525314"><a name="p87549525314"></a><a name="p87549525314"></a>failure-rate策略重试时间。单位：ms/s/m/h/d。</p>
</td>
</tr>
<tr id="row9116018216"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p19101124719315"><a name="p19101124719315"></a><a name="p19101124719315"></a>restart-strategy.failure-rate.delay</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p15527174542"><a name="p15527174542"></a><a name="p15527174542"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p4701858431"><a name="p4701858431"></a><a name="p4701858431"></a>默认值和akka.ask.timeout配置值一样，请参见Distributed Coordination (via Akka)</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1754105217318"><a name="p1754105217318"></a><a name="p1754105217318"></a>failure-rate策略重试间隔时间。单位：ms/s/m/h/d。</p>
</td>
</tr>
</tbody>
</table>

## 配置Kerberos-based Security<a name="section28916381843"></a>

Flink安全模式下必须配置Kerberos相关配置项。

配置项包括kerberos的keytab、principal等。

**表 9**  参数说明

<a name="table454519361652"></a>
<table><thead align="left"><tr id="row8545163613511"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p105451236759"><a name="p105451236759"></a><a name="p105451236759"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p6546103620517"><a name="p6546103620517"></a><a name="p6546103620517"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p165468361352"><a name="p165468361352"></a><a name="p165468361352"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p85461362512"><a name="p85461362512"></a><a name="p85461362512"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19546193617518"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p65961071165"><a name="p65961071165"></a><a name="p65961071165"></a>security.kerberos.login.keytab</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p123904324616"><a name="p123904324616"></a><a name="p123904324616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1283812241612"><a name="p1283812241612"></a><a name="p1283812241612"></a>根据实际业务配置</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p25071175618"><a name="p25071175618"></a><a name="p25071175618"></a>该参数为客户端参数，keytab路径。</p>
</td>
</tr>
<tr id="row13655647852"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p25961574615"><a name="p25961574615"></a><a name="p25961574615"></a>security.kerberos.login.principal</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1039014322616"><a name="p1039014322616"></a><a name="p1039014322616"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p48380241264"><a name="p48380241264"></a><a name="p48380241264"></a>根据实际业务配置</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p550719171963"><a name="p550719171963"></a><a name="p550719171963"></a>该参数为客户端参数，如果keytab和principal都设置，默认会使用keytab认证。</p>
</td>
</tr>
<tr id="row171251748952"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1759620710614"><a name="p1759620710614"></a><a name="p1759620710614"></a>security.kerberos.login.contexts</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p739033214612"><a name="p739033214612"></a><a name="p739033214612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p13838152413617"><a name="p13838152413617"></a><a name="p13838152413617"></a>Client、KafkaClient</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1150811171061"><a name="p1150811171061"></a><a name="p1150811171061"></a>该参数为服务器端参数，Flink生成jass文件的contexts。</p>
</td>
</tr>
</tbody>
</table>

## 配置HA<a name="section83813381560"></a>

Flink的HA模式依赖于ZooKeeper，所以必须配置ZooKeeper相关配置。

配置项包括ZooKeeper地址，路径，安全认证等。

**表 10**  参数说明

<a name="table4784519778"></a>
<table><thead align="left"><tr id="row1278513191176"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p197856191671"><a name="p197856191671"></a><a name="p197856191671"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p167856191970"><a name="p167856191970"></a><a name="p167856191970"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p107855191478"><a name="p107855191478"></a><a name="p107855191478"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p197855197713"><a name="p197855197713"></a><a name="p197855197713"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row978514194716"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p7379201120813"><a name="p7379201120813"></a><a name="p7379201120813"></a>high-availability</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p22382361986"><a name="p22382361986"></a><a name="p22382361986"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p124818301813"><a name="p124818301813"></a><a name="p124818301813"></a>zookeeper</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p186533228815"><a name="p186533228815"></a><a name="p186533228815"></a>是否启用HA模式。当前支持两种模式：</p>
<a name="ul2091118445817"></a><a name="ul2091118445817"></a><ul id="ul2091118445817"><li>none，只运行单个jobManager，jobManager的状态不进行Checkpoint。</li><li>ZooKeeper。<a name="ul51738558335"></a><a name="ul51738558335"></a><ul id="ul51738558335"><li>非YARN模式下，支持多个jobManager，通过选举产生leader。</li><li>YARN模式下只存在一个jobManager。</li></ul>
</li></ul>
</td>
</tr>
<tr id="row825818427718"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p0379611188"><a name="p0379611188"></a><a name="p0379611188"></a>high-availability.zookeeper.quorum</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p112381363818"><a name="p112381363818"></a><a name="p112381363818"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p17481153012810"><a name="p17481153012810"></a><a name="p17481153012810"></a>自动配置</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p11653322981"><a name="p11653322981"></a><a name="p11653322981"></a>ZooKeeper quorum地址。</p>
</td>
</tr>
<tr id="row2906042970"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p6379161116813"><a name="p6379161116813"></a><a name="p6379161116813"></a>high-availability.zookeeper.path.root</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p02380361487"><a name="p02380361487"></a><a name="p02380361487"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p144811830688"><a name="p144811830688"></a><a name="p144811830688"></a>/flink</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p9653162216819"><a name="p9653162216819"></a><a name="p9653162216819"></a>Flink在ZooKeeper上创建的根目录，存放HA模式必须的元数据。</p>
</td>
</tr>
<tr id="row1351924312719"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3379611984"><a name="p3379611984"></a><a name="p3379611984"></a>high-availability.storageDir</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p52425361486"><a name="p52425361486"></a><a name="p52425361486"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1248113305810"><a name="p1248113305810"></a><a name="p1248113305810"></a>hdfs:///flink/recovery</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p76531522889"><a name="p76531522889"></a><a name="p76531522889"></a>存放state backend中JobManager元数据，ZooKeeper只保存实际数据的指针。</p>
</td>
</tr>
<tr id="row139515447717"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p16230721193"><a name="p16230721193"></a><a name="p16230721193"></a>high-availability.zookeeper.client.session-timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1562132416915"><a name="p1562132416915"></a><a name="p1562132416915"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1354717157915"><a name="p1354717157915"></a><a name="p1354717157915"></a>60000</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p575619818917"><a name="p575619818917"></a><a name="p575619818917"></a>ZooKeeper客户端会话超时时间。单位：ms。</p>
</td>
</tr>
<tr id="row076834410710"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p14230421991"><a name="p14230421991"></a><a name="p14230421991"></a>high-availability.zookeeper.client.connection-timeout</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p56219247917"><a name="p56219247917"></a><a name="p56219247917"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p105478153910"><a name="p105478153910"></a><a name="p105478153910"></a>15000</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1375712814910"><a name="p1375712814910"></a><a name="p1375712814910"></a>ZooKeeper客户端连接超时时间。单位：ms。</p>
</td>
</tr>
<tr id="row5459645276"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p12305214915"><a name="p12305214915"></a><a name="p12305214915"></a>high-availability.zookeeper.client.retry-wait</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p20620248911"><a name="p20620248911"></a><a name="p20620248911"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p854771510917"><a name="p854771510917"></a><a name="p854771510917"></a>5000</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p27571385913"><a name="p27571385913"></a><a name="p27571385913"></a>ZooKeeper客户端重试等待时间。单位：ms。</p>
</td>
</tr>
<tr id="row910517461873"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p02301621910"><a name="p02301621910"></a><a name="p02301621910"></a>high-availability.zookeeper.client.max-retry-attempts</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p862824792"><a name="p862824792"></a><a name="p862824792"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p185507159916"><a name="p185507159916"></a><a name="p185507159916"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p8757981996"><a name="p8757981996"></a><a name="p8757981996"></a>ZooKeeper客户端最大重试次数。</p>
</td>
</tr>
<tr id="row178612191574"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p923042798"><a name="p923042798"></a><a name="p923042798"></a>high-availability.zookeeper.client.acl</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p196292410911"><a name="p196292410911"></a><a name="p196292410911"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p9550101512910"><a name="p9550101512910"></a><a name="p9550101512910"></a>按照集群的安装模式自动配置:</p>
<a name="ul9550111519914"></a><a name="ul9550111519914"></a><ul id="ul9550111519914"><li>安全模式：creator</li><li>普通模式：open</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1575719812919"><a name="p1575719812919"></a><a name="p1575719812919"></a>设置ZooKeeper节点的ACL (open creator)。</p>
</td>
</tr>
<tr id="row278715191572"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1824116366914"><a name="p1824116366914"></a><a name="p1824116366914"></a>zookeeper.sasl.disable</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p148821570104"><a name="p148821570104"></a><a name="p148821570104"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p181010212104"><a name="p181010212104"></a><a name="p181010212104"></a>按照集群的安装模式自动配置:</p>
<a name="ul11101172101018"></a><a name="ul11101172101018"></a><ul id="ul11101172101018"><li>安全模式：false</li><li>普通模式：true</li></ul>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p872016421092"><a name="p872016421092"></a><a name="p872016421092"></a>基于SASL认证的使能开关。</p>
</td>
</tr>
<tr id="row2788201914715"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p192413361898"><a name="p192413361898"></a><a name="p192413361898"></a>zookeeper.sasl.service-name</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p788217751010"><a name="p788217751010"></a><a name="p788217751010"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1210120211018"><a name="p1210120211018"></a><a name="p1210120211018"></a>zookeeper</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><a name="ul107205421091"></a><a name="ul107205421091"></a><ul id="ul107205421091"><li>如果ZooKeeper服务端配置了不同于“ZooKeeper”的服务名，可以设置此配置项。</li><li>如果客户端和服务端的服务名不一致，认证会失败。</li></ul>
</td>
</tr>
</tbody>
</table>

## 配置Environment<a name="section481819171312"></a>

对于JVM配置有特定要求的场景，可以通过配置项传递JVM参数到客户端，JobMananger，TaskManager等。

可配置JVM参数。

**表 11**  参数说明

<a name="table10693153613148"></a>
<table><thead align="left"><tr id="row18694103691419"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p1869453691411"><a name="p1869453691411"></a><a name="p1869453691411"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p46941836171419"><a name="p46941836171419"></a><a name="p46941836171419"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p15694636151418"><a name="p15694636151418"></a><a name="p15694636151418"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p0694436171411"><a name="p0694436171411"></a><a name="p0694436171411"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13695153614147"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1386535331416"><a name="p1386535331416"></a><a name="p1386535331416"></a>env.java.opts</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2923918153"><a name="p2923918153"></a><a name="p2923918153"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p19865105315141"><a name="p19865105315141"></a><a name="p19865105315141"></a>-Xloggc:&lt;LOG_DIR&gt;/gc.log -XX:+PrintGCDetails -XX:-OmitStackTraceInFastThrow -XX:+PrintGCTimeStamps -XX:+PrintGCDateStamps -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=20 -XX:GCLogFileSize=20M</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p19865553181411"><a name="p19865553181411"></a><a name="p19865553181411"></a>JVM参数，会传递到启动脚本，JobManager，TaskManager，Yarn客户端。比如传递远程调试的参数等。</p>
</td>
</tr>
</tbody>
</table>

## 配置YARN<a name="section1217131071812"></a>

Flink运行在Yarn集群上时，JobManager运行在Application  Master上。JobManager的一些配置参数依赖于YARN，通过配置YARN相关的配置，使Flink更好的运行在YARN上。

配置项包括yarn  container的内存，虚拟内核，端口等。

**表 12**  参数说明

<a name="table1797925013183"></a>
<table><thead align="left"><tr id="row20979135015183"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p5979350121819"><a name="p5979350121819"></a><a name="p5979350121819"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p1297975061820"><a name="p1297975061820"></a><a name="p1297975061820"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p2098085012184"><a name="p2098085012184"></a><a name="p2098085012184"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p10980165010189"><a name="p10980165010189"></a><a name="p10980165010189"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row69809503189"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p342974316269"><a name="p342974316269"></a><a name="p342974316269"></a>yarn.maximum-failed-containers</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p76935918274"><a name="p76935918274"></a><a name="p76935918274"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p767833162719"><a name="p767833162719"></a><a name="p767833162719"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p16466185216262"><a name="p16466185216262"></a><a name="p16466185216262"></a>当TaskManager所属容器出错后，重新申请container次数。默认值为Flink集群启动时TaskManager的数量。</p>
</td>
</tr>
<tr id="row1841814588188"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p84299434261"><a name="p84299434261"></a><a name="p84299434261"></a>yarn.application-attempts</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p8693119162710"><a name="p8693119162710"></a><a name="p8693119162710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p136781238278"><a name="p136781238278"></a><a name="p136781238278"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p74671152102616"><a name="p74671152102616"></a><a name="p74671152102616"></a>Application master重启次数，次数是算在一个validity interval的最大次数，validity interval在Flink中设置为akka的timeout。重启后AM的地址和端口会变化，client需要手动连接。</p>
</td>
</tr>
<tr id="row89261659181819"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1842904322616"><a name="p1842904322616"></a><a name="p1842904322616"></a>yarn.heartbeat-delay</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p176932982716"><a name="p176932982716"></a><a name="p176932982716"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p56781239275"><a name="p56781239275"></a><a name="p56781239275"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p44671852152612"><a name="p44671852152612"></a><a name="p44671852152612"></a>Application Master和YARN Resource Manager心跳的时间间隔。单位：seconds</p>
</td>
</tr>
<tr id="row93514010191"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1142920435267"><a name="p1142920435267"></a><a name="p1142920435267"></a>yarn.containers.vcores</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2069339142711"><a name="p2069339142711"></a><a name="p2069339142711"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p567833112710"><a name="p567833112710"></a><a name="p567833112710"></a>默认值是TaskManager的slot数</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p94671852152617"><a name="p94671852152617"></a><a name="p94671852152617"></a>YARN container vcores数量。</p>
</td>
</tr>
<tr id="row91325011919"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1013211041917"><a name="p1013211041917"></a><a name="p1013211041917"></a>yarn.application-master.port</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p146931094272"><a name="p146931094272"></a><a name="p146931094272"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p14679193202714"><a name="p14679193202714"></a><a name="p14679193202714"></a>32586-32650</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1213217012199"><a name="p1213217012199"></a><a name="p1213217012199"></a>Application Master端口号设置，支持端口范围。</p>
</td>
</tr>
</tbody>
</table>

