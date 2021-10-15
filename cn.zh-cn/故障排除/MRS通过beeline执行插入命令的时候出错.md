# MRS通过beeline执行插入命令的时候出错<a name="mrs_03_0235"></a>

## 用户问题<a name="section18305143583116"></a>

MRS通过beeline执行插入命令的时出错

## 问题现象<a name="section117424454313"></a>

在hive的beeline中执行**insert into**插入语句的时候会报以下的错误:

```
Mapping run in Tez on Hive transactional table fails when data volume is high with error: "org.apache.hadoop.hive.ql.lockmgr.LockException Reason: Transaction... already aborted, Hive SQL state [42000]."
```

## 原因分析<a name="section1237061220324"></a>

对于Join操作，由于集群配置不理想和Tez资源设置不合理导致该问题。

## 处理步骤<a name="section156191822193911"></a>

可以在beeline上设置配置参数进行解决。

1.  设置以下属性以优化性能（建议在集群级别进行更改）
    -   设置hive.auto.convert.sortmerge.join = true
    -   设置hive.optimize.bucketmapjoin = true
    -   设置hive.optimize.bucketmapjoin.sortedmerge = true

2.  更改以下内容以调整Tez的资源 。
    -   设置hive.tez.container.size = \{与YARN容器相同的大小\}
    -   将hive.tez.container.size设置为与YARN容器大小yarn.scheduler.minimum-allocation-mb相同或更小的值（如设置为二分之一或四分之一的值），但不要超过yarn.scheduler.maximum-allocation-mb 。


