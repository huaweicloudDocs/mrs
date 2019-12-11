# Flume向Spark Streaming提交作业，提交到集群后报类找不到<a name="ZH-CN_TOPIC_0169495350"></a>

## 用户问题<a name="zh-cn_topic_0135447910_section18305143583116"></a>

Flume向Spark Streaming提交作业，提交到集群后报类找不到。

## 问题现象<a name="zh-cn_topic_0135447910_section117424454313"></a>

Spark Streaming代码打成jar包提交到集群后报类找不到错误，通过以下两种方式依然不生效。

1.  在提交Spark作业的时候使用**--jars**  命令引用类所在的jar包。
2.  将类所在的jar包引入Spark Streaming的jar包。

## 原因分析<a name="zh-cn_topic_0135447910_section1237061220324"></a>

执行Spark作业时无法加载部分jar，导致找不到class。

## 处理步骤<a name="zh-cn_topic_0135447910_section520813413313"></a>

1.  使用  **--jars**  加载flume-ng-sdk-\{version\}.jar依赖包。
2.  同时修改**spark-default.conf**中两个配置项。

    **spark.driver.extraClassPath=$PWD/\*:\{加上原来配置的值\}**

    **spark.executor.extraClassPath =$PWD/\***

3.  作业运行成功。如果还有报错，则需要排查还有哪个jar没有加载，再次执行步骤1和步骤2。

