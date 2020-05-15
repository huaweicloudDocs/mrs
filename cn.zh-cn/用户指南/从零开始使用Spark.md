# 从零开始使用Spark<a name="ZH-CN_TOPIC_0173178541"></a>

本章节提供从零开始使用Spark提交sparkPi作业的操作指导，sparkPi是最经典的Spark作业，它用来计算Pi（π）值。

## 操作步骤<a name="sd2a57331ab704780bbe437bd73c7c8de"></a>

1.  <a name="l73a12356415f4048981acfcdd6579007"></a>准备sparkPi程序。

    开源的Spark的样例程序包含多个例子，其中包含sparkPi。可以从[https://d3kbcqa49mib13.cloudfront.net/spark-2.1.0-bin-hadoop2.7.tgz](https://d3kbcqa49mib13.cloudfront.net/spark-2.1.0-bin-hadoop2.7.tgz)中下载Spark的样例程序。

    解压后在“spark-2.1.0-bin-hadoop2.7/examples/jars“路径下获取“spark-examples\_2.11-2.1.0.jar“，即为Spark的样例程序。spark-examples\_2.11-2.1.0.jar样例程序包含sparkPi程序。

2.  上传数据至OBS。
    1.  登录OBS控制台。
    2.  单击“创建桶“，创建一个名称为sparkpi的桶。

        sparkpi仅为示例，桶名称必须全局唯一，否则会创建桶失败。存储类别和桶策略分别保持默认值，“高级配置“选择“不配置“。

    3.  单击sparksql桶名称，并选择“对象”。
    4.  单击“新建文件夹“，分别创建program、output文件夹，创建完成后如[图1](#feb7f851ced0f44e9aafe1d249526e5b6)所示。

        **图 1**  文件夹列表<a name="feb7f851ced0f44e9aafe1d249526e5b6"></a>  
        ![](figures/文件夹列表.png "文件夹列表")

    5.  进入program文件夹，单击上传文件，从本地选择[1](#l73a12356415f4048981acfcdd6579007)中下载的程序包，“存储类别“选择“标准存储“。

3.  登录MRS控制台，在左侧导航栏选择“集群列表 \> 现有集群“，单击集群名称。
4.  提交sparkPi作业。
    1.  在MRS控制台选择“作业管理“，单击“添加“，进入“添加作业“页面，具体请参见[运行Spark作业](运行Spark作业.md)。

        只有集群处于“运行中“状态时才能提交作业。

        作业提交成功后默认为“已接受“状态，不需要用户手动执行作业。

5.  查看作业执行结果。
    1.  进入“作业管理“页面，在“作业“页签查看作业是否执行完成。

        作业运行需要时间，作业运行结束后，刷新作业列表。

        作业执行成功或失败后都不能再次执行，只能新增或者复制作业，配置作业参数后重新提交作业。

    2.  进入OBS路径，查看作业输出信息。

        可以到OBS中的“sparkpi \> output“文件夹中查看相关的output文件，需要下载到本地以文本方式打开进行查看。

6.  删除集群。

    请参见[删除集群](删除集群.md)章节。


