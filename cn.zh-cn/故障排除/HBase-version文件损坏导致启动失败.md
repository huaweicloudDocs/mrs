# HBase version文件损坏导致启动失败<a name="mrs_03_0115"></a>

## 问题背景<a name="zh-cn_topic_0167274943_s2a86d4e9a3904293addd1c2baac35557"></a>

HBase启动失败。

## 原因分析<a name="zh-cn_topic_0167274943_saf8e8662aeb84fa397ea94d370156755"></a>

1.  HBase启动时会读取hbase.version文件，但是日志显示读取存在异常。

    ![](figures/zh-cn_image_0264281723.png)

2.  通过**hadoop fs -cat  /hbase/hbase.version**命令发现文件不能正常查看，该文件损坏。

## 解决办法<a name="zh-cn_topic_0167274943_sb3283261286e41428e15111d63e9105e"></a>

1.  <a name="zh-cn_topic_0167274943_l6b279b8cf6a2455c95073287a2ccb7fa"></a>执行**hbase hbck -fixVersionFile**命令修复文件。
2.  如[1](#zh-cn_topic_0167274943_l6b279b8cf6a2455c95073287a2ccb7fa)不能解决，从同版本的其他集群中获取hbase.version文件上传进行替换。
3.  重新启动HBase服务。

