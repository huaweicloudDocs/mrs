# 界面配置dfs.blocksize后put数据，block大小还是原来的大小<a name="mrs_03_0083"></a>

## 问题背景与现象<a name="zh-cn_topic_0167275441_s8c03434db87d4eee9610cff894082d22"></a>

界面配置“dfs.blocksize“，将其设置为268435456，put数据，block大小还是原来的大小。

## 原因分析<a name="zh-cn_topic_0167275441_sd3558c4fb1dd46d2b2906f0a99fb251f"></a>

客户端的“hdfs-site.xml“文件中的dfs.blocksize大小没有更改，以客户端配置为准。

## 解决办法<a name="zh-cn_topic_0167275441_sfffb1346002e46d28cb94c2fd00314b7"></a>

1.  确保“dfs.blocksize“为512的倍数。
2.  重新下载安装客户端或者更改客户端配置。
3.  dfs.blocksize是客户端配置，以客户端为准。若客户端不配置，以服务端为准。

