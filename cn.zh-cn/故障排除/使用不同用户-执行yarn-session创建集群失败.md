# 使用不同用户，执行yarn-session创建集群失败<a name="mrs_03_0136"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274935_section370710207470"></a>

使用Flink过程中，具有两个相同权限用户testuser和bdpuser。

使用用户testuser创建Flink集群正常，但是切换至bdpuser用户创建Fllink集群时，执行yarn-session.sh命令报错：

```
2019-01-02 14:28:09,098 | ERROR | [main] | Ensure path threw exception | org.apache.flink.shaded.curator.org.apache.curator.framework.imps.CuratorFrameworkImpl (CuratorFrameworkImpl.java:566) 
org.apache.flink.shaded.zookeeper.org.apache.zookeeper.KeeperException$NoAuthException: KeeperErrorCode = NoAuth for /flink/application_1545397824912_0022
```

## 可能原因<a name="zh-cn_topic_0167274935_section27469961718"></a>

高可用配置项未修改。由于在Flink的配置文件中，**high-availability.zookeeper.client.acl**默认为**creator**，仅创建者有权限访问，新用户无法访问ZooKeeper上的目录导致yarn-session.sh执行失败。

## 解决办法<a name="zh-cn_topic_0167274935_section13544011114717"></a>

1.  修改客户端配置文件**conf/flink-conf.yaml**中配置项**high-availability.zookeeper.path.root**，例如：

    ```
    high-availability.zookeeper.path.root： flink2
    ```

2.  重新提交任务。

