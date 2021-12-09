# MR任务异常临时文件不删除<a name="mrs_03_0298"></a>

## 用户问题<a name="section18305143583116"></a>

MR任务异常临时文件为什么没有删除？

## 问题现象<a name="section117424454313"></a>

HDFS临时目录文件过多，占用内存。

## 原因分析<a name="section1237061220324"></a>

MR任务提交时会将相关配置文件、jar包和-files添加的文件都放入hdfs上的临时目录，方便后面container启动以后获取相应的文件。由配置项yarn.app.mapreduce.am.staging-dir决定具体存放位置，默认值是/tmp/hadoop-yarn/staging。

正常运行的MR任务会在Job结束以后就清理这些临时文件，但是当Job对应的yarn任务是异常退出时，这些临时文件不会被清理，长时间积攒导致该临时目录下的文件数量越来越多，占用存储空间越来越多。

## 处理步骤<a name="section1515233911213"></a>

1.  登录集群。
    1.  以root用户登录任意一个Master节点，用户密码为创建集群时用户自定义的密码。
    2.  如果集群开启Kerberos认证，执行如下命令进入客户端安装目录并设置环境变量，再认证用户并按照提示输入密码，该密码请向管理员获取。

        **cd **_**客户端安装目录**_

        **source bigdata\_env**

        **kinit hdfs**

    3.  如果集群未开启Kerberos认证，执行如下命令切换到omm用户，再进入客户端安装目录设置环境变量。

        **su - omm**

        **cd **_**客户端安装目录**_

        **source bigdata\_env**

2.  获取文件列表。

    **hdfs dfs -ls /tmp/hadoop-yarn/staging/\*/.staging/ | grep "^drwx" | awk '\{print $8\}' \> job\_file\_list**

    job\_file\_list文件中就是所有任务的文件夹列表，文件内容参考：

    ```
    /tmp/hadoop-yarn/staging/omm/.staging/job__<Timestamp>_<ID>
    ```

3.  统计当前运行中的任务。

    **mapred job -list 2\>/dev/null | grep job\_ | awk '\{print $1\}' \> run\_job\_list**

    run\_job\_list文件里面就是当前正在运行的JobId列表，文件内容格式为：

    ```
    job_<Timestamp>_<ID>
    ```

4.  删除job\_file\_list文件中正在运行中的任务。确保在删除过期数据时不会误删正在运行任务的数据。

    **cat run\_job\_list | while read line; do sed -i "/$line/d" job\_file\_list; done**

5.  删除过期数据。

    **cat job\_file\_list | while read line; do hdfs dfs -rm -r $line; done**

6.  清除临时文件。

    **rm -rf run\_job\_list job\_file\_list**


