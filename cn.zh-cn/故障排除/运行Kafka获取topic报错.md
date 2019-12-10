# 运行Kafka获取topic报错<a name="ZH-CN_TOPIC_0168547248"></a>

## 用户问题<a name="section18305143583116"></a>

客户运行Kafka获取topic报错。

## 问题现象<a name="section117424454313"></a>

运行Kafka获取topic时报错，报错内容如下：

```
ERROR org.apache.kafka.common.errors.InvalidReplicationFactorException: Replication factor: 2 larger than available brokers: 0.
```

## 原因分析<a name="section1237061220324"></a>

由特殊字符导致获取zookeeper地址的变量错误。

## 处理步骤<a name="section85027392079"></a>

1.  登录任意一个Master节点。
2.  <a name="li679244874819"></a>执行**cat /opt/client/Kafka/kafka/config/server.properties |grep '^zookeeper.connect ='**命令，查看zookeeper地址的变量。
3.  重新运行Kafka获取topic，其中从[2](#li679244874819)中获取的变量不要添加任何字符。

