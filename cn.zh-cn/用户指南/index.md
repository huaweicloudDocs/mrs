# 13\_MRS用户指南-大纲调整190603

-   [IAM权限管理]
    -   [IAM权限管理基本概念](IAM权限管理基本概念.md)
    -   [创建用户并授权使用MRS](创建用户并授权使用MRS.md)
    -   [创建MRS自定义策略](创建MRS自定义策略.md)
    -   [策略语法：细粒度策略](策略语法-细粒度策略.md)
    -   [策略语法：RBAC](策略语法-RBAC.md)
    -   [IAM用户同步MRS](IAM用户同步MRS.md)

-   [入门]
    -   [如何使用MRS](如何使用MRS.md)
    -   [创建集群](创建集群-入门.md)
    -   [上传示例数据和程序](上传示例数据和程序.md)
    -   [添加作业](添加作业.md)
    -   [删除集群](删除集群-入门.md)

-   [配置集群]
    -   [概览](概览.md)
    -   [集群列表简介](集群列表简介.md)
    -   [购买方式简介](购买方式简介.md)
    -   [快速购买Hadoop分析集群](快速购买Hadoop分析集群.md)
    -   [快速购买HBase集群](快速购买HBase集群.md)
    -   [快速购买Kafka集群](快速购买Kafka集群.md)
    -   [自定义购买集群](自定义购买集群.md)
    -   [创建集群](创建集群.md)
    -   [创建最小规格集群](创建最小规格集群.md)
    -   [创建专属云MRS集群](创建专属云MRS集群.md)
    -   [创建集群（历史版本）](创建集群（历史版本）.md)
    -   [添加集群标签](添加集群标签.md)
    -   [通过引导操作安装第三方软件]
        -   [引导操作简介](引导操作简介.md)
        -   [准备引导操作脚本](准备引导操作脚本.md)
        -   [添加引导操作](添加引导操作.md)
        -   [查看执行记录](查看执行记录.md)
        -   [脚本样例](脚本样例.md)


-   [管理现有集群]
    -   [查看和监控集群]
        -   [查看集群基本信息](查看集群基本信息.md)
        -   [查看集群补丁信息](查看集群补丁信息.md)
        -   [查看和定制集群监控指标](查看和定制集群监控指标.md)
        -   [管理服务和主机监控](管理服务和主机监控.md)

    -   [扩容集群](扩容集群.md)
    -   [缩容集群](缩容集群.md)
    -   [配置弹性伸缩规则](配置弹性伸缩规则.md)
    -   [创建集群时配置弹性伸缩规则](创建集群时配置弹性伸缩规则.md)
    -   [升级Master节点规格](升级Master节点规格.md)
    -   [配置消息通知](配置消息通知.md)
    -   [运维]
        -   [运维授权](运维授权.md)
        -   [日志共享](日志共享.md)

    -   [删除集群](删除集群.md)
    -   [退订集群](退订集群.md)
    -   [删除失败任务](删除失败任务.md)
    -   [组件管理]
        -   [支持滚动重启](支持滚动重启.md)

    -   [作业管理]
        -   [作业简介](作业简介.md)
        -   [运行MapReduce作业](运行MapReduce作业.md)
        -   [运行Spark作业](运行Spark作业.md)
        -   [运行HiveSql作业](运行HiveSql作业.md)
        -   [运行SparkSql作业](运行SparkSql作业.md)
        -   [运行Flink作业](运行Flink作业.md)
        -   [运行Kafka作业](运行Kafka作业.md)
        -   [查看作业配置信息和日志](查看作业配置信息和日志.md)
        -   [停止作业](停止作业.md)
        -   [复制作业](复制作业.md)
        -   [删除作业](删除作业.md)
        -   [使用OBS加密数据运行作业](使用OBS加密数据运行作业.md)
        -   [配置作业消息通知](配置作业消息通知.md)

    -   [管理数据文件](管理数据文件.md)
    -   [告警管理]
        -   [查看告警列表](查看告警列表.md)
        -   [查看与手动清除告警](查看与手动清除告警.md)

    -   [告警参考]
        -   [ALM-12001 审计日志转储失败](ALM-12001-审计日志转储失败.md)
        -   [ALM-12002 HA资源异常](ALM-12002-HA资源异常.md)
        -   [ALM-12004 OLdap资源异常](ALM-12004-OLdap资源异常.md)
        -   [ALM-12005 OKerberos资源异常](ALM-12005-OKerberos资源异常.md)
        -   [ALM-12006 节点故障](ALM-12006-节点故障.md)
        -   [ALM-12007 进程故障](ALM-12007-进程故障.md)
        -   [ALM-12010 Manager主备节点间心跳中断](ALM-12010-Manager主备节点间心跳中断.md)
        -   [ALM-12011 Manager主备节点同步数据异常](ALM-12011-Manager主备节点同步数据异常.md)
        -   [ALM-12012 NTP服务异常](ALM-12012-NTP服务异常.md)
        -   [ALM-12016 CPU使用率超过阈值](ALM-12016-CPU使用率超过阈值.md)
        -   [ALM-12017 磁盘容量不足](ALM-12017-磁盘容量不足.md)
        -   [ALM-12018 内存使用率超过阈值](ALM-12018-内存使用率超过阈值.md)
        -   [ALM-12027 主机PID使用率超过阈值](ALM-12027-主机PID使用率超过阈值.md)
        -   [ALM-12028 主机D状态进程数超过阈值](ALM-12028-主机D状态进程数超过阈值.md)
        -   [ALM-12031 omm用户或密码即将过期](ALM-12031-omm用户或密码即将过期.md)
        -   [ALM-12032 ommdba用户或密码即将过期](ALM-12032-ommdba用户或密码即将过期.md)
        -   [ALM-12033 慢盘故障](ALM-12033-慢盘故障.md)
        -   [ALM-12034 周期备份任务失败](ALM-12034-周期备份任务失败.md)
        -   [ALM-12035 恢复失败后数据状态未知](ALM-12035-恢复失败后数据状态未知.md)
        -   [ALM-12037 NTP服务器异常](ALM-12037-NTP服务器异常.md)
        -   [ALM-12038 监控指标转储失败](ALM-12038-监控指标转储失败.md)
        -   [ALM-12039 GaussDB主备数据不同步](ALM-12039-GaussDB主备数据不同步.md)
        -   [ALM-12040 系统熵值不足](ALM-12040-系统熵值不足.md)
        -   [ALM-13000 ZooKeeper服务不可用](ALM-13000-ZooKeeper服务不可用.md)
        -   [ALM-13001 ZooKeeper可用连接数不足](ALM-13001-ZooKeeper可用连接数不足.md)
        -   [ALM-13002 ZooKeeper内存使用量超过阈值](ALM-13002-ZooKeeper内存使用量超过阈值.md)
        -   [ALM-14000 HDFS服务不可用](ALM-14000-HDFS服务不可用.md)
        -   [ALM-14001 HDFS磁盘空间使用率超过阈值](ALM-14001-HDFS磁盘空间使用率超过阈值.md)
        -   [ALM-14002 DataNode磁盘空间使用率超过阈值](ALM-14002-DataNode磁盘空间使用率超过阈值.md)
        -   [ALM-14003 丢失的HDFS块数量超过阈值](ALM-14003-丢失的HDFS块数量超过阈值.md)
        -   [ALM-14004 损坏的HDFS块数量超过阈值](ALM-14004-损坏的HDFS块数量超过阈值.md)
        -   [ALM-14006 HDFS文件数超过阈值](ALM-14006-HDFS文件数超过阈值.md)
        -   [ALM-14007 HDFS NameNode内存使用率超过阈值](ALM-14007-HDFS-NameNode内存使用率超过阈值.md)
        -   [ALM-14008 HDFS DataNode内存使用率超过阈值](ALM-14008-HDFS-DataNode内存使用率超过阈值.md)
        -   [ALM-14009 故障DataNode数量超过阈值](ALM-14009-故障DataNode数量超过阈值.md)
        -   [ALM-14010 NameService服务异常](ALM-14010-NameService服务异常.md)
        -   [ALM-14011 HDFS DataNode数据目录配置不合理](ALM-14011-HDFS-DataNode数据目录配置不合理.md)
        -   [ALM-14012 HDFS Journalnode数据不同步](ALM-14012-HDFS-Journalnode数据不同步.md)
        -   [ALM-16000 连接到HiveServer的session数占最大允许数的百分比超过阈值](ALM-16000-连接到HiveServer的session数占最大允许数的百分比超过阈值.md)
        -   [ALM-16001 Hive数据仓库空间使用率超过阈值](ALM-16001-Hive数据仓库空间使用率超过阈值.md)
        -   [ALM-16002 Hive SQL执行成功率低于阈值](ALM-16002-Hive-SQL执行成功率低于阈值.md)
        -   [ALM-16004 Hive服务不可用](ALM-16004-Hive服务不可用.md)
        -   [ALM-18000 Yarn服务不可用](ALM-18000-Yarn服务不可用.md)
        -   [ALM-18002 NodeManager心跳丢失](ALM-18002-NodeManager心跳丢失.md)
        -   [ALM-18003 NodeManager不健康](ALM-18003-NodeManager不健康.md)
        -   [ALM-18006 执行MapReduce任务超时](ALM-18006-执行MapReduce任务超时.md)
        -   [ALM-19000 HBase服务不可用](ALM-19000-HBase服务不可用.md)
        -   [ALM-19006 HBase容灾同步失败](ALM-19006-HBase容灾同步失败.md)
        -   [ALM-25000 LdapServer服务不可用](ALM-25000-LdapServer服务不可用.md)
        -   [ALM-25004 LdapServer数据同步异常](ALM-25004-LdapServer数据同步异常.md)
        -   [ALM-25500 KrbServer服务不可用](ALM-25500-KrbServer服务不可用.md)
        -   [ALM-27001 DBService服务不可用](ALM-27001-DBService服务不可用.md)
        -   [ALM-27003 DBService主备节点间心跳中断](ALM-27003-DBService主备节点间心跳中断.md)
        -   [ALM-27004 DBService主备数据不同步](ALM-27004-DBService主备数据不同步.md)
        -   [ALM-28001 Spark服务不可用](ALM-28001-Spark服务不可用.md)
        -   [ALM-26051 Storm服务不可用](ALM-26051-Storm服务不可用.md)
        -   [ALM-26052 Storm服务可用Supervisor数量小于阈值](ALM-26052-Storm服务可用Supervisor数量小于阈值.md)
        -   [ALM-26053 Storm Slot使用率超过阈值](ALM-26053-Storm-Slot使用率超过阈值.md)
        -   [ALM-26054 Storm Nimbus堆内存使用率超过阈值](ALM-26054-Storm-Nimbus堆内存使用率超过阈值.md)
        -   [ALM-38000 Kafka服务不可用](ALM-38000-Kafka服务不可用.md)
        -   [ALM-38001 Kafka磁盘容量不足](ALM-38001-Kafka磁盘容量不足.md)
        -   [ALM-38002 Kafka堆内存使用率超过阈值](ALM-38002-Kafka堆内存使用率超过阈值.md)
        -   [ALM-24000 Flume服务不可用](ALM-24000-Flume服务不可用.md)
        -   [ALM-24001 Flume Agent异常](ALM-24001-Flume-Agent异常.md)
        -   [ALM-24003 Flume Client连接中断](ALM-24003-Flume-Client连接中断.md)
        -   [ALM-24004 Flume读取数据异常](ALM-24004-Flume读取数据异常.md)
        -   [ALM-24005 Flume传输数据异常](ALM-24005-Flume传输数据异常.md)
        -   [ALM-12041关键文件权限异常](ALM-12041关键文件权限异常.md)
        -   [ALM-12042 关键文件配置异常](ALM-12042-关键文件配置异常.md)
        -   [ALM-23001 Loader服务不可用](ALM-23001-Loader服务不可用.md)
        -   [ALM-12357 审计日志导出到OBS失败](ALM-12357-审计日志导出到OBS失败.md)
        -   [ALM-12014 设备分区丢失](ALM-12014-设备分区丢失.md)
        -   [ALM-12015 设备分区文件系统只读](ALM-12015-设备分区文件系统只读.md)
        -   [ALM-12043 DNS解析时长超过阈值](ALM-12043-DNS解析时长超过阈值.md)
        -   [ALM-12045 网络读包丢包率超过阈值](ALM-12045-网络读包丢包率超过阈值.md)
        -   [ALM-12046 网络写包丢包率超过阈值](ALM-12046-网络写包丢包率超过阈值.md)
        -   [ALM-12047 网络读包错误率超过阈值](ALM-12047-网络读包错误率超过阈值.md)
        -   [ALM-12048 网络写包错误率超过阈值](ALM-12048-网络写包错误率超过阈值.md)
        -   [ALM-12049 网络读吞吐率超过阈值](ALM-12049-网络读吞吐率超过阈值.md)
        -   [ALM-12050 网络写吞吐率超过阈值](ALM-12050-网络写吞吐率超过阈值.md)
        -   [ALM-12051 磁盘Inode使用率超过阈值](ALM-12051-磁盘Inode使用率超过阈值.md)
        -   [ALM-12052 TCP临时端口使用率超过阈值](ALM-12052-TCP临时端口使用率超过阈值.md)
        -   [ALM-12053 文件句柄使用率超过阈值](ALM-12053-文件句柄使用率超过阈值.md)
        -   [ALM-12054 证书文件失效](ALM-12054-证书文件失效.md)
        -   [ALM-12055 证书文件即将过期](ALM-12055-证书文件即将过期.md)
        -   [ALM-18008 Yarn ResourceManager堆内存使用率超过阈值](ALM-18008-Yarn-ResourceManager堆内存使用率超过阈值.md)
        -   [ALM-18009 MapReduce JobHistoryServer堆内存使用率超过阈值](ALM-18009-MapReduce-JobHistoryServer堆内存使用率超过阈值.md)
        -   [ALM-20002 Hue服务不可用](ALM-20002-Hue服务不可用.md)
        -   [ALM-43001 Spark服务不可用](ALM-43001-Spark服务不可用.md)
        -   [ALM-43006 JobHistory进程堆内存使用超出阈值](ALM-43006-JobHistory进程堆内存使用超出阈值.md)
        -   [ALM-43007 JobHistory进程非堆内存使用超出阈值](ALM-43007-JobHistory进程非堆内存使用超出阈值.md)
        -   [ALM-43008 JobHistory进程直接内存使用超出阈值](ALM-43008-JobHistory进程直接内存使用超出阈值.md)
        -   [ALM-43009 JobHistory GC 时间超出阈值](ALM-43009-JobHistory-GC-时间超出阈值.md)
        -   [ALM-43010 JDBCServer进程堆内存使用超出阈值](ALM-43010-JDBCServer进程堆内存使用超出阈值.md)
        -   [ALM-43011 JDBCServer进程非堆内存使用超出阈值](ALM-43011-JDBCServer进程非堆内存使用超出阈值.md)
        -   [ALM-43012 JDBCServer进程直接内存使用超出阈值](ALM-43012-JDBCServer进程直接内存使用超出阈值.md)
        -   [ALM-43013 JDBCServer GC 时间超出阈值](ALM-43013-JDBCServer-GC-时间超出阈值.md)

    -   [补丁管理]
        -   [MRS 1.7.0前版本补丁操作指导](MRS-1-7-0前版本补丁操作指导.md)
        -   [MRS 1.7.0后版本补丁操作指导](MRS-1-7-0后版本补丁操作指导.md)
        -   [滚动补丁](滚动补丁.md)
        -   [修复隔离主机补丁](修复隔离主机补丁.md)

    -   [MRS补丁说明]
        -   [MRS 1.5.1.4补丁说明](MRS-1-5-1-4补丁说明.md)
        -   [MRS 1.7.1.3补丁说明](MRS-1-7-1-3补丁说明.md)
        -   [MRS 1.7.1.5补丁说明](MRS-1-7-1-5补丁说明.md)
        -   [MRS 1.7.1.6补丁说明](MRS-1-7-1-6补丁说明.md)
        -   [MRS 2.0.1.1补丁说明](MRS-2-0-1-1补丁说明.md)
        -   [MRS 2.0.1.2补丁说明](MRS-2-0-1-2补丁说明.md)

    -   [对象管理]
        -   [对象管理简介](对象管理简介.md)
        -   [查看配置](查看配置.md)
        -   [管理服务操作](管理服务操作.md)
        -   [配置服务参数](配置服务参数.md)
        -   [配置服务自定义参数](配置服务自定义参数.md)
        -   [同步服务配置](同步服务配置.md)
        -   [管理角色实例操作](管理角色实例操作.md)
        -   [配置角色实例参数](配置角色实例参数.md)
        -   [同步角色实例配置](同步角色实例配置.md)
        -   [退服和入服务角色实例](退服和入服务角色实例.md)
        -   [管理主机（节点）操作](管理主机（节点）操作.md)
        -   [隔离主机](隔离主机.md)
        -   [取消隔离主机](取消隔离主机.md)
        -   [启动及停止集群](启动及停止集群.md)
        -   [同步集群配置](同步集群配置.md)
        -   [导出集群的配置数据](导出集群的配置数据.md)

    -   [日志管理]
        -   [查看及导出审计日志](查看及导出审计日志.md)
        -   [导出服务日志](导出服务日志.md)
        -   [配置审计日志导出参数](配置审计日志导出参数.md)

    -   [健康检查管理]
        -   [执行健康检查](执行健康检查.md)
        -   [查看并导出检查报告](查看并导出检查报告.md)
        -   [DBService健康检查指标项说明](DBService健康检查指标项说明.md)
        -   [Flume 健康检查指标项说明](Flume-健康检查指标项说明.md)
        -   [HBase健康检查指标项说明](HBase健康检查指标项说明.md)
        -   [Host健康检查指标项说明](Host健康检查指标项说明.md)
        -   [HDFS健康检查指标项说明](HDFS健康检查指标项说明.md)
        -   [Hive健康检查指标项说明](Hive健康检查指标项说明.md)
        -   [Kafka健康检查指标项说明](Kafka健康检查指标项说明.md)
        -   [KrbServer健康检查指标项说明](KrbServer健康检查指标项说明.md)
        -   [LdapServer健康检查指标项说明](LdapServer健康检查指标项说明.md)
        -   [Loader健康检查指标项说明](Loader健康检查指标项说明.md)
        -   [MapReduce健康检查指标项说明](MapReduce健康检查指标项说明.md)
        -   [OMS健康检查指标项说明](OMS健康检查指标项说明.md)
        -   [Spark健康检查指标项说明](Spark健康检查指标项说明.md)
        -   [Storm健康检查指标项说明](Storm健康检查指标项说明.md)
        -   [Yarn健康检查指标项说明](Yarn健康检查指标项说明.md)
        -   [ZooKeeper健康检查指标项说明](ZooKeeper健康检查指标项说明.md)

    -   [租户管理]
        -   [租户简介](租户简介.md)
        -   [添加租户](添加租户.md)
        -   [添加子租户](添加子租户.md)
        -   [删除租户](删除租户.md)
        -   [管理租户目录](管理租户目录.md)
        -   [恢复租户数据](恢复租户数据.md)
        -   [添加资源池](添加资源池.md)
        -   [修改资源池](修改资源池.md)
        -   [删除资源池](删除资源池.md)
        -   [配置队列](配置队列.md)
        -   [配置资源池的队列容量策略](配置资源池的队列容量策略.md)
        -   [清除队列配置](清除队列配置.md)

    -   [备份与恢复]
        -   [备份与恢复简介](备份与恢复简介.md)
        -   [备份元数据](备份元数据.md)
        -   [恢复元数据](恢复元数据.md)
        -   [修改备份任务](修改备份任务.md)
        -   [查看备份恢复任务](查看备份恢复任务.md)

    -   [安全管理]
        -   [未开启Kerberos认证集群中的默认用户清单](未开启Kerberos认证集群中的默认用户清单.md)
        -   [Kerberos认证集群中的默认用户清单](Kerberos认证集群中的默认用户清单-安全.md)
        -   [修改操作系统用户密码](修改操作系统用户密码.md)
        -   [修改admin密码](修改admin密码.md)
        -   [修改Kerberos管理员密码](修改Kerberos管理员密码.md)
        -   [修改LDAP管理员和LDAP用户密码](修改LDAP管理员和LDAP用户密码.md)
        -   [修改组件运行用户密码](修改组件运行用户密码.md)
        -   [修改OMS数据库管理员密码](修改OMS数据库管理员密码.md)
        -   [修改OMS数据库数据访问用户密码](修改OMS数据库数据访问用户密码.md)
        -   [修改组件数据库用户密码](修改组件数据库用户密码.md)
        -   [更换HA证书](更换HA证书.md)
        -   [更新集群密钥](更新集群密钥.md)

    -   [MRS多用户权限管理]
        -   [MRS集群中的用户与权限](MRS集群中的用户与权限.md)
        -   [Kerberos认证集群中的默认用户清单](Kerberos认证集群中的默认用户清单.md)
        -   [创建角色](创建角色.md)
        -   [创建用户组](创建用户组.md)
        -   [创建用户](创建用户.md)
        -   [修改用户信息](修改用户信息.md)
        -   [锁定用户](锁定用户.md)
        -   [解锁用户](解锁用户.md)
        -   [删除用户](删除用户.md)
        -   [修改操作用户密码](修改操作用户密码.md)
        -   [初始化系统用户密码](初始化系统用户密码.md)
        -   [下载用户认证文件](下载用户认证文件.md)
        -   [修改密码策略](修改密码策略.md)
        -   [配置跨集群互信](配置跨集群互信.md)
        -   [配置并使用互信集群的用户](配置并使用互信集群的用户.md)
        -   [配置MRS多用户访问OBS细粒度权限](配置MRS多用户访问OBS细粒度权限.md)


-   [管理历史集群]
    -   [查看历史集群基本信息](查看历史集群基本信息.md)
    -   [查看历史集群作业配置信息](查看历史集群作业配置信息.md)

-   [查看操作日志](查看操作日志.md)
-   [管理数据连接](管理数据连接.md)
-   [连接集群]
    -   [登录集群]
        -   [集群节点简介](集群节点简介.md)
        -   [登录集群节点](登录集群节点.md)
        -   [如何确认MRS Manger的主备管理节点](如何确认MRS-Manger的主备管理节点.md)

    -   [使用MRS客户端]
        -   [集群内节点使用MRS客户端](集群内节点使用MRS客户端.md)
        -   [集群外节点使用MRS客户端](集群外节点使用MRS客户端.md)
        -   [更新客户端](更新客户端.md)

    -   [访问MRS集群上托管的开源组件Web页面]
        -   [开源组件Web站点](开源组件Web站点.md)
        -   [开源组件端口列表](开源组件端口列表.md)
        -   [创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md)


-   [数据迁移]
    -   [准备工作](准备工作.md)
    -   [元数据导出](元数据导出.md)
    -   [数据拷贝](数据拷贝.md)
    -   [数据恢复](数据恢复.md)

-   [数据备份与恢复]
    -   [HDFS数据](HDFS数据.md)
    -   [Hive元数据](Hive元数据.md)
    -   [Hive数据](Hive数据.md)
    -   [HBase数据](HBase数据.md)
    -   [Kafka数据](Kafka数据.md)

-   [MRS集群组件操作指导]
    -   [从零开始使用Hadoop](从零开始使用Hadoop.md)
    -   [从零开始使用Spark SQL](从零开始使用Spark-SQL.md)
    -   [使用Spark]
        -   [从零开始使用Spark](从零开始使用Spark.md)
        -   [Spark对接OpenTSDB]
            -   [创建表关联OpenTSDB](创建表关联OpenTSDB.md)
            -   [插入数据至OpenTSDB表](插入数据至OpenTSDB表.md)
            -   [查询OpenTSDB表](查询OpenTSDB表.md)
            -   [默认配置修改](默认配置修改.md)


    -   [使用Hive]
        -   [从零开始使用Hive](从零开始使用Hive.md)
        -   [配置Hive参数](配置Hive参数.md)

    -   [使用HBase]
        -   [从零开始使用HBase](从零开始使用HBase.md)
        -   [配置HBase备份](配置HBase备份.md)
        -   [配置HBase参数](配置HBase参数.md)
        -   [启用集群间拷贝功能](启用集群间拷贝功能.md)
        -   [使用ReplicationSyncUp工具](使用ReplicationSyncUp工具.md)
        -   [使用HIndex]
            -   [HIndex介绍](HIndex介绍.md)
            -   [批量加载索引数据](批量加载索引数据.md)
            -   [使用索引生成工具](使用索引生成工具.md)
            -   [索引数据迁移](索引数据迁移.md)


    -   [使用Hue]
        -   [访问Hue的WebUI](访问Hue的WebUI.md)
        -   [在Hue WebUI使用HiveQL编辑器](在Hue-WebUI使用HiveQL编辑器.md)
        -   [在Hue WebUI使用元数据浏览器](在Hue-WebUI使用元数据浏览器.md)
        -   [在Hue WebUI使用文件浏览器](在Hue-WebUI使用文件浏览器.md)
        -   [在Hue WebUI使用作业浏览器](在Hue-WebUI使用作业浏览器.md)

    -   [使用Kafka]
        -   [管理Kafka主题](管理Kafka主题.md)
        -   [查看Kafka主题](查看Kafka主题.md)
        -   [管理Kafka用户权限](管理Kafka用户权限.md)
        -   [管理Kafka主题中的消息](管理Kafka主题中的消息.md)
        -   [基于binlog的MySQL数据同步到MRS集群中](基于binlog的MySQL数据同步到MRS集群中.md)

    -   [使用Storm]
        -   [使用客户端提交Storm拓扑](使用客户端提交Storm拓扑.md)
        -   [访问Storm的WebUI](访问Storm的WebUI.md)
        -   [管理Storm拓扑](管理Storm拓扑.md)
        -   [查看Storm拓扑日志](查看Storm拓扑日志.md)

    -   [使用CarbonData]
        -   [CarbonData入门](CarbonData入门.md)
        -   [CarbonData表简介](CarbonData表简介.md)
        -   [创建CarbonData表](创建CarbonData表.md)
        -   [删除CarbonData表](删除CarbonData表.md)

    -   [使用Flume]
        -   [使用简介](使用简介.md)
        -   [安装Flume客户端](安装Flume客户端.md)
        -   [查看Flume客户端日志](查看Flume客户端日志.md)
        -   [停止或卸载Flume客户端](停止或卸载Flume客户端.md)
        -   [使用Flume客户端加密工具](使用Flume客户端加密工具.md)
        -   [Flume配置参数说明](Flume配置参数说明.md)
        -   [样例：使用Flume采集日志并导入Kafka生产者](样例-使用Flume采集日志并导入Kafka生产者.md)
        -   [样例：使用Flume采集日志并导入OBS](样例-使用Flume采集日志并导入OBS.md)
        -   [样例：使用Flume监控OBS目录并上传文件到HDFS](样例-使用Flume监控OBS目录并上传文件到HDFS.md)

    -   [使用Loader]
        -   [Loader使用简介](Loader使用简介.md)
        -   [Loader连接配置说明](Loader连接配置说明.md)
        -   [管理Loader连接](管理Loader连接.md)
        -   [Loader作业源连接配置说明](Loader作业源连接配置说明.md)
        -   [Loader作业目的连接配置说明](Loader作业目的连接配置说明.md)
        -   [管理Loader作业](管理Loader作业.md)
        -   [准备MySQL数据库连接的驱动](准备MySQL数据库连接的驱动.md)
        -   [样例：通过Loader将数据从OBS导入HDFS](样例-通过Loader将数据从OBS导入HDFS.md)

    -   [使用Presto]
        -   [访问Presto的WebUI](访问Presto的WebUI.md)
        -   [使用客户端执行查询语句](使用客户端执行查询语句.md)
        -   [在DLF中使用Presto转储](在DLF中使用Presto转储.md)
        -   [配置Presto组件权限](配置Presto组件权限.md)

    -   [使用KafkaManager]
        -   [KafkaManager介绍](KafkaManager介绍.md)
        -   [访问KafkaManager的WebUI](访问KafkaManager的WebUI.md)
        -   [管理Kafka集群](管理Kafka集群.md)
        -   [Kafka集群监控管理](Kafka集群监控管理.md)

    -   [使用OpenTSDB]
        -   [使用MRS客户端操作OpenTSDB指标数据](使用MRS客户端操作OpenTSDB指标数据.md)
        -   [使用curl命令操作OpenTSDB](使用curl命令操作OpenTSDB.md)

    -   [使用Flink]
        -   [从零开始使用Flink](从零开始使用Flink.md)
        -   [配置管理Flink](配置管理Flink.md)
        -   [安全配置](安全配置.md)
        -   [安全加固](安全加固.md)
        -   [日志介绍](日志介绍.md)
        -   [性能调优](性能调优.md)
        -   [Shell操作命令](Shell操作命令.md)

    -   [使用Impala]
        -   [从零开始使用Impala](从零开始使用Impala.md)

    -   [使用Kudu]
        -   [从零开始使用Kudu](从零开始使用Kudu.md)

    -   [使用MRS访问OBS]
        -   [使用原生s3方式对接](使用原生s3方式对接.md)
        -   [使用Huawei OBS方式对接](使用Huawei-OBS方式对接.md)
        -   [使用ECS委托自动获取AK/SK访问OBS](使用ECS委托自动获取AK-SK访问OBS.md)


-   [安全性]
    -   [集群（未启用Kerberos认证）安全配置建议](集群（未启用Kerberos认证）安全配置建议.md)

-   [附录]
    -   [MRS所使用的弹性云服务器规格](MRS所使用的弹性云服务器规格.md)
    -   [MRS所使用的裸金属服务器规格](MRS所使用的裸金属服务器规格.md)
    -   [修订记录]

