# 查询作业exe对象列表<a name="ZH-CN_TOPIC_0109962607"></a>

## 功能介绍<a name="section40666287163540"></a>

查询所有作业的exe对象列表。该接口不兼容Sahara。

## URI<a name="section25682805163556"></a>

-   URI格式

    GET /v1.1/\{project\_id\}/job-exes

-   参数说明

    **表 1**  URI参数说明

    <a name="table49499141194754"></a>
    <table><thead align="left"><tr id="row33700024194754"><th class="cellrowborder" valign="top" width="33.33%" id="mcps1.2.4.1.1"><p id="p16571835194812"><a name="p16571835194812"></a><a name="p16571835194812"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.98%" id="mcps1.2.4.1.2"><p id="p141410194812"><a name="p141410194812"></a><a name="p141410194812"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.69%" id="mcps1.2.4.1.3"><p id="p11454278194812"><a name="p11454278194812"></a><a name="p11454278194812"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row12931900144556"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p40851019144556"><a name="p40851019144556"></a><a name="p40851019144556"></a>project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p20598275144556"><a name="p20598275144556"></a><a name="p20598275144556"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p57847563144556"><a name="p57847563144556"></a><a name="p57847563144556"></a>项目编号。获取方法，请参见<a href="获取项目编号.md">获取项目编号</a>。</p>
    </td>
    </tr>
    <tr id="row35752174172358"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p8897384172437"><a name="p8897384172437"></a><a name="p8897384172437"></a>cluster_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p25096105172358"><a name="p25096105172358"></a><a name="p25096105172358"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p19518602172358"><a name="p19518602172358"></a><a name="p19518602172358"></a>集群编号。</p>
    </td>
    </tr>
    <tr id="row38478540172358"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p10762543172358"><a name="p10762543172358"></a><a name="p10762543172358"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p66459692172358"><a name="p66459692172358"></a><a name="p66459692172358"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p14525961172358"><a name="p14525961172358"></a><a name="p14525961172358"></a>作业执行对象的编号。</p>
    </td>
    </tr>
    <tr id="row37407495194754"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p15101241163039"><a name="p15101241163039"></a><a name="p15101241163039"></a>page_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p18389069163039"><a name="p18389069163039"></a><a name="p18389069163039"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p43193283194011"><a name="p43193283194011"></a><a name="p43193283194011"></a>分页查询每页返回的最大作业数量。</p>
    <p id="p29751386163039"><a name="p29751386163039"></a><a name="p29751386163039"></a>取值范围：[1～100]</p>
    </td>
    </tr>
    <tr id="row35367419193832"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p46188714193832"><a name="p46188714193832"></a><a name="p46188714193832"></a>current_page</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p440986719390"><a name="p440986719390"></a><a name="p440986719390"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p47634477193832"><a name="p47634477193832"></a><a name="p47634477193832"></a>当前查询页码。</p>
    </td>
    </tr>
    <tr id="row693784194754"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p56196540194754"><a name="p56196540194754"></a><a name="p56196540194754"></a>job_name</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p3914081919390"><a name="p3914081919390"></a><a name="p3914081919390"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p4074171193913"><a name="p4074171193913"></a><a name="p4074171193913"></a>作业名称。</p>
    </td>
    </tr>
    <tr id="row56520805193848"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.4.1.1 "><p id="p14782481193848"><a name="p14782481193848"></a><a name="p14782481193848"></a>state</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.98%" headers="mcps1.2.4.1.2 "><p id="p2369909219390"><a name="p2369909219390"></a><a name="p2369909219390"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.69%" headers="mcps1.2.4.1.3 "><p id="p57659102193943"><a name="p57659102193943"></a><a name="p57659102193943"></a>作业状态编码：</p>
    <a name="ul29263952193948"></a><a name="ul29263952193948"></a><ul id="ul29263952193948"><li>-1：Terminated<span id="ph23950039172554"><a name="ph23950039172554"></a><a name="ph23950039172554"></a>表示已终止的作业状态</span></li><li>2：Running<span id="ph54215248172549"><a name="ph54215248172549"></a><a name="ph54215248172549"></a>表示运行中的作业状态</span></li><li>3：Completed<span id="ph10697548172546"><a name="ph10697548172546"></a><a name="ph10697548172546"></a>表示已完成的作业状态</span></li><li>4：Abnormal<span id="ph1654186172542"><a name="ph1654186172542"></a><a name="ph1654186172542"></a>表示异常的作业状态</span></li></ul>
    </td>
    </tr>
    </tbody>
    </table>


## 请求消息<a name="section7976792193238"></a>

**请求参数**

无。

## 响应消息<a name="section38599577193858"></a>

**响应参数**

响应参数如[表2](#table5154210817547)所示。

**表 2**  响应参数说明

<a name="table5154210817547"></a>
<table><thead align="left"><tr id="row5182537317547"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p32664405195759"><a name="p32664405195759"></a><a name="p32664405195759"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p46043636195759"><a name="p46043636195759"></a><a name="p46043636195759"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p28269015195759"><a name="p28269015195759"></a><a name="p28269015195759"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p5931773195759"><a name="p5931773195759"></a><a name="p5931773195759"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row36805501785"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3743739718911"><a name="p3743739718911"></a><a name="p3743739718911"></a>totalRecord</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p45227392195611"><a name="p45227392195611"></a><a name="p45227392195611"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p6118898618911"><a name="p6118898618911"></a><a name="p6118898618911"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p3898511218911"><a name="p3898511218911"></a><a name="p3898511218911"></a>作业列表总数。</p>
</td>
</tr>
<tr id="row2282909519515"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4404627518911"><a name="p4404627518911"></a><a name="p4404627518911"></a>job_executions</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p34745157195611"><a name="p34745157195611"></a><a name="p34745157195611"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p2387674618911"><a name="p2387674618911"></a><a name="p2387674618911"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p5376380218911"><a name="p5376380218911"></a><a name="p5376380218911"></a>作业列表参数，请参见<a href="#ZH-CN_TOPIC_0109962607__table3315199519550">表3</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  job\_executions参数说明

<a name="table3315199519550"></a>
<table><thead align="left"><tr id="row578377519550"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p38420820195833"><a name="p38420820195833"></a><a name="p38420820195833"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p25078681195833"><a name="p25078681195833"></a><a name="p25078681195833"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p18107258195833"><a name="p18107258195833"></a><a name="p18107258195833"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45%" id="mcps1.2.5.1.4"><p id="p57401825195833"><a name="p57401825195833"></a><a name="p57401825195833"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row4877039619550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1036349219556"><a name="p1036349219556"></a><a name="p1036349219556"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p14843936195640"><a name="p14843936195640"></a><a name="p14843936195640"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p3507660919556"><a name="p3507660919556"></a><a name="p3507660919556"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p3191186819556"><a name="p3191186819556"></a><a name="p3191186819556"></a>作业ID。</p>
</td>
</tr>
<tr id="row5452608519550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p492591519556"><a name="p492591519556"></a><a name="p492591519556"></a>create_at</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p4327066019576"><a name="p4327066019576"></a><a name="p4327066019576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p65547675193741"><a name="p65547675193741"></a><a name="p65547675193741"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p46076642191954"><a name="p46076642191954"></a><a name="p46076642191954"></a>作业创建时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row90837019550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p646916119550"><a name="p646916119550"></a><a name="p646916119550"></a>update_at</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3861131219576"><a name="p3861131219576"></a><a name="p3861131219576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p31855594195115"><a name="p31855594195115"></a><a name="p31855594195115"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p9461207191918"><a name="p9461207191918"></a><a name="p9461207191918"></a>作业更新时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row5085722819550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p2579483119550"><a name="p2579483119550"></a><a name="p2579483119550"></a>tenant_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2782844319576"><a name="p2782844319576"></a><a name="p2782844319576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5844159719550"><a name="p5844159719550"></a><a name="p5844159719550"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1768719515356"><a name="p1768719515356"></a><a name="p1768719515356"></a>项目编号。获取方法，请参见<a href="获取项目编号.md">获取项目编号</a>。</p>
</td>
</tr>
<tr id="row5690483719550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4588905219550"><a name="p4588905219550"></a><a name="p4588905219550"></a>job_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3175518319576"><a name="p3175518319576"></a><a name="p3175518319576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p44975318193910"><a name="p44975318193910"></a><a name="p44975318193910"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p3001481419550"><a name="p3001481419550"></a><a name="p3001481419550"></a><span id="ph2267355217626"><a name="ph2267355217626"></a><a name="ph2267355217626"></a>Yarn的作业ID</span></p>
</td>
</tr>
<tr id="row169787619550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p331026719550"><a name="p331026719550"></a><a name="p331026719550"></a>job_name</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3892885219576"><a name="p3892885219576"></a><a name="p3892885219576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p42427159193910"><a name="p42427159193910"></a><a name="p42427159193910"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p2005248319550"><a name="p2005248319550"></a><a name="p2005248319550"></a>作业名称。</p>
</td>
</tr>
<tr id="row4625462019550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5563670019550"><a name="p5563670019550"></a><a name="p5563670019550"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p5105041719576"><a name="p5105041719576"></a><a name="p5105041719576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p29918955193921"><a name="p29918955193921"></a><a name="p29918955193921"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p2026254620146"><a name="p2026254620146"></a><a name="p2026254620146"></a>作业执行开始时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row2176045219550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1776620019550"><a name="p1776620019550"></a><a name="p1776620019550"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p5350353519576"><a name="p5350353519576"></a><a name="p5350353519576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p37327910193921"><a name="p37327910193921"></a><a name="p37327910193921"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p5041299620146"><a name="p5041299620146"></a><a name="p5041299620146"></a>作业执行结束时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row6143635119550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1028852819550"><a name="p1028852819550"></a><a name="p1028852819550"></a>cluster_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1002360519576"><a name="p1002360519576"></a><a name="p1002360519576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5862431019550"><a name="p5862431019550"></a><a name="p5862431019550"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p2281683220216"><a name="p2281683220216"></a><a name="p2281683220216"></a>作业所属集群ID。</p>
</td>
</tr>
<tr id="row5588512519550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3040126119550"><a name="p3040126119550"></a><a name="p3040126119550"></a>group_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p5610474819576"><a name="p5610474819576"></a><a name="p5610474819576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1380124819410"><a name="p1380124819410"></a><a name="p1380124819410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1891440820216"><a name="p1891440820216"></a><a name="p1891440820216"></a>作业执行组ID。</p>
</td>
</tr>
<tr id="row2461506319550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4766307219550"><a name="p4766307219550"></a><a name="p4766307219550"></a>jar_path</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p37938719576"><a name="p37938719576"></a><a name="p37938719576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1405183219410"><a name="p1405183219410"></a><a name="p1405183219410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p34979288192243"><a name="p34979288192243"></a><a name="p34979288192243"></a>执行程序jar包或sql文件地址。</p>
</td>
</tr>
<tr id="row3958047819550"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5190214619550"><a name="p5190214619550"></a><a name="p5190214619550"></a>input</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p305716219576"><a name="p305716219576"></a><a name="p305716219576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1627104919410"><a name="p1627104919410"></a><a name="p1627104919410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p4996084420258"><a name="p4996084420258"></a><a name="p4996084420258"></a>数据输入地址。</p>
</td>
</tr>
<tr id="row1217098519727"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4632576819727"><a name="p4632576819727"></a><a name="p4632576819727"></a>output</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1393120319576"><a name="p1393120319576"></a><a name="p1393120319576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p989452319410"><a name="p989452319410"></a><a name="p989452319410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p852868320258"><a name="p852868320258"></a><a name="p852868320258"></a>数据输出地址。</p>
</td>
</tr>
<tr id="row3799281119842"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p5751881819842"><a name="p5751881819842"></a><a name="p5751881819842"></a>job_log</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p5714228319576"><a name="p5714228319576"></a><a name="p5714228319576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p3324274119410"><a name="p3324274119410"></a><a name="p3324274119410"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p4477291020258"><a name="p4477291020258"></a><a name="p4477291020258"></a>作业日志存储地址。</p>
</td>
</tr>
<tr id="row399573611990"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p153208431990"><a name="p153208431990"></a><a name="p153208431990"></a>job_type</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3572794819576"><a name="p3572794819576"></a><a name="p3572794819576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p580869611990"><a name="p580869611990"></a><a name="p580869611990"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p74233721990"><a name="p74233721990"></a><a name="p74233721990"></a>作业类型码。</p>
<a name="ul52805946192537"></a><a name="ul52805946192537"></a><ul id="ul52805946192537"><li>1：MapReduce</li><li>2：Spark</li><li>3：Hive Script</li><li>4：HiveQL（当前不支持）</li><li>5：DistCp</li><li>6：Spark Script</li><li>7：Spark SQL（该接口当前不支持）</li></ul>
</td>
</tr>
<tr id="row4199685319913"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p4630192719913"><a name="p4630192719913"></a><a name="p4630192719913"></a>file_action</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1907364619576"><a name="p1907364619576"></a><a name="p1907364619576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5222674819913"><a name="p5222674819913"></a><a name="p5222674819913"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p250820819913"><a name="p250820819913"></a><a name="p250820819913"></a>导入导出数据。</p>
</td>
</tr>
<tr id="row4714693819921"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p6080567119921"><a name="p6080567119921"></a><a name="p6080567119921"></a>arguments</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3861448819576"><a name="p3861448819576"></a><a name="p3861448819576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5092218519921"><a name="p5092218519921"></a><a name="p5092218519921"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p10094543192658"><a name="p10094543192658"></a><a name="p10094543192658"></a>程序执行的关键参数，该参数由用户程序内的函数指定，MRS只负责参数的传入。该参数可为空。</p>
</td>
</tr>
<tr id="row6009214319943"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3562540819943"><a name="p3562540819943"></a><a name="p3562540819943"></a>hql</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3613758719576"><a name="p3613758719576"></a><a name="p3613758719576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p6523786219943"><a name="p6523786219943"></a><a name="p6523786219943"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p4977550119943"><a name="p4977550119943"></a><a name="p4977550119943"></a>HQL脚本语句。</p>
</td>
</tr>
<tr id="row1859114019956"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p2948735219956"><a name="p2948735219956"></a><a name="p2948735219956"></a>job_state</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1344375019576"><a name="p1344375019576"></a><a name="p1344375019576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p5877310219956"><a name="p5877310219956"></a><a name="p5877310219956"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p22201137165828"><a name="p22201137165828"></a><a name="p22201137165828"></a>作业状态编码：</p>
<a name="ul65592507165828"></a><a name="ul65592507165828"></a><ul id="ul65592507165828"><li>-1：Terminated<span id="ph20189027172420"><a name="ph20189027172420"></a><a name="ph20189027172420"></a>表示已终止的作业状态</span></li><li>2：Running<span id="ph37345054172438"><a name="ph37345054172438"></a><a name="ph37345054172438"></a>表示运行中的作业状态</span></li><li>3：Completed<span id="ph62887618172457"><a name="ph62887618172457"></a><a name="ph62887618172457"></a>表示已完成的作业状态</span></li><li>4：Abnormal<span id="ph20122543172510"><a name="ph20122543172510"></a><a name="ph20122543172510"></a>表示异常的作业状态</span></li></ul>
</td>
</tr>
<tr id="row51998636191052"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p51139963191052"><a name="p51139963191052"></a><a name="p51139963191052"></a>job_final_status</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3786274619576"><a name="p3786274619576"></a><a name="p3786274619576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p52088375191052"><a name="p52088375191052"></a><a name="p52088375191052"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p25388152145857"><a name="p25388152145857"></a><a name="p25388152145857"></a>作业最终状态码。</p>
<a name="ul27166780145857"></a><a name="ul27166780145857"></a><ul id="ul27166780145857"><li>0：未完成</li><li>1：执行错误，终止执行</li><li>2：执行完成并且成功</li><li>3：已取消</li></ul>
</td>
</tr>
<tr id="row4584195819116"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p2221115219116"><a name="p2221115219116"></a><a name="p2221115219116"></a>hive_script_path</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3494040619576"><a name="p3494040619576"></a><a name="p3494040619576"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p3402997419116"><a name="p3402997419116"></a><a name="p3402997419116"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p496448119116"><a name="p496448119116"></a><a name="p496448119116"></a>Hive脚本地址。</p>
</td>
</tr>
<tr id="row7998612191113"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p43907848191113"><a name="p43907848191113"></a><a name="p43907848191113"></a>create_by</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p4620195519576"><a name="p4620195519576"></a><a name="p4620195519576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p48146760191113"><a name="p48146760191113"></a><a name="p48146760191113"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p7573477191113"><a name="p7573477191113"></a><a name="p7573477191113"></a>创建作业的用户ID。</p>
</td>
</tr>
<tr id="row46507344191132"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p8998499191132"><a name="p8998499191132"></a><a name="p8998499191132"></a>finished_step</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2767181619576"><a name="p2767181619576"></a><a name="p2767181619576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p50461418191132"><a name="p50461418191132"></a><a name="p50461418191132"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p60843054191132"><a name="p60843054191132"></a><a name="p60843054191132"></a>当前已完成的步骤数。</p>
</td>
</tr>
<tr id="row63007578191145"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p3340165191145"><a name="p3340165191145"></a><a name="p3340165191145"></a>job_main_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1804922919576"><a name="p1804922919576"></a><a name="p1804922919576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p4495656219439"><a name="p4495656219439"></a><a name="p4495656219439"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1759059320856"><a name="p1759059320856"></a><a name="p1759059320856"></a>作业主ID。</p>
</td>
</tr>
<tr id="row10088168191225"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p11835266191225"><a name="p11835266191225"></a><a name="p11835266191225"></a>job_step_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3743260419576"><a name="p3743260419576"></a><a name="p3743260419576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1667749119439"><a name="p1667749119439"></a><a name="p1667749119439"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p1438564520856"><a name="p1438564520856"></a><a name="p1438564520856"></a>作业步骤ID。</p>
</td>
</tr>
<tr id="row54963709191240"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p22875416191240"><a name="p22875416191240"></a><a name="p22875416191240"></a>postpone_at</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2539823419576"><a name="p2539823419576"></a><a name="p2539823419576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p30188072191240"><a name="p30188072191240"></a><a name="p30188072191240"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p4057938120917"><a name="p4057938120917"></a><a name="p4057938120917"></a>延迟时间，十三位时间戳。</p>
</td>
</tr>
<tr id="row20295505191252"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p33323170191252"><a name="p33323170191252"></a><a name="p33323170191252"></a>step_name</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p140990519576"><a name="p140990519576"></a><a name="p140990519576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p59751102191252"><a name="p59751102191252"></a><a name="p59751102191252"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p8001113191252"><a name="p8001113191252"></a><a name="p8001113191252"></a>作业步骤名。</p>
</td>
</tr>
<tr id="row31355889191259"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p56799042191259"><a name="p56799042191259"></a><a name="p56799042191259"></a>step_num</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3494471319576"><a name="p3494471319576"></a><a name="p3494471319576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p2995550191259"><a name="p2995550191259"></a><a name="p2995550191259"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p51527704201027"><a name="p51527704201027"></a><a name="p51527704201027"></a>步骤数量。</p>
</td>
</tr>
<tr id="row3898483219138"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p365478919138"><a name="p365478919138"></a><a name="p365478919138"></a>task_num</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2376224919576"><a name="p2376224919576"></a><a name="p2376224919576"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p2120762919138"><a name="p2120762919138"></a><a name="p2120762919138"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p34076263201027"><a name="p34076263201027"></a><a name="p34076263201027"></a>任务数量。</p>
</td>
</tr>
<tr id="row16929053191331"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p29076056191331"><a name="p29076056191331"></a><a name="p29076056191331"></a>update_by</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p2533039419577"><a name="p2533039419577"></a><a name="p2533039419577"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p44613171191331"><a name="p44613171191331"></a><a name="p44613171191331"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p56897059191331"><a name="p56897059191331"></a><a name="p56897059191331"></a>更新作业的用户ID。</p>
</td>
</tr>
<tr id="row60220269191339"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p46003592191339"><a name="p46003592191339"></a><a name="p46003592191339"></a>spend_time</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1576137919577"><a name="p1576137919577"></a><a name="p1576137919577"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p41009304191339"><a name="p41009304191339"></a><a name="p41009304191339"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p33419357191339"><a name="p33419357191339"></a><a name="p33419357191339"></a>作业执行持续时间，单位：秒。</p>
</td>
</tr>
<tr id="row25391145191345"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p43416868191345"><a name="p43416868191345"></a><a name="p43416868191345"></a>step_seq</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3937518119577"><a name="p3937518119577"></a><a name="p3937518119577"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p48053375191345"><a name="p48053375191345"></a><a name="p48053375191345"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p9263191345"><a name="p9263191345"></a><a name="p9263191345"></a>步骤序列号。</p>
</td>
</tr>
<tr id="row12938423191358"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p41379368191358"><a name="p41379368191358"></a><a name="p41379368191358"></a>progress</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p3707990519577"><a name="p3707990519577"></a><a name="p3707990519577"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p34684936191358"><a name="p34684936191358"></a><a name="p34684936191358"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45%" headers="mcps1.2.5.1.4 "><p id="p58016455191358"><a name="p58016455191358"></a><a name="p58016455191358"></a>作业执行进度。</p>
</td>
</tr>
</tbody>
</table>

## 示例<a name="section1210015461189"></a>

-   请求示例

    ```
    GET/v1.1/{project_id}/job-exes?page_size=10&current_page=1&state=3&job_name=myfirstjob
    ```

-   响应示例

    ```
    {
        "totalRecord": 14, 
        "job_executions": [
            {
                "id": "669476bd-89d2-45aa-8f1a-872d16de377e", 
                "create_at": 1484641003707, 
                "update_at": 1484641003707, 
                "tenant_id": "3f99e3319a8943ceb15c584f3325d064", 
                "job_id": "", 
                "job_name": "myfirstjob", 
                "start_time": 1484641003707, 
                "end_time": null, 
                "cluster_id": "2b460e01-3351-4170-b0a7-57b9dd5ffef3", 
                "group_id": "669476bd-89d2-45aa-8f1a-872d16de377e", 
                "jar_path": "s3a://jp-test1/program/hadoop-mapreduce-examples-2.4.1.jar", 
                "input": "s3a://jp-test1/input/", 
                "output": "s3a://jp-test1/output/", 
                "job_log": "s3a://jp-test1/joblogs/", 
                "job_type": 1, 
                "file_action": "", 
                "arguments": "wordcount", 
                "hql": "", 
                "job_state": 2, 
                "job_final_status": 1, 
                "hive_script_path": null, 
                "create_by": "3f99e3319a8943ceb15c584f3325d064", 
                "finished_step": 0, 
                "job_main_id": "", 
                "job_step_id": "", 
                "postpone_at": 1484641003174, 
                "step_name": "", 
                "step_num": 0, 
                "task_num": 0, 
                "update_by": "3f99e3319a8943ceb15c584f3325d064", 
                "spend_time": null, 
                "step_seq": 222, 
                "progress": "first progress"
            }
        ]
    }
    ```


## 状态码<a name="section7365446163631"></a>

状态码如[表4](#table1584477916050)所示。

**表 4**  状态码

<a name="table1584477916050"></a>
<table><thead align="left"><tr id="row1339492016050"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="p3411176516050"><a name="p3411176516050"></a><a name="p3411176516050"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="p1158961516050"><a name="p1158961516050"></a><a name="p1158961516050"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row3719767816050"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="p6428795219421"><a name="p6428795219421"></a><a name="p6428795219421"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="p1800220919421"><a name="p1800220919421"></a><a name="p1800220919421"></a>查询作业exe对象列表成功。</p>
</td>
</tr>
</tbody>
</table>

异常状态码请参见[状态码](状态码.md)。

