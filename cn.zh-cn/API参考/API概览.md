# API概览<a name="ZH-CN_TOPIC_0172486224"></a>

MRS提供的符合RESTful API的设计规范的接口，如[表1](#table19188625114234)所示。

**表 1**  接口

<a name="table19188625114234"></a>
<table><thead align="left"><tr id="row46891655114234"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p46739895163751"><a name="p46739895163751"></a><a name="p46739895163751"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p29122247114234"><a name="p29122247114234"></a><a name="p29122247114234"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p10091830114234"><a name="p10091830114234"></a><a name="p10091830114234"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row53528912114234"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p66734216388"><a name="p66734216388"></a><a name="p66734216388"></a>集群管理接口</p>
<p id="p521334011245"><a name="p521334011245"></a><a name="p521334011245"></a></p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1281148114234"><a name="p1281148114234"></a><a name="p1281148114234"></a><a href="创建集群并执行作业.md">创建集群并执行作业</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p61542071114234"><a name="p61542071114234"></a><a name="p61542071114234"></a>POST /v1.1/{project_id}/run-job-flow</p>
</td>
</tr>
<tr id="row17007731114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p35448961114234"><a name="p35448961114234"></a><a name="p35448961114234"></a><a href="调整集群节点.md">调整集群节点</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p5380317114234"><a name="p5380317114234"></a><a name="p5380317114234"></a>PUT /v1.1/{project_id}/cluster_infos/{cluster_id}</p>
</td>
</tr>
<tr id="row48422859114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p29937495114234"><a name="p29937495114234"></a><a name="p29937495114234"></a><a href="查询集群列表.md">查询集群列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14053056114234"><a name="p14053056114234"></a><a name="p14053056114234"></a>GET /v1.1/{project_id}/cluster_infos</p>
</td>
</tr>
<tr id="row59368643114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p44130804114234"><a name="p44130804114234"></a><a name="p44130804114234"></a><a href="查询集群详情.md">查询集群详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p26210967114234"><a name="p26210967114234"></a><a name="p26210967114234"></a>GET /v1.1/{project_id}/cluster_infos/{cluster_id}</p>
</td>
</tr>
<tr id="row34572116114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p48878035114234"><a name="p48878035114234"></a><a name="p48878035114234"></a><a href="删除集群.md">删除集群</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p64389915114234"><a name="p64389915114234"></a><a name="p64389915114234"></a>DELETE /v1.1/{project_id}/clusters/{cluster_id}</p>
</td>
</tr>
<tr id="row4728911811245"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1962739911245"><a name="p1962739911245"></a><a name="p1962739911245"></a><a href="查询主机列表.md">查询主机列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p4631546211245"><a name="p4631546211245"></a><a name="p4631546211245"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/hosts</p>
</td>
</tr>
<tr id="row6090042114234"><td class="cellrowborder" rowspan="3" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p24986229163815"><a name="p24986229163815"></a><a name="p24986229163815"></a>作业对象接口（V1）</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p41642070114234"><a name="p41642070114234"></a><a name="p41642070114234"></a><a href="新增作业并执行.md">新增作业并执行</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p23863027114234"><a name="p23863027114234"></a><a name="p23863027114234"></a>POST /v1.1/{project_id}/jobs/submit-job</p>
</td>
</tr>
<tr id="row8518062114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18874453114234"><a name="p18874453114234"></a><a name="p18874453114234"></a><a href="查询作业exe对象列表.md">查询作业exe对象列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2159141114234"><a name="p2159141114234"></a><a name="p2159141114234"></a>GET /v1.1/{project_id}/job-exes</p>
</td>
</tr>
<tr id="row19432270114234"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p30510066114234"><a name="p30510066114234"></a><a name="p30510066114234"></a><a href="查询作业exe对象详情.md">查询作业exe对象详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p28804495114234"><a name="p28804495114234"></a><a name="p28804495114234"></a>GET /v1.1/{project_id}/job-exes/{job_exe_id}</p>
</td>
</tr>
<tr id="row52627792114234"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p15580262163751"><a name="p15580262163751"></a><a name="p15580262163751"></a>作业执行对象接口（V1）</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p34992729114234"><a name="p34992729114234"></a><a name="p34992729114234"></a><a href="删除作业执行对象.md">删除作业执行对象</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p8331133114234"><a name="p8331133114234"></a><a name="p8331133114234"></a>DELETE /v1.1/{project_id}/job-executions/{job_execution_id}</p>
</td>
</tr>
<tr id="row317462205211"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p101751422115216"><a name="p101751422115216"></a><a name="p101751422115216"></a>作业对象接口（V2）</p>
<p id="p9996717175311"><a name="p9996717175311"></a><a name="p9996717175311"></a></p>
<p id="p1479871885314"><a name="p1479871885314"></a><a name="p1479871885314"></a></p>
<p id="p6371131914537"><a name="p6371131914537"></a><a name="p6371131914537"></a></p>
<p id="p1187611945318"><a name="p1187611945318"></a><a name="p1187611945318"></a></p>
<p id="p8989226145313"><a name="p8989226145313"></a><a name="p8989226145313"></a></p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1231195605313"><a name="p1231195605313"></a><a name="p1231195605313"></a><a href="新增并执行作业.md">新增并执行作业</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p9311185665319"><a name="p9311185665319"></a><a name="p9311185665319"></a>POST /v2/{project_id}/clusters/{cluster_id}/job-executions</p>
</td>
</tr>
<tr id="row15996151745311"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12312165612534"><a name="p12312165612534"></a><a name="p12312165612534"></a><a href="查询单个作业信息.md">查询单个作业信息</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2312956195313"><a name="p2312956195313"></a><a name="p2312956195313"></a>GET /v2/{project_id}/clusters/{cluster_id}/job-executions</p>
</td>
</tr>
<tr id="row9798201835311"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18312556195313"><a name="p18312556195313"></a><a name="p18312556195313"></a><a href="查询作业列表信息.md">查询作业列表信息</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17312115612534"><a name="p17312115612534"></a><a name="p17312115612534"></a>GET /v2/{project_id}/clusters/{cluster_id}/job-executions</p>
</td>
</tr>
<tr id="row183711192539"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5312115695311"><a name="p5312115695311"></a><a name="p5312115695311"></a><a href="终止作业.md">终止作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p931245665312"><a name="p931245665312"></a><a name="p931245665312"></a>POST /v2/{project_id}/clusters/{cluster_id}/job-executions/{job_execution_id}/kill</p>
</td>
</tr>
<tr id="row13876191945315"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15314205685319"><a name="p15314205685319"></a><a name="p15314205685319"></a><a href="批量删除作业.md">批量删除作业</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p83141356195317"><a name="p83141356195317"></a><a name="p83141356195317"></a>POST /v2/{project_id}/clusters/{cluster_id}/job-executions/batch-delete</p>
</td>
</tr>
<tr id="row169891626195318"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p7314115615320"><a name="p7314115615320"></a><a name="p7314115615320"></a><a href="获取SQL结果.md">获取SQL结果</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p53148566530"><a name="p53148566530"></a><a name="p53148566530"></a>GET /v2/{project_id}/clusters/{cluster_id}/job-executions/{job_execution_id}/sql-result</p>
</td>
</tr>
<tr id="row841247510304"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1454235624212"><a name="p1454235624212"></a><a name="p1454235624212"></a>弹性伸缩接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p2578801610304"><a name="p2578801610304"></a><a name="p2578801610304"></a><a href="配置弹性伸缩规则.md">配置弹性伸缩规则</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p845458610304"><a name="p845458610304"></a><a name="p845458610304"></a>POST /v1.1/{project_id}/autoscaling-policy/{cluster_id}</p>
</td>
</tr>
<tr id="row1394256135919"><td class="cellrowborder" rowspan="4" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1716214121306"><a name="p1716214121306"></a><a name="p1716214121306"></a>标签管理接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p69495675912"><a name="p69495675912"></a><a name="p69495675912"></a><a href="查询指定集群的标签.md">查询指定集群的标签</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p439773114615"><a name="p439773114615"></a><a name="p439773114615"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/tags</p>
</td>
</tr>
<tr id="row19628155375918"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16628753125917"><a name="p16628753125917"></a><a name="p16628753125917"></a><a href="批量添加-删除集群标签.md">批量添加/删除集群标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p78391839134618"><a name="p78391839134618"></a><a name="p78391839134618"></a>POST /v1.1/{project_id}/clusters/{cluster_id}/tags/action</p>
</td>
</tr>
<tr id="row89495507598"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1095014508597"><a name="p1095014508597"></a><a name="p1095014508597"></a><a href="查询所有标签.md">查询所有标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1077864918464"><a name="p1077864918464"></a><a name="p1077864918464"></a>GET /v1.1/{project_id}/clusters/tags</p>
</td>
</tr>
<tr id="row7556948185917"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1655634845916"><a name="p1655634845916"></a><a name="p1655634845916"></a><a href="查询特定标签的集群列表.md">查询特定标签的集群列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p11164185874614"><a name="p11164185874614"></a><a name="p11164185874614"></a>POST /v1.1/{project_id}/clusters/resource_instances/action</p>
</td>
</tr>
</tbody>
</table>

