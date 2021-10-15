# 运行Spark报错<a name="mrs_03_0043"></a>

## 用户问题<a name="section18305143583116"></a>

运行Spark作业报找不到指定的类。

## 问题现象<a name="section117424454313"></a>

运行Spark作业报找不到指定的类。报错内容如下：

```
Exception encountered | org.apache.spark.internal.Logging$class.logError(Logging.scala:91)
org.apache.hadoop.hbase.DoNotRetryIOException: java.lang.ClassNotFoundException: org.apache.phoenix.filter.SingleCQKeyValueComparisonFilter
```

## 原因分析<a name="section1237061220324"></a>

用户配置的默认路径不正确。

## 处理步骤<a name="section4717145115210"></a>

1.  登录任意Master节点。
2.  修改Spark客户端目录下的配置文件。

    执行**vim /opt/client/Spark/spark/conf/spark-defaults.conf**命令，打开spark-defaults.conf文件，设置“spark.executor.extraClassPath“  取值为“$\{PWD\}/\*“。


