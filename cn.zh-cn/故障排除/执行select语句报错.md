# 执行select语句报错<a name="ZH-CN_TOPIC_0210454006"></a>

## 问题现象<a name="zh-cn_topic_0167276298_s279271d9ef1f448c82bf851fcc361636"></a>

执行语句select count\(\*\) from XXX;时客户端报错：Error:Error while processing statement :FAILED:Execution Error,return code 2 from ...

这个报错return code2说明是在执行mapreduce任务期间报错导致任务失败。

![](figures/zh-cn_image_0167275662.jpg)

## 原因分析<a name="zh-cn_topic_0167276298_s2be99397c5de4111a414f6fbd0fb7c2f"></a>

1.  进入yarn原生页面查看mapreduce任务的日志看到报错是无法识别到压缩方式导致错误，看文件后缀是gzip压缩，堆栈却报出是zlib方式。

    ![](figures/zh-cn_image_0167276373.png)

2.  因此怀疑此语句查询的表对应的HDFS上的文件有问题，map日志中打印出了解析的对应的文件名，将其从HDFS上下载到本地，看到是gz结尾的文件，使用**tar**命令解压报错，格式不正确无法解压。使用file命令查看文件属性发现此文件来自于FAT系统的压缩而非unix。

    ![](figures/zh-cn_image_0167275251.png)


## 解决办法<a name="zh-cn_topic_0167276298_sd6477f1effc345f1abf9f4286dc8eb07"></a>

将格式不正确的文件移除hdfs目录或者替换为正确的格式的文件。

