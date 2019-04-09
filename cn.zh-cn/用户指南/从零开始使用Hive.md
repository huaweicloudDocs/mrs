# 从零开始使用Hive<a name="ZH-CN_TOPIC_0122531563"></a>

Hive是基于Hadoop的一个数据仓库工具，可将结构化的数据文件映射成一张数据库表，并提供类SQL的功能对数据进行分析处理，通过类SQL语句快速实现简单的MapReduce统计，不必开发专门的MapReduce应用，十分适合数据仓库的统计分析。

## 背景信息<a name="section316983143915"></a>

MRS集群创建成功后，默认在集群所有节点的“/opt/client“目录安装保存了原始客户端。在使用客户端前，需要下载并更新客户端配置文件，确认MRS Manager的主管理节点后才能使用客户端。

假定用户开发一个应用程序，用于管理企业中的使用A业务的用户信息，使用Hive客户端实现A业务操作流程如下：

**普通表的操作：**

-   创建用户信息表user\_info。
-   在用户信息中新增用户的学历、职称信息。
-   根据用户编号查询用户姓名和地址。
-   A业务结束后，删除用户信息表。

**表 1**  用户信息

<a name="zh-cn_topic_0037446806_table27353390"></a>
<table><thead align="left"><tr id="zh-cn_topic_0037446806_row32789387"><th class="cellrowborder" valign="top" width="19.998000199980005%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0037446806_p38694667"><a name="zh-cn_topic_0037446806_p38694667"></a><a name="zh-cn_topic_0037446806_p38694667"></a><strong id="zh-cn_topic_0037446806_b12707688"><a name="zh-cn_topic_0037446806_b12707688"></a><a name="zh-cn_topic_0037446806_b12707688"></a>编号</strong></p>
</th>
<th class="cellrowborder" valign="top" width="15.678432156784321%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0037446806_p22689808"><a name="zh-cn_topic_0037446806_p22689808"></a><a name="zh-cn_topic_0037446806_p22689808"></a><strong id="zh-cn_topic_0037446806_b2881685"><a name="zh-cn_topic_0037446806_b2881685"></a><a name="zh-cn_topic_0037446806_b2881685"></a>姓名</strong></p>
</th>
<th class="cellrowborder" valign="top" width="17.558244175582445%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0037446806_p32089967"><a name="zh-cn_topic_0037446806_p32089967"></a><a name="zh-cn_topic_0037446806_p32089967"></a><strong id="zh-cn_topic_0037446806_b20374254"><a name="zh-cn_topic_0037446806_b20374254"></a><a name="zh-cn_topic_0037446806_b20374254"></a>性别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="15.2984701529847%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0037446806_p39701876"><a name="zh-cn_topic_0037446806_p39701876"></a><a name="zh-cn_topic_0037446806_p39701876"></a><strong id="zh-cn_topic_0037446806_b21772565"><a name="zh-cn_topic_0037446806_b21772565"></a><a name="zh-cn_topic_0037446806_b21772565"></a>年龄</strong></p>
</th>
<th class="cellrowborder" valign="top" width="31.46685331466853%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0037446806_p18747312"><a name="zh-cn_topic_0037446806_p18747312"></a><a name="zh-cn_topic_0037446806_p18747312"></a><strong id="zh-cn_topic_0037446806_b34508084"><a name="zh-cn_topic_0037446806_b34508084"></a><a name="zh-cn_topic_0037446806_b34508084"></a>地址</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0037446806_row43691456"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p49347015"><a name="zh-cn_topic_0037446806_p49347015"></a><a name="zh-cn_topic_0037446806_p49347015"></a>12005000201</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p37685299"><a name="zh-cn_topic_0037446806_p37685299"></a><a name="zh-cn_topic_0037446806_p37685299"></a>A</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p32610412"><a name="zh-cn_topic_0037446806_p32610412"></a><a name="zh-cn_topic_0037446806_p32610412"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p24197721"><a name="zh-cn_topic_0037446806_p24197721"></a><a name="zh-cn_topic_0037446806_p24197721"></a>19</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p13858403"><a name="zh-cn_topic_0037446806_p13858403"></a><a name="zh-cn_topic_0037446806_p13858403"></a>A城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row57616766"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p36446461"><a name="zh-cn_topic_0037446806_p36446461"></a><a name="zh-cn_topic_0037446806_p36446461"></a>12005000202</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p66482253"><a name="zh-cn_topic_0037446806_p66482253"></a><a name="zh-cn_topic_0037446806_p66482253"></a>B</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p16353430"><a name="zh-cn_topic_0037446806_p16353430"></a><a name="zh-cn_topic_0037446806_p16353430"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p49559423"><a name="zh-cn_topic_0037446806_p49559423"></a><a name="zh-cn_topic_0037446806_p49559423"></a>23</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p54890288"><a name="zh-cn_topic_0037446806_p54890288"></a><a name="zh-cn_topic_0037446806_p54890288"></a>B城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row24250547"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p18137316"><a name="zh-cn_topic_0037446806_p18137316"></a><a name="zh-cn_topic_0037446806_p18137316"></a>12005000203</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p59836530"><a name="zh-cn_topic_0037446806_p59836530"></a><a name="zh-cn_topic_0037446806_p59836530"></a>C</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p14920772"><a name="zh-cn_topic_0037446806_p14920772"></a><a name="zh-cn_topic_0037446806_p14920772"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p623043"><a name="zh-cn_topic_0037446806_p623043"></a><a name="zh-cn_topic_0037446806_p623043"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p50466518"><a name="zh-cn_topic_0037446806_p50466518"></a><a name="zh-cn_topic_0037446806_p50466518"></a>C城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row51545483"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p14434584"><a name="zh-cn_topic_0037446806_p14434584"></a><a name="zh-cn_topic_0037446806_p14434584"></a>12005000204</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p28350637"><a name="zh-cn_topic_0037446806_p28350637"></a><a name="zh-cn_topic_0037446806_p28350637"></a>D</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p14700275"><a name="zh-cn_topic_0037446806_p14700275"></a><a name="zh-cn_topic_0037446806_p14700275"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p49871633"><a name="zh-cn_topic_0037446806_p49871633"></a><a name="zh-cn_topic_0037446806_p49871633"></a>18</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p13070512"><a name="zh-cn_topic_0037446806_p13070512"></a><a name="zh-cn_topic_0037446806_p13070512"></a>D城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row50525752"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p66054074"><a name="zh-cn_topic_0037446806_p66054074"></a><a name="zh-cn_topic_0037446806_p66054074"></a>12005000205</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p48779793"><a name="zh-cn_topic_0037446806_p48779793"></a><a name="zh-cn_topic_0037446806_p48779793"></a>E</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p58849189"><a name="zh-cn_topic_0037446806_p58849189"></a><a name="zh-cn_topic_0037446806_p58849189"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p2055005"><a name="zh-cn_topic_0037446806_p2055005"></a><a name="zh-cn_topic_0037446806_p2055005"></a>21</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p32237730"><a name="zh-cn_topic_0037446806_p32237730"></a><a name="zh-cn_topic_0037446806_p32237730"></a>E城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row21704116"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p13202999"><a name="zh-cn_topic_0037446806_p13202999"></a><a name="zh-cn_topic_0037446806_p13202999"></a>12005000206</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p62809978"><a name="zh-cn_topic_0037446806_p62809978"></a><a name="zh-cn_topic_0037446806_p62809978"></a>F</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p54443429"><a name="zh-cn_topic_0037446806_p54443429"></a><a name="zh-cn_topic_0037446806_p54443429"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p47841633"><a name="zh-cn_topic_0037446806_p47841633"></a><a name="zh-cn_topic_0037446806_p47841633"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p49967061"><a name="zh-cn_topic_0037446806_p49967061"></a><a name="zh-cn_topic_0037446806_p49967061"></a>F城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row47050372"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p52983808"><a name="zh-cn_topic_0037446806_p52983808"></a><a name="zh-cn_topic_0037446806_p52983808"></a>12005000207</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p63830089"><a name="zh-cn_topic_0037446806_p63830089"></a><a name="zh-cn_topic_0037446806_p63830089"></a>G</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p2854726"><a name="zh-cn_topic_0037446806_p2854726"></a><a name="zh-cn_topic_0037446806_p2854726"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p29906272"><a name="zh-cn_topic_0037446806_p29906272"></a><a name="zh-cn_topic_0037446806_p29906272"></a>29</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p6488958"><a name="zh-cn_topic_0037446806_p6488958"></a><a name="zh-cn_topic_0037446806_p6488958"></a>G城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row58400626"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p32830290"><a name="zh-cn_topic_0037446806_p32830290"></a><a name="zh-cn_topic_0037446806_p32830290"></a>12005000208</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p42007851"><a name="zh-cn_topic_0037446806_p42007851"></a><a name="zh-cn_topic_0037446806_p42007851"></a>H</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p47192740"><a name="zh-cn_topic_0037446806_p47192740"></a><a name="zh-cn_topic_0037446806_p47192740"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p64515557"><a name="zh-cn_topic_0037446806_p64515557"></a><a name="zh-cn_topic_0037446806_p64515557"></a>30</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p58377623"><a name="zh-cn_topic_0037446806_p58377623"></a><a name="zh-cn_topic_0037446806_p58377623"></a>H城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row55636561"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p10267631"><a name="zh-cn_topic_0037446806_p10267631"></a><a name="zh-cn_topic_0037446806_p10267631"></a>12005000209</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p26371793"><a name="zh-cn_topic_0037446806_p26371793"></a><a name="zh-cn_topic_0037446806_p26371793"></a>I</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p55740512"><a name="zh-cn_topic_0037446806_p55740512"></a><a name="zh-cn_topic_0037446806_p55740512"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p18687619"><a name="zh-cn_topic_0037446806_p18687619"></a><a name="zh-cn_topic_0037446806_p18687619"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p37302179"><a name="zh-cn_topic_0037446806_p37302179"></a><a name="zh-cn_topic_0037446806_p37302179"></a>I城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0037446806_row175293"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="p20275141018126"><a name="p20275141018126"></a><a name="p20275141018126"></a>12005000210</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="p7273191071210"><a name="p7273191071210"></a><a name="p7273191071210"></a>J</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="p12194165416015"><a name="p12194165416015"></a><a name="p12194165416015"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="p127221061217"><a name="p127221061217"></a><a name="p127221061217"></a>25</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="p2270910101219"><a name="p2270910101219"></a><a name="p2270910101219"></a>J城市</p>
</td>
</tr>
</tbody>
</table>

## 操作步骤<a name="section16880721113918"></a>

1.  <a name="zh-cn_topic_0037446806_li899018155342"></a>下载客户端配置文件。
    1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击名称为“mrs\_20180707“的集群。“mrs\_20180707“集群为[创建集群](创建集群-入门.md)中创建的集群。
    2.  单击“点击查看“，打开MRS Manager，首次进入MRS Manager需根据提示绑定弹性公网IP及添加安全组规则。
    3.  单击“服务管理“，然后单击“下载客户端“。

        “客户端类型“选择“仅配置文件“，“下载路径“选择“服务器端“，单击“确定“开始生成客户端配置文件，文件生成后默认保存在主管理节点“/tmp/MRS-client”。

        **图 1**  仅下载客户端的配置文件<a name="fig944109133910"></a>  
        ![](figures/仅下载客户端的配置文件.png "仅下载客户端的配置文件")


2.  登录MRS Manager的主管理节点。
    1.  在“集群列表 \> mrs\_20180707“区域，“节点信息“页签中查看节点名称，名称中包含“master1“的节点为Master1节点，名称中包含“master2“的节点为Master2节点。

        MRS Manager的主备管理节点默认安装在集群Master节点上。在主备模式下，由于Master1和Master2之间会切换，Master1节点不一定是MRS Manager的主管理节点，需要在Master1节点中执行命令，确认MRS Manager的主管理节点。命令请参考[2.d](#zh-cn_topic_0037446806_li143162717212)。

    2.   针对MRS1.6.2版本（不包含）前的集群，以**linux**用户使用密码方式登录Master1节点。针对MRS1.6.2版本（包含）后的集群，以**root**用户使用密码方式登录Master1节点。操作方法，请参见《用户指南》中[登录弹性云服务器（VNC方式）](登录弹性云服务器（VNC方式）.md)章节。
    3.  切换至**omm**用户。

        **sudo su - root**

        **su - omm**

    4.  <a name="zh-cn_topic_0037446806_li143162717212"></a>执行以下命令确认MRS Manager的主管理节点。

        **sh $\{BIGDATA\_HOME\}/om-0.0.1/sbin/status-oms.sh**

        回显信息中“HAActive“参数值为“active“的节点为主管理节点（如下例中“mgtomsdat-sh-3-01-1”为主管理节点），参数值为“standby“的节点为备管理节点（如下例中“mgtomsdat-sh-3-01-2”为备管理节点）。

        ```
        Ha mode
        double
        NodeName              HostName                      HAVersion          StartTime                HAActive             HAAllResOK           HARunPhase 
        192-168-0-30          mgtomsdat-sh-3-01-1           V100R001C01        2014-11-18 23:43:02      active               normal               Actived    
        192-168-0-24          mgtomsdat-sh-3-01-2           V100R001C01        2014-11-21 07:14:02      standby              normal               Deactived
        ```

    5.  使用**root**用户登录MRS Manager的主管理节点，例如“192-168-0-30“节点。

3.  执行以下命令切换到客户端安装目录。

    MRS集群创建成功后，客户端默认安装在“/opt/client“目录下。

    cd /opt/client

4.  <a name="li15639738131312"></a>执行以下命令，更新主管理节点的客户端配置。

    切换到**omm**用户。

    **sudo su - omm**

    **sh refreshConfig.sh /opt/client** _客户端配置文件压缩包完整路径_

    例如，执行命令：

    **sh refreshConfig.sh /opt/client /tmp/MRS-client/MRS\_Services\_Client.tar**

    界面显示以下信息表示配置刷新更新成功：

    ```
     ReFresh components client config is complete.
     Succeed to refresh components client config.
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >对于MRS 1.8.3版本和MRS 2.0.0之后版本集群，步骤[1](#zh-cn_topic_0037446806_li899018155342)\~[4](#li15639738131312)的操作也可以参考[更新客户端](更新客户端.md)页面的方法二操作。  

5.  在Master节点使用客户端。
    1.  在已更新客户端的主管理节点，例如“192-168-0-30“节点，执行以下命令切换到客户端目录。

        **cd /opt/client**

    2.  执行以下命令配置环境变量。

        **source bigdata\_env**

    3.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户，当前用户需要具有创建Hive表的权限，具体请参见[创建角色](创建角色-安全.md)配置拥有对应权限的角色，参考[创建用户](创建用户-安全.md)为用户绑定对应角色。如果当前集群未启用Kerberos认证，则无需执行此命令。

        **kinit MRS集群用户**

        例如，kinit admin。

    4.  直接执行Hive组件的客户端命令。

        **beeline**


6.  运行Hive客户端命令，实现A业务。

    **内部表的操作：**

    1. 根据[表1](#zh-cn_topic_0037446806_table27353390)创建用户信息表user\_info并添加相关数据。

    create table user\_info\(id string,name string,gender string,age int,addr string\);

    insert into table user\_info\(id,name,gender,age,addr\) values\("12005000201","A","男","19","A城市"\);

    ......（其他语句相同）

    2. 在用户信息表user\_info中新增用户的学历、职称信息。

    以增加编号为12005000201的用户的学历、职称信息为例，其他用户类似。

    alter table user\_info add columns\(education string,technical string\);

    3.根据用户编号查询用户姓名和地址。

    以查询编号为12005000201的用户姓名和地址为例，其他用户类似。

    select name,addr from user\_info where id='12005000201';

    4.删除用户信息表。

    drop table user\_info;

    **外部分区表的操作：**

    创建外部分区表并导入数据：

    1.创建外部表数据存储路径：

    hdfs dfs -mkdir /hive/user\_info

    2.建表：

    create external table user\_info\(id string,name string,gender string,age int,addr string\) partitioned by\(year string\) row format delimited fields terminated by ' ' lines terminated by '\\n' stored as textfile location '/hive/user\_info';

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >fields terminated指明分隔的字符,如按空格分隔，' '。  
    >lines terminated 指明分行的字符，如按换行分隔，'\\n'。  
    >/hive/user\_info为数据文件的路径。  

    3.导入数据。

    3.1.使用insert语句插入数据。

    insert into user\_info partition\(year="2018"\) values \("12005000201","A","男","19","A城市"\);

    3.2使用load data命令导入文件数据。

    3.2.1.根据[表1](#zh-cn_topic_0037446806_table27353390)数据创建文件。如，文件名为txt.log，以空格拆分字段，以换行符作为行分隔符。

    3.2.2.上传文件至hdfs。

    hdfs dfs -put txt.log /tmp

    3.2.3.加载数据到表中。

    load data inpath '/tmp/txt.log' into table user\_info partition \(year='2011'\);

    4.查询导入数据。

    select \* from user\_info;

    5..删除用户信息表。

    drop table user\_info;

7.  删除集群。

    请参见《用户指南》中的[删除集群](删除集群.md)章节。


