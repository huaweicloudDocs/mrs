# 在Hue WebUI使用作业浏览器<a name="ZH-CN_TOPIC_0050661082"></a>

## 操作场景<a name="zh-cn_topic_0049949146_section18334049192439"></a>

-   针对MRS 1.8.1之前的集群，MRS集群启用Kerberos认证后，用户需要使用图形化界面查看集群中所有作业时，可以通过Hue完成任务。
-   针对MRS 1.8.1及之后的集群，用户需要使用图形化界面查看集群中所有作业时，可以通过Hue完成任务。

## 访问“Job Browser“<a name="section5797126615627"></a>

1.  访问Hue WebUI，然后单击“Job Browser“。
2.  默认显示当前集群的所有作业。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >“Job Browser“显示的数字表示集群中所有作业的总数。  

    “Job Browser“将显示作业以下信息：

    **表 1**  MRS作业属性介绍

    <a name="table1535121615634"></a>
    <table><thead align="left"><tr id="row3653459615634"><th class="cellrowborder" valign="top" width="30.64%" id="mcps1.2.3.1.1"><p id="p6208203415634"><a name="p6208203415634"></a><a name="p6208203415634"></a>属性名</p>
    </th>
    <th class="cellrowborder" valign="top" width="69.36%" id="mcps1.2.3.1.2"><p id="p6258888115634"><a name="p6258888115634"></a><a name="p6258888115634"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3638438215634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p5861077415634"><a name="p5861077415634"></a><a name="p5861077415634"></a><span class="parmname" id="parmname651230815634"><a name="parmname651230815634"></a><a name="parmname651230815634"></a>“日志”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p4601693715634"><a name="p4601693715634"></a><a name="p4601693715634"></a>表示作业的日志信息。如果作业有输出日志，则显示<a name="image4985223515634"></a><a name="image4985223515634"></a><span><img id="image4985223515634" src="figures/zh-cn_image_0056734290.jpg" height="11.97" width="15.96"></span>。</p>
    </td>
    </tr>
    <tr id="row837856815634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p6145380715634"><a name="p6145380715634"></a><a name="p6145380715634"></a><span class="parmname" id="parmname5902398315634"><a name="parmname5902398315634"></a><a name="parmname5902398315634"></a>“ID”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p1170250215634"><a name="p1170250215634"></a><a name="p1170250215634"></a>表示作业的编号，由系统自动生成。</p>
    </td>
    </tr>
    <tr id="row4179649115634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p757542315634"><a name="p757542315634"></a><a name="p757542315634"></a><span class="parmname" id="parmname829825415634"><a name="parmname829825415634"></a><a name="parmname829825415634"></a>“名称”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p962955515634"><a name="p962955515634"></a><a name="p962955515634"></a>表示作业的名称。</p>
    </td>
    </tr>
    <tr id="row5785170415634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p3007262415634"><a name="p3007262415634"></a><a name="p3007262415634"></a><span class="parmname" id="parmname4062410415634"><a name="parmname4062410415634"></a><a name="parmname4062410415634"></a>“Application Type”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p4545346115634"><a name="p4545346115634"></a><a name="p4545346115634"></a>表示作业的类型。</p>
    </td>
    </tr>
    <tr id="row3636957415634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p5547641915634"><a name="p5547641915634"></a><a name="p5547641915634"></a><span class="parmname" id="parmname5090328915634"><a name="parmname5090328915634"></a><a name="parmname5090328915634"></a>“状态”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p4353124015634"><a name="p4353124015634"></a><a name="p4353124015634"></a>表示作业的状态，包含<span class="parmvalue" id="parmvalue6440495915634"><a name="parmvalue6440495915634"></a><a name="parmvalue6440495915634"></a>“RUNNING”</span>、<span class="parmname" id="parmname4277372315634"><a name="parmname4277372315634"></a><a name="parmname4277372315634"></a>“SUCCEEDED”</span>、<span class="parmname" id="parmname4941918715634"><a name="parmname4941918715634"></a><a name="parmname4941918715634"></a>“FAILED”</span>和<span class="parmname" id="parmname4211950615634"><a name="parmname4211950615634"></a><a name="parmname4211950615634"></a>“KILLED”</span>。</p>
    </td>
    </tr>
    <tr id="row5762128115634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p6025435615634"><a name="p6025435615634"></a><a name="p6025435615634"></a><span class="parmname" id="parmname5889071115634"><a name="parmname5889071115634"></a><a name="parmname5889071115634"></a>“用户”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p4876463415634"><a name="p4876463415634"></a><a name="p4876463415634"></a>表示启动该作业的用户。</p>
    </td>
    </tr>
    <tr id="row6699930515634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p3681217615634"><a name="p3681217615634"></a><a name="p3681217615634"></a><span class="parmname" id="parmname4882948415634"><a name="parmname4882948415634"></a><a name="parmname4882948415634"></a>“Maps”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p2899630415634"><a name="p2899630415634"></a><a name="p2899630415634"></a>表示作业执行Map过程的进度。</p>
    </td>
    </tr>
    <tr id="row2640859715634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p5823459415634"><a name="p5823459415634"></a><a name="p5823459415634"></a><span class="parmname" id="parmname6612283415634"><a name="parmname6612283415634"></a><a name="parmname6612283415634"></a>“Reduces”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p1938163515634"><a name="p1938163515634"></a><a name="p1938163515634"></a>表示作业执行Reduce过程的进度。</p>
    </td>
    </tr>
    <tr id="row42764615634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p5872159915634"><a name="p5872159915634"></a><a name="p5872159915634"></a><span class="parmname" id="parmname3635078315634"><a name="parmname3635078315634"></a><a name="parmname3635078315634"></a>“队列”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p5882909815634"><a name="p5882909815634"></a><a name="p5882909815634"></a>表示作业运行时使用的YARN队列。</p>
    </td>
    </tr>
    <tr id="row3803033115634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p3463932915634"><a name="p3463932915634"></a><a name="p3463932915634"></a><span class="parmname" id="parmname384881415634"><a name="parmname384881415634"></a><a name="parmname384881415634"></a>“优先级”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p5432230215634"><a name="p5432230215634"></a><a name="p5432230215634"></a>表示作业运行时的优先级。</p>
    </td>
    </tr>
    <tr id="row3625261215634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p6055795215634"><a name="p6055795215634"></a><a name="p6055795215634"></a><span class="parmname" id="parmname672866115634"><a name="parmname672866115634"></a><a name="parmname672866115634"></a>“持续时间”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p624709415634"><a name="p624709415634"></a><a name="p624709415634"></a>表示作业运行使用的时间。</p>
    </td>
    </tr>
    <tr id="row4245889915634"><td class="cellrowborder" valign="top" width="30.64%" headers="mcps1.2.3.1.1 "><p id="p5078049915634"><a name="p5078049915634"></a><a name="p5078049915634"></a><span class="parmname" id="parmname5783806015634"><a name="parmname5783806015634"></a><a name="parmname5783806015634"></a>“已提交”</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="69.36%" headers="mcps1.2.3.1.2 "><p id="p1957978715634"><a name="p1957978715634"></a><a name="p1957978715634"></a>表示作业提交到MRS集群的时间。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果MRS集群安装了Spark组件，则默认会启动一个作业“Spark-JDBCServer“，用于执行任务。  


## 搜索作业<a name="section1851936815652"></a>

1.  在“Job Browser“的“用户名“或“文本“，输入指定的字符，系统会自动搜索包含此关键字的全部作业。
2.  清空搜索框的内容，系统会重新显示所有作业。

## 查看作业详细信息<a name="section145630421574"></a>

1.  在“Job Browser“的作业列表，单击作业所在的行，可以打开作业详情。
2.  在“元数据“页签，可查看作业的元数据。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >单击![](figures/icon_mrs_dbjoblog.jpg)可打开作业运行时的日志。  


