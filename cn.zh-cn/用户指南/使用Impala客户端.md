# 使用Impala客户端<a name="mrs_01_24190"></a>

Impala是用于处理存储在Hadoop集群中的大量数据的MPP（大规模并行处理）SQL查询引擎。 它是一个用C++和Java编写的开源软件。 与其他Hadoop的SQL引擎相比，它拥有高性能和低延迟的特点。

## 背景信息<a name="zh-cn_topic_0264266132_section316983143915"></a>

假定用户开发一个应用程序，用于管理企业中的使用A业务的用户信息，使用Impala客户端实现A业务操作流程如下：

**普通表的操作：**

-   创建用户信息表user\_info。
-   在用户信息中新增用户的学历、职称信息。
-   根据用户编号查询用户姓名和地址。
-   A业务结束后，删除用户信息表。

**表 1**  用户信息

<a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_table27353390"></a>
<table><thead align="left"><tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row32789387"><th class="cellrowborder" valign="top" width="19.998000199980005%" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p38694667"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p38694667"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p38694667"></a><strong id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b12707688"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b12707688"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b12707688"></a>编号</strong></p>
</th>
<th class="cellrowborder" valign="top" width="15.678432156784321%" id="mcps1.2.6.1.2"><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p22689808"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p22689808"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p22689808"></a><strong id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b2881685"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b2881685"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b2881685"></a>姓名</strong></p>
</th>
<th class="cellrowborder" valign="top" width="17.558244175582445%" id="mcps1.2.6.1.3"><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32089967"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32089967"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32089967"></a><strong id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b20374254"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b20374254"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b20374254"></a>性别</strong></p>
</th>
<th class="cellrowborder" valign="top" width="15.2984701529847%" id="mcps1.2.6.1.4"><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p39701876"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p39701876"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p39701876"></a><strong id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b21772565"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b21772565"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b21772565"></a>年龄</strong></p>
</th>
<th class="cellrowborder" valign="top" width="31.46685331466853%" id="mcps1.2.6.1.5"><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18747312"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18747312"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18747312"></a><strong id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b34508084"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b34508084"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_b34508084"></a>地址</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row43691456"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49347015"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49347015"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49347015"></a>12005000201</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37685299"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37685299"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37685299"></a>A</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32610412"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32610412"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32610412"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p24197721"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p24197721"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p24197721"></a>19</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13858403"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13858403"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13858403"></a>A城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row57616766"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p36446461"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p36446461"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p36446461"></a>12005000202</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66482253"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66482253"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66482253"></a>B</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p16353430"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p16353430"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p16353430"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49559423"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49559423"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49559423"></a>23</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54890288"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54890288"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54890288"></a>B城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row24250547"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18137316"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18137316"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18137316"></a>12005000203</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p59836530"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p59836530"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p59836530"></a>C</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14920772"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14920772"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14920772"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p623043"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p623043"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p623043"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p50466518"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p50466518"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p50466518"></a>C城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row51545483"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14434584"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14434584"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14434584"></a>12005000204</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p28350637"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p28350637"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p28350637"></a>D</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14700275"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14700275"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p14700275"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49871633"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49871633"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49871633"></a>18</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13070512"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13070512"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13070512"></a>D城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row50525752"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66054074"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66054074"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p66054074"></a>12005000205</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p48779793"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p48779793"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p48779793"></a>E</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58849189"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58849189"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58849189"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2055005"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2055005"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2055005"></a>21</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32237730"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32237730"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32237730"></a>E城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row21704116"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13202999"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13202999"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p13202999"></a>12005000206</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p62809978"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p62809978"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p62809978"></a>F</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54443429"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54443429"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p54443429"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47841633"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47841633"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47841633"></a>32</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49967061"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49967061"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p49967061"></a>F城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row47050372"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p52983808"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p52983808"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p52983808"></a>12005000207</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p63830089"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p63830089"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p63830089"></a>G</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2854726"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2854726"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p2854726"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p29906272"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p29906272"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p29906272"></a>29</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p6488958"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p6488958"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p6488958"></a>G城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row58400626"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32830290"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32830290"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p32830290"></a>12005000208</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p42007851"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p42007851"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p42007851"></a>H</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47192740"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47192740"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p47192740"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p64515557"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p64515557"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p64515557"></a>30</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58377623"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58377623"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p58377623"></a>H城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row55636561"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p10267631"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p10267631"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p10267631"></a>12005000209</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p26371793"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p26371793"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p26371793"></a>I</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p55740512"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p55740512"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p55740512"></a>男</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18687619"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18687619"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p18687619"></a>26</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37302179"><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37302179"></a><a name="zh-cn_topic_0264266132_zh-cn_topic_0037446806_p37302179"></a>I城市</p>
</td>
</tr>
<tr id="zh-cn_topic_0264266132_zh-cn_topic_0037446806_row175293"><td class="cellrowborder" valign="top" width="19.998000199980005%" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0264266132_p20275141018126"><a name="zh-cn_topic_0264266132_p20275141018126"></a><a name="zh-cn_topic_0264266132_p20275141018126"></a>12005000210</p>
</td>
<td class="cellrowborder" valign="top" width="15.678432156784321%" headers="mcps1.2.6.1.2 "><p id="zh-cn_topic_0264266132_p7273191071210"><a name="zh-cn_topic_0264266132_p7273191071210"></a><a name="zh-cn_topic_0264266132_p7273191071210"></a>J</p>
</td>
<td class="cellrowborder" valign="top" width="17.558244175582445%" headers="mcps1.2.6.1.3 "><p id="zh-cn_topic_0264266132_p12194165416015"><a name="zh-cn_topic_0264266132_p12194165416015"></a><a name="zh-cn_topic_0264266132_p12194165416015"></a>女</p>
</td>
<td class="cellrowborder" valign="top" width="15.2984701529847%" headers="mcps1.2.6.1.4 "><p id="zh-cn_topic_0264266132_p127221061217"><a name="zh-cn_topic_0264266132_p127221061217"></a><a name="zh-cn_topic_0264266132_p127221061217"></a>25</p>
</td>
<td class="cellrowborder" valign="top" width="31.46685331466853%" headers="mcps1.2.6.1.5 "><p id="zh-cn_topic_0264266132_p2270910101219"><a name="zh-cn_topic_0264266132_p2270910101219"></a><a name="zh-cn_topic_0264266132_p2270910101219"></a>J城市</p>
</td>
</tr>
</tbody>
</table>

## 前提条件<a name="zh-cn_topic_0264266132_section1022821213273"></a>

已安装客户端，例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

## 操作步骤<a name="zh-cn_topic_0264266132_section10873172642318"></a>

1.  以客户端安装用户，登录安装客户端的节点。
2.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

3.  执行以下命令配置环境变量。

    **source bigdata\_env**

4.  运行Impala客户端命令，实现A业务。

    直接执行Impala组件的客户端命令：

    **impala-shell**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >默认情况下，**impala-shell**尝试连接到localhost的21000端口上的Impala守护程序。如需连接到其他主机，请使用**-i <host:port\>**选项，例如：impala-shell -i xxx.xxx.xxx.xxx:21000。要自动连接到特定的Impala数据库，请使用**-d <database\>**选项。例如，如果您的所有Kudu表都位于数据库“impala\_kudu”中，则**-d impala\_kudu**可以使用此数据库。要退出Impala Shell，请使用**quit**命令。

    **内部表的操作：**

    1.  根据[表1](#zh-cn_topic_0264266132_zh-cn_topic_0037446806_table27353390)创建用户信息表user\_info并添加相关数据。

        ```
        create table user_info(id string,name string,gender string,age int,addr string);
        insert into table user_info(id,name,gender,age,addr) values("12005000201","A","男",19,"A城市");
        ```

        ......（其他语句相同）

    2.  在用户信息表user\_info中新增用户的学历、职称信息。

        以增加编号为12005000201的用户的学历、职称信息为例，其他用户类似。

        ```
        alter table user_info add columns(education string,technical string);
        ```

    3.  根据用户编号查询用户姓名和地址。

        以查询编号为12005000201的用户姓名和地址为例，其他用户类似。

        ```
        select name,addr from user_info where id='12005000201';
        ```

    4.  删除用户信息表。

        ```
        drop table user_info;
        ```

    **外部分区表的操作：**

    创建外部分区表并导入数据

    1.  创建外部表数据存储路径。

        **hdfs dfs -mkdir /hive**

        **hdfs dfs -mkdir /hive/user\_info**

    2.  建表。

        ```
        create external table user_info(id string,name string,gender string,age int,addr string) partitioned by(year string) row format delimited fields terminated by ' ' lines terminated by '\n' stored as textfile location '/hive/user_info';
        ```

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >fields terminated指明分隔的字符,如按空格分隔，' '。
        >lines terminated 指明分行的字符，如按换行分隔，'\\n'。
        >/hive/user\_info为数据文件的路径。

    3.  导入数据。
        1.  使用insert语句插入数据。

            ```
            insert into user_info partition(year="2018") values ("12005000201","A","男",19,"A城市");
            ```

        2.  使用load data命令导入文件数据。
            1.  根据[表1](#zh-cn_topic_0264266132_zh-cn_topic_0037446806_table27353390)数据创建文件。如，文件名为txt.log，以空格拆分字段，以换行符作为行分隔符。
            2.  上传文件至hdfs。

                **hdfs dfs -put txt.log /tmp**

            3.  加载数据到表中。

                **load data inpath '/tmp/txt.log' into table user\_info partition \(year='2018'\);**


    4.  查询导入数据。

        ```
        select * from user_info;
        ```

    5.  删除用户信息表。

        ```
        drop table user_info;
        ```



