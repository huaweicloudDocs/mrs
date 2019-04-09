# 基于binlog的MySQL数据同步到MRS集群中<a name="ZH-CN_TOPIC_0163410355"></a>

本章节为您介绍使用Maxwell同步工具将线下基于binlog的数据迁移到MRS Kafka集群中的指导。

Maxwell是一个开源程序（[https://maxwells-daemon.io](https://maxwells-daemon.io)），通过读取MySQL的binlog日志，将增删改等操作转为JSON格式发送到输出端\(如控制台/文件/Kafka等\)。Maxwell可部署在MySQL机器上，也可独立部署在其他与MySQL网络可通的机器上。

Maxwell运行在Linux服务器上，常见的有EulerOS、Ubuntu、Debian、CentOS、OpenSUSE等，且需要Java 1.8+支持。

同步数据具体内容如下。

1.  [配置MySQL](#section17682011252)
2.  [安装Maxwell](#section935158131710)
3.  [配置Maxwell](#section897274173612)
4.  [启动Maxwell](#section182543817211)
5.  [验证Maxwell](#section191261916641)
6.  [停止Maxwell](#section07395261236)
7.  [Maxwell生成的数据格式及常见字段含义](#section3609745132419)

## 配置MySQL<a name="section17682011252"></a>

1.  开启binlog，在MySQL中打开my.cnf文件，在\[mysqld\] 区块检查是否配置server\_id，log-bin与binlog\_format，若没有配置请执行如下命令添加配置项并重启MySQL，若已经配置则忽略此步骤。

    ```
    $ vi my.cnf
    
    [mysqld]
    server_id=1
    log-bin=master
    binlog_format=row
    ```

2.  <a name="li101111736164511"></a>Maxwell需要连接MySQL，并创建一个名称为maxwell的数据库存储元数据，且需要能访问需要同步的数据库，所以建议新创建一个MySQL用户专门用来给Maxwell使用。使用root登录MySQL之后，执行如下命令创建maxwell用户（其中XXXXXX是密码，请修改为实际值）。
    -   若Maxwell程序部署在非MySQL机器上，则创建的maxwell用户需要有远程登录数据库的权限，此时创建命令为

        **mysql\> GRANT ALL on maxwell.\* to 'maxwell'@'%' identified by 'XXXXXX';**

        **mysql\> GRANT SELECT, REPLICATION CLIENT, REPLICATION SLAVE on \*.\* to 'maxwell'@'%';**

    -   若Maxwell部署在MySQL机器上，则创建的maxwell用户可以设置为只能在本机登录数据库，此时创建命令为

        **mysql\> GRANT SELECT, REPLICATION CLIENT, REPLICATION SLAVE on \*.\* to 'maxwell'@'localhost' identified by 'XXXXXX';**

        **mysql\> GRANT ALL on maxwell.\* to 'maxwell'@'localhost';**



## 安装Maxwell<a name="section935158131710"></a>

1.  下载安装包，下载路径为[https://github.com/zendesk/maxwell/releases](https://github.com/zendesk/maxwell/releases)，选择名为maxwell-XXX.tar.gz的二进制文件下载，其中XXX为版本号。
2.  使用WinSCP等传输工具将tar.gz包上传到任意目录下（本示例路径为Master节点的/opt）。
3.  使用PuTTY等工具登录部署Maxwell的服务器，并执行如下命令进入tar.gz包所在目录。

    **cd /opt**

4.  执行如下命令解压“maxwell-XXX.tar.gz”压缩包，并进入“maxwell-XXX”文件夹。

    **tar -zxvf maxwell-XXX.tar.gz**

    **cd maxwell-XXX**


## 配置Maxwell<a name="section897274173612"></a>

在Maxwell的conf目录下有一个config.properties文件，配置项说明请参见[表1](#table49411722133920)。若没有conf目录，则是在maxwell的文件夹下将config.properties.example修改成config.properties。

**表 1**  Maxwell配置项说明

<a name="table49411722133920"></a>
<table><thead align="left"><tr id="row16941172216396"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p594142213399"><a name="p594142213399"></a><a name="p594142213399"></a>配置项</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p794111220399"><a name="p794111220399"></a><a name="p794111220399"></a>是否必填</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.3"><p id="p1294111221394"><a name="p1294111221394"></a><a name="p1294111221394"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.4"><p id="p99413224399"><a name="p99413224399"></a><a name="p99413224399"></a>默认值</p>
</th>
</tr>
</thead>
<tbody><tr id="row494172283910"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1450445214116"><a name="p1450445214116"></a><a name="p1450445214116"></a>user</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p85041352174117"><a name="p85041352174117"></a><a name="p85041352174117"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p1050445212418"><a name="p1050445212418"></a><a name="p1050445212418"></a>连接MySQL的用户名，即<a href="#li101111736164511">2</a>中新创建的用户</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p1350445220417"><a name="p1350445220417"></a><a name="p1350445220417"></a>-</p>
</td>
</tr>
<tr id="row1294110221394"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p350435204117"><a name="p350435204117"></a><a name="p350435204117"></a>password</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p145041652144110"><a name="p145041652144110"></a><a name="p145041652144110"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p95042052164118"><a name="p95042052164118"></a><a name="p95042052164118"></a>连接MySQL的密码</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p4504135217414"><a name="p4504135217414"></a><a name="p4504135217414"></a>-</p>
</td>
</tr>
<tr id="row169411822143913"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p165043525419"><a name="p165043525419"></a><a name="p165043525419"></a>host</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p850419522412"><a name="p850419522412"></a><a name="p850419522412"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p3504105234114"><a name="p3504105234114"></a><a name="p3504105234114"></a>MySQL地址</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p14504125213411"><a name="p14504125213411"></a><a name="p14504125213411"></a>localhost</p>
</td>
</tr>
<tr id="row19941192211392"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1850555220417"><a name="p1850555220417"></a><a name="p1850555220417"></a>port</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p65052524413"><a name="p65052524413"></a><a name="p65052524413"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p19505105244110"><a name="p19505105244110"></a><a name="p19505105244110"></a>MySQL端口</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p250545244119"><a name="p250545244119"></a><a name="p250545244119"></a>3306</p>
</td>
</tr>
<tr id="row179411322133910"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p05050526411"><a name="p05050526411"></a><a name="p05050526411"></a>log_level</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1505115220418"><a name="p1505115220418"></a><a name="p1505115220418"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p1750513528414"><a name="p1750513528414"></a><a name="p1750513528414"></a>日志打印级别，可选值为</p>
<a name="ul3178205310440"></a><a name="ul3178205310440"></a><ul id="ul3178205310440"><li>debug</li><li>info</li><li>warn</li><li>error</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p125051452164117"><a name="p125051452164117"></a><a name="p125051452164117"></a>info</p>
</td>
</tr>
<tr id="row209411222153919"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p195050523413"><a name="p195050523413"></a><a name="p195050523413"></a>output_ddl</p>
<p id="p1505852104115"><a name="p1505852104115"></a><a name="p1505852104115"></a></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p250513523417"><a name="p250513523417"></a><a name="p250513523417"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p850535214111"><a name="p850535214111"></a><a name="p850535214111"></a>是否发送DDL(数据库与数据表的定义修改)事件</p>
<a name="ul25311317194514"></a><a name="ul25311317194514"></a><ul id="ul25311317194514"><li>true：发送DDL事件</li><li>false：不发送DDL事件</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p7506115244113"><a name="p7506115244113"></a><a name="p7506115244113"></a>false</p>
</td>
</tr>
<tr id="row19941522143912"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p5506105212410"><a name="p5506105212410"></a><a name="p5506105212410"></a>producer</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p1050615528414"><a name="p1050615528414"></a><a name="p1050615528414"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p45065521419"><a name="p45065521419"></a><a name="p45065521419"></a>生产者类型，配置为kafka</p>
<a name="ul18903443184517"></a><a name="ul18903443184517"></a><ul id="ul18903443184517"><li>stdout：将生成的事件打印在日志中</li><li>kafka：将生成的事件发送到kafka</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p15064523411"><a name="p15064523411"></a><a name="p15064523411"></a>stdout</p>
</td>
</tr>
<tr id="row1913185319468"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p213255324619"><a name="p213255324619"></a><a name="p213255324619"></a>producer_partition_by</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p51323530466"><a name="p51323530466"></a><a name="p51323530466"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p13745572472"><a name="p13745572472"></a><a name="p13745572472"></a>分区策略，用来确保相同一类的数据写入到kafka同一分区</p>
<a name="ul108581437155118"></a><a name="ul108581437155118"></a><ul id="ul108581437155118"><li>database：使用数据库名称做分区，保证同一个数据库的事件写入到kafka同一个分区中</li><li>table：使用表名称做分区，保证同一个表的事件写入到kafka同一个分区中</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p11374165714475"><a name="p11374165714475"></a><a name="p11374165714475"></a>databa</p>
</td>
</tr>
<tr id="row0596105394618"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p57665511487"><a name="p57665511487"></a><a name="p57665511487"></a>ignore_producer_error</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8766175174811"><a name="p8766175174811"></a><a name="p8766175174811"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p167666512489"><a name="p167666512489"></a><a name="p167666512489"></a>是否忽略生产者发送数据失败的错误</p>
<a name="ul720014302521"></a><a name="ul720014302521"></a><ul id="ul720014302521"><li>true：在日志中打印错误信息并跳过错误的数据，程序继续运行</li><li>false：在日志中打印错误信息并终止程序</li></ul>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p076717517482"><a name="p076717517482"></a><a name="p076717517482"></a>true</p>
</td>
</tr>
<tr id="row845205464613"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1876795134818"><a name="p1876795134818"></a><a name="p1876795134818"></a>metrics_slf4j_interval</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14767165134817"><a name="p14767165134817"></a><a name="p14767165134817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p1576775124819"><a name="p1576775124819"></a><a name="p1576775124819"></a>在日志中输出上传kafka成功与失败数据的数量统计的时间间隔，单位为秒</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p167671255489"><a name="p167671255489"></a><a name="p167671255489"></a>60</p>
</td>
</tr>
<tr id="row17348195410461"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p91321216174816"><a name="p91321216174816"></a><a name="p91321216174816"></a>kafka.bootstrap.servers</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p4132141612486"><a name="p4132141612486"></a><a name="p4132141612486"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p11132131684817"><a name="p11132131684817"></a><a name="p11132131684817"></a>kafka代理节点地址，配置形式为HOST:PORT[,HOST:PORT]</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p81321816134817"><a name="p81321816134817"></a><a name="p81321816134817"></a>-</p>
</td>
</tr>
<tr id="row96461454154613"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p81322016124817"><a name="p81322016124817"></a><a name="p81322016124817"></a>kafka_topic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p141322016204813"><a name="p141322016204813"></a><a name="p141322016204813"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p12132516204814"><a name="p12132516204814"></a><a name="p12132516204814"></a>写入kafka的topic名称</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p013221694818"><a name="p013221694818"></a><a name="p013221694818"></a>maxwell</p>
</td>
</tr>
<tr id="row208796549468"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1132111611488"><a name="p1132111611488"></a><a name="p1132111611488"></a>dead_letter_topic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p413391613487"><a name="p413391613487"></a><a name="p413391613487"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p12133716154812"><a name="p12133716154812"></a><a name="p12133716154812"></a>当发送某条记录出错时，记录该条出错记录主键的kafka topic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p11333167481"><a name="p11333167481"></a><a name="p11333167481"></a>-</p>
</td>
</tr>
<tr id="row819165584611"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p113314161485"><a name="p113314161485"></a><a name="p113314161485"></a>kafka_version</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2013321684811"><a name="p2013321684811"></a><a name="p2013321684811"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p61331616174814"><a name="p61331616174814"></a><a name="p61331616174814"></a>Maxwell使用的kafka producer版本号，不能在config.properties中配置，需要在启动命令时用-- kafka_version xxx参数传入</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p31339166482"><a name="p31339166482"></a><a name="p31339166482"></a>-</p>
</td>
</tr>
<tr id="row2392155515467"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1213391644820"><a name="p1213391644820"></a><a name="p1213391644820"></a>kafka_partition_hash</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p121331216204811"><a name="p121331216204811"></a><a name="p121331216204811"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p11133101614482"><a name="p11133101614482"></a><a name="p11133101614482"></a>划分kafka topic partition的算法，支持default或murmur3</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p41334168482"><a name="p41334168482"></a><a name="p41334168482"></a>default</p>
</td>
</tr>
<tr id="row1374917557462"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p10133131610482"><a name="p10133131610482"></a><a name="p10133131610482"></a>kafka_key_format</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p2133516194814"><a name="p2133516194814"></a><a name="p2133516194814"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p2133161619482"><a name="p2133161619482"></a><a name="p2133161619482"></a>Kafka record的key生成方式，支持array或Hash</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p11133716154811"><a name="p11133716154811"></a><a name="p11133716154811"></a>Hash</p>
</td>
</tr>
<tr id="row1725595615462"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p1133316124817"><a name="p1133316124817"></a><a name="p1133316124817"></a>ddl_kafka_topic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p14133141664817"><a name="p14133141664817"></a><a name="p14133141664817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p6133171613483"><a name="p6133171613483"></a><a name="p6133171613483"></a>当output_ddl配置为true时，DDL操作写入的topic</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p013331624810"><a name="p013331624810"></a><a name="p013331624810"></a>{kafka_topic}</p>
</td>
</tr>
<tr id="row12559125616463"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p16493202424812"><a name="p16493202424812"></a><a name="p16493202424812"></a>filter</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p8493924144814"><a name="p8493924144814"></a><a name="p8493924144814"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.3 "><p id="p349332464814"><a name="p349332464814"></a><a name="p349332464814"></a>过滤数据库或表。</p>
<a name="ul1439410583596"></a><a name="ul1439410583596"></a><ul id="ul1439410583596"><li>若只想采集mydatabase的库，可以配置为<p id="p15976175911016"><a name="p15976175911016"></a><a name="p15976175911016"></a>exclude:   *.*,include: mydatabase.*</p>
</li><li>若只想采集mydatabase.mytable的表，可以配置为<p id="p76591078118"><a name="p76591078118"></a><a name="p76591078118"></a>exclude:   *.*,include: mydatabase.mytable</p>
</li><li>若只想采集mydatabase库下的mytable，mydate_123, mydate_456表，可以配置为<p id="p112093169112"><a name="p112093169112"></a><a name="p112093169112"></a>exclude: *.*,include: mydatabase.mytable, include: mydatabase./mydate_\\d*/</p>
</li></ul>
<p id="p1949472434815"><a name="p1949472434815"></a><a name="p1949472434815"></a></p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.4 "><p id="p5559356104618"><a name="p5559356104618"></a><a name="p5559356104618"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 启动Maxwell<a name="section182543817211"></a>

1.  使用PuTTY工具登录Maxwell所在的服务器。
2.  执行如下命令进入Maxwell安装目录。

    **cd /opt/maxwell-1.21.0/**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果是初次使用Maxwell，建议将conf/config.properties中的log\_level改为debug\(调试级别\)，以便观察启动之后是否能正常从MySQL获取数据并发送到kafka，当整个流程调试通过之后，再把log\_level修改为info，然后先停止再启动Maxwell生效。  
    >\# log level \[debug | info | warn | error\]  
    >log\_level=debug  

3.  执行如下命令启动Maxwell。

    **source /opt/client/bigdata\_env**

    **bin/Maxwell**

    **bin/maxwell --user='maxwell' --password='XXXXXX' --host='127.0.0.1' \\**

    **--producer=kafka --kafka.bootstrap.servers=kafkahost:9092 --kafka\_topic=Maxwell**

    其中，user，password和host分别表示MySQL的用户名，密码和IP地址，这三个参数可以通过修改配置项配置也可以通过上述命令配置，kafkahost为流式集群的Core节点的IP地址。

    显示类似如下信息，表示Maxwell启动成功。

    ```
    Success to start Maxwell [78092].
    ```


## 验证Maxwell<a name="section191261916641"></a>

1.  使用PuTTY工具登录Maxwell所在的服务器。
2.  查看日志。如果日志里面没有ERROR日志，且有打印如下日志，表示与MySQL连接正常。

    ```
    BinlogConnectorLifecycleListener - Binlog connected.
    ```

3.  登录MySQL数据库，对测试数据进行更新/创建/删除等操作。操作语句可以参考如下示例。

    ```
    -- 创建库
    create database test;
    -- 创建表
    create table test.e (
      id int(10) not null primary key auto_increment,
      m double,
      c timestamp(6),
      comment varchar(255) charset 'latin1'
    );
    -- 增加记录
    insert into test.e set m = 4.2341, c = now(3), comment = 'I am a creature of light.';
    -- 更新记录
    update test.e set m = 5.444, c = now(3) where id = 1;
    -- 删除记录
    delete from test.e where id = 1;
    -- 修改表
    alter table test.e add column torvalds bigint unsigned after m;
    -- 删除表
    drop table test.e;
    -- 删除库
    drop database test;
    ```

4.  观察Maxwell的日志输出，如果没有WARN/ERROR打印，则表示Maxwell安装配置正常。

    若要确定数据是否成功上传，可设置config.properties中的log\_level为debug，则数据上传成功时会立刻打印如下JSON格式数据，具体字段含义请参考[Maxwell生成的数据格式及常见字段含义](#section3609745132419)。

    ```
    {"database":"test","table":"e","type":"insert","ts":1541150929,"xid":60556,"commit":true,"data":{"id":1,"m":4.2341,"c":"2018-11-02 09:28:49.297000","comment":"I am a creature of light."}}
    ……
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >当整个流程调试通过之后，可以把config.properties文件中的配置项log\_level修改为info，减少日志打印量，并重启Maxwell。  
    >```  
    ># log level [debug | info | warn | error]  
    >log_level=info  
    >```  


## 停止Maxwell<a name="section07395261236"></a>

1.  使用PuTTY工具登录Maxwell所在的服务器。
2.  执行如下命令，获取Maxwell的进程标识（PID）。输出的第二个字段即为PID。

    **ps -ef | grep Maxwell | grep -v grep**

3.  执行如下命令，强制停止Maxwell进程。

    **kill -9 PID**


## Maxwell生成的数据格式及常见字段含义<a name="section3609745132419"></a>

Maxwell生成的数据格式为JSON，常见字段含义如下：

-   type：操作类型，包含database-create，database-drop，table-create，table-drop，table-alter，insert，update，delete
-   databse：操作的数据库名称
-   ts：操作时间，13位时间戳
-   table：操作的表名
-   data：数据增加/删除/修改之后的内容
-   old：数据修改前的内容或者表修改前的结构定义
-   sql：DDL操作的SQL语句
-   def：表创建与表修改的结构定义
-   xid：事物唯一ID
-   commit：数据增加/删除/修改操作是否已提交

