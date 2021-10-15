# API概览<a name="mrs_02_0007"></a>

MRS提供的符合RESTful API的设计规范的接口，如[表1](#table19188625114234)和[表2](#table476918443717)所示。如何选择不同版本的接口请参见[API版本选择建议](API版本选择建议.md)。

**表 1**  V2接口

<a name="table19188625114234"></a>
<table><thead align="left"><tr id="row46891655114234"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p46739895163751"><a name="p46739895163751"></a><a name="p46739895163751"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p29122247114234"><a name="p29122247114234"></a><a name="p29122247114234"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p10091830114234"><a name="p10091830114234"></a><a name="p10091830114234"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row18158055133212"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p7159205523219"><a name="p7159205523219"></a><a name="p7159205523219"></a>集群管理接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p131591255133218"><a name="p131591255133218"></a><a name="p131591255133218"></a><a href="创建集群.md">创建集群</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p15340165023320"><a name="p15340165023320"></a><a name="p15340165023320"></a>POST /v2/{project_id}/clusters</p>
</td>
</tr>
<tr id="row317462205211"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p101751422115216"><a name="p101751422115216"></a><a name="p101751422115216"></a>作业对象接口</p>
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
<tr id="row15996151745311"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12312165612534"><a name="p12312165612534"></a><a name="p12312165612534"></a><a href="查询作业列表信息.md">查询作业列表信息</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2312956195313"><a name="p2312956195313"></a><a name="p2312956195313"></a>GET /v2/{project_id}/clusters/{cluster_id}/job-executions</p>
</td>
</tr>
<tr id="row9798201835311"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18312556195313"><a name="p18312556195313"></a><a name="p18312556195313"></a><a href="查询单个作业信息.md">查询单个作业信息</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17312115612534"><a name="p17312115612534"></a><a name="p17312115612534"></a>GET /v2/{project_id}/clusters/{cluster_id}/job-executions/{job_execution_id}</p>
</td>
</tr>
<tr id="row183711192539"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5312115695311"><a name="p5312115695311"></a><a name="p5312115695311"></a><a href="终止作业-0.md">终止作业</a></p>
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
<tr id="row1349974520582"><td class="cellrowborder" rowspan="3" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p115971579016"><a name="p115971579016"></a><a name="p115971579016"></a>SQL接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p549919451582"><a name="p549919451582"></a><a name="p549919451582"></a><a href="提交SQL语句.md">提交SQL语句</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p13499104575815"><a name="p13499104575815"></a><a name="p13499104575815"></a>POST  /v2/{project_id}/clusters/{cluster_id}/sql-execution</p>
</td>
</tr>
<tr id="row106823519585"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p16829519583"><a name="p16829519583"></a><a name="p16829519583"></a><a href="查询SQL结果.md">查询SQL结果</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1775520566412"><a name="p1775520566412"></a><a name="p1775520566412"></a>GET  /v2/{project_id}/clusters/{cluster_id}/sql-execution/{sql_id}</p>
</td>
</tr>
<tr id="row62963525583"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p4296145210587"><a name="p4296145210587"></a><a name="p4296145210587"></a><a href="取消SQL执行任务.md">取消SQL执行任务</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p172961152145810"><a name="p172961152145810"></a><a name="p172961152145810"></a>POST  /v2/{project_id}/clusters/{cluster_id}/sql-execution/{sql_id}/cancel</p>
</td>
</tr>
<tr id="row8396163812916"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1350511391697"><a name="p1350511391697"></a><a name="p1350511391697"></a>集群HDFS文件接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p3505139698"><a name="p3505139698"></a><a name="p3505139698"></a><a href="获取指定目录文件列表.md">获取指定目录文件列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p195052039191"><a name="p195052039191"></a><a name="p195052039191"></a>GET /v2/{project_id}/clusters/{cluster_id}/files?path={directory}&amp;offset={offset}&amp;limit={limit}&amp;sort_key={sort_key}&amp;order={order}</p>
</td>
</tr>
<tr id="row7612763143"><td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p6442151412142"><a name="p6442151412142"></a><a name="p6442151412142"></a>委托管理（V2）</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p20612156141420"><a name="p20612156141420"></a><a name="p20612156141420"></a><a href="查询用户（组）与IAM委托的映射关系.md">查询用户（组）与IAM委托的映射关系</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p8612761143"><a name="p8612761143"></a><a name="p8612761143"></a><span>GET /v2/{project_id}/clusters/{cluster_id}/agency-mapping</span></p>
</td>
</tr>
<tr id="row1114016911410"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p71419971418"><a name="p71419971418"></a><a name="p71419971418"></a><a href="更新用户（组）与IAM委托的映射关系.md">更新用户（组）与IAM委托的映射关系</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p114139191413"><a name="p114139191413"></a><a name="p114139191413"></a><span>PUT /v2/{project_id}/clusters/{cluster_id}/agency-mapping</span></p>
</td>
</tr>
</tbody>
</table>

**表 2**  V1.1接口

<a name="table476918443717"></a>
<table><thead align="left"><tr id="row1769124163712"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p376913414379"><a name="p376913414379"></a><a name="p376913414379"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.2"><p id="p1876917416372"><a name="p1876917416372"></a><a name="p1876917416372"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p176917411373"><a name="p176917411373"></a><a name="p176917411373"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row137706414374"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1477017433712"><a name="p1477017433712"></a><a name="p1477017433712"></a>集群管理接口</p>
<p id="p177706414376"><a name="p177706414376"></a><a name="p177706414376"></a></p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p177024133720"><a name="p177024133720"></a><a name="p177024133720"></a><a href="创建集群并执行作业.md">创建集群并执行作业</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1977013420372"><a name="p1977013420372"></a><a name="p1977013420372"></a>POST /v1.1/{project_id}/run-job-flow</p>
</td>
</tr>
<tr id="row56801846153818"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p176805460381"><a name="p176805460381"></a><a name="p176805460381"></a><a href="调整集群节点.md">调整集群节点</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p368094693814"><a name="p368094693814"></a><a name="p368094693814"></a><span>PUT /v1.1/{project_id}/cluster_infos/{cluster_id}</span></p>
</td>
</tr>
<tr id="row7311546193810"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p5311346163813"><a name="p5311346163813"></a><a name="p5311346163813"></a><a href="查询集群列表.md">查询集群列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1332646143814"><a name="p1332646143814"></a><a name="p1332646143814"></a><span>GET /v1.1/{project_id}/cluster_infos</span></p>
</td>
</tr>
<tr id="row464110230417"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1864692384115"><a name="p1864692384115"></a><a name="p1864692384115"></a><a href="查询集群详情.md">查询集群详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p56461723184120"><a name="p56461723184120"></a><a name="p56461723184120"></a><span>GET /v1.1/{project_id}/cluster_infos/{cluster_id}</span></p>
</td>
</tr>
<tr id="row77701640375"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2077019413376"><a name="p2077019413376"></a><a name="p2077019413376"></a><a href="删除集群-2.md">删除集群</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p2077017433711"><a name="p2077017433711"></a><a name="p2077017433711"></a>DELETE /v1.1/{project_id}/clusters/{cluster_id}</p>
</td>
</tr>
<tr id="row107706413378"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1177064133715"><a name="p1177064133715"></a><a name="p1177064133715"></a><a href="查询主机列表.md">查询主机列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15770124153714"><a name="p15770124153714"></a><a name="p15770124153714"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/hosts</p>
</td>
</tr>
<tr id="row157707413372"><td class="cellrowborder" rowspan="3" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p1277017413715"><a name="p1277017413715"></a><a name="p1277017413715"></a>作业对象接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p577064163717"><a name="p577064163717"></a><a name="p577064163717"></a><a href="新增作业并执行.md">新增作业并执行</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p277017413712"><a name="p277017413712"></a><a name="p277017413712"></a>POST /v1.1/{project_id}/jobs/submit-job</p>
</td>
</tr>
<tr id="row12770124153714"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p67703420378"><a name="p67703420378"></a><a name="p67703420378"></a><a href="查询作业exe对象列表.md">查询作业exe对象列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p57701412377"><a name="p57701412377"></a><a name="p57701412377"></a>GET /v1.1/{project_id}/job-exes</p>
</td>
</tr>
<tr id="row17770243376"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p18770164203711"><a name="p18770164203711"></a><a name="p18770164203711"></a><a href="查询作业exe对象详情.md">查询作业exe对象详情</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1677018415373"><a name="p1677018415373"></a><a name="p1677018415373"></a>GET /v1.1/{project_id}/job-exes/{job_exe_id}</p>
</td>
</tr>
<tr id="row77701548378"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p4770134183717"><a name="p4770134183717"></a><a name="p4770134183717"></a>作业执行对象接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p2770242373"><a name="p2770242373"></a><a name="p2770242373"></a><a href="删除作业执行对象.md">删除作业执行对象</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p11770743376"><a name="p11770743376"></a><a name="p11770743376"></a>DELETE /v1.1/{project_id}/job-executions/{job_execution_id}</p>
</td>
</tr>
<tr id="row1577211443711"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p147729443712"><a name="p147729443712"></a><a name="p147729443712"></a>弹性伸缩接口</p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p1577213463714"><a name="p1577213463714"></a><a name="p1577213463714"></a><a href="配置弹性伸缩规则.md">配置弹性伸缩规则</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p7772114173712"><a name="p7772114173712"></a><a name="p7772114173712"></a>POST /v1.1/{project_id}/autoscaling-policy/{cluster_id}</p>
</td>
</tr>
<tr id="row187721946371"><td class="cellrowborder" rowspan="6" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p197728419372"><a name="p197728419372"></a><a name="p197728419372"></a>标签管理接口</p>
<p id="p19674311405"><a name="p19674311405"></a><a name="p19674311405"></a></p>
</td>
<td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.2 "><p id="p9772849379"><a name="p9772849379"></a><a name="p9772849379"></a><a href="给指定集群添加标签.md">给指定集群添加标签</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p177729423718"><a name="p177729423718"></a><a name="p177729423718"></a>POST /v1.1/{project_id}/clusters/{cluster_id}/tags</p>
</td>
</tr>
<tr id="row1772124183718"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p157721242376"><a name="p157721242376"></a><a name="p157721242376"></a><a href="删除指定集群的标签.md">删除指定集群的标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p20772134113716"><a name="p20772134113716"></a><a name="p20772134113716"></a>DELETE /v1.1/{project_id}/clusters/{cluster_id}/tags/{key}</p>
</td>
</tr>
<tr id="row877215416373"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p477217483712"><a name="p477217483712"></a><a name="p477217483712"></a><a href="查询指定集群的标签.md">查询指定集群的标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p20772194103711"><a name="p20772194103711"></a><a name="p20772194103711"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/tags</p>
</td>
</tr>
<tr id="row377212414374"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1772447371"><a name="p1772447371"></a><a name="p1772447371"></a><a href="批量添加-删除集群标签.md">批量添加/删除集群标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17773184163713"><a name="p17773184163713"></a><a name="p17773184163713"></a>POST /v1.1/{project_id}/clusters/{cluster_id}/tags/action</p>
</td>
</tr>
<tr id="row127734463714"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p277314463719"><a name="p277314463719"></a><a name="p277314463719"></a><a href="查询所有标签.md">查询所有标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p077311412376"><a name="p077311412376"></a><a name="p077311412376"></a>GET /v1.1/{project_id}/clusters/tags</p>
</td>
</tr>
<tr id="row136749115404"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p267471144016"><a name="p267471144016"></a><a name="p267471144016"></a><a href="查询特定标签的集群列表.md">查询特定标签的集群列表</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16748154012"><a name="p16748154012"></a><a name="p16748154012"></a>POST /v1.1/{project_id}/clusters/resource_instances/action</p>
</td>
</tr>
</tbody>
</table>

