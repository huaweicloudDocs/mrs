# 使用Oozie客户端<a name="mrs_01_24193"></a>

## 操作场景<a name="zh-cn_topic_0264266061_s73cc65a7fbfb4321ab80199959561d37"></a>

该任务指导用户在运维场景或业务场景中使用Oozie客户端。

## 前提条件<a name="zh-cn_topic_0264266061_s2da0086f0bc84bb69150a5cd50f8a24f"></a>

-   已安装客户端。例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

-   各组件业务用户由系统管理员根据业务需要创建。安全模式下，“机机”用户需要下载keytab文件。“人机”用户第一次登录时需修改密码。

## 使用Oozie客户端<a name="zh-cn_topic_0264266061_s0af1abfd047941a29aaddd2a713d338b"></a>

1.  安装客户端。
    -   MRS 3.x之前版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
    -   MRS 3.x及之后版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。

2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  判断集群认证模式。
    -   安全模式，执行以下命令进行用户认证。_exampleUser_为提交任务的用户名。

        **kinit** _exampleUser_

    -   普通模式，执行[6](#zh-cn_topic_0264266061_li1585491617519)。

6.  <a name="zh-cn_topic_0264266061_li1585491617519"></a>配置Hue。
    1.  spark2x环境配置（如果不涉及spark2x任务，可以跳过此步骤）：

        **hdfs dfs -put /opt/hadoopclient/Spark2x/spark/jars/\*.jar /user/oozie/share/lib/spark2x/**

    2.  上传Oozie配置文件以及Jar包至HDFS：

        **hdfs dfs -mkdir /user/**_exampleUser_

        **hdfs dfs -put -f /opt/hadoopclient/Oozie/oozie-client-5.1.0-hw-ei-310003/examples /user/**_exampleUser_/

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   _exampleUser_为提交任务的用户名。
        >-   在提交任务的用户和非job.properties文件均无变更的前提下，客户端安装目录/Oozie/oozie-client-5.1.0-hw-ei-310003/examples目录一经上传HDFS，后续可重复使用，无需多次提交。
        >-   当HDFS目录“/user/oozie/share”中的jar包发生变化时，需要重启Oozie服务。
        >-   解决Spark和Yarn关于jetty的jar冲突。
        >    **hdfs dfs -rm -f /user/oozie/share/lib/spark/jetty-all-9.2.22.v20170606.jar**
        >-   普通模式下，上传过程如果遇到“Permission denied“的问题，可执行以下命令进行处理。
        >    **su - omm**
        >    **source /opt/hadoopclient/bigdata\_env**
        >    **hdfs dfs -chmod -R 777 /user/oozie**
        >    **exit**



