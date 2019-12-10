# 使用udf函数提示"Invalid function"<a name="ZH-CN_TOPIC_0207461512"></a>

## 问题现象<a name="zh-cn_topic_0167275811_s4062da02d4d340ed9dbd38c42c5a7475"></a>

在 Hive客户端中使用Spark创建UDF函数时，报出"ERROR 10011","invalid function"的异常，如下：

```
Error: Error while compiling statement: FAILED: SemanticException [Error 10011]: Line 1:7 Invalid function 'test_udf' (state=42000,code=10011)
```

在多个HiveServer之间使用UDF也存在上述问题。例如，在HiveServer1中使用HiverServer2创建的UDF，如果不及时同步元数据信息，连接HiveServer1的客户端也会提示上述错误信息。

## 可能原因<a name="zh-cn_topic_0167275811_sde58cdd386c74b8c940eb2114143b0a3"></a>

多个HiveServer之间或者Hive与Spark之间共用的元数据未同步，导致不同HiveServer实例内存数据不一致，造成UDF不生效。

## 解决方案<a name="zh-cn_topic_0167275811_sf8f53c018c784bab9ca84e6d32b5d35d"></a>

需要将新建的UDF信息同步到HiveServer中，执行reload function操作即可。

