# Flink对接OBS文件系统<a name="mrs_01_1288"></a>

使用本章节前已参考[配置存算分离集群（委托方式）](配置存算分离集群（委托方式）.md)或[配置存算分离集群（AKSK方式）](配置存算分离集群（AKSK方式）.md)完成存算分离集群配置。

1.  使用安装客户端的用户登录Flink客户端安装节点。
2.  执行如下命令初始化环境变量。

    **source $\{client\_home\}/bigdata\_env**

3.  需要配置好Flink客户端。具体配置参考[安装客户端（3.x及之后版本）](安装客户端（3-x及之后版本）.md)。
4.  如果是安全集群，使用以下命令进行用户认证，如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit **_用户名_

5.  在Flink命令行显式添加要访问的OBS文件系统。

    **./bin/flink run --class com.huawei.bigdata.flink.examples.FlinkProcessingTimeAPIMain ./config/FlinkCheckpointJavaExample.jar --chkPath obs://**_OBS并行文件系统名称_


>![](public_sys-resources/icon-note.gif) **说明：** 
>由于Flink作业是On Yarn运行，在配置Flink对接OBS文件系统之前需要确保Yarn对接OBS文件系统功能是正常的。

