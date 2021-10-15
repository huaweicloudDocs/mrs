# SparkStreaming消费Kafka消息失败，提示Error getting partition metadata<a name="mrs_03_0065"></a>

## 问题现象<a name="zh-cn_topic_0167275353_sf1db540c14e54778b6b4d6c6c2200ca7"></a>

使用SparkStreaming来消费Kafka中指定Topic的消息时，发现无法从Kafka中获取到数据。提示如下错误： Error getting partition metadata。

```
Exception in thread "main" org.apache.spark.SparkException:  Error getting partition metadata for 'testtopic'. Does the topic exist?
org.apache.spark.streaming.kafka.KafkaCluster$$anonfun$checkErrors$1.apply(KafkaCluster.scala:366)
org.apache.spark.streaming.kafka.KafkaCluster$$anonfun$checkErrors$1.apply(KafkaCluster.scala:366)
scala.util.Either.fold(Either.scala:97)
org.apache.spark.streaming.kafka.KafkaCluster$.checkErrors(KafkaCluster.scala:365)
org.apache.spark.streaming.kafka.KafkaUtils$.createDirectStream(KafkaUtils.scala:422)
com.huawei.bigdata.spark.examples.FemaleInfoCollectionPrint$.main(FemaleInfoCollectionPrint.scala:45)
com.huawei.bigdata.spark.examples.FemaleInfoCollectionPrint.main(FemaleInfoCollectionPrint.scala)
sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
java.lang.reflect.Method.invoke(Method.java:498)
org.apache.spark.deploy.SparkSubmit$.org$apache$spark$deploy$SparkSubmit$$runMain(SparkSubmit.scala:762)
org.apache.spark.deploy.SparkSubmit$.doRunMain$1(SparkSubmit.scala:183)
org.apache.spark.deploy.SparkSubmit$.submit(SparkSubmit.scala:208)
org.apache.spark.deploy.SparkSubmit$.main(SparkSubmit.scala:123)
org.apache.spark.deploy.SparkSubmit.main(SparkSubmit.scala)
```

## 可能原因<a name="zh-cn_topic_0167275353_section18513165114376"></a>

1.  Kafka服务异常。
2.  客户端Consumer侧采用非安全访问，服务端配置禁止访问。
3.  客户端Consumer侧采用非安全访问，Kafak Topic设置ACL。

## 原因分析<a name="zh-cn_topic_0167275353_sda1fa700b23b46be9d5f5adfb2943e40"></a>

1.  查看kafka服务状态：
    -   MRS Manager界面操作：登录MRS Manager，依次选择 "服务管理 \> Kafka ，查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。

    -   FusionInsight Manager界面操作：登录FusionInsight Manager，选择“集群 \> 待操作集群的名称 \> 服务 \> Kafka，

        查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。



1.  通过Manager页面，查看当前Kafka集群配置，发现未配置“allow.everyone.if.no.acl.found“或配置为“false“。
    -   MRS Manager界面操作入口：登录MRS Manager，依次选择 “服务管理 \> Kafka\> 配置”。
    -   FusionInsight Manager界面操作入口：登录FusionInsight Manager，选择“集群 \> 待操作集群的名称 \> 服务 \> Kafka \> 配置"。

2.  当acl设置为false不允许采用Kafka非安全端口21005来进行访问。
3.  通过客户端命令查看topic的acl权限设置信息：

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
    User:test_user has Allow permission for operations: Write from hosts: * 
    ```

    Topic设置acl，则不允许采用Kafka非安全端口21005来访问。


## 解决办法<a name="zh-cn_topic_0167275353_section892460194610"></a>

1.  修改或者添加自定义配置“allow.everyone.if.no.acl.found“参数为“true“，重启Kafka服务。
2.  删除Topic设置的ACL。

    例如：

    **kinit test\_user**

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >需要使用Kafka管理员用户（属于kafkaadmin组）操作。

    例如：

    **kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka   **--remove --allow-principal User:test\_user --producer --topic  **topic\_acl******

    **kafka-acls.sh --authorizer-properties zookeeper.connect=**10.5.144.2:2181/kafka**  --remove --allow-principal User:test\_user --consumer --topic  **topic\_acl**  --group test**


