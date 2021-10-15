# Spark连接其他服务认证问题<a name="mrs_03_0289"></a>

## 问题现象<a name="section117424454313"></a>

-   Spark连接HBase，报认证失败或者连接不到hbase表。
-   Spark连接HBase报找不到jar包。

## 原因分析<a name="section1237061220324"></a>

-   问题1：HBase没有获取到当前任务的认证信息，导致连接HBase的时候认证失败，无法读取到相应数据
-   问题2：Spark默认没有加载HBase相关的jar包，需要使用--jars添加到任务中

## 处理步骤<a name="section16530919173311"></a>

-   问题1：可以尝试开启hbase认证开关：spark.yarn.security.credentials.hbase.enabled=true。但不建议直接用HBase客户端的hbase-site.xml替换Spark客户端下的hbase-site.xml，两者并不是完全相同。
-   问题2：需要将HBase相关的包使用--jars上传。

