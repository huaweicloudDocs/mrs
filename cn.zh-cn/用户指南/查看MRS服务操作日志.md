# 查看MRS服务操作日志<a name="zh-cn_topic_0012808265"></a>

“操作日志“页面记录用户对集群和作业的操作信息。日志信息常用于集群运行异常时的问题定位，帮助用户快速定位问题原因，以便及时解决问题。

## 操作类型<a name="section42049383165922"></a>

目前MRS记录以下操作类型的日志信息，可在搜索框中筛选查询：

-   集群操作
    -   创建集群、删除集群、扩容集群和缩容集群等
    -   创建目录、删除目录和删除文件

-   作业操作：创建作业、停止作业和删除作业
-   数据操作：IAM用户任务、新增用户、新增用户组等操作

## 日志字段<a name="section57726380165938"></a>

日志列表默认按时间顺序排列，时间最近的日志显示在最前端。

日志信息中的各字段说明如[表1](#table5924273517010)所示。

**表 1**  日志说明

<a name="table5924273517010"></a>
<table><thead align="left"><tr id="row2217974117010"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p37124417010"><a name="p37124417010"></a><a name="p37124417010"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p5559965417010"><a name="p5559965417010"></a><a name="p5559965417010"></a>参数说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row595250417010"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p6693723117010"><a name="p6693723117010"></a><a name="p6693723117010"></a>操作类型</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p234869017010"><a name="p234869017010"></a><a name="p234869017010"></a>记录执行的操作类型，包括：</p>
<a name="ul2977561517418"></a><a name="ul2977561517418"></a><ul id="ul2977561517418"><li>集群操作</li><li>作业操作</li><li>数据操作</li></ul>
</td>
</tr>
<tr id="row431321819572"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1382637719572"><a name="p1382637719572"></a><a name="p1382637719572"></a>操作IP</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p4619474419572"><a name="p4619474419572"></a><a name="p4619474419572"></a>记录执行操作的IP地址。</p>
<div class="note" id="note48964576112218"><a name="note48964576112218"></a><a name="note48964576112218"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p38028006112218"><a name="p38028006112218"></a><a name="p38028006112218"></a>当MRS集群部署失败时，集群会被自动删除，并且自动删除集群的操作日志中不包含用户的<span class="parmname" id="parmname61267378112225"><a name="parmname61267378112225"></a><a name="parmname61267378112225"></a>“操作IP”</span>信息。</p>
</div></div>
</td>
</tr>
<tr id="row1556529017010"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p459724117010"><a name="p459724117010"></a><a name="p459724117010"></a>操作内容</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p4481421617010"><a name="p4481421617010"></a><a name="p4481421617010"></a>记录实际操作内容，不超过2048字符。</p>
</td>
</tr>
<tr id="row3264057817010"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p4623164717010"><a name="p4623164717010"></a><a name="p4623164717010"></a>时间</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5037024317010"><a name="p5037024317010"></a><a name="p5037024317010"></a>记录操作的时间。对于已删除的集群，界面只显示6个月内的日志信息，若需要查看6个月之前的日志信息，请联系华为云支持人员。</p>
</td>
</tr>
<tr id="row023116111504"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1530916121004"><a name="p1530916121004"></a><a name="p1530916121004"></a>企业项目</p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p630961214014"><a name="p630961214014"></a><a name="p630961214014"></a>操作的集群所属的企业项目。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  按钮说明

<a name="table3011042510139"></a>
<table><thead align="left"><tr id="row708755810139"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p6655665410139"><a name="p6655665410139"></a><a name="p6655665410139"></a>按钮</p>
</th>
<th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p2237991710139"><a name="p2237991710139"></a><a name="p2237991710139"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row01413151604"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1114015205"><a name="p1114015205"></a><a name="p1114015205"></a><a name="image92291244111"></a><a name="image92291244111"></a><span><img id="image92291244111" src="figures/icon_mrs_allproject.png" width="97.09" height="18.608961"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p171414158013"><a name="p171414158013"></a><a name="p171414158013"></a>在下拉框中选择企业项目，筛选日志。</p>
</td>
</tr>
<tr id="row9266410139"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p750586110139"><a name="p750586110139"></a><a name="p750586110139"></a><a name="image181221479111"></a><a name="image181221479111"></a><span><img id="image181221479111" src="figures/icon_mrs_allstatus.png" width="97.09" height="17.799789"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p5344702710412"><a name="p5344702710412"></a><a name="p5344702710412"></a>在下拉框中选择操作类型，筛选日志。</p>
<a name="ul1294383513519"></a><a name="ul1294383513519"></a><ul id="ul1294383513519"><li>全部：表示筛选所有的日志</li><li>集群操作：表示筛选<span class="parmvalue" id="parmvalue55934352155149"><a name="parmvalue55934352155149"></a><a name="parmvalue55934352155149"></a>“集群操作”</span>的日志</li><li>作业操作：表示筛选<span class="parmvalue" id="parmvalue64948673155154"><a name="parmvalue64948673155154"></a><a name="parmvalue64948673155154"></a>“作业操作”</span>的日志</li><li>数据操作：表示筛选<span class="parmvalue" id="parmvalue18611152114414"><a name="parmvalue18611152114414"></a><a name="parmvalue18611152114414"></a>“数据操作”</span>的日志</li></ul>
</td>
</tr>
<tr id="row63630108154320"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p53765115154320"><a name="p53765115154320"></a><a name="p53765115154320"></a><a name="image1736713118459"></a><a name="image1736713118459"></a><span><img id="image1736713118459" src="figures/icon_mrs_selectdate.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p60007083154320"><a name="p60007083154320"></a><a name="p60007083154320"></a><span id="ph43662682154836"><a name="ph43662682154836"></a><a name="ph43662682154836"></a>根据时间筛选日志。</span></p>
<a name="ol2595430715486"></a><a name="ol2595430715486"></a><ol id="ol2595430715486"><li>单击输入框。</li><li>选择日期和时间。</li><li>单击<span class="uicontrol" id="uicontrol4762305415486"><a name="uicontrol4762305415486"></a><a name="uicontrol4762305415486"></a>“确认”</span>。</li></ol>
<p id="p57734443154828"><a name="p57734443154828"></a><a name="p57734443154828"></a>左侧框为需要查询的开始时间，右侧框为需要查询的结束时间。右侧的输入框选择的时间必须大于或等于左侧输入框的时间，否则，无法根据时间筛选日志。</p>
</td>
</tr>
<tr id="row3595494810139"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p2666966910139"><a name="p2666966910139"></a><a name="p2666966910139"></a><a name="image1811862119376"></a><a name="image1811862119376"></a><span><img id="image1811862119376" src="figures/icon_mrs_search_L.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1275954610139"><a name="p1275954610139"></a><a name="p1275954610139"></a>在搜索框中输入<span class="parmname" id="parmname12295406155845"><a name="parmname12295406155845"></a><a name="parmname12295406155845"></a>“操作内容”</span>中的关键字，单击<a name="image92235719379"></a><a name="image92235719379"></a><span><img id="image92235719379" src="figures/icon_mrs_search_L.png"></span>，搜索日志。</p>
</td>
</tr>
<tr id="row4772705110139"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p4068596210139"><a name="p4068596210139"></a><a name="p4068596210139"></a><a name="image161918257385"></a><a name="image161918257385"></a><span><img id="image161918257385" src="figures/icon_mrs_fresh_R.png"></span></p>
</td>
<td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p722865810139"><a name="p722865810139"></a><a name="p722865810139"></a>单击<a name="image4439104113409"></a><a name="image4439104113409"></a><span><img id="image4439104113409" src="figures/icon_mrs_fresh_R.png"></span>，手动刷新日志列表。</p>
</td>
</tr>
</tbody>
</table>

