# HBase日志文件过大导致OS盘空间不足<a name="mrs_03_0294"></a>

## 用户问题<a name="section7422205115512"></a>

OS盘/var/log分区空间不足。

## 问题现象<a name="section7749157195512"></a>

“/var/log/Bigdata/hbase/\*/hbase-omm-\*.out”日志文件过大，造成OS盘/var/log分区空间不足。

## 原因分析<a name="section893314412561"></a>

在HBase长时间运行场景下，操作系统会把JVM创建的“/tmp/.java\_pid\*”文件定期清理。因为HBase的内存监控使用了JVM的jinfo命令，而jinfo依赖“/tmp/.java\_pid\*”文件，当该文件不存在时，jinfo会执行**kill -3**将jstack信息打印到.out日志文件里，从而导致.out日志文件过大。

## 处理步骤<a name="section1637769105619"></a>

在每个HBase实例的节点上部署定期清理.out日志文件的定时任务。后台登录HBase的实例节点，在crontab -e中添加每天0点清理.out日志的定时任务。

**crontab -e**

**00 00 \* \* \* for file in \`ls /var/log/Bigdata/hbase/\*/hbase-omm-\*.out\`; do echo "" \> $file; done**

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果.out大文件出现比较频繁，可以每天清理多次或者调整操作系统的自动清理策略。

