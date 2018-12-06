# 从零开始使用HBase<a name="ZH-CN_TOPIC_0040912785"></a>

HBase是一个高可靠性、高性能、面向列、可伸缩的分布式存储系统。本章节提供从零开始使用HBase的操作指导，在“mrs\_20160907“集群Master节点中更新客户端，通过客户端实现创建表，往表中插入数据，修改表，读取表数据，删除表中数据以及删除表的功能。

## 背景信息<a name="zh-cn_topic_0037446806_section42481530142855"></a>

MRS集群创建成功后，默认在集群所有节点的“/opt/client“目录安装保存了原始客户端。在使用客户端前，需要先下载客户端文件并更新客户端，确认MRS Manager的主管理节点后才能使用客户端。

假定用户开发一个应用程序，用于管理企业中的使用A业务的用户信息，使用HBase客户端实现A业务操作流程如下：

-   创建用户信息表user\_info。
-   在用户信息中新增用户的学历、职称信息。
-   根据用户编号查询用户姓名和地址。
-   根据用户姓名进行查询。
-   用户销户，删除用户信息表中该用户的数据。
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
<tr id="zh-cn_topic_0037446806_row175293"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0037446806_p14198754"><a name="zh-cn_topic_0037446806_p14198754"></a><a name="zh-cn_topic_0037446806_p14198754"></a>12005000210</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0037446806_p9248440"><a name="zh-cn_topic_0037446806_p9248440"></a><a name="zh-cn_topic_0037446806_p9248440"></a>J</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0037446806_p10926182"><a name="zh-cn_topic_0037446806_p10926182"></a><a name="zh-cn_topic_0037446806_p10926182"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0037446806_p12605589"><a name="zh-cn_topic_0037446806_p12605589"></a><a name="zh-cn_topic_0037446806_p12605589"></a>25</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0037446806_p14419821"><a name="zh-cn_topic_0037446806_p14419821"></a><a name="zh-cn_topic_0037446806_p14419821"></a>J城市</p>
</td>
</tr>
</tbody>
</table>

## 操作步骤<a name="zh-cn_topic_0037446806_section495220663118"></a>

1.  下载客户端配置文件。
    1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击名称为“mrs\_20160907“的集群。“mrs\_20160907“集群为[创建集群](创建集群-入门.md#ZH-CN_TOPIC_0043125076)中创建的集群。
    2.  单击“点击查看“，打开MRS Manager，首次进入MRS Manager需根据提示绑定弹性公网IP及添加安全组规则。
    3.  单击“服务管理“，然后单击“下载客户端“。

        “客户端类型“选择“仅配置文件“，“下载路径“选择“服务器端“，单击“确定“开始生成客户端配置文件，文件生成后默认保存在主管理节点“/tmp/MRS-client”。


2.  登录MRS Manager的主管理节点。
    1.  在“集群列表 \> mrs\_20160907“区域，“节点信息“页签中查看节点名称，名称中包含“master1“的节点为Master1节点，名称中包含“master2“的节点为Master2节点。

        MRS Manager的主备管理节点默认安装在集群Master节点上。在主备模式下，由于Master1和Master2之间会切换，Master1节点不一定是MRS Manager的主管理节点，需要在Master1节点中执行命令，确认MRS Manager的主管理节点。命令请参考[2.d](从零开始使用HBase.md#zh-cn_topic_0037446806_li143162717212)。

    2.   针对MRS1.6.2版本（不包含）前的集群，以**linux**用户使用密码方式登录Master1节点。针对MRS1.6.2版本（包含）后的集群，以**root**用户使用密码方式登录Master1节点。操作方法，请参见《用户指南》中[登录弹性云服务器（VNC方式）](登录弹性云服务器（VNC方式）.md)章节。
    3.  切换至**omm**用户。

        **sudo su - root**

        **su - omm**

    4.  执行以下命令确认MRS Manager的主管理节点。

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

    **cd /opt/client**

4.  执行以下命令，更新主管理节点的客户端配置。

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

5.  在Master节点使用客户端。
    1.  在已更新客户端的主管理节点，例如“192-168-0-30“节点，执行以下命令切换到客户端目录。

        **cd /opt/client**

    2.  执行以下命令配置环境变量。

        **source bigdata\_env**

    3.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

        **kinit MRS 集群用户**

        例如，kinit admin。

    4.  直接执行HBase组件的客户端命令。

        **hbase shell**


6.  运行HBase客户端命令，实现A业务。
    1.  根据[表1](#zh-cn_topic_0037446806_table27353390)创建用户信息表user\_info并添加相关数据。

        **create** '_user\_info_',\{**NAME**  =\> 'i'\}

        以增加编号12005000201的用户信息为例，其他用户信息参照如下命令依次添加：

        **put** '_user\_info_','_12005000201_','_**i:name**_','_A_'

        **put** '_user\_info_','_12005000201_','_**i:gender**_','_Male_'

        **put** '_user\_info_','_12005000201_','_**i:age**_','_19_'

        **put** '_user\_info_','_12005000201_','_**i:address**_','_City A_'

    2.  在用户信息表user\_info中新增用户的学历、职称信息。

        以增加编号为12005000201的用户的学历、职称信息为例，其他用户类似。

        **put** '_user\_info_','_12005000201_','**i:degree**','_master_'

        **put** '_user\_info_','_12005000201_','**i:pose**','_manager_'

    3.  根据用户编号查询用户姓名和地址。

        以查询编号为12005000201的用户姓名和地址为例，其他用户类似。

        **scan**'_user\_info_',\{**STARTROW**=\>'_12005000201_',**STOPROW**=\>'_12005000201_',**COLUMNS**=\>\['**i:name**','**i:address**'\]\}

    4.  根据用户姓名进行查询。

        以查询A用户信息为例，其他用户类似。

        **scan**'_user\_info_',\{**FILTER**=\>"SingleColumnValueFilter\('i','name',=,'binary:_A_'\)"\}

    5.  删除用户信息表中该用户的数据。

        所有用户的数据都需要删除，以删除编号为12005000201的用户数据为例，其他用户类似。

        **delete**'_user\_info_','_12005000201_','i'

    6.  删除用户信息表。

        **disable**'_user\_info_';**drop** '_user\_info_'


7.  终止集群。

    请参见《用户指南》中的[终止集群](终止集群.md)章节。


