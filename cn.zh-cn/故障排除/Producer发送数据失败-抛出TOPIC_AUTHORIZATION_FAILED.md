# Producer发送数据失败，抛出TOPIC\_AUTHORIZATION\_FAILED<a name="mrs_03_0061"></a>

## 问题现象<a name="zh-cn_topic_0167276234_s8c5a413588744f3ea1320d012fdb73cb"></a>

使用MRS安装集群，主要安装ZooKeeper、Kafka。

在使用Producer向Kafka发送数据功能时，发现客户端抛出TOPIC\_AUTHORIZATION\_FAILED。

## 可能原因<a name="zh-cn_topic_0167276234_s32d34cd2ed084d9dbf63d1ca6576eea0"></a>

1.  Kafka服务异常。
2.  客户端Producer侧采用非安全访问，服务端配置禁止访问。
3.  客户端Producer侧采用非安全访问，Kafka Topic设置ACL。

## 原因分析<a name="zh-cn_topic_0167276234_section7028627115832"></a>

Producer发送数据到Kafka失败，可能原因客户端Producer侧问题或者Kafka侧问题。

1.  查看kafka服务状态：
    -   MRS Manager界面操作：登录MRS Manager，依次选择 "服务管理 \> Kafka ，查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。
    -   FusionInsight Manager界面操作：登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka，

        查看当前Kafka状态，发现状态为良好，且监控指标内容显示正确。

2.  查看Producer客户端日志，发现打印TOPIC\_AUTHORIZATION\_FAILED异常信息。

    ```
    [root@10-10-144-2 client]# kafka-console-producer.sh --broker-list 10.5.144.2:9092 --topic test
    1
    [2017-01-24 16:58:36,671] WARN Error while fetching metadata with correlation id 0 : {test=TOPIC_AUTHORIZATION_FAILED} (org.apache.kafka.clients.NetworkClient)
    [2017-01-24 16:58:36,672] ERROR Error when sending message to topic test with key: null, value: 1 bytes with error: Not authorized to access topics: [test] (org.apache.kafka.clients.producer.internals.ErrorLoggingCallback)
    ```

    Producer采用9092端口来访问Kafka，9092为非安全端口。

3.  通过Manager页面，查看当前Kafka集群配置，发现未设置自定义配置“allow.everyone.if.no.acl.found“=“false“。
    -   MRS Manager界面操作入口：登录MRS Manager，依次选择 “服务管理 \> Kafka\> 配置”。
    -   FusionInsight Manager界面操作入口：登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> Kafka \> 配置"。

4.  当acl设置为false不允许采用9092来进行访问。
5.  查看Producer客户端日志，发现打印TOPIC\_AUTHORIZATION\_FAILED异常信息。

    ```
    [root@10-10-144-2 client]# kafka-console-producer.sh --broker-list 10.5.144.2:21005 --topic test_acl
    1
    [2017-01-25 11:09:40,012] WARN Error while fetching metadata with correlation id 0 : {test_acl=TOPIC_AUTHORIZATION_FAILED} (org.apache.kafka.clients.NetworkClient)
    [2017-01-25 11:09:40,013] ERROR Error when sending message to topic test_acl with key: null, value: 1 bytes with error: Not authorized to access topics: [test_acl] (org.apache.kafka.clients.producer.internals.ErrorLoggingCallback)
    [2017-01-25 11:14:40,010] WARN Error while fetching metadata with correlation id 1 : {test_acl=TOPIC_AUTHORIZATION_FAILED} (org.apache.kafka.clients.NetworkClient)
    ```

    Producer采用21005端口来访问Kafka，21005为非安全端口。

6.  通过客户端命令查看topic的acl权限设置信息。

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:24002/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
    User:test_user has Allow permission for operations: Write from hosts: * 
    ```

    Topic设置acl，则不允许采用9092来访问。

7.  查看Producer客户端日志，发现打印TOPIC\_AUTHORIZATION\_FAILED异常信息。

    ```
    [root@10-10-144-2 client]# kafka-console-producer.sh --broker-list 10.5.144.2:21007 --topic topic_acl --producer.config /opt/client/Kafka/kafka/config/producer.properties
    1
    [2017-01-25 12:43:58,506] WARN Error while fetching metadata with correlation id 0 : {topic_acl=TOPIC_AUTHORIZATION_FAILED} (org.apache.kafka.clients.NetworkClient)
    [2017-01-25 12:43:58,507] ERROR Error when sending message to topic topic_acl with key: null, value: 1 bytes with error: Not authorized to access topics: [topic_acl] (org.apache.kafka.clients.producer.internals.ErrorLoggingCallback)
    ```

    Producer采用21007端口来访问Kafka。

8.  通过客户端命令klist查询当前认证用户。

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
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
    User:test_user has Allow permission for operations: Write from hosts: * 
    ```

    Topic设置acl，用户test\_user具有producer权限。test无权限进行producer操作。

    解决方法参考步骤2。

10. 通过SSH登录Kafka Broker：

    通过**cd /var/log/Bigdata/kafka/broker**命令进入日志目录。

    查看kafka-authorizer.log发现如下日志提示用户不属于kafka或者kafkaadmin组。

    ```
    2017-01-25 13:26:33,648 | INFO  | [kafka-request-handler-0] | The principal is test, belongs to Group : [hadoop, ficommon] | kafka.authorizer.logger (SimpleAclAuthorizer.scala:169)
    2017-01-25 13:26:33,648 | WARN  | [kafka-request-handler-0] | The user is not belongs to kafka or kafkaadmin group, authorize failed! | kafka.authorizer.logger (SimpleAclAuthorizer.scala:170)
    ```

    解决方法参考步骤3。


## 解决办法<a name="zh-cn_topic_0167276234_s2d3c010d3bc0406fa3f531ccd76c297f"></a>

1.  配置自定义配置“allow.everyone.if.no.acl.found“参数为“true“，重启Kafka服务。
2.  采用具有权限用户登录。

    例如：

    **kinit test\_user**

    或者赋予用户相关权限。

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >需要使用Kafka管理员用户（属于kafkaadmin组）操作。

    例如：

    **kafka-acls.sh --authorizer-properties zookeeper.connect=10.5.144.2:2181/kafka  --topic topic\_acl --producer --add --allow-principal User:test**

    ```
    [root@10-10-144-2 client]# kafka-acls.sh --authorizer-properties zookeeper.connect=8.5.144.2:2181/kafka --list --topic topic_acl
    Current ACLs for resource `Topic:topic_acl`: 
     User:test_user has Allow permission for operations: Describe from hosts: *
     User:test_user has Allow permission for operations: Write from hosts: *
      User:test has Allow permission for operations: Describe from hosts: *
      User:test has Allow permission for operations: Write from hosts: *
    ```

3.  用户加入**Kafka**组或者**Kafkaadmin**组。

