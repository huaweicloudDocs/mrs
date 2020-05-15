# 在DLF中使用Presto转储<a name="ZH-CN_TOPIC_0192512530"></a>

## 前提条件<a name="section17912151442419"></a>

-   MRS集群中安装了Presto组件。
-   已完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“点击同步”进行IAM用户同步），具体参考[IAM用户同步MRS](IAM用户同步MRS.md)。
-   用户拥有操作OBS桶的权限，具体参考[ECS委托方式访问OBS](ECS委托方式访问OBS.md)和[配置MRS多用户访问OBS细粒度权限](配置MRS多用户访问OBS细粒度权限.md)。
-   用户已完成Presto权限配置，具体请参考[配置Presto组件权限](配置Presto组件权限.md)。

## 在DLF创建MRS PrestoSQL类型的数据连接<a name="section2028018713307"></a>

1.  在DLF控制台的左侧导航栏，选择“数据管理 \> 连接管理”。
2.  在页面的右上方，单击“新建数据连接”。
3.  参考[表1](#table487712591418)配置相关参数。

    **表 1**  新建数据连接

    <a name="table487712591418"></a>
    <table><thead align="left"><tr id="row287813541410"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p1687816512140"><a name="p1687816512140"></a><a name="p1687816512140"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p387814518143"><a name="p387814518143"></a><a name="p387814518143"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1787911511142"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p08791552148"><a name="p08791552148"></a><a name="p08791552148"></a>数据链接类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p987913531417"><a name="p987913531417"></a><a name="p987913531417"></a>选择“MapReduce服务 ( MRS PrestoSQL )”。</p>
    </td>
    </tr>
    <tr id="row387935191413"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1187965151415"><a name="p1187965151415"></a><a name="p1187965151415"></a>数据连接名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1687995101419"><a name="p1687995101419"></a><a name="p1687995101419"></a><span>数据连接</span><span>的名称，只能包含英文字母、数字、</span><span>“_”</span><span>、“-”，且长度为1~100个字符。</span></p>
    </td>
    </tr>
    <tr id="row1987914510149"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p187918519147"><a name="p187918519147"></a><a name="p187918519147"></a>集群名</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p18793551410"><a name="p18793551410"></a><a name="p18793551410"></a><span>选择Presto所属的MRS集群。</span></p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“测试”，测试数据连接的连通性。如果无法连通，数据连接将无法创建。
5.  单击“确定”，创建数据连接。

## 在DLF脚本开发页面新建并执行SQL脚本<a name="section5530207102217"></a>

>![](public_sys-resources/icon-caution.gif) **注意：**   
>该场景下转储到OBS上的查询结果，最大只会保留最近的10000次查询结果，当查询次数超过该限制时，会自动按照查询时间先后顺序老化历史查询结果。请用户注意并合理使用，避免造成数据丢失风险。  

1.  在DLF控制台的左侧导航栏，选择“数据开发 \> 脚本开发”。
2.  在“右侧区域”，单击“新建SQL脚本”，选择“Presto”。
3.  在编辑器右上方“数据连接”处选择[在DLF创建MRS PrestoSQL类型的数据连接](#section2028018713307)中创建的连接。
4.  在编辑器右上方“模式”处选择所选连接对应模式。
5.  在编辑器中输入SQL语句（支持输入多条SQL语句），如需单独执行某部分SQL语句，请选中SQL语句再运行。
6.  在编辑器上方，单击“运行”。SQL语句运行完成后，在编辑器下方可以查看脚本的执行历史、执行结果。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   不支持管理员类型的操作，即需要执行“set role admin”才能执行的命令都不支持。  
    >-   由于每条语句都是单独执行的，所以对于设置上下文的语句（如“use”），执行后不会生效。  
    >-   开启Presto授权情况下，各类用户默认权限如下：  
    >    -   hive下的mrs\_reserved的数据库，默认所有人均有读写权限。  
    >    -   hive下的default数据库，具备MRS CommonOperations、MRS FullAccess、MRS Administrator、Tenant Administrator策略的IAM用户，均有读写权限；MRS ReadOnlyAccess策略的用户，对该数据库有只读权限。  
    >    -   集群的admin用户以及具备MRS FullAccess、MRS Administrator、Tenant Administrator策略的IAM用户，具备hive数据库的admin角色。  


