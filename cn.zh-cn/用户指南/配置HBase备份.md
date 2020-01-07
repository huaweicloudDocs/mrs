# 配置HBase备份<a name="ZH-CN_TOPIC_0173178437"></a>

## 操作场景<a name="section55510827154955"></a>

HBase集群备份作为提高HBase集群系统高可用性的一个关键特性，为HBase提供了实时的异地数据备份功能。它对外提供了基础的运维工具，包含主备关系维护、重建，数据校验，数据同步进展查看等功能。为了实现数据的实时备份，可以把本HBase集群中的数据备份到另一个集群。

## 前提条件<a name="section748518154955"></a>

-   主备集群都已经安装并启动成功（在Console页面“现有集群”页签，查看集群状态为“运行中”），且获取集群的管理员权限。

-   必须保证主备集群间的网络畅通和端口的使用，请参见《MapReduce服务通信矩阵》。
-   主备集群必须已配置跨集群互信，请参见[配置跨集群互信](配置跨集群互信.md)。
-   如果主集群上有历史数据，需要同步到备集群上，那么主备集群必须配置跨集群拷贝，请参见[启用集群间拷贝功能](启用集群间拷贝功能.md)。
-   主备集群上的时间必须一致，而且主备集群上的NTP服务必须使用同一个时间源。
-   必须在主备集群中的/etc/hosts文件中，配置**主备集群所有机器**的机器名与业务IP地址的对应关系。配置方式为在hosts文件中追加"192.\*\*\*.\*\*\*.\*\*\* host1"。
-   主备集群间的网络带宽需要根据业务流量而定，不应少于最大的可能业务流量。

## 使用约束<a name="section10327240154955"></a>

-   尽管备份提供了实时的数据复制功能，但实际的数据同步进展，由多方面的因素决定的，例如，当前主集群业务的繁忙程度，备集群进程的健康状态等。因此，在正常情形下，备集群不应该接管业务。极端情形下是否可以接管业务，可由系统维护人员以及决策人员根据当前的数据同步指标来决定。

-   备份功能当前仅支持一主一备。
-   通常情况下，不允许对备集群的同步表进行表级别的操作，例如修改表属性、删除表等，一旦误操作备集群后会造成主集群数据同步失败、备集群对应表的数据丢失。
-   主集群的HBase表已启用备份功能同步数据，用户每次修改表的结构时，需要手动修改备集群的同步表结构，保持与主集群表结构一致。

## 操作步骤<a name="section38133389154955"></a>

**启用主集群的备份功能来同步put方式写入的数据**

1.  <a name="li1966213718714"></a>登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0207903632.png)进行IAM用户同步）。  
    >-   针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“HBase \> 服务配置”，设置“参数类别”为“全部配置”，进入HBase配置界面。
3.  <a name="li66750118154955"></a>选择“RegionServer \> Replication”，查看“hbase.replication”配置项的值是否为“true”。如果参数值为“false”，配置“hbase.replication”为“true”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >MRS 2.0.1及其以后版本中该配置已被移除，需跳过步骤[3](#li66750118154955)。  

4.  （可选）如[表1](#table6909942154955)所示，为HBase备份操作过程中的可选配置项，您可以根据描述来进行参数配置，或者使用缺省提供的值。

    **表 1**  可选配置项

    <a name="table6909942154955"></a>
    <table><thead align="left"><tr id="row52059452154955"><th class="cellrowborder" valign="top" width="18.98%" id="mcps1.2.5.1.1"><p id="p56066123154955"><a name="p56066123154955"></a><a name="p56066123154955"></a>配置入口</p>
    </th>
    <th class="cellrowborder" valign="top" width="28.01%" id="mcps1.2.5.1.2"><p id="p45062147154955"><a name="p45062147154955"></a><a name="p45062147154955"></a>配置项</p>
    </th>
    <th class="cellrowborder" valign="top" width="13.350000000000001%" id="mcps1.2.5.1.3"><p id="p26155275154955"><a name="p26155275154955"></a><a name="p26155275154955"></a>缺省值</p>
    </th>
    <th class="cellrowborder" valign="top" width="39.660000000000004%" id="mcps1.2.5.1.4"><p id="p38202507154955"><a name="p38202507154955"></a><a name="p38202507154955"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row7395372154955"><td class="cellrowborder" rowspan="2" valign="top" width="18.98%" headers="mcps1.2.5.1.1 "><p id="p62154261154955"><a name="p62154261154955"></a><a name="p62154261154955"></a>“HMaster &gt; 性能”</p>
    </td>
    <td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.5.1.2 "><p id="p1330415154955"><a name="p1330415154955"></a><a name="p1330415154955"></a>“hbase.master.logcleaner.ttl”</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.350000000000001%" headers="mcps1.2.5.1.3 "><p id="p40654818154955"><a name="p40654818154955"></a><a name="p40654818154955"></a>600000</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="p4705941154955"><a name="p4705941154955"></a><a name="p4705941154955"></a>指定HLog的保存期限。如果配置值为“604800000”（单位：毫秒），表示HLog的保存期限为7天。</p>
    </td>
    </tr>
    <tr id="row42353470154955"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p8079028154955"><a name="p8079028154955"></a><a name="p8079028154955"></a>“hbase.master.cleaner.interval”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p50421568154955"><a name="p50421568154955"></a><a name="p50421568154955"></a>60000</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p57615175154955"><a name="p57615175154955"></a><a name="p57615175154955"></a>用于定义HLog的删除周期，即超过设置的时间的HLog会被自动删除。建议尽可能配置大的值来保留更多的HLog。</p>
    </td>
    </tr>
    <tr id="row48774533154955"><td class="cellrowborder" rowspan="5" valign="top" width="18.98%" headers="mcps1.2.5.1.1 "><p id="p58423123154955"><a name="p58423123154955"></a><a name="p58423123154955"></a>“RegionServer &gt; Replication”</p>
    </td>
    <td class="cellrowborder" valign="top" width="28.01%" headers="mcps1.2.5.1.2 "><p id="p34652497154955"><a name="p34652497154955"></a><a name="p34652497154955"></a>“replication.source.size.capacity”</p>
    </td>
    <td class="cellrowborder" valign="top" width="13.350000000000001%" headers="mcps1.2.5.1.3 "><p id="p55388839154955"><a name="p55388839154955"></a><a name="p55388839154955"></a>16777216</p>
    </td>
    <td class="cellrowborder" valign="top" width="39.660000000000004%" headers="mcps1.2.5.1.4 "><p id="p57310974154955"><a name="p57310974154955"></a><a name="p57310974154955"></a>当主集群同步数据到备集群中时，主集群会从HLog中读取数据，此时会根据本参数配置的大小读取并发送。</p>
    </td>
    </tr>
    <tr id="row46036721154955"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p37986924154955"><a name="p37986924154955"></a><a name="p37986924154955"></a>“replication.source.nb.capacity”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p57041979154955"><a name="p57041979154955"></a><a name="p57041979154955"></a>25000</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p56997575154955"><a name="p56997575154955"></a><a name="p56997575154955"></a>当主集群同步数据到备集群中时，主集群会从HLog中读取数据，此时会根据本参数配置的个数读取并发送。与“replication.source.size.capacity”一起配置使用。</p>
    </td>
    </tr>
    <tr id="row43216127154955"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p10845360154955"><a name="p10845360154955"></a><a name="p10845360154955"></a>“replication.source.maxretriesmultiplier”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p6058962154955"><a name="p6058962154955"></a><a name="p6058962154955"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p21013900154955"><a name="p21013900154955"></a><a name="p21013900154955"></a>发送Log数据失败后，重新尝试的次数限制。</p>
    </td>
    </tr>
    <tr id="row54907378154955"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p18312644154955"><a name="p18312644154955"></a><a name="p18312644154955"></a>“replication.source.sleepforretries”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p6929219154955"><a name="p6929219154955"></a><a name="p6929219154955"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p24395862154955"><a name="p24395862154955"></a><a name="p24395862154955"></a>当发送Log数据失败后的休眠时间。（单位：毫秒）</p>
    </td>
    </tr>
    <tr id="row18236171154955"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p734872154955"><a name="p734872154955"></a><a name="p734872154955"></a>“hbase.regionserver.replication.handler.count”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p59524653154955"><a name="p59524653154955"></a><a name="p59524653154955"></a>6</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p56767603154955"><a name="p56767603154955"></a><a name="p56767603154955"></a>备用集群用于接收数据的RPC处理程序的线程数。</p>
    </td>
    </tr>
    </tbody>
    </table>


**启用主集群备份功能来同步Bulkload方式写入的数据**

1.  <a name="li65160752154955"></a>是否启用Bulkload写数据备份功能？

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >当使用了HBase 的bulkload导入数据的特性时且需要同步这些数据时，需要开启批量写数据备份功能。  

    是，执行[6](#li57688977154955)。

    否，执行[11](#li33254619154955)。

2.  <a name="li57688977154955"></a>选择“组件管理 \> HBase \> 服务配置”，设置“参数类别”为“全部配置”，进入HBase配置界面。
3.  在主、备集群的HBase配置界面，搜索并修改“hbase.replication.cluster.id”参数，表示主、备集群HBase的id，例如主集群HBase的id配置为"replication1"，备集群HBase的id配置为"replication2"，用于主备集群的连接。为了节省数据开销建议参数值长度不超过30。
4.  <a name="li3244131341713"></a>在备集群的HBase配置界面，搜索并修改“hbase.replication.conf.dir”参数，表示备集群中所使用主集群客户端的HBase配置，用于启用bulkload数据备份功能时的数据备份。参数值为路径名，例如"/home"。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   当启用bulkload数据备份功能时，需在备集群的所有RegionServer节点上手动放置主集群中HBase相应客户端配置文件\(core-site.xml, hdfs-site.xml, hbase-site.xml\)，放置配置文件的实际路径为$\{hbase.replication.conf.dir\}/$\{hbase.replication.cluster.id\}。例如备集群的hbase.replication.conf.dir配置为"/home"，主集群的hbase.replication.cluster.id配置为"replication1"，则配置文件放置在备集群中实际的路径为"/home/replication1"。并修改对应目录及文件相应权限，可执行如下命令"chown -R omm:wheel /home/replication1"。  
    >-   客户端配置文件可从主集群中的的客户端中获取，例如，路径为"/opt/client/HBase/hbase/conf"。更新配置文件的方法请参见[更新客户端](更新客户端.md)。  
    >-   MRS 2.0之前的版本无需配置此参数，可跳过步骤[8](#li3244131341713)。  

5.  在主集群的HBase配置界面，搜索并修改“hbase.replication.bulkload.enabled”参数，将配置项的值修改为“true”，启用Bulkload写数据备份功能。

**重启HBase服务并安装客户端。**

1.  单击“保存配置”，保存配置。在弹出窗口中勾选“重新启动受影响的服务和实例。”，单击“确定”重启HBase服务。

    界面提示“操作成功。”，单击“完成”，服务成功启动。

2.  <a name="li33254619154955"></a>在主备集群，选择“服务管理 \> 下载客户端”，请参见[更新客户端](更新客户端.md)，更新客户端配置文件。

**同步主集群表数据。（主集群无数据可不执行）**

1.  <a name="li12641483154955"></a>使用PuTTY，以“hbase”用户进入集群的HBase shell界面。
    1.  在已更新客户端的主管理节点，执行以下命令切换到客户端目录。

        **cd /opt/client**

    2.  执行以下命令配置环境变量。

        **source bigdata\_env**

    3.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

        **_kinit hbase_**

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >执行**kinit hbase**后系统提示输入密码，hbase用户默认密码是Hbase@123。  

    4.  直接执行HBase组件的客户端命令。

        **_hbase shell_**



1.  检查备集群上是否已有历史数据？如果有历史数据且需要保持主备集群上的数据完全一致，需要先清理备集群上的数据。
    1.  在备集群的hbase shell界面中，执行**list**命令查看备集群中已经存在的表。
    2.  根据输出列表依次执行**disable** '_tableName_';**drop** '_tableName_'删除备集群上的数据表。

2.  检查配置HBase备份并启用数据同步后，主集群是否已存在表及数据，且历史数据需要同步到备集群？

    执行**list**命令查看主集群中已经存在的表，使用**scan ‘tableName’**命令查看表中是否已经有历史数据

    -   是，存在表且需要同步数据，执行[15](#li4226821210491)。
    -   否，不需要同步数据，任务结束。

3.  <a name="li4226821210491"></a>配置HBase备份时不支持自动同步表中的历史数据，需要对主集群的历史数据进行备份，然后再手动同步历史数据到备集群中。

    手动同步即单表的同步，单表手动同步通过Export、distcp、Import来完成。

    单表手动同步操作步骤：

    1.  从主集群导出表中数据。

        **hbase org.apache.hadoop.hbase.mapreduce.Export -Dhbase.mapreduce.include.deleted.rows=true** _表名 保存源数据的目录_

        例如，**hbase org.apache.hadoop.hbase.mapreduce.Export -Dhbase.mapreduce.include.deleted.rows=true t1 /user/hbase/t1**

    2.  把导出的数据复制到备集群。

        **hadoop distcp** _主集群保存源数据的目录 hdfs://ActiveNameNodeIP:9820/备集群保存源数据的目录_

        其中，ActiveNameNodeIP是备集群中主NameNode节点的IP地址。

        例如，**hadoop distcp /user/hbase/t1 hdfs://192.168.40.2:9820/user/hbase/t1**

    3.  使用备集群HBase表用户，在备集群中导入数据。

        **hbase org.apache.hadoop.hbase.mapreduce.Import** _-Dimport.bulk.output=备集群保存输出的目录 表名 备集群保存源数据的目录_

        **hbase org.apache.hadoop.hbase.mapreduce.LoadIncrementalHFiles** _备集群保存输出的目录 表名_

        例如，**hbase org.apache.hadoop.hbase.mapreduce.Import -Dimport.bulk.output=/user/hbase/output\_t1 t1 /user/hbase/t1**

        **hbase org.apache.hadoop.hbase.mapreduce.LoadIncrementalHFiles /user/hbase/output\_t1 t1**



**添加主备集群备份关系。**

1.  <a name="li46664485154955"></a>在HBase shell中执行如下命令，创建主集群HBase与备集群HBase之间的备份同步关系。

    **add\_peer** '_备集群ID',_ _CLUSTER\_KEY =\>_  '_备集群ZooKeeper地址信息_',**\{HDFS\_CONFS =\> true\}**

    -   备集群ID表示主集群识别备集群使用的id，建议使用字母与数字。
    -   备集群ZooKeeper地址信息包含ZooKeeper业务IP地址、侦听客户端连接的端口和备集群的HBase在ZooKeeper上的根目录。
    -   **\{HDFS\_CONFS =\> true\}**表示将主集群的默认HDFS配置信息同步到对应集群，用于备集群的HBase访问主集群的HDFS。如果不启用Bulkload批量写数据备份，可以不使用此参数。

        例如，添加包含BulkLoad数据的主备集群备份关系，若备集群ID为“replication2”，备集群ZooKeeper地址信息为“**192.168.40.2,192.168.40.3,192.168.40.4:2181:/hbase**”。

        -   针对MRS 2.0.1及之后版本，安全集群请执行：**add\_peer** **'replication2',**CLUSTER\_KEY =\>**** **'192.168.40.2,192.168.40.3,192.168.40.4:2181:/hbase',CONFIG =\> \{ "hbase.regionserver.kerberos.principal" =\> "<val\>", "hbase.master.kerberos.principal" =\> "<val2\>" \}**，普通集群请执行**add\_peer** **'replication2',**CLUSTER\_KEY =\>**** **'192.168.40.2,192.168.40.3,192.168.40.4:2181:/hbase'**

            其中参数“hbase.master.kerberos.principal”和“hbase.regionserver.kerberos.principal”为安全集群中hbase的kerberos用户，可搜索客户端中hbase-site.xml文件得到参数值。例如，客户端安装在master节点的/opt/client下，则可使用命令“grep "kerberos.principal" /opt/client/HBase/hbase/conf/hbase-site.xml -A1”获取，如下图所示。

            **图 1**  获取hbase的principal<a name="fig8470448204618"></a>  
            ![](figures/获取hbase的principal.png "获取hbase的principal")

        -   针对MRS 2.0.1之前版本，仅需执行**：add\_peer** **'replication2',**CLUSTER\_KEY =\>**** **'192.168.40.2,192.168.40.3,192.168.40.4:2181:/hbase'**

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >1.  单击“服务管理 \> ZooKeeper \> 实例”，获取ZooKeeper业务IP地址。  
        >2.  单击“服务管理 \> ZooKeeper \> 服务配置”，“参数类别”选择”全部配置“，搜索获取clientPort,即为侦听客户端连接的端口。  
        >3.  执行**list\_peers**命令判断主备备份关系添加结果，当界面提示以下信息表示成功。  
        >    ```  
        >    hbase(main):003:0> list_peers  
        >    PEER_ID CLUSTER_KEY ENDPOINT_CLASSNAME STATE REPLICATE_ALL NAMESPACES TABLE_CFS BANDWIDTH SERIAL  
        >    replication2 192.168.0.13,192.168.0.177,192.168.0.25:2181:/hbase ENABLED  true   0 false  
        >    ```  
        >    MRS 2.0.1之前的版本，执行"list\_peers"命令后，界面提示以下信息表示成功。  
        >    ```  
        >    hbase(main):003:0> list_peers  
        >    PEER_ID CLUSTER_KEY STATE TABLE_CFS  
        >    replication2 192.168.0.13,192.168.0.177,192.168.0.25:2181:/hbase ENABLED  
        >    ```  



**指定主备集群写数据状态。**

1.  在主集群HBase shell界面，执行以下命令保持写数据状态。

    **set\_clusterState\_active**

    界面提示以下信息表示执行成功：

    ```
    hbase(main):001:0> set_clusterState_active
    => true
    ```

2.  在备集群HBase shell界面，执行以下命令保持只读数据状态。

    **set\_clusterState\_standby**

    界面提示以下信息表示执行成功：

    ```
    hbase(main):001:0> set_clusterState_standby
    => true
    ```


**启用HBase备份功能同步数据。**

1.  检查备集群的HBase服务实例中，是否已存在一个命名空间，与待启用备份功能的HBase表所属的命名空间名称相同？

    在备集群的HBase shell中，执行**list\_namespace**命令 ，查询命名空间。

    -   是，存在同名的命令空间，执行[20](#li15192291154955)。
    -   否，不存在同名的命令空间，需先在备集群的HBase shell中，执行

        **create\_namespace 'ns1'**创建同名的命名空间，然后执行[20](#li15192291154955)。

2.  <a name="li15192291154955"></a>在主集群的HBase shell中，执行以下命令，启用主集群表的数据实时备份功能，确保后续主集群中修改的数据能够实时同步到备集群中。

    一次只能针对一个HTable进行数据同步。

    **enable\_table\_replication '**_表名_**'**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若备集群中不存与要开启实时同步的表同名的表，则该表会自动创建。  
    >-   若备集群中存在与要开启实时同步的表同名的表，则两个表的结构必须一致。  
    >-   若'表名'设置了加密算法SMS4或AES，则不支持对此HBase表启用将数据从主集群实时同步到备集群的功能。  
    >-   若备集群不在线，或备集群中已存在同名但结构不同的表，启用备份功能将失败。  
    >    若备集群不在线，请启动备集群；  
    >    若备集群中已存在同名但结构不同的表，请修改备集群的表结构为相同的表结构。在备集群的HBase shell中，执行**alter**命令，参考示例修改。  

3.  <a name="li3638114154955"></a>在主集群的HBase shell中，执行以下命令，启用主集群的实时备份功能，同步HBase的权限表。

    **enable\_table\_replication 'hbase:acl'**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >主集群HBase源数据表修改权限时，如果备集群需要正常读取数据，请修改备集群角色的权限。  


**检验主备集群数据同步状态。**

1.  在HBase客户端执行以下命令，校验主备集群同步的数据。启用备份同步功能后，也可以执行该命令检验新的同步数据是否一致。

    **hbase org.apache.hadoop.hbase.mapreduce.replication.VerifyReplication --starttime**_=开始时间_ **--endtime**_=结束时间_ _列族名称 备集群ID 表名_

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   开始时间必须早于结束时间。  
    >-   开始时间和结束时间需要填写时间戳的格式，例如执行date -d "2015-09-30 00:00:00" +%s将普通时间转化为时间戳格式。因此命令返回的为10位数字（精确到秒），而HBase识别的为13位（精确到毫秒），所以需要在date命令返回的结果后补上3个0。  

    **主备集群发生倒换**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >1.  当备集群需要被倒换为主集群时，请参见[1](#li1966213718714)\~[11](#li33254619154955)和[16](#li46664485154955)\~[21](#li3638114154955)重新配置主备关系。  
    >2.  勿需执行“同步集群表数据”操作，即[12](#li12641483154955)\~[15](#li4226821210491)。  


## 相关命令<a name="section7753034154955"></a>

**表 2**  HBase备份

<a name="table24016027154955"></a>
<table><thead align="left"><tr id="row21421163154955"><th class="cellrowborder" valign="top" width="15.661566156615661%" id="mcps1.2.4.1.1"><p id="p57392613154955"><a name="p57392613154955"></a><a name="p57392613154955"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="41.7941794179418%" id="mcps1.2.4.1.2"><p id="p18290059154955"><a name="p18290059154955"></a><a name="p18290059154955"></a>命令</p>
</th>
<th class="cellrowborder" valign="top" width="42.544254425442546%" id="mcps1.2.4.1.3"><p id="p5099847154955"><a name="p5099847154955"></a><a name="p5099847154955"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row10434430154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p39882522154955"><a name="p39882522154955"></a><a name="p39882522154955"></a>建立主备关系</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p178961476238"><a name="p178961476238"></a><a name="p178961476238"></a><strong id="b2090110712237"><a name="b2090110712237"></a><a name="b2090110712237"></a>add_peer</strong>&nbsp;<em id="i6317135405414"><a name="i6317135405414"></a><a name="i6317135405414"></a>'备集群ID',CLUSTER_KEY =&gt;</em><em id="i14318135485414"><a name="i14318135485414"></a><a name="i14318135485414"></a>'备集群地址信息'</em></p>
<p id="p1990811762311"><a name="p1990811762311"></a><a name="p1990811762311"></a>示例：</p>
<p id="p990914714230"><a name="p990914714230"></a><a name="p990914714230"></a><strong id="b12182814195517"><a name="b12182814195517"></a><a name="b12182814195517"></a>add_peer '1',CLUSTER_KEY =&gt;</strong> <strong id="b685316772419"><a name="b685316772419"></a><a name="b685316772419"></a>'zk1,zk2,zk3:2181:/hbase'</strong></p>
<p id="p179165712231"><a name="p179165712231"></a><a name="p179165712231"></a><strong id="b9860151935511"><a name="b9860151935511"></a><a name="b9860151935511"></a>add_peer  '1',CLUSTER_KEY =&gt;</strong> <strong id="b84316200242"><a name="b84316200242"></a><a name="b84316200242"></a>'zk1,zk2,zk3:2181:/hbase1'</strong></p>
<p id="p1292615715230"><a name="p1292615715230"></a><a name="p1292615715230"></a>MRS 2.0.1之前的版本建立主备关系命令如下：</p>
<p id="p9994133411135"><a name="p9994133411135"></a><a name="p9994133411135"></a><strong id="b1299417343139"><a name="b1299417343139"></a><a name="b1299417343139"></a>add_peer</strong>&nbsp;<em id="i4996123451316"><a name="i4996123451316"></a><a name="i4996123451316"></a>'备集群ID', '备集群地址信息'</em></p>
<p id="p1799914347139"><a name="p1799914347139"></a><a name="p1799914347139"></a>示例：</p>
<p id="p1711335101319"><a name="p1711335101319"></a><a name="p1711335101319"></a><strong id="b111133501310"><a name="b111133501310"></a><a name="b111133501310"></a>add_peer '1', 'zk1,zk2,zk3:2181:/hbase'</strong></p>
<p id="p1561135151311"><a name="p1561135151311"></a><a name="p1561135151311"></a><strong id="b9843541319"><a name="b9843541319"></a><a name="b9843541319"></a>add_peer  '1', 'zk1,zk2,zk3:2181:/hbase1'</strong></p>
<p id="p7430185310"><a name="p7430185310"></a><a name="p7430185310"></a>注：MRS 1.7以前版本中zookeeper端口为24002，请注意调整。</p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p32979070154955"><a name="p32979070154955"></a><a name="p32979070154955"></a>建立主集群与备集群的关系，让其互相对应。如果启用Bulkload批量写数据备份，则命令为<strong id="b14664114534"><a name="b14664114534"></a><a name="b14664114534"></a>add_peer&nbsp;<em id="i16664315539"><a name="i16664315539"></a><a name="i16664315539"></a>'备集群ID',<em id="i19663612532"><a name="i19663612532"></a><a name="i19663612532"></a>CLUSTER_KEY =&gt;</em></em> '</strong><em id="i14570141925317"><a name="i14570141925317"></a><a name="i14570141925317"></a><strong id="b757081945314"><a name="b757081945314"></a><a name="b757081945314"></a>备集群地址信息</strong><em id="i457019197534"><a name="i457019197534"></a><a name="i457019197534"></a><strong id="b15701819155318"><a name="b15701819155318"></a><a name="b15701819155318"></a>'，</strong></em></em>并配置参数<em id="i615992420163"><a name="i615992420163"></a><a name="i615992420163"></a>"hbase.replication.conf.dir"</em>，同时手动拷贝主集群的hbase相应客户端配置文件到备集群的所有RegionServer节点<strong id="b415972420166"><a name="b415972420166"></a><a name="b415972420166"></a></strong>，详情请参考<a href="#li65160752154955">5</a>~<a href="#li33254619154955">11</a>。</p>
<p id="p1640102532413"><a name="p1640102532413"></a><a name="p1640102532413"></a>MRS 2.0.1之前的版本，当启用Bulkload批量写数据备份，则命令为: <strong id="b154232592418"><a name="b154232592418"></a><a name="b154232592418"></a>add_peer <em id="i043132511248"><a name="i043132511248"></a><a name="i043132511248"></a>'备集群ID',<em id="i8469253242"><a name="i8469253242"></a><a name="i8469253242"></a>'备集群地址信息'</em></em>,{HDFS_CONF =&gt; true}。</strong></p>
</td>
</tr>
<tr id="row16700746154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p10583211154955"><a name="p10583211154955"></a><a name="p10583211154955"></a>移除主备关系</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p51933801154955"><a name="p51933801154955"></a><a name="p51933801154955"></a><strong id="b64751030154955"><a name="b64751030154955"></a><a name="b64751030154955"></a>remove_peer</strong>&nbsp;<em id="i45888363154955"><a name="i45888363154955"></a><a name="i45888363154955"></a>'备集群ID'</em></p>
<p id="p10342090154955"><a name="p10342090154955"></a><a name="p10342090154955"></a>示例：</p>
<p id="p25969946154955"><a name="p25969946154955"></a><a name="p25969946154955"></a><strong id="b32402925154955"><a name="b32402925154955"></a><a name="b32402925154955"></a>remove_peer '1'</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p7391306154955"><a name="p7391306154955"></a><a name="p7391306154955"></a>在主集群中移除备集群的信息。</p>
</td>
</tr>
<tr id="row66521757154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p19553217154955"><a name="p19553217154955"></a><a name="p19553217154955"></a>查询主备关系</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p40306738154955"><a name="p40306738154955"></a><a name="p40306738154955"></a><strong id="b27216322154955"><a name="b27216322154955"></a><a name="b27216322154955"></a>list_peers</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p57038480154955"><a name="p57038480154955"></a><a name="p57038480154955"></a>在主集群中查询已经设置的备集群的信息，主要为Zookeeper信息。</p>
</td>
</tr>
<tr id="row43584280154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p40665823154955"><a name="p40665823154955"></a><a name="p40665823154955"></a>启用用户表实时同步</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p5597329154955"><a name="p5597329154955"></a><a name="p5597329154955"></a><strong id="b50375967154955"><a name="b50375967154955"></a><a name="b50375967154955"></a>enable_table_replication</strong>&nbsp;<em id="i50730520154955"><a name="i50730520154955"></a><a name="i50730520154955"></a>'表名'</em></p>
<p id="p53921503154955"><a name="p53921503154955"></a><a name="p53921503154955"></a>示例：</p>
<p id="p15531484154955"><a name="p15531484154955"></a><a name="p15531484154955"></a><strong id="b5565632154955"><a name="b5565632154955"></a><a name="b5565632154955"></a>enable_table_replication 't1'</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p48163049154955"><a name="p48163049154955"></a><a name="p48163049154955"></a>在主集群中，设置已存在的表同步到备集群。</p>
</td>
</tr>
<tr id="row30814265154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p12927522154955"><a name="p12927522154955"></a><a name="p12927522154955"></a>禁用用户表实时同步</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p40496360154955"><a name="p40496360154955"></a><a name="p40496360154955"></a><strong id="b28922921154955"><a name="b28922921154955"></a><a name="b28922921154955"></a>disable_table_replication</strong>&nbsp;<em id="i58979698154955"><a name="i58979698154955"></a><a name="i58979698154955"></a>'表名'</em></p>
<p id="p61055236154955"><a name="p61055236154955"></a><a name="p61055236154955"></a>示例：</p>
<p id="p12626216154955"><a name="p12626216154955"></a><a name="p12626216154955"></a><strong id="b46527088154955"><a name="b46527088154955"></a><a name="b46527088154955"></a>disable_table_replication 't1'</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p10597780154955"><a name="p10597780154955"></a><a name="p10597780154955"></a>在主集群中，设置已存在的表不同步到备集群。</p>
</td>
</tr>
<tr id="row28271163154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p8262887154955"><a name="p8262887154955"></a><a name="p8262887154955"></a>主备集群数据校验</p>
<p id="p7257127154955"><a name="p7257127154955"></a><a name="p7257127154955"></a></p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p50956389154955"><a name="p50956389154955"></a><a name="p50956389154955"></a><strong id="b555728513477"><a name="b555728513477"></a><a name="b555728513477"></a>bin/hbase org.apache.hadoop.hbase.mapreduce.replication.VerifyReplication --starttime</strong><em id="i55617170154955"><a name="i55617170154955"></a><a name="i55617170154955"></a>=开始时间</em>&nbsp;<strong id="b5693857413477"><a name="b5693857413477"></a><a name="b5693857413477"></a>--endtime=结束时间 列族名称 备集群ID 表名</strong></p>
<p id="p33361377154955"><a name="p33361377154955"></a><a name="p33361377154955"></a></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p17917034154955"><a name="p17917034154955"></a><a name="p17917034154955"></a>检查指定的表在主备集群间的数据是否一致。</p>
<p id="p27035579154955"><a name="p27035579154955"></a><a name="p27035579154955"></a>命令行中参数说明如下：</p>
<a name="ul41993619154955"></a><a name="ul41993619154955"></a><ul id="ul41993619154955"><li>开始时间：如果未设置，则取默认的开始时间为0。</li><li>结束时间：如果未设置，则取默认的结束时间为当前操作提交的时间。</li><li>表名：如果未输入表名，则默认校验所有的启用了实时同步的用户表。</li></ul>
</td>
</tr>
<tr id="row38247654154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p11052256154955"><a name="p11052256154955"></a><a name="p11052256154955"></a>切换数据写入状态</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p22817563154955"><a name="p22817563154955"></a><a name="p22817563154955"></a><strong id="b4031480154955"><a name="b4031480154955"></a><a name="b4031480154955"></a>set_clusterState_active</strong></p>
<p id="p36283327154955"><a name="p36283327154955"></a><a name="p36283327154955"></a><strong id="b58114487154955"><a name="b58114487154955"></a><a name="b58114487154955"></a>set_clusterState_standby</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p9653002154955"><a name="p9653002154955"></a><a name="p9653002154955"></a>设置集群HBase表是否可写入数据。</p>
</td>
</tr>
<tr id="row19768159154955"><td class="cellrowborder" valign="top" width="15.661566156615661%" headers="mcps1.2.4.1.1 "><p id="p57717036154955"><a name="p57717036154955"></a><a name="p57717036154955"></a>新增或更新已经在对端集群保存的主集群中HDFS配置</p>
</td>
<td class="cellrowborder" valign="top" width="41.7941794179418%" headers="mcps1.2.4.1.2 "><p id="p44568321154955"><a name="p44568321154955"></a><a name="p44568321154955"></a><strong id="b65570575154955"><a name="b65570575154955"></a><a name="b65570575154955"></a>set_replication_hdfs_confs 'PeerId', {'key1' =&gt;  'value1', 'key2' =&gt; 'value2'}</strong></p>
</td>
<td class="cellrowborder" valign="top" width="42.544254425442546%" headers="mcps1.2.4.1.3 "><p id="p9616324154955"><a name="p9616324154955"></a><a name="p9616324154955"></a>启用包含Bulkload数据的备份，在主集群修改HDFS参数时，新的参数值默认不会从主集群自动同步到备集群，需要手动执行命令同步。受影响的参数如下：</p>
<a name="ul19438053154955"></a><a name="ul19438053154955"></a><ul id="ul19438053154955"><li>“fs.defaultFS”</li><li>“dfs.client.failover.proxy.provider.hacluster”</li><li>“dfs.client.failover.connection.retries.on.timeouts”</li><li>“dfs.client.failover.connection.retries”</li></ul>
<p id="p34748846154955"><a name="p34748846154955"></a><a name="p34748846154955"></a>例如，“fs.defaultFS”修改为“hdfs://hacluster_sale”，同步HDFS配置到id为1的备集群时执行：<strong id="b44304164154955"><a name="b44304164154955"></a><a name="b44304164154955"></a>set_replication_hdfs_confs '1', {'fs.defaultFS' =&gt; 'hdfs://hacluster_sale'}</strong></p>
<p id="p2172155419011"><a name="p2172155419011"></a><a name="p2172155419011"></a>MRS 2.0.1及其之后的版本该命令已被移除，如需同步，则需手动把主集群中更改的客户端配置拷贝到备集群中，详情请参考<a href="#li3244131341713">8</a>的说明。</p>
</td>
</tr>
</tbody>
</table>

