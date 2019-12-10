# 引入jar包不正确，导致Spark任务无法运行<a name="ZH-CN_TOPIC_0169690315"></a>

## 用户问题<a name="section18305143583116"></a>

执行Spark任务，任务无法运行。

## 问题现象<a name="section117424454313"></a>

执行Spark任务，任务无法运行。

## 原因分析<a name="section1237061220324"></a>

执行Spark任务时，引入的jar包不正确，导致Spark任务运行失败。

## 处理步骤<a name="section19592015143711"></a>

1.  登录任意Master节点。
2.  执行**cd /opt/Bigdata/MRS\_\*/install/FusionInsight-Spark-\*/spark/examples/jars**命令， 查看样例程序的jar包。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >jar包名最多为1023字符，不能包含;|&\>,<'$特殊字符，且不可为空或全空格。  

3.  检查OBS桶上的执行程序，执行程序可存储于HDFS或者OBS中，不同的文件系统对应的路径存在差异。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   OBS存储路径：以“s3a://”开头。示例：s3a://wordcount/program/hadoop-mapreduce-examples-2.7.x.jar  
    >-   HDFS存储路径：以“/user”开头。Spark Script需要以“.sql”结尾，MR和Spark需要以“.jar”结尾。sql、jar不区分大小写。  


