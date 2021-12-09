# spark-shell执行sql跨文件系统load数据到hive表失败<a name="mrs_03_0283"></a>

## 用户问题<a name="section18305143583116"></a>

使用spark-shell命令执行sql或者spark-submit提交的spark任务里面有sql的load命令，并且原数据和目标表存储位置不是同一套文件系统，上述两种方式MapReduce任务启动时会报错。

## 原因分析<a name="section1237061220324"></a>

当使用load导入数据到hive表的时候，属于需要跨文件系统的情况（例如原数据在hdfs上，而hive表数据存放在obs上），并且文件长度大于阈值（默认32M），则会触发使用distcp的MapReduce任务来执行数据迁移操作。这个MapReduce任务配置直接从spark任务配置里面提取，但是spark任务的net.topology.node.switch.mapping.impl配置项不是hadoop的默认值，需要使用spark的jar包，因此MapReduce会报类找不到。

## 处理步骤<a name="section16451144015715"></a>

方案一：

如果文件较小，则可以将默认长度设置得大于文件最大长度，例如最大的文件是95M，则设置：

```
hive.exec.copyfile.maxsize=104857600
```

方案二：

如果确实文件较大，需要使用distcp任务来提高数据迁移效率，则可以在spark任务启动的时候增加设置参数：

```
--conf spark.hadoop.net.topology.node.switch.mapping.impl=org.apache.hadoop.net.ScriptBasedMapping
```

