# Hiveserver或者Metastore实例的健康状态为Concerning<a name="ZH-CN_TOPIC_0208559513"></a>

## 问题现象<a name="zh-cn_topic_0167274562_sf10df03c6be743d693a1ba5536bfc228"></a>

Hiveserver或者Metastore实例的健康状态为Concerning。

## 可能原因<a name="zh-cn_topic_0167274562_sde58cdd386c74b8c940eb2114143b0a3"></a>

hiveserver或者metastore实例在启动的时候发生异常，无法正常启动。如，当修改MetaStore/HiveServer GC参数时，可通过查看对应进程的启动日志，如hiveserver.out\(hadoop-omm-jar-192-168-1-18.out\)文件排查。 如下异常：

Error: Could not find or load main class Xmx2048M

说明java虚拟机启动时，将Xmx2048M 作为java进程的启动参数而不是JVM的启动参数了，如下将符号‘-’误删掉。

```
METASTORE_GC_OPTS=Xms1024M Xmx2048M -DIgnoreReplayReqDetect 
-XX\:CMSFullGCsBeforeCompaction\=1 -XX\:+UseConcMarkSweepGC 
-XX\:+CMSParallelRemarkEnabled -XX\:+UseCMSCompactAtFullCollection 
-XX\:+ExplicitGCInvokesConcurrent -server -XX\:MetaspaceSize\=128M 
-XX\:MaxMetaspaceSize\=256M
```

## 解决方案<a name="zh-cn_topic_0167274562_section15541112445215"></a>

因此遇到此类异常应该检查最近的变更项，以确认是否配置有误。

```
METASTORE_GC_OPTS=Xms1024M -Xmx2048M -DIgnoreReplayReqDetect 
-XX\:CMSFullGCsBeforeCompaction\=1 -XX\:+UseConcMarkSweepGC 
-XX\:+CMSParallelRemarkEnabled -XX\:+UseCMSCompactAtFullCollection 
-XX\:+ExplicitGCInvokesConcurrent -server -XX\:MetaspaceSize\=128M 
-XX\:MaxMetaspaceSize\=256M
```

