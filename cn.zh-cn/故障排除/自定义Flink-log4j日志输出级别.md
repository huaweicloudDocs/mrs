# 自定义Flink log4j日志输出级别<a name="mrs_03_0220"></a>

## 用户问题<a name="zh-cn_topic_0135447910_section18305143583116"></a>

MRS 3.1.0集群自定义Flink log4j日志级别不生效。

## 问题现象<a name="zh-cn_topic_0135447910_section117424454313"></a>

1.  在使用MRS 3.1.0集群Flink数据分析时，将$Flink\_HOME/conf目录下的log4j.properties文件中日志级别修改为INFO级别日志。
2.  任务正常提交后，console未打印出INFO级别日志，输出的日志级别还是ERROR级别。

## 原因分析<a name="zh-cn_topic_0135447910_section1237061220324"></a>

修改$Flink\_HOME/conf目录下的log4j.properties文件，控制的是JobManager和TaskManager的算子内的日志输出，输出的日志会打印到对应的yarn contain中，可以在yarn web ui查看对应日志。MRS 3.1.0及之后版本的Flink 1.12.0版本开始默认的日志框架是log4j2，配置的方式跟之前log4j的方式有区别，使用如log4j日志规则不会生效。

## 处理步骤<a name="section233210502511"></a>

Log4j2详细日志规格配置参考开源官方文档：[http://logging.apache.org/log4j/2.x/manual/configuration.html\#Properties](http://logging.apache.org/log4j/2.x/manual/configuration.html#Properties)

