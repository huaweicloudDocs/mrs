# 管理Loader作业<a name="ZH-CN_TOPIC_0071958197"></a>

## 操作场景<a name="zh-cn_topic_0071084974_section3370941195922"></a>

Loader页面支持创建、查看、编辑和删除作业。

## 前提条件<a name="zh-cn_topic_0071084974_section177816810113"></a>

已访问Loader页面，参见[Loader页面介绍](Loader使用简介.md#zh-cn_topic_0070859522_section27711559)。

## 创建作业<a name="zh-cn_topic_0071084974_section5247810030"></a>

1.  访问Loader页面，单击“新建作业“。
2.  在“基本信息“填写参数。
    1.  在“名称“填写一个作业的名称。
    2.  在“源连接“和“目的连接“选择对应的连接。

        选择某个类型的连接，表示从指定的源获取数据，并保存到目的位置。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果没有需要的连接，可单击“添加新连接“。  


3.  在“自“填写源连接的作业配置。

    具体请参见[Loader作业源连接配置说明](Loader作业源连接配置说明.md#ZH-CN_TOPIC_0071958195)。

4.  在“至“填写目的连接的作业配置。

    具体请参见[Loader作业目的连接配置说明](Loader作业目的连接配置说明.md#ZH-CN_TOPIC_0071958196)。

5.  在“目的连接“是否选择了数据库类型的连接？

    数据库类型的连接包含以下几种：

    -   generic-jdbc-connector
    -   hbase-connector
    -   hive-connector
    -   voltdb-connector

    “目的连接“选择数据库类型的连接时，还需要配置业务数据与数据库表字段的对应关系：

    -   是，请执行[6](#zh-cn_topic_0071084974_li36346884152825)。
    -   否，请执行[7](#zh-cn_topic_0071084974_li57339120154326)。

6.  <a name="zh-cn_topic_0071084974_li36346884152825"></a>在“字段映射“填写字段对应关系。然后执行[7](#zh-cn_topic_0071084974_li57339120154326)。

    “字段映射“的对应关系，表示用户数据中每一列与数据库的表字段的匹配关系。

    **表 1** “字段映射“属性

    <a name="zh-cn_topic_0071084974_table1352764011231"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0071084974_row3847336211231"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084974_p2933465211231"><a name="zh-cn_topic_0071084974_p2933465211231"></a><a name="zh-cn_topic_0071084974_p2933465211231"></a><strong id="zh-cn_topic_0071084974_b6268528311231"><a name="zh-cn_topic_0071084974_b6268528311231"></a><a name="zh-cn_topic_0071084974_b6268528311231"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084974_p4434316111231"><a name="zh-cn_topic_0071084974_p4434316111231"></a><a name="zh-cn_topic_0071084974_p4434316111231"></a><strong id="zh-cn_topic_0071084974_b6354413011231"><a name="zh-cn_topic_0071084974_b6354413011231"></a><a name="zh-cn_topic_0071084974_b6354413011231"></a>说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0071084974_row4680087711231"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p3277469711231"><a name="zh-cn_topic_0071084974_p3277469711231"></a><a name="zh-cn_topic_0071084974_p3277469711231"></a>列号</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p3750479711231"><a name="zh-cn_topic_0071084974_p3750479711231"></a><a name="zh-cn_topic_0071084974_p3750479711231"></a>表示业务数据的字段顺序。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row199886011231"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p2768999211231"><a name="zh-cn_topic_0071084974_p2768999211231"></a><a name="zh-cn_topic_0071084974_p2768999211231"></a>样本</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p2829691311231"><a name="zh-cn_topic_0071084974_p2829691311231"></a><a name="zh-cn_topic_0071084974_p2829691311231"></a>表示业务数据的第一行值样例。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row5334563011231"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p2602874011231"><a name="zh-cn_topic_0071084974_p2602874011231"></a><a name="zh-cn_topic_0071084974_p2602874011231"></a>列族</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p2795319511231"><a name="zh-cn_topic_0071084974_p2795319511231"></a><a name="zh-cn_topic_0071084974_p2795319511231"></a><span class="parmname" id="zh-cn_topic_0071084974_parmname25976934113443"><a name="zh-cn_topic_0071084974_parmname25976934113443"></a><a name="zh-cn_topic_0071084974_parmname25976934113443"></a>“目的连接”</span>为hbase-connector类型时，支持定义保存数据的具体列族。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row5025216611231"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p4389364911231"><a name="zh-cn_topic_0071084974_p4389364911231"></a><a name="zh-cn_topic_0071084974_p4389364911231"></a>目的字段</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p6572465611231"><a name="zh-cn_topic_0071084974_p6572465611231"></a><a name="zh-cn_topic_0071084974_p6572465611231"></a>配置保存数据的具体字段。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row35872584113138"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p19998169113138"><a name="zh-cn_topic_0071084974_p19998169113138"></a><a name="zh-cn_topic_0071084974_p19998169113138"></a>类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p9239024113138"><a name="zh-cn_topic_0071084974_p9239024113138"></a><a name="zh-cn_topic_0071084974_p9239024113138"></a>显示用户选择字段的类型。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row311688211355"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p5114091311355"><a name="zh-cn_topic_0071084974_p5114091311355"></a><a name="zh-cn_topic_0071084974_p5114091311355"></a>行键</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p4877328411355"><a name="zh-cn_topic_0071084974_p4877328411355"></a><a name="zh-cn_topic_0071084974_p4877328411355"></a><span class="parmname" id="zh-cn_topic_0071084974_parmname41238143113535"><a name="zh-cn_topic_0071084974_parmname41238143113535"></a><a name="zh-cn_topic_0071084974_parmname41238143113535"></a>“目的连接”</span>为hbase-connector类型时，需要勾选作为行键的<span class="parmname" id="zh-cn_topic_0071084974_parmname4707228311389"><a name="zh-cn_topic_0071084974_parmname4707228311389"></a><a name="zh-cn_topic_0071084974_parmname4707228311389"></a>“目的字段”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果From是sftp/ftp/obs/hdfs等文件类型连接器，Field Mapping 样值取自文件第一行数据，需要保证第一行数据是完整的，Loader作业不会抽取没有Mapping上的列。  

7.  <a name="zh-cn_topic_0071084974_li57339120154326"></a>在“任务配置“填写作业的运行参数。

    **表 2**  Loader作业运行属性

    <a name="zh-cn_topic_0071084974_table53417707172948"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0071084974_row38145227172948"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0071084974_p50270734172948"><a name="zh-cn_topic_0071084974_p50270734172948"></a><a name="zh-cn_topic_0071084974_p50270734172948"></a><strong id="zh-cn_topic_0071084974_b45153969172948"><a name="zh-cn_topic_0071084974_b45153969172948"></a><a name="zh-cn_topic_0071084974_b45153969172948"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0071084974_p21245121172948"><a name="zh-cn_topic_0071084974_p21245121172948"></a><a name="zh-cn_topic_0071084974_p21245121172948"></a><strong id="zh-cn_topic_0071084974_b61004868172948"><a name="zh-cn_topic_0071084974_b61004868172948"></a><a name="zh-cn_topic_0071084974_b61004868172948"></a>说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0071084974_row64509191173017"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p22475877173148"><a name="zh-cn_topic_0071084974_p22475877173148"></a><a name="zh-cn_topic_0071084974_p22475877173148"></a>抽取并发数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p60128183173147"><a name="zh-cn_topic_0071084974_p60128183173147"></a><a name="zh-cn_topic_0071084974_p60128183173147"></a>设置map任务的个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row56267396172948"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p46891984173148"><a name="zh-cn_topic_0071084974_p46891984173148"></a><a name="zh-cn_topic_0071084974_p46891984173148"></a>加载(写入)并发数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p31508572173147"><a name="zh-cn_topic_0071084974_p31508572173147"></a><a name="zh-cn_topic_0071084974_p31508572173147"></a>设置reduce任务的个数。</p>
    <p id="zh-cn_topic_0071084974_p1980382211379"><a name="zh-cn_topic_0071084974_p1980382211379"></a><a name="zh-cn_topic_0071084974_p1980382211379"></a>该参数只有在目的字段为Hbase和Hive时才会显示。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row59970770173145"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p52917653173148"><a name="zh-cn_topic_0071084974_p52917653173148"></a><a name="zh-cn_topic_0071084974_p52917653173148"></a>单个分片的最大错误记录数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p52348730173145"><a name="zh-cn_topic_0071084974_p52348730173145"></a><a name="zh-cn_topic_0071084974_p52348730173145"></a>设置一个错误阈值，如果单个map任务的错误记录超过设置阈值则任务自动结束，已经获取的数据不回退。</p>
    <div class="note" id="zh-cn_topic_0071084974_note975348317355"><a name="zh-cn_topic_0071084974_note975348317355"></a><a name="zh-cn_topic_0071084974_note975348317355"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0071084974_p2067249117355"><a name="zh-cn_topic_0071084974_p2067249117355"></a><a name="zh-cn_topic_0071084974_p2067249117355"></a><span class="parmname" id="zh-cn_topic_0071084974_parmname38458483173542"><a name="zh-cn_topic_0071084974_parmname38458483173542"></a><a name="zh-cn_topic_0071084974_parmname38458483173542"></a>“generic-jdbc-connector”</span>的<span class="parmname" id="zh-cn_topic_0071084974_parmname61960237173551"><a name="zh-cn_topic_0071084974_parmname61960237173551"></a><a name="zh-cn_topic_0071084974_parmname61960237173551"></a>“MYSQL”</span>和<span class="parmname" id="zh-cn_topic_0071084974_parmname60872599173557"><a name="zh-cn_topic_0071084974_parmname60872599173557"></a><a name="zh-cn_topic_0071084974_parmname60872599173557"></a>“MPPDB”</span>默认批量读写数据，每一批次数据最多只记录一次错误记录。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0071084974_row61283543173145"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0071084974_p49942378173148"><a name="zh-cn_topic_0071084974_p49942378173148"></a><a name="zh-cn_topic_0071084974_p49942378173148"></a>脏数据目录</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0071084974_p10938031173145"><a name="zh-cn_topic_0071084974_p10938031173145"></a><a name="zh-cn_topic_0071084974_p10938031173145"></a>设置一个脏数据目录，在出现脏数据的场景中在该目录保存脏数据。如果不设置则不保存。</p>
    </td>
    </tr>
    </tbody>
    </table>

8.  单击“保存“。

## 查看作业<a name="zh-cn_topic_0071084974_section1741883310620"></a>

1.  访问Loader页面，默认显示Loader作业管理页面。
    -   如果集群启用了Kerberos认证，则默认显示所有当前用户创建的作业，不支持显示其他用户的作业。
    -   如果集群未启用Kerberos认证，则显示集群中全部的作业。

2.  在“Sqoop作业“中输入指定作业的名称或连接类型，可以筛选该作业。
3.  单击“刷新列表“，可以获取作业的最新状态。

## 编辑作业<a name="zh-cn_topic_0071084974_section22250948101420"></a>

1.  访问Loader页面，默认显示Loader作业管理页面。
2.  单击指定作业的名称，进入编辑页面。
3.  根据业务需要，修改作业配置参数。
4.  单击“保存“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >左侧导航栏支持作业的基本操作，包含“运行“、“复制“、“删除“、“激活“、“历史记录“和“显示作业JSON定义“。  


## 删除作业<a name="zh-cn_topic_0071084974_section49823441102034"></a>

1.  访问Loader页面。
2.  在指定作业所在行，单击![](figures/icon_mrs_deleteloaderjob.jpg)。

    您还可以勾选一个或多个作业，单击作业列表右上方的“删除作业“。

3.  在弹出的对话框窗口，单击“是，将其删除“。

    如果某个Loader作业正处于“运行中“的状态，则无法删除作业。


