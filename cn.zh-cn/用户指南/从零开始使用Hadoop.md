# 从零开始使用Hadoop<a name="ZH-CN_TOPIC_0173178039"></a>

本章节提供从零开始使用Hadoop提交wordcount作业的操作指导，wordcount是最经典的Hadoop作业，它用来统计海量文本的单词数量。

## 操作步骤<a name="saf50f0a3153d4dff94e983737fcd55ae"></a>

1.  <a name="le287346e84914cffadab7f39de92b68d"></a>准备wordcount程序。

    开源的Hadoop的样例程序包含多个例子，其中包含wordcount。可以从[https://dist.apache.org/repos/dist/release/hadoop/common/](https://dist.apache.org/repos/dist/release/hadoop/common/)中下载Hadoop的样例程序。

    例如，选择hadoop-2.7.x版本，下载“hadoop-2.7.x.tar.gz“，解压后在“hadoop-2.7.x\\share\\hadoop\\mapreduce“路径下获取“hadoop-mapreduce-examples-2.7.x.jar“，即为Hadoop的样例程序。“hadoop-mapreduce-examples-2.7.x.jar“样例程序包含了wordcount程序。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >hadoop-2.7.x表示Hadoop的版本号。  

2.  <a name="l8608e4e8ac884c7a919ca1928791488c"></a>准备数据文件。

    数据文件无格式要求，准备一个或多个txt文件即可，如下内容为txt文件样例：

    ```
    qwsdfhoedfrffrofhuncckgktpmhutopmma
    jjpsffjfjorgjgtyiuyjmhombmbogohoyhm
    jhheyeombdhuaqqiquyebchdhmamdhdemmj
    doeyhjwedcrfvtgbmojiyhhqssddddddfkf
    kjhhjkehdeiyrudjhfhfhffooqweopuyyyy
    ```

3.  上传数据至OBS。
    1.  登录OBS控制台。
    2.  单击“创建桶“，创建一个名称为wordcount01的桶。

        wordcount01仅为示例，桶名称必须全局唯一，否则会创建桶失败。

    3.  在OBS桶列表中单击桶名称wordcount01，选择“对象 \> 新建文件夹”，分别创建program、input文件夹，创建完成后如[图1](#f5b788a3e684449bbb706e7ed88f3ceee)所示。

        **图 1**  wordcount01桶文件夹列表<a name="f5b788a3e684449bbb706e7ed88f3ceee"></a>  
        ![](figures/wordcount01桶文件夹列表.png "wordcount01桶文件夹列表")

        -   program：存放用户程序
        -   input：存放用户数据文件

    4.  进入program文件夹，单击“上传对象 \> 添加文件”，从本地选择[1](#le287346e84914cffadab7f39de92b68d)中下载的程序包，然后单击“上传“，上传完成后如[图2](#fa54363aacb7640879f2f7d041a36e3fe)所示。

        **图 2**  程序列表<a name="fa54363aacb7640879f2f7d041a36e3fe"></a>  
        ![](figures/程序列表.png "程序列表")

    5.  进入input文件夹，将[2](#l8608e4e8ac884c7a919ca1928791488c)中准备的数据文件上传到input文件夹，上传完成后如[图3](#f0e55f4ecae264fe0ad38e57eec115caa)所示。

        **图 3**  数据文件列表<a name="f0e55f4ecae264fe0ad38e57eec115caa"></a>  
        ![](figures/数据文件列表.png "数据文件列表")

4.  登录MRS控制台，在左侧导航栏选择“集群列表 \> 现有集群”，单击集群名称。创建集群请参考[自定义购买集群](自定义购买集群.md)。
5.  提交wordcount作业。

    在MRS控制台选择“作业管理“页签，单击“添加“，进入“添加作业“页面，具体请参见[运行MapReduce作业](运行MapReduce作业.md)。

    **图 4**  wordcount作业<a name="fig9521125485918"></a>  
    ![](figures/wordcount作业.png "wordcount作业")

    -   作业类型选择“MapReduce”。
    -   作业名称为“mr\_01”。
    -   执行程序路径配置为OBS上存放程序的地址。例如：obs://wordcount01/program/hadoop-mapreduce-examples-2.7.x.jar。
    -   执行程序参数中填写的参数为：wordcount obs://wordcount01/input/ obs://wordcount01/output/。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >-   参数“**obs://wordcount01/input/**”中的OBS桶名需要替换为实际环境创建的桶名。  
        >-   参数“**obs://wordcount01/output/**”中的OBS桶名需要替换为实际环境创建的桶名，目录output请手动输入一个不存在的目录。  

    -   服务配置参数无需填写。

    只有集群处于“运行中“状态时才能提交作业。

    作业提交成功后默认为“已接受“状态，不需要用户手动执行作业。

6.  查看作业执行结果。
    1.  进入“作业管理“页面，查看作业是否执行完成。

        作业运行需要时间，作业运行结束后，刷新作业列表，查看作业列表如[图5](#fc74e09fd0d7f41c8b061b802b7511799)所示。

        **图 5**  作业列表<a name="fc74e09fd0d7f41c8b061b802b7511799"></a>  
        ![](figures/作业列表.png "作业列表")

        作业执行成功或失败后都不能再次执行，只能新增或者复制作业，配置作业参数后重新提交作业。

    2.  登录OBS控制台，进入OBS路径，查看作业输出信息。

        可以到OBS中的“wordcount01 \> output“目录中查看相关的output文件，需要下载到本地以文本方式打开进行查看，如[图6](#fbf08cc0204524993bf5e047668bfc9f3)所示。

        **图 6**  输出文件列表<a name="fbf08cc0204524993bf5e047668bfc9f3"></a>  
        ![](figures/输出文件列表.png "输出文件列表")

7.  删除集群。

    请参见[删除集群](删除集群.md)章节。


