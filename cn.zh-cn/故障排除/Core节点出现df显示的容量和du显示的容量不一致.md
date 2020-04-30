# Core节点出现df显示的容量和du显示的容量不一致<a name="ZH-CN_TOPIC_0232157197"></a>

## 用户问题<a name="section18305143583116"></a>

Core节点出现df显示的容量和du显示的容量不一致

## 问题现象<a name="section117424454313"></a>

Core节点出现df显示的容量和du显示的容量不一致：

分别使用命令**df -h**  和命令**du -sh /srv/BigData/hadoop/data1/**查询得到的/srv/BigData/hadoop/data1/目录磁盘占用量相差较大（大于10G）。

## 原因分析<a name="section1237061220324"></a>

使用命令**lsof |grep deleted**可以查询到此目录下有大量log文件处于deleted状态。

出现此问题的一种情况是长时间运行某些spark任务，任务中的一些container一直运行，并且持续产生日志；spark的executor在打印日志的时候使用了log4j的日志滚动功能，将日志输出到stdout文件下；而container同时也会监控这个文件，导致此文件被两个进程同时监控。当其中一个进程按照配置滚动的时候，删除了最早的日志文件，但是另一个进程依旧占用此文件句柄。从而产生了deleted状态的文件。

## 处理步骤<a name="section520813413313"></a>

将spark的executor日志输出目录修改成其他名称

1.  打开日志配置文件，默认在<客户端地址\>/Spark/spark/conf/log4j-executor.properties。
2.  将日志输出文件改名，例如：

    log4j.appender.sparklog.File = $\{spark.yarn.app.container.log.dir\}/stdout改为：log4j.appender.sparklog.File = $\{spark.yarn.app.container.log.dir\}/stdout.log

3.  保存退出
4.  重新提交任务。

