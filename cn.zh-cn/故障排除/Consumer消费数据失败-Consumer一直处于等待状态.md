# Consumer消费数据失败，Consumer一直处于等待状态<a name="mrs_03_0064"></a>

## 问题现象<a name="zh-cn_topic_0167276017_s8c5a413588744f3ea1320d012fdb73cb"></a>

使用MRS服务安装集群，主要安装ZooKeeper、Kafka。

在使用Consumer从Kafka消费数据时，发现客户端一直处于等待状态。

## 可能原因<a name="zh-cn_topic_0167276017_s32d34cd2ed084d9dbf63d1ca6576eea0"></a>

1.  Kafka服务异常。
2.  客户端Consumer侧采用非安全访问，服务端配置禁止访问。
3.  客户端Consumer侧采用非安全访问，Kafak Topic设置ACL。

## 原因分析<a name="zh-cn_topic_0167276017_section7028627115832"></a>

Consumer向Kafka消费数据失败，可能原因客户端Consumer侧问题或者Kafka侧问题。

1.  查看kafka服务状态：
    -   MRS Manager界面操作：登录MRS Manager，依次选择 "服务管理 \> Kafka ，查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。
    -   FusionInsight Manager界面操作：登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka，

        查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。

2.  查看Consumer客户端日志发现频繁连接Broker节点和断链打印信息，如下所示。

    ```
    [root@10-10-144-2 client]# kafka-console-consumer.sh --topic test --zookeeper 10.5.144.2:2181/kafka --from-beginning 
    
    
    [2017-03-07 09:22:00,658] INFO Fetching metadata from broker BrokerEndPoint(1,10.5.144.2,9092) with correlation id 26 for 1 topic(s) Set(test) (kafka.client.ClientUtils$)
    [2017-03-07 09:22:00,659] INFO Connected to 10.5.144.2:9092 for producing (kafka.producer.SyncProducer)
    [2017-03-07 09:22:00,659] INFO Disconnecting from 10.5.144.2:9092 (kafka.producer.SyncProducer)
    ```

    Consumer采用9092端口来访问Kafka，9092为非安全端口。

3.  通过Manager页面查看当前Kafka集群配置，发现未配置自定义参数“allow.everyone.if.no.acl.found“=“false“。
    -   MRS Manager界面操作入口：登录MRS Manager，依次选择 “服务管理 \> Kafka\> 配置”。
    -   FusionInsight Manager界面操作入口：登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置"。

4.  当acl设置为false不允许采用9092来进行访问。
5.  查看Consumer客户端日志发现频繁连接Broker节点和断链打印信息，如下所示。

    ```
    [root@10-10-144-2 client]# kafka-console-consumer.sh --topic test_acl --zookeeper 10.5.144.2:2181/kafka --from-beginning
    
    
    [2017-03-07 09:49:16,992] INFO Fetching metadata from broker BrokerEndPoint(2,10.5.144.3,9092) with correlation id 16 for 1 topic(s) Set(topic_acl) (kafka.client.ClientUtils$)
    [2017-03-07 09:49:16,993] INFO Connected to 10.5.144.3:9092 for producing (kafka.producer.SyncProducer)
    [2017-03-07 09:49:16,994] INFO Disconnecting from 10.5.144.3:9092 (kafka.producer.SyncProducer)
    ```

    Consumer采用21005端口来访问Kafka，21005为非安全端口。

6.  通过客户端命令查看topic的acl权限设置信息。

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
    User:test_user has Allow permission for operations: Write from hosts: * 
    ```

    Topic设置acl，则不允许采用9092来访问。

7.  查看Consumer客户端日志发现打印信息，如下所示。

    ```
    [root@10-10-144-2 client]# kafka-console-consumer.sh --topic topic_acl --bootstrap-server 10.5.144.2:21007 --consumer.config /opt/client/Kafka/kafka/config/consumer.properties --from-beginning --new-consumer
    
    [2017-03-07 10:19:18,478] INFO Kafka version : 0.9.0.0 (org.apache.kafka.common.utils.AppInfoParser)
    [2017-03-07 10:19:18,478] INFO Kafka commitId : unknown (org.apache.kafka.common.utils.AppInfoParser)
    ```

    Consumer采用21007端口来访问Kafka。

8.  通过客户端命令klist查询当前认证用户：

    ```
    [root@10-10-144-2 client]# klist
    Ticket cache: FILE:/tmp/krb5cc_0
    Default principal: test@HADOOP.COM
    
    Valid starting     Expires            Service principal
    01/25/17 11:06:48  01/26/17 11:06:45  krbtgt/HADOOP.COM@HADOOP.COM
    ```

    当前认证用户为**test**。

9.  通过客户端命令查看topic的acl权限设置信息。

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:24002/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
     User:test_user has Allow permission for operations: Write from hosts: * 
     User:ttest_user has Allow permission for operations: Read from hosts: *
    ```

    Topic设置acl，test无权限进行consumer操作。

    解决方法参考[2](#zh-cn_topic_0167276017_li42828707125627)。

10. 通过SSH登录Kafka Broker：

    通过**cd /var/log/Bigdata/kafka/broker**命令进入日志目录。

    查看kafka-authorizer.log发现如下日志提示用户不属于kafka或者kafkaadmin组。

    ```
    2017-01-25 13:26:33,648 | INFO  | [kafka-request-handler-0] | The principal is test, belongs to Group : [hadoop, ficommon] | kafka.authorizer.logger (SimpleAclAuthorizer.scala:169)
    2017-01-25 13:26:33,648 | WARN  | [kafka-request-handler-0] | The user is not belongs to kafka or kafkaadmin group, authorize failed! | kafka.authorizer.logger (SimpleAclAuthorizer.scala:170)
    ```

    解决方法参考[3](#zh-cn_topic_0167276017_li40704794133146)。


## 解决办法<a name="zh-cn_topic_0167276017_s2d3c010d3bc0406fa3f531ccd76c297f"></a>

1.  配置自定义参数“allow.everyone.if.no.acl.found“参数为“true“，重启Kafka服务。
2.  <a name="zh-cn_topic_0167276017_li42828707125627"></a>采用具有权限用户登录。

    例如：

    **kinit test\_user**

    或者赋予用户相关权限。

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >需要使用Kafka管理员用户（属于kafkaadmin组）操作。

    例如：

    **kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka  --topic topic\_acl --consumer --add --allow-principal User:test --group test**

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=8.5.144.2:2181/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
     User:test_user has Allow permission for operations: Write from hosts: *
      User:test has Allow permission for operations: Describe from hosts: *
      User:test has Allow permission for operations: Write from hosts: *
      User:test has Allow permission for operations: Read from hosts: *
      
    ```

3.  <a name="zh-cn_topic_0167276017_li40704794133146"></a>用户加入**Kafka**组或者**Kafkaadmin**组。

