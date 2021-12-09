# 使用Yarn客户端<a name="mrs_01_24196"></a>

## 操作场景<a name="zh-cn_topic_0264266044_sfa78c979cca846bc9a575e06ffe87515"></a>

该任务指导用户在运维场景或业务场景中使用Yarn客户端。

## 前提条件<a name="zh-cn_topic_0264266044_s6d0150e80cca450287f729fb56ed593b"></a>

-   已安装客户端。

    例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

-   各组件业务用户由系统管理员根据业务需要创建。安全模式下，“机机”用户需要下载keytab文件。“人机”用户第一次登录时需修改密码。普通模式不需要下载keytab文件及修改密码操作。

## 使用Yarn客户端<a name="zh-cn_topic_0264266044_sc37d25bf096f4cfc9238391b20eef646"></a>

1.  安装客户端。
    -   MRS 3.x之前版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
    -   MRS 3.x及之后版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。

2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  如果集群为安全模式，执行以下命令进行用户认证。普通模式集群无需执行用户认证。

    **kinit** _组件业务用户_

6.  直接执行Yarn命令。例如：

    **yarn application -list**


## 客户端常见使用问题<a name="zh-cn_topic_0264266044_section29499362105048"></a>

1.  当执行Yarn客户端命令时，客户端程序异常退出，报“java.lang.OutOfMemoryError”的错误。

    这个问题是由于Yarn客户端运行时的所需的内存超过了Yarn客户端设置的内存上限（默认为128MB）。对于MRS 3.x后续版本集群，可以通过修改“<客户端安装路径\>/HDFS/component\_env“中的“CLIENT\_GC\_OPTS“来修改Yarn客户端的内存上限。例如，需要设置该内存上限为1GB，则设置：

    ```
    export CLIENT_GC_OPTS="-Xmx1G"
    ```

    对于MRS 3.x之前版本集群，可以通过修改“<客户端安装路径\>/HDFS/component\_env“中的“GC\_OPTS\_YARN“来修改Yarn客户端的内存上限。例如，需要设置该内存上限为1GB，则设置：

    ```
    export GC_OPTS_YARN="-Xmx1G"
    ```

    在修改完后，使用如下命令刷新客户端配置，使之生效：

    **source **<_客户端安装路径_\>/**bigdata\_env**

2.  如何设置Yarn客户端运行时的日志级别？

    Yarn客户端运行时的日志是默认输出到Console控制台的，其级别默认是INFO级别。有的时候为了定位问题，需要开启DEBUG级别日志，可以通过导出一个环境变量来设置，命令如下：

    **export YARN\_ROOT\_LOGGER=DEBUG,console**

    在执行完上面命令后，再执行Yarn Shell命令时，即可打印出DEBUG级别日志。

    如果想恢复INFO级别日志，可执行如下命令：

    **export YARN\_ROOT\_LOGGER=INFO,console**


