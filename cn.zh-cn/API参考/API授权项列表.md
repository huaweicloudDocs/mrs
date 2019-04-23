# API授权项列表<a name="ZH-CN_TOPIC_0146622928"></a>

**表 1**  API授权项列表

<a name="table2037611282232"></a>
<table><thead align="left"><tr id="row10376172872314"><th class="cellrowborder" valign="top" width="38.800000000000004%" id="mcps1.2.5.1.1"><p id="p1537622842319"><a name="p1537622842319"></a><a name="p1537622842319"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="18.05%" id="mcps1.2.5.1.2"><p id="p8376192816237"><a name="p8376192816237"></a><a name="p8376192816237"></a>API功能</p>
</th>
<th class="cellrowborder" valign="top" width="18.15%" id="mcps1.2.5.1.3"><p id="p7376828122311"><a name="p7376828122311"></a><a name="p7376828122311"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p2376122815230"><a name="p2376122815230"></a><a name="p2376122815230"></a>授权作用域</p>
</th>
</tr>
</thead>
<tbody><tr id="row837692812311"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p837642812313"><a name="p837642812313"></a><a name="p837642812313"></a>POST /v1.1/{project_id}/run-job-flow</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p157892532610"><a name="p157892532610"></a><a name="p157892532610"></a>创建集群并执行作业</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p2781225172615"><a name="p2781225172615"></a><a name="p2781225172615"></a>mrs:cluster:create</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul16542832173518"></a><a name="ul16542832173518"></a><ul id="ul16542832173518"><li>支持：<p id="p10785251264"><a name="p10785251264"></a><a name="p10785251264"></a>项目(Project)</p>
<p id="p1278102514264"><a name="p1278102514264"></a><a name="p1278102514264"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row20376112832314"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p14376112802313"><a name="p14376112802313"></a><a name="p14376112802313"></a>PUT /v1.1/{project_id}/cluster_infos/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p278192513264"><a name="p278192513264"></a><a name="p278192513264"></a>调整集群节点</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p157802542613"><a name="p157802542613"></a><a name="p157802542613"></a>mrs:cluster:resize</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul17481131813614"></a><a name="ul17481131813614"></a><ul id="ul17481131813614"><li>支持：<p id="p17483121873610"><a name="p17483121873610"></a><a name="p17483121873610"></a>项目(Project)</p>
<p id="p1748491813360"><a name="p1748491813360"></a><a name="p1748491813360"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row1637615284232"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p9376172812235"><a name="p9376172812235"></a><a name="p9376172812235"></a>GET /v1.1/{project_id}/cluster_infos</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p178225162619"><a name="p178225162619"></a><a name="p178225162619"></a>查询集群列表</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p978182519268"><a name="p978182519268"></a><a name="p978182519268"></a>mrs:cluster:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul17827721103611"></a><a name="ul17827721103611"></a><ul id="ul17827721103611"><li>支持：<p id="p14833621163618"><a name="p14833621163618"></a><a name="p14833621163618"></a>项目(Project)</p>
<p id="p98331021183610"><a name="p98331021183610"></a><a name="p98331021183610"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row1037616283230"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p11251175492616"><a name="p11251175492616"></a><a name="p11251175492616"></a>GET /v1.1/{project_id}/cluster_infos/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p1525125419260"><a name="p1525125419260"></a><a name="p1525125419260"></a>查询集群详情</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p1525125412261"><a name="p1525125412261"></a><a name="p1525125412261"></a>mrs:cluster:get</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul1833102513362"></a><a name="ul1833102513362"></a><ul id="ul1833102513362"><li>支持：<p id="p1936202573617"><a name="p1936202573617"></a><a name="p1936202573617"></a>项目(Project)</p>
<p id="p83614253361"><a name="p83614253361"></a><a name="p83614253361"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row43761928142320"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p1251754162618"><a name="p1251754162618"></a><a name="p1251754162618"></a>DELETE /v1.1/{project_id}/clusters/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p125115411261"><a name="p125115411261"></a><a name="p125115411261"></a>删除集群</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p17251954152611"><a name="p17251954152611"></a><a name="p17251954152611"></a>mrs:cluster:delete</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul6361730113616"></a><a name="ul6361730113616"></a><ul id="ul6361730113616"><li>支持：<p id="p8368173018362"><a name="p8368173018362"></a><a name="p8368173018362"></a>项目(Project)</p>
<p id="p2375193063615"><a name="p2375193063615"></a><a name="p2375193063615"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row893512564257"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p19252195492617"><a name="p19252195492617"></a><a name="p19252195492617"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/hosts</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p32521254202619"><a name="p32521254202619"></a><a name="p32521254202619"></a>查询主机列表</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p172527544268"><a name="p172527544268"></a><a name="p172527544268"></a>mrs:host:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul8942385364"></a><a name="ul8942385364"></a><ul id="ul8942385364"><li>支持：<p id="p1198203843614"><a name="p1198203843614"></a><a name="p1198203843614"></a>项目(Project)</p>
<p id="p1998103819361"><a name="p1998103819361"></a><a name="p1998103819361"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row937662822311"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p725255492620"><a name="p725255492620"></a><a name="p725255492620"></a>POST /v1.1/{project_id}/jobs/submit-job</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p425245418263"><a name="p425245418263"></a><a name="p425245418263"></a>新增作业并执行</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p325255412261"><a name="p325255412261"></a><a name="p325255412261"></a>mrs:job:submit</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul17740204210365"></a><a name="ul17740204210365"></a><ul id="ul17740204210365"><li>支持：<p id="p12743144218369"><a name="p12743144218369"></a><a name="p12743144218369"></a>项目(Project)</p>
<p id="p7743942113618"><a name="p7743942113618"></a><a name="p7743942113618"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row1151210531258"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p1325218547268"><a name="p1325218547268"></a><a name="p1325218547268"></a>GET /v1.1/{project_id}/job-exes</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p1725211544269"><a name="p1725211544269"></a><a name="p1725211544269"></a>查询作业exe对象列表</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p425245419264"><a name="p425245419264"></a><a name="p425245419264"></a>mrs:job:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul16500146113618"></a><a name="ul16500146113618"></a><ul id="ul16500146113618"><li>支持：<p id="p7503846173619"><a name="p7503846173619"></a><a name="p7503846173619"></a>项目(Project)</p>
<p id="p1750314468362"><a name="p1750314468362"></a><a name="p1750314468362"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row52622510251"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p15252135482620"><a name="p15252135482620"></a><a name="p15252135482620"></a>GET /v1.1/{project_id}/job-exes/{job_exe_id}</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p1725210545266"><a name="p1725210545266"></a><a name="p1725210545266"></a>查询作业exe对象详情</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p4252175482610"><a name="p4252175482610"></a><a name="p4252175482610"></a>mrs:job:get</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul7657205015362"></a><a name="ul7657205015362"></a><ul id="ul7657205015362"><li>支持：<p id="p4659125083615"><a name="p4659125083615"></a><a name="p4659125083615"></a>项目(Project)</p>
<p id="p116615507366"><a name="p116615507366"></a><a name="p116615507366"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row1293794816257"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p52535547266"><a name="p52535547266"></a><a name="p52535547266"></a>POST /v1.1/{project_id}/autoscaling-policy/{cluster_id}</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p162533546267"><a name="p162533546267"></a><a name="p162533546267"></a>配置弹性伸缩规则</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p15253254192610"><a name="p15253254192610"></a><a name="p15253254192610"></a>mrs:cluster:policy</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul1188014532364"></a><a name="ul1188014532364"></a><ul id="ul1188014532364"><li>支持：<p id="p48831453163617"><a name="p48831453163617"></a><a name="p48831453163617"></a>项目(Project)</p>
<p id="p488395310362"><a name="p488395310362"></a><a name="p488395310362"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row10260154602515"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p122536541261"><a name="p122536541261"></a><a name="p122536541261"></a>GET /v1.1/{project_id}/clusters/{cluster_id}/tags</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p8253454192618"><a name="p8253454192618"></a><a name="p8253454192618"></a>查询指定集群的标签</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p725319548265"><a name="p725319548265"></a><a name="p725319548265"></a>mrs:tag:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul1928465818368"></a><a name="ul1928465818368"></a><ul id="ul1928465818368"><li>支持：<p id="p182872058123610"><a name="p182872058123610"></a><a name="p182872058123610"></a>项目(Project)</p>
<p id="p6289145817362"><a name="p6289145817362"></a><a name="p6289145817362"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row12378112814237"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p11253135422615"><a name="p11253135422615"></a><a name="p11253135422615"></a>POST /v1.1/{project_id}/clusters/{cluster_id}/tags/action</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p19253195412261"><a name="p19253195412261"></a><a name="p19253195412261"></a>批量添加/删除集群标签</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p16253175410269"><a name="p16253175410269"></a><a name="p16253175410269"></a>mrs:tag:batchOperate</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul19797153719"></a><a name="ul19797153719"></a><ul id="ul19797153719"><li>支持：<p id="p2982161103714"><a name="p2982161103714"></a><a name="p2982161103714"></a>项目(Project)</p>
<p id="p69830163717"><a name="p69830163717"></a><a name="p69830163717"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row5878342162515"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p18254135432619"><a name="p18254135432619"></a><a name="p18254135432619"></a>GET /v1.1/{project_id}/clusters/tags</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p12254195492616"><a name="p12254195492616"></a><a name="p12254195492616"></a>查询所有标签</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p825435482611"><a name="p825435482611"></a><a name="p825435482611"></a>mrs:tag:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul1375585123716"></a><a name="ul1375585123716"></a><ul id="ul1375585123716"><li>支持：<p id="p16759175173716"><a name="p16759175173716"></a><a name="p16759175173716"></a>项目(Project)</p>
<p id="p9760125163719"><a name="p9760125163719"></a><a name="p9760125163719"></a>企业项目(Enterprise Project)</p>
</li><li>不支持：无</li></ul>
</td>
</tr>
<tr id="row8114194052515"><td class="cellrowborder" valign="top" width="38.800000000000004%" headers="mcps1.2.5.1.1 "><p id="p16254165419264"><a name="p16254165419264"></a><a name="p16254165419264"></a>POST /v1.1/{project_id}/clusters/resource_instances/action</p>
</td>
<td class="cellrowborder" valign="top" width="18.05%" headers="mcps1.2.5.1.2 "><p id="p1325435422610"><a name="p1325435422610"></a><a name="p1325435422610"></a>查询特定标签的集群列表</p>
</td>
<td class="cellrowborder" valign="top" width="18.15%" headers="mcps1.2.5.1.3 "><p id="p1125414549265"><a name="p1125414549265"></a><a name="p1125414549265"></a>mrs:tag:listResource</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><a name="ul31616104371"></a><a name="ul31616104371"></a><ul id="ul31616104371"><li>支持：<p id="p0254754102619"><a name="p0254754102619"></a><a name="p0254754102619"></a>项目(Project)</p>
</li><li>不支持：<p id="p8254165462619"><a name="p8254165462619"></a><a name="p8254165462619"></a>企业项目(Enterprise Project)</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

