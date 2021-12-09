# 执行Kafka Topic创建操作，发现无法创建提示NoAuthException<a name="mrs_03_0121"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276024_s5d135719deec4560b99adb07a0aa6416"></a>

在使用Kafka客户端命令创建Topic时，发现Topic无法被创建。

```
kafka-topics.sh --create --zookeeper 192.168.234.231:2181/kafka --replication-factor 1 --partitions 2 --topic test
```

提示错误NoAuthException，KeeperErrorCode = NoAuth for /config/topics。

具体如下：

```
Error while executing topic command org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /config/topics
org.I0Itec.zkclient.exception.ZkException: org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /config/topics
 at org.I0Itec.zkclient.exception.ZkException.create(ZkException.java:68)
 at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:685)
 at org.I0Itec.zkclient.ZkClient.create(ZkClient.java:304)
 at org.I0Itec.zkclient.ZkClient.createPersistent(ZkClient.java:213)
 at kafka.utils.ZkUtils$.createParentPath(ZkUtils.scala:215)
 at kafka.utils.ZkUtils$.updatePersistentPath(ZkUtils.scala:338)
 at kafka.admin.AdminUtils$.writeTopicConfig(AdminUtils.scala:247)
```

## 可能原因<a name="zh-cn_topic_0167276024_s8efdc02bbb1a42cba8fa3e43e2e68817"></a>

用户不属于**kafkaadmin**组，Kafka提供安全访问接口，kafkaamdin组用户才可以进行topic删除操作。

## 原因分析<a name="zh-cn_topic_0167276024_section10342981143649"></a>

1.  使用客户端命令，打印NoAuthException异常。

    ```
    Error while executing topic command org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /config/topics
    org.I0Itec.zkclient.exception.ZkException: org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /config/topics
     at org.I0Itec.zkclient.exception.ZkException.create(ZkException.java:68)
     at org.I0Itec.zkclient.ZkClient.retryUntilConnected(ZkClient.java:685)
     at org.I0Itec.zkclient.ZkClient.create(ZkClient.java:304)
     at org.I0Itec.zkclient.ZkClient.createPersistent(ZkClient.java:213)
     at kafka.utils.ZkUtils$.createParentPath(ZkUtils.scala:215)
     at kafka.utils.ZkUtils$.updatePersistentPath(ZkUtils.scala:338)
     at kafka.admin.AdminUtils$.writeTopicConfig(AdminUtils.scala:247)
    ```

2.  通过客户端命令**klist**查询当前认证用户：

    ```
    [root@10-10-144-2 client]# klist
    Ticket cache: FILE:/tmp/krb5cc_0
    Default principal: test@HADOOP.COM
    
    Valid starting     Expires            Service principal
    01/25/17 11:06:48  01/26/17 11:06:45  krbtgt/HADOOP.COM@HADOOP.COM
    ```

    如上例中当前认证用户为**test**。

3.  通过命令**id**查询用户组信息。

    ```
    [root@10-10-144-2 client]# id test
    uid=20032(test) gid=10001(hadoop) groups=10001(hadoop),9998(ficommon),10003(kafka)
    ```


## 解决办法<a name="zh-cn_topic_0167276024_section38845959134910"></a>

MRS Manager界面操作：

1.  登录MRS Manager。
2.  选择“系统设置 \> 用户管理”。
3.  在操作用户对应的“操作”列，单击“修改”。
4.  为用户加入**kafkaadmin**组。

    **图 1**  为用户加入kafkaadmin组<a name="zh-cn_topic_0167276024_fig65541556172518"></a>  
    ![](figures/为用户加入kafkaadmin组.png "为用户加入kafkaadmin组")

5.  通过命令**id**查询用户组信息。

    ```
    [root@10-10-144-2 client]# id test
    uid=20032(test) gid=10001(hadoop) groups=10001(hadoop),9998(ficommon),10002(kafkaadmin)，10003(kafka)
    ```


FusionInsight Manager界面操作：

1.  登录FusionInsight Manager。
2.  选择“系统 \> 权限 \> 用户”。
3.  在使用的用户所在行的单击“修改”。
4.  为用户添加**kafkaadmin**组。单击“确定”完成修改操作。
5.  通过命令**id**查询用户组信息。

    ```
    [root@10-10-144-2 client]# id test
    uid=20032(test) gid=10001(hadoop) groups=10001(hadoop),9998(ficommon),10002(kafkaadmin)，10003(kafka)
    ```


