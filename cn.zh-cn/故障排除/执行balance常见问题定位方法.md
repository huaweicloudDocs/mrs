# 执行balance常见问题定位方法<a name="mrs_03_0094"></a>

## 问题1：报没权限（Access denied）执行balance<a name="zh-cn_topic_0167276457_section47724704103832"></a>

**问题详细**：执行start-balancer.sh，“hadoop-root-balancer-主机名.out”日志显示“Access denied for user test1. Superuser privilege is required”

```
 
cat /opt/client/HDFS/hadoop/logs/hadoop-root-balancer-host2.out
Time Stamp               Iteration#  Bytes Already Moved  Bytes Left To Move  Bytes Being Moved
INFO: Watching file:/opt/client/HDFS/hadoop/etc/hadoop/log4j.properties for changes with interval : 60000
org.apache.hadoop.ipc.RemoteException(org.apache.hadoop.security.AccessControlException): Access denied for user test1. 
Superuser privilege is required
at org.apache.hadoop.hdfs.server.namenode.FSPermissionChecker.checkSuperuserPrivilege(FSPermissionChecker.java:122)
at org.apache.hadoop.hdfs.server.namenode.FSNamesystem.checkSuperuserPrivilege(FSNamesystem.java:5916)

```

**问题根因：**

执行balance需要使用管理员账户

**解决方法**

-   安全版本

    使用hdfs（默认密码Hdfs@123）或者其他属于supergroup组的用户认证后，执行balance

-   普通版本

    执行HDFS的balance命令前，需要在客户端执行su - hdfs命令。


## 问题2：执行balance失败，/system/balancer.id文件异常<a name="zh-cn_topic_0167276457_section6644201091646"></a>

**问题详细**：

在HDFS客户端启动一个Balance进程，该进程被异常停止后，再次执行Balance操作，操作会失败。

```
org.apache.hadoop.ipc.RemoteException(org.apache.hadoop.protocol.RecoveryInProgressException): Failed to APPEND_FILE /system/balancer.id for DFSClient because lease recovery is in progress. Try again later.
```

**问题根因：**

通常，HDFS执行Balance操作结束后，会自动释放“/system/balancer.id”文件，可再次正常执行Balance。

但在上述场景中，由于第一次的Balance操作是被异常停止的，所以第二次进行Balance操作时，“/system/balancer.id”文件仍然存在，则会触发append /system/balancer.id操作，进而导致Balance操作失败。

**解决方法**

方法1：等待硬租期超过1小时后，原有客户端释放租约，再执行第二次Balance操作。

方法2：删除HDFS中的“/system/balancer.id”文件，再执行下次Balance操作。

