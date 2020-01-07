# 使用客户端提交Storm拓扑<a name="ZH-CN_TOPIC_0173177954"></a>

## 操作场景<a name="se6b7b91686f741e68713b7d1b2d44f55"></a>

用户可以根据业务需要，在MRS集群的客户端中提交Storm拓扑，持续处理用户的流数据。启用Kerberos认证的集群，需要提交拓扑的用户属于“stormadmin“或“storm“组。

## 前提条件<a name="s26390c77824e48628302cd27728a109b"></a>

已刷新客户端。

## 操作步骤<a name="s8bca61259f7943bfa5d387cbb7e90a5b"></a>

1.  根据业务情况，准备好客户端，并登录安装客户端的节点。

    例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[集群内节点使用MRS客户端](集群内节点使用MRS客户端.md)。

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

    -   MRS 1.8.0之前的版本拓扑包路径为**/opt/client/Storm/storm-xxx/examples/storm-starter/storm-starter-topologies-xxx.jar**，xxx代表storm的版本号。
    -   MRS 1.8.5及之后版本的拓扑包路径为**/opt/Bigdata/MRS\_XXX/install/FusionInsight-Storm-xxx/adapter/client/controller/storm-examples/lib/storm-starter-xxx-mrs-xx.jar**，Storm-xxx和storm-starter-xxx中的xxx代表storm的版本号，MRS-XXX中的XXX代表MRS的版本号。mrs-xx中的xx代表MRS的大版本号，如MRS 1.8.5版本集群此处为**mrs-1.8.0**。
    -   对于MRS 2.0.1之后版本，拓扑包路径请选择用户自己的拓扑包存放路径。

    例如：

    -   提交storm 1.0.2版本客户端的样例拓扑：**storm jar /opt/client/Storm/storm-1.0.2/examples/storm-starter/storm-starter-topologies-1.0.2.jar org.apache.storm.starter.WordCountTopology topo1**

    -   提交storm 1.2.1版本且MRS版本为1.8.5的客户端样例拓扑：**storm jar /opt/Bigdata/MRS\_1.8.5/install/FusionInsight-Storm-1.2.1/adapter/client/controller/storm-examples/lib/storm-starter-1.2.1-mrs-1.8.0.jar org.apache.storm.starter.WordCountTopology topo1**

    界面提示以下信息表示提交成功：

    ```
    Finished submitting topology: topo1
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果需要拓扑支持采样消息，则还需要增加参数“topology.debug“和“topology.eventlogger.executors“。  
    >-   拓扑如何处理数据是拓扑自身行为。样例拓扑随机生成字符并分隔字符串，需要查看处理情况时，请启用采样功能并参见[查看拓扑处理数据日志](查看Storm拓扑日志.md#s0ffb38030e2a49ccb229939a92913f29)。  

7.  执行以下命令，查看Storm中的拓扑。启用Kerberos认证的集群，只有属于“stormadmin“或“storm“的用户可以查看所有拓扑。

    **storm list**


