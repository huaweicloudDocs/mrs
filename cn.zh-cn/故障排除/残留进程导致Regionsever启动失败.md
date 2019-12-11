# 残留进程导致Regionsever启动失败<a name="ZH-CN_TOPIC_0181626563"></a>

## 问题现象<a name="zh-cn_topic_0167276367_s3a5d27a5e0df400e8d676c5269e79eae"></a>

HBase服务启动失败，健康检查报错。

## 原因分析<a name="zh-cn_topic_0167276367_s955ba8d349e641d9872e9a99c5f6b800"></a>

查看启动HBase服务时manager页面的详细打印信息，提示the previous process is not quit。

## 解决办法<a name="zh-cn_topic_0167276367_s3b9e068a933a484aa20086b85d84d1fb"></a>

1.  登录节点，后台通过执行**ps -ef | grep HRegionServer**发现确实存在一个残留的进程。
2.  确认进程可以kill后，kill掉该进程（如果kill无法终止该进程，需要使用kill -9来强制终止该进程）。
3.  重新启动HBase服务成功。

