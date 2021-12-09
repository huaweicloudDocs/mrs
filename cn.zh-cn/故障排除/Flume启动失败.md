# Flume启动失败<a name="mrs_03_0058"></a>

## 问题现象<a name="zh-cn_topic_0167275225_section0345175892713"></a>

安装Flume服务或重启Flume服务失败。

## 原因分析<a name="zh-cn_topic_0167275225_section152394773410"></a>

1.  Flume堆内存设置的值大于机器剩余内存，查看Flume启动日志：

    ```
    [CST 2019-02-26 13:31:43][INFO] [[checkMemoryValidity:124]] [GC_OPTS is invalid: Xmx(40960000MB) is bigger than the free memory(56118MB) in system.] [9928]
    ```

2.  Flume文件或文件夹权限异常，界面或后台会提示如下信息：

    ```
    [2019-02-26 13:38:02]RoleInstance prepare to start failure [{ScriptExecutionResult=ScriptExecutionResult [exitCode=126, output=, errMsg=sh: line 1: /opt/Bigdata/MRS_XXX/install/FusionInsight-Flume-1.9.0/flume/bin/flume-manage.sh: Permission denied
    ```

3.  JAVA\_HOME配置错误，查看Flume agent启动日志：

    ```
    Info: Sourcing environment configuration script /opt/FlumeClient/fusioninsight-flume-1.9.0/conf/flume-env.sh
    + '[' -n '' ']'
    + exec /tmp/MRS-Client/MRS_Flume_ClientConfig/JDK/jdk-8u18/bin/java '-XX:OnOutOfMemoryError=bash /opt/FlumeClient/fusioninsight-flume-1.9.0/bin/out_memory_error.sh /opt/FlumeClient/fusioninsight-flume-1.9.0/conf %p' -Xms2G -Xmx4G -XX:CMSFullGCsBeforeCompaction=1 -XX:+UseConcMarkSweepGC -XX:+CMSParallelRemarkEnabled -XX:+UseCMSCompactAtFullCollection -Dkerberos.domain.name=hadoop.hadoop.com -verbose:gc -XX:+UseGCLogFileRotation -XX:NumberOfGCLogFiles=10 -XX:GCLogFileSize=1M -XX:+PrintGCDetails -XX:+PrintGCDateStamps -Xloggc:/var/log/Bigdata//flume-client-1/flume/flume-root-20190226134231-%p-gc.log -Dproc_org.apache.flume.node.Application -Dproc_name=client -Dproc_conf_file=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf/properties.properties -Djava.security.krb5.conf=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf//krb5.conf -Djava.security.auth.login.config=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf//jaas.conf -Dzookeeper.server.principal=zookeeper/hadoop.hadoop.com -Dzookeeper.request.timeout=120000 -Dflume.instance.id=884174180 -Dflume.agent.name=clientName1 -Dflume.role=client -Dlog4j.configuration.watch=true -Dlog4j.configuration=log4j.properties -Dflume_log_dir=/var/log/Bigdata//flume-client-1/flume/ -Dflume.service.id=flume-client-1 -Dbeetle.application.home.path=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf/service -Dflume.called.from.service -Dflume.conf.dir=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf -Dflume.metric.conf.dir=/opt/FlumeClient/fusioninsight-flume-1.9.0/conf -Dflume.script.home=/opt/FlumeClient/fusioninsight-flume-1.9.0/bin -cp '/opt/FlumeClient/fusioninsight-flume-1.9.0/conf:/opt/FlumeClient/fusioninsight-flume-1.9.0/lib/*:/opt/FlumeClient/fusioninsight-flume-1.9.0/conf/service/' -Djava.library.path=/opt/FlumeClient/fusioninsight-flume-1.9.0/plugins.d/native/native org.apache.flume.node.Application --conf-file /opt/FlumeClient/fusioninsight-flume-1.9.0/conf/properties.properties --name client
    /opt/FlumeClient/fusioninsight-flume-1.9.0/bin/flume-ng: line 233: /tmp/FusionInsight-Client/Flume/FusionInsight_Flume_ClientConfig/JDK/jdk-8u18/bin/java: No such file or directory
    ```


## 解决办法<a name="zh-cn_topic_0167275225_section53141350193510"></a>

1.  适当调大堆内存（xmx）的值。
2.  与正常启动Flume的节点进行文件和文件夹权限对比，更改错误文件或文件夹权限。
3.  重新配置JAVA\_HOME。客户端替换$\{install\_home\}/fusioninsight-flume-_flume组件版本号_/conf/ENV\_VARS文件中JAVA\_HOME的值，服务端替换etc目录下ENV\_VARS文件中JAVA\_HOME的值。

    其中JAVA\_HOME的值可通过登录正常启动Flume的节点，执行**echo $\{JAVA\_HOME\}**获取。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >$\{install\_home\}为Flume客户端的安装路径。


