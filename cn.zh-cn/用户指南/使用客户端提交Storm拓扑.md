# 使用客户端提交Storm拓扑<a name="ZH-CN_TOPIC_0057181202"></a>

## 操作场景<a name="zh-cn_topic_0057061151_section63666741154720"></a>

用户可以根据业务需要，在MRS集群的客户端中提交Storm拓扑，持续处理用户的流数据。启用Kerberos认证的集群，需要提交拓扑的用户属于“stormadmin“或“storm“组。

## 前提条件<a name="zh-cn_topic_0057061151_section951436815483"></a>

已刷新客户端。

## 操作步骤<a name="zh-cn_topic_0057061151_section273864979823"></a>

1.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[客户端管理](客户端管理.md)。

2.  执行以下命令切换用户。

    **sudo su - omm**

3.  执行以下命令，切换到客户端目录，例如“/opt/client“。

    **cd /opt/client**

4.  执行以下命令，配置环境变量。

    **source bigdata\_env**

5.  启用Kerberos认证的集群，执行以下命令认证用户身份。未启用Kerberos认证集群无需执行。

    **kinit** _**Storm用户**_

    例如，**kinit admin**

6.  执行以下命令，提交Storm拓扑：

    **storm jar** _**拓扑包路径 拓扑Main方法的类名称 拓扑名称**_

    例如，提交客户端的样例拓扑：

    **storm jar /opt/client/Storm/storm-1.0.2/examples/storm-starter/storm-starter-topologies-1.0.2.jar org.apache.storm.starter.WordCountTopology topo1**

    界面提示以下信息表示提交成功：

    ```
    Finished submitting topology: topo1
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果需要拓扑支持采样消息，则还需要增加参数“topology.debug“和“topology.eventlogger.executors“。例如，  
    >    **storm jar /opt/client/Storm/storm-1.0.2/examples/storm-starter/storm-starter-topologies-1.0.2.jar org.apache.storm.starter.WordCountTopology topo1 -c topology.debug=true -c topology.eventlogger.executors=1**。  
    >-   拓扑如何处理数据是拓扑自身行为。样例拓扑随机生成字符并分隔字符串，需要查看处理情况时，请启用采样功能并参见[查看拓扑处理数据日志](查看Storm拓扑日志.md#zh-cn_topic_0053981410_section3146436417554)。  

7.  执行以下命令，查看Storm中的拓扑。启用Kerberos认证的集群，只有属于“stormadmin“或“storm“的用户可以查看所有拓扑。

    **storm list**


