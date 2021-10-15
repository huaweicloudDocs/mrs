# 调整shell客户端日志级别<a name="mrs_03_0086"></a>

-   **临时调整**，关闭该shell客户端窗口后，日志会还原为默认值。
    1.  执行**export HADOOP\_ROOT\_LOGGER**命令可以调整客户端日志级别。
    2.  执行**export HADOOP\_ROOT\_LOGGER=_日志级别_,console**，可以调整shell 客户端的日志级别。

        **export HADOOP\_ROOT\_LOGGER=DEBUG,console**，调整为DEBUG。

        **export HADOOP\_ROOT\_LOGGER=ERROR,console**，调整为ERROR。


-   **永久调整**
    1.  在HDFS客户端环境变量配置文件“/opt/client/HDFS/component\_env”（其中“/opt/client”需要改为实际客户端路径）增加“export HADOOP\_ROOT\_LOGGER=_日志级别_,console”。
    2.  执行**source /opt/client/bigdata\_env**。
    3.  重新执行客户端命令。


