# 管理Storm拓扑<a name="ZH-CN_TOPIC_0057181204"></a>

## 操作场景<a name="zh-cn_topic_0053981411_section63666741154720"></a>

用户可以使用Storm的WebUI管理拓扑。“storm“用户组的用户只能管理由自己提交的拓扑任务，“stormadmin“用户组的用户可以管理所有拓扑任务。

## 操作步骤<a name="zh-cn_topic_0053981411_section6149081717539"></a>

1.  访问Storm的WebUI。
2.  在“Topology summary“区域，单击指定的拓扑名称。
3.  通过“Topology actions“管理Storm拓扑。
    -   激活拓扑

        单击“Activate“，转化当前拓扑为激活状态。

    -   去激活拓扑

        单击“Deactivate“，转化当前拓扑为去激活状态。

    -   重部署拓扑

        单击“Rebalance“，将当前拓扑重新部署执行，需要输入执行重部署的等待时间，单位为秒。一般在集群中节点数发生变化时进行，以更好利用集群资源。

    -   删除拓扑

        单击“Kill“，将当前拓扑删除，需要输入执行操作的等待时间，单位为秒。

    -   采样、停止采样拓扑消息

        单击“Debug“，在弹出窗口输入流数据采样消息的数值，单位为百分比，表示从开始采样到停止采样这段时间内所有数据的采集比例。例如输入“10“，则采集比例为10%。

        如果需要停止采样，则单击“Stop Debug“。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >只有在提交拓扑时启用采样功能，才支持此功能。查看采样处理数据，请参见[查看拓扑处理数据日志](查看Storm拓扑日志.md#zh-cn_topic_0053981410_section3146436417554)。  

    -   修改拓扑日志级别

        单击“Change Log Level“，可以为Storm日志指定新的日志信息级别。


4.  显示拓扑结构图。

    在“Topology Visualization“区域单击“Show Visualization“，执行拓扑可视化操作。


