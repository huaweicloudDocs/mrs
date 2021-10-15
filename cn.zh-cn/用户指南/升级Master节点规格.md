# 升级Master节点规格<a name="mrs_01_0626"></a>

随着用户业务的增长，Core节点的扩容，CPU使用率变高，而Master节点规格已经不满足用户需求时，则需要升级Master节点规格。本章节介绍Master节点规格升级的操作流程。

## 前提条件<a name="section992610122158"></a>

确认是否开启了企业主机安全（Host Security Service，简称HSS）服务，如果已开启，升级Master节点规格前需要先暂时关闭HSS服务对MRS集群的监测。

## 使用限制<a name="section203093751115"></a>

-   仅支持2个Master节点的集群升级Master节点规格 。
-   不支持使用BMS类型规格的集群升级Master节点规格 。

## 集群Master节点规格升级（适用MRS 1.8.2及之后MRS 3.x之前版本）<a name="section931793154614"></a>

1.  登录MRS管理控制台。
2.  选择  “集群列表  \>  现有集群“  ，选中需要升级Master节点规格的集群并单击集群名，进入集群信息页面。
3.  在“节点管理“页签Master节点组的“操作”列选择“升级规格“，进入“升级Master规格“页面。

    ![](figures/5-10-升级规格.png)

4.  选择升级后的规格，单击“提交“成功提交升级Master规格任务。

    节点规格升级过程需要时间，升级成功后集群状态更新为“运行中”，请您耐心等待。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >升级过程中集群会自动关闭升级的虚拟机，升级完成后自动开启该虚拟机 。


## 集群Master节点规格升级（适用MRS 1.8.2之前版本及MRS 3.0.5版本）<a name="section43251723164812"></a>

**Master节点规格升级前准备**

1.  <a name="li487181481727"></a>登录MRS管理控制台。
2.  选择  “集群列表  \>  现有集群“  ，选中需要升级Master节点规格的集群并单击集群名，进入集群信息页面。
3.  查看集群状态，确保集群状态为“运行中”。
4.  在“节点管理“页签查看各节点状态，确保集群所有节点的状态为“运行中”。
5.  登录Manager，进入集群管理页面，具体请参见[访问Manager](访问Manager-2.md)。
6.  选择“集群 \> 服务 \> ZooKeeper \> 概览”，确保ZooKeeper服务的“运行状态“为“良好“。

    **图 1**  ZooKeeper服务状态<a name="fig13948230194818"></a>  
    ![](figures/ZooKeeper服务状态.png "ZooKeeper服务状态")

7.  用户根据自己的需要更新服务参数配置，具体请参考[配置服务参数](配置服务参数.md)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >该步骤仅在升级备Master节点前操作一次即可。

8.  <a name="li36491855204611"></a>选择“集群 \> 服务 \> HDFS \> 实例”。
9.  <a name="li3448141413114"></a>记录“NameNode\(备\)“的业务IP，当升级主Master节点规格时请记录“NameNode\(主\)“的业务IP，如[图2](#fig12363132192817)所示。

    **图 2**  NameNode业务IP<a name="fig12363132192817"></a>  
    ![](figures/NameNode业务IP.png "NameNode业务IP")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >仅当集群类型为分析集群时执行[8](#li36491855204611)-[9](#li3448141413114)分别记录主备节点的IP。

10. 在Manager页面右上方查看![](figures/zh-cn_image_0000001166687707.png)图形的右侧数字，确保该数字显示为“0”表示集群的运行任务数为0。
11. 单击“主机 ”，若集群类型为分析集群，则勾选[9](#li3448141413114)记录的“NameNode“的业务IP所对应的主机前的复选框。若集群类型为流式集群，则不区分主备节点，分别选择主机升级即可。
12. <a name="li12169193211415"></a>选择“更多\> 停止所有实例”，并等待所有实例停止完成。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   当升级Manager所在的节点时，可能出现Manager无法登录问题，是Manager所在的节点在进行主备倒换的正常现象，请稍后重新登录即可。若长时间无法登录，请联系运维人员处理。
    >-   停止所有角色后，可能出现如下告警，Master节点规格升级完成并启动所有角色后，告警将自动恢复。
    >    -   [ALM-12006 节点故障](ALM-12006-节点故障-125.md)
    >    -   [ALM-12010 Manager主备节点间心跳中断](ALM-12010-Manager主备节点间心跳中断-127.md)
    >    -   [ALM-12039 OMS数据库主备不同步](ALM-12039-OMS数据库主备不同步.md)
    >    -   [ALM-14000 HDFS服务不可用](ALM-14000-HDFS服务不可用-153.md)
    >    -   [ALM-14010 NameService服务异常](ALM-14010-NameService服务异常-158.md)
    >    -   [ALM-14012 Journalnode数据不同步](ALM-14012-Journalnode数据不同步.md)
    >    -   [ALM-16004 Hive服务不可用](ALM-16004-Hive服务不可用-162.md)
    >    -   [ALM-18000 Yarn服务不可用](ALM-18000-Yarn服务不可用-163.md)
    >    -   [ALM-19000 HBase服务不可用](ALM-19000-HBase服务不可用-166.md)
    >    -   [ALM-20002 Hue服务不可用](ALM-20002-Hue服务不可用-168.md)
    >    -   [ALM-23001 Loader服务不可用](ALM-23001-Loader服务不可用-169.md)
    >    -   [ALM-27001 DBService服务不可用](ALM-27001-DBService服务不可用-181.md)
    >    -   [ALM-27003 DBService主备节点间心跳中断](ALM-27003-DBService主备节点间心跳中断-182.md)
    >    -   [ALM-27004 DBService主备数据不同步](ALM-27004-DBService主备数据不同步-183.md)
    >    -   [ALM-43001 Spark2x服务不可用](ALM-43001-Spark2x服务不可用.md)


**Master节点规格升级操作**

1.  登录MRS管理控制台。
2.  选择  “集群列表  \>  现有集群“  ，选中需要升级Master节点规格的集群并单击集群名，进入集群信息页面。
3.  在“节点管理“页签Master节点组的“操作”列选择“升级规格“。
4.  选择升级后的规格，单击“下一步“。
5.  在弹出的“确认“页面确认升级后的节点规格及费用，确认无误后单击“确认“。
6.  确保已停止备Master节点的所有服务（详细操作请参考**Master节点规格升级前准备**的[1](#li487181481727)-[12](#li12169193211415)），在“升级Master规格“页面勾选“我已确认关闭备master节点上的所有服务“和“若升级前未成功停止所有服务，可能导致数据保存失败或损坏“两项提示内容，并单击“提交订单“。
7.  在弹出的“警告“页面，再次确认已确认关闭备master节点上的所有服务，然后单击“确定“开始升级备Master节点的规格。

    节点规格升级需要时间，请耐心等待。升级成功后集群状态更新为“Master备节点升级完成”，否则请联系运维人员处理。

8.  备Master节点升级成功后，参考****Master节点规格升级后操作****的[1](#li1571022151014)-[11](#li47118211017)完成备Master节点所有服务的启动及参数配置。
9.  备Master节点服务启动正常后，进行NameNode主备倒换。仅当集群类型为分析集群时执行该步骤，流式集群跳过该步骤。
    1.  分别访问主备节点的NameNode WebUI界面，NameNode WebUI访问方法请参考[11](#li47118211017)。
    2.  <a name="li67484244318"></a>分别在NameNode WebUI页面的标题栏选择“Overview”，查看并记录主备节点的Namenode ID。记录后不要关闭该页面。

        **图 3**  主节点的Namenode ID<a name="fig72881017493"></a>  
        ![](figures/主节点的Namenode-ID.png "主节点的Namenode-ID")

    3.  任意登录一个Master节点的弹性云服务器，执行如下命令配置环境变量。

        ```
        source /opt/Bigdata/client/bigdata_env
        ```

    4.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

        ```
        kinit MRS集群用户
        ```

        例如,  **kinit admin**.

    5.  执行如下命令进行NameNode主备倒换。

        ```
        hdfs haadmin -failover <主节点Namenode ID> <备节点Namenode ID>
        ```

    6.  进入[9.b](#li67484244318)中未关闭的NameNode WebUI页面，然后刷新该页面，可以看到该NameNode已经主备倒换完成。

        **图 4**  NameNode<a name="fig3872103795519"></a>  
        ![](figures/NameNode.png "NameNode")

10. 参考**Master节点规格升级前准备**的[1](#li487181481727)-[12](#li12169193211415)，停止主Master节点的所有服务。
11. 在“升级Master规格“页面勾选“我已确认启动备master节点上的所有服务“和“我已确认关闭主master节点的所有服务“，并单击“提交主节点升级订单“。
12. 在弹出的“确认“页面再次确认已停止主Master节点的所有服务，然后单击“确定“开始升级主Master节点的规格。

    节点规格升级过程需要时间，请您耐心等待。升级成功后集群状态更新为“Master升级规格成功”，否则请联系运维人员处理。

13. 参考**Master节点规格升级后操作**的[1](#li1571022151014)-[11](#li47118211017)完成主Master节点所有服务的启动及参数配置。
14. 在“升级Master规格“页面勾选“我已确认启动主master节点上的所有服务“，并单击“确定“完成Master规格升级。

**Master节点规格升级后操作**

1.  <a name="li1571022151014"></a>登录Manager，进入集群管理页面，具体请参见[访问Manager](访问Manager-2.md)。
2.  单击“主机 ”，查看Master节点规格升级前准备中[9](#li3448141413114)记录的“NameNode“的业务IP所对应的主机是否满足“运行状态“是为“良好“，“磁盘“、“内存“、“CPU使用率“显示正常（有数值），若满足执行[9](#li1271115271019)。若不满足执行下一步。
3.  远程登录备Master节点，详情请参见[登录集群节点](登录集群节点.md)。
4.  执行以下命令切换为omm用户。

    ```
    su - omm
    ```

5.  执行以下命令启动Agent。

    ```
    sh /opt/Bigdata/nodeagent/bin/start-agent.sh
    ```

6.  执行以下命令确认Agent启动成功。

    ```
    jps | grep NodeAgent
    ```

7.  登录Manager，进入集群管理页面，具体请参考[访问Manager](访问Manager-2.md)。
8.  单击“主机 ”，查看Master节点规格升级前准备中[9](#li3448141413114)记录的“NameNode“的业务IP所对应的主机，确保其“运行状态“是为“良好“，“磁盘“、“内存“、“CPU使用率“显示正常（有数值）。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >Agent成功启动到主机状态显示正常，最长可能需要3分钟时间生效，请耐心等待。若长时间显示异常，请联系运维人员处理。

9.  <a name="li1271115271019"></a>在Manager单击“主机 ”，勾选Master节点规格升级前准备中[9](#li3448141413114)记录的“NameNode“的业务IP所对应的主机前的复选框。
10. 选择“更多\> 启动所有实例”，并等待所有实例启动完成。
11. <a name="li47118211017"></a>访问NameNode WebUI界面，查看NameNode启动状态。

    1.  在Manager页面选择“集群 \> 服务 \> HDFS \> 概览”。
    2.  在“HDFS 概述”栏目，单击“NameNode WebUI“右侧升级完成的备节点或主节点的“NameNode“。
    3.  进入NameNode WebUI界面，在标题栏选择“Startup Progress”，确保Percent Complete显示100%后再执行下一步，如[图5](#fig111356111213)所示。

        **图 5**  NameNode的启动状态<a name="fig111356111213"></a>  
        ![](figures/NameNode的启动状态.png "NameNode的启动状态")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >仅当集群类型为分析集群时执行[11](#li47118211017)，流式集群跳过该步骤。


