# Flume 服务端进程故障<a name="ZH-CN_TOPIC_0181626574"></a>

## 问题现象<a name="zh-cn_topic_0167274573_section18651179162810"></a>

Flume运行一段时间后，MRS Manager界面Flume实例显示运行状态“故障”。

## 原因分析<a name="zh-cn_topic_0167274573_section155572154348"></a>

Flume文件或文件夹权限异常，重启后Manager界面提示如下信息：

```
[2019-02-26 13:38:02]RoleInstance prepare to start failure [{ScriptExecutionResult=ScriptExecutionResult [exitCode=126, output=, errMsg=sh: line 1: /opt/Bigdata/MRS_XXX/install/FusionInsight-Flume-1.6.0/flume/bin/flume-manage.sh: Permission denied
```

## 解决办法<a name="zh-cn_topic_0167274573_section930421011360"></a>

与运行正常的Flume节点进行文件和文件夹权限对比，更改错误文件或文件夹权限。

