# 使用Storm客户端<a name="mrs_01_24194"></a>

## 操作场景<a name="zh-cn_topic_0265781906_scc6744d7a5a6433f901fa254a6fd8754"></a>

该任务指导用户在运维场景或业务场景中使用Storm客户端。

## 前提条件<a name="zh-cn_topic_0265781906_s97a1fb645a964d3bada59b808f6cab48"></a>

-   已安装客户端。例如安装目录为“/opt/hadoopclient”。
-   各组件业务用户由系统管理员根据业务需要创建。安全模式下，“机机”用户需要下载keytab文件。“人机”用户第一次登录时需修改密码。（普通模式不涉及）

## 操作步骤<a name="zh-cn_topic_0265781906_scd63f70223e14394b9859e5b66d6d978"></a>

1.  根据业务情况，准备好客户端，登录安装客户端的节点。

    请根据客户端所在位置，参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_24212.html)章节，登录安装客户端的节点。

2.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

3.  执行以下命令配置环境变量。

    **source bigdata\_env**

4.  若安装了Storm多实例，在使用Storm命令提交拓扑时，请执行以下命令加载具体实例的环境变量，否则请跳过此步骤。例如，Storm-2实例：

    **source Storm-2/component\_env**

5.  执行以下命令，进行用户认证。（普通模式跳过此步骤）

    **kinit **_组件业务用户_

6.  执行命令进行客户端操作。

    例如执行以下命令：

    -   **cql**
    -   **storm**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >同一个storm客户端不能同时连接安全和非安全的ZooKeeper。


