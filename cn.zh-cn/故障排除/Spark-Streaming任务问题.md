# Spark Streaming任务问题<a name="mrs_03_0288"></a>

## 问题现象<a name="section117424454313"></a>

-   连接Kafka报类找不到。
-   连接带Kerberos的Kafka，报认证错误。
-   SparkStreaming任务运行一段时间后开始报TOKEN过期问题。

## 原因分析<a name="section1237061220324"></a>

-   问题1：Spark提交任务默认不会加载kafka的相关包，所以需要在启动命令中增加--jars来指定对应kafka版本的jar包
-   问题2：连接Kafka无法使用Spark的认证信息，需要将相关的认证使用jvm的参数设置进去。
-   问题3：Spark默认使用当前客户端的认证信息提交任务，也可以使用代码login的方式。但是这两种认证方式都无法更新任务使用的TOKEN，当提交的时候生成的TOKEN信息过期以后就无法在使用，因此报错。解决办法是使用--keytab和--principal将keytab文件和对应用户带入任务中。

## 处理步骤<a name="section16530919173311"></a>

-   问题1：启动命令中增加--jars来指定对应kafka版本的jar包，一般是在Spark客户端目录/jars/streamingClient（0.8版本kafka）和spark客户端目录/jars/streamingClient010（0.10版本kafka）。
-   问题2：参考指导文档[编辑并运行程序](https://support.huaweicloud.com/devg-mrs/mrs_06_0213.html)。
-   问题3：使用--keytab和--principal将keytab文件和对应用户带入任务中。如果此处的keytab文件和之前kafka的jaas.conf中配置的是同一个，则spark会报一个文件多次上传的问题。解决办法是复制一份keytab文件，使得--files和--keytab上传不同的文件。

