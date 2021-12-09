# Spark任务由于内存不够，作业卡住<a name="mrs_03_0038"></a>

## 用户问题<a name="section18305143583116"></a>

Spark提交作业内存不足导致任务长时间处于pending状态或者运行中内存溢出。

## 问题现象<a name="section117424454313"></a>

使用Spark提交作业后，长期卡住不动。反复运行作业后报错，内容如下：

```
Exception in thread "main" org.apache.spark.SparkException: Job aborted due to stage failure: 
Aborting TaskSet 3.0 because task 0 (partition 0) cannot run anywhere due to node and executor blacklist. 
Blacklisting behavior can be configured via spark.blacklist.*. 
```

## 原因分析<a name="section1237061220324"></a>

内存不足导致Spark提交的作业任务长时间处于pending状态。

## 处理步骤<a name="section150512392323"></a>

1.  登录MRS Console页面，在现有集群中，选择集群名称，在“节点信息”页面，查看当前集群的节点规格。
2.  提高nodemanager进程所持有的集群资源。

    MRS Manager界面操作：

    1.  登录MRS Manager页面，选择“服务管理 \> Yarn \> 服务配置”。
    2.  在“参数类别“中选择“全部配置“，然后在搜索框中搜索**yarn.nodemanager.resource.memory-mb**，查看该参数值。建议配置成节点物理内存总量的75%-90%。

    FusionInsight Manager界面操作：

    1.  登录FusionInsight Manager。选择“集群 \> 服务 \> Yarn”。
    2.  单击“配置”，选择“全部配置”。然后在搜索框中搜索**yarn.nodemanager.resource.memory-mb**，查看该参数值。建议配置成节点物理内存总量的75%-90%。

3.  修改Spark的服务配置。

    MRS Manager界面操作：

    1.  登录MRS Manager页面，选择“服务管理“\>“Spark“  \>“服务配置”。
    2.  在“参数类别“中选择“全部配置“，然后在搜索框中搜索**spark.driver.memory**和**spark.executor.memory**

        根据作业的需要调大或者调小该值，具体以提交的Spark作业的复杂度和内存需要为参考（一般调大）。

    FusionInsight Manager界面操作：

    1.  登录FusionInsight Manager。选择“集群 \> 服务 \> Spark”。
    2.  单击“配置”，选择“全部配置”。然后在搜索框中搜索**spark.driver.memory**和**spark.executor.memory**，根据作业的需要调大或者调小该值，具体以提交的Spark作业的复杂度和内存需要为参考（一般调大）。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果使用到SparkJDBC作业，搜索并修改**SPARK\_EXECUTOR\_MEMORY**和**SPARK\_DRIVER\_MEMORY**两个参数取值，具体以提交的Spark作业的复杂度和内存需要为参考（一般调大）。
    >-   如果对核数有要求，可以搜索并修改**spark.driver.cores**和**spark.executor.cores**的核数取值**。**

4.  Spark依赖内存做计算，如果以上还是不能满足任务的提交需要，建议进行[扩容集群](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0063.html)。

