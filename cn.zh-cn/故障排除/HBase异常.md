# HBase异常<a name="mrs_03_0217"></a>

## 用户问题<a name="section18305143583116"></a>

HBase异常。

## 问题现象<a name="section117424454313"></a>

导入数据到hbase报错：NotServingRegionException。

## 原因分析<a name="section1237061220324"></a>

当一个block size大于2G时，hdfs在seek的时候会出现读取异常，持续频繁写入regionserver时出现了full gc，且时间比较久，导致hmaster与regionserver之间的心跳异常，然后hmaster把regionserver标记为dead状态，强制重启了Regionserver，重启后触发servercrash机制开始回滚wal日志。现在这个splitwal的文件已经达到将近2.1G，且其仅有一个block块，导致hdfs seek异常，引起splitwal失败，regionserver检测到当前这个wal日志还需要split，又会触发splitwal日志的机制进行回滚，就这样在split与split失败之间不停循环，导致无法上线该regionserver节点上的region，最后出现查询该RS上某一个region时会报region not online的异常。

## 处理步骤<a name="section10354134118129"></a>

1.  进入HBase服务页面：
    -   MRS 1.8.10及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)，然后选择“服务管理 \> HBase”。
    -   MRS 1.8.10之后及2._x_版本，单击集群名称，登录集群详情页面，选择“组件管理 \> HBase”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“同步”进行IAM用户同步）。

    -   MRS 3.x及后续版本，登录FusionInsight Manager。然后选择“集群 \>  _待操作的集群名_称 \> 服务 \> HBase”。

2.  在“HMaster Web UI“右侧，单击“HMaster \(主\)“进入HBase Web UI界面。
3.  在“Procedures“页签查看问题节点。
4.  以root用户登录问题节并执行**hdfs dfs -ls**命令查看所有块信息。
5.  执行**hdfs dfs -mkdir**命令新建目录用于存放问题块。
6.  执行**hdfs dfs -mv**将问题块转移至新建目录位置。

## 建议与总结<a name="section8898183420"></a>

以下两点可供参考：

-   数据块损坏，通过**hdfs fsck /tmp -files -blocks -racks**命令检查block数据块健康信息。
-   region正在分裂时对数据的操作会抛NotServingRegionException异常。

