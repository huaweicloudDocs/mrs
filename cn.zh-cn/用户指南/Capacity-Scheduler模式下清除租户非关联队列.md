# Capacity Scheduler模式下清除租户非关联队列<a name="admin_guide_000125"></a>

## 操作场景<a name="zh-cn_topic_0263899263_s94bd05867723402788c78624748a68a1"></a>

在Yarn Capacity Scheduler模式下，删除租户的时候，只是把租户队列的容量设置为0，并且把状态设为“STOPPED”，但是队列在Yarn的服务里面仍然残留。由于Yarn的机制，无法动态删除队列，管理员可以执行命令手动清除残留的队列。

## 对系统的影响<a name="zh-cn_topic_0263899263_section035427203612"></a>

-   脚本运行过程中会重启controller服务，同步Yarn的配置，并重启主备ResourceManager实例。
-   重启controller服务时，无法登录和操作FusionInsight Manager。
-   重启主备ResourceManager实例后，Yarn组件以及依赖Yarn的组件会出现短暂的服务不可用告警。

## 前提条件<a name="zh-cn_topic_0263899263_s24257ed61c9f43209a08e354c61dac50"></a>

已删除某个租户，但该租户对应的队列依然存在。

## 操作步骤<a name="zh-cn_topic_0263899263_section7614183215345"></a>

1.  确定该租户对应的队列依然存在。
    1.  在FusionInsight Manager界面，选择“集群  \>  _待操作集群的名称_  \> 服务  \>  Yarn“。通过“ResourceManager\(主\)”链接进入ResourceManager WebUI界面。
    2.  单击左侧“Scheduler”界面，可以查看租户对应的队列依然存在，且状态为“STOPPED”，“Configured Capacity”值为0。

2.  以**omm**用户登录主管理节点。
3.  执行以下目录，执行“cleanQueuesAndRestartRM.sh”脚本。

    **cd $\{BIGDATA\_HOME\}/om-server/om/sbin**

    **./cleanQueuesAndRestartRM.sh** **-c **_集群ID_****

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“集群ID”为需执行操作集群ID号，可在FusionInsight Manager的“集群 \>_ 待操作集群的名称_  \> 集群属性”中查看。

    在脚本运行过程中，需输入**yes**及管理员密码。

    ```
    Running the script will restart Controller and restart ResourceManager.
    Are you sure you want to continue connecting (yes/no)?yes
    Please input admin password:
    Begin to backup queues ...
    ...
    ```

4.  脚本运行成功后，在FusionInsight Manager界面，选择“集群  \>  _待操作集群名称_  \> 服务  \>  Yarn“。通过“ResourceManager\(主\)”链接进入ResourceManager WebUI界面。
5.  单击左侧“Scheduler”界面，确认被删除租户的队列已经清除。

