# 停止或卸载Flume客户端<a name="ZH-CN_TOPIC_0173178818"></a>

## 操作场景<a name="s55c24d727b874ee6abd0f7f03b68c7b1"></a>

指导运维工程师停止、启动Flume客户端，以及在不需要Flume数据采集通道时，卸载Flume客户端。

## 操作步骤<a name="s07beb52489454bce883d8062608a73da"></a>

-   停止Flume角色的客户端。

假设Flume客户端安装路径为“/opt/FlumeClient“，执行以下命令，停止Flume客户端：

**cd /opt/FlumeClient/fusioninsight-flume-1.6.0/bin**

**./flume-manage.sh stop**

执行脚本后，显示如下信息，说明成功的停止了Flume客户端：

```
Stop Flume PID=120689 successful..
```

>![](public_sys-resources/icon-note.gif) **说明：**   
>Flume客户端停止后会自动重启，如果不需自动重启，请执行以下命令：  
>**./flume-manage.sh stop force**  
>需要启动时，可执行以下命令：  
>**./flume-manage.sh start force**  

-   卸载Flume角色的客户端。

假设Flume客户端安装路径为“/opt/FlumeClient“，执行以下命令，卸载Flume客户端：

**cd /opt/FlumeClient/fusioninsight-flume-1.6.0/inst**

**./uninstall.sh**

