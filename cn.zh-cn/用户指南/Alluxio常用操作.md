# Alluxio常用操作<a name="ZH-CN_TOPIC_0207620793"></a>

## 前期准备<a name="section1897373121617"></a>

1.  创建安装Alluxio组件的集群。
2.  以root用户登录集群的主Master节点，密码为用户创建集群时设置的root密码。
3.  执行如下命令，配置环境变量。

    **source /opt/client/bigdata\_env**


## 使用Alluxio Shell<a name="section173691030181412"></a>

[Alluxio shell](https://docs.alluxio.io/os/user/2.0/en/basic/Command-Line-Interface.html)包含多种与Alluxio交互的命令行操作。

-   要查看文件系统操作命令列表。

    **alluxio fs**

-   使用ls命令列出 Alluxio 里的文件。例如列出根目录下所有文件。

    **alluxio fs ls /**

-   使用copyFromLocal命令可以复制本地文件到 Alluxio 中。

    **alluxio fs copyFromLocal /home/test\_input.txt /test\_input.txt**

    命令执行后回显：

    ```
    Copied file:///home/test_input.txt to /test_input.txt
    ```

-   再次使用ls命令列出Alluxio中的文件，可以看到刚刚拷贝的test\_input.txt文件。

    **alluxio fs ls /**

    命令执行后回显：

    ```
    12       PERSISTED 11-28-2019 17:10:17:449 100% /test_input.txt
    ```

    输出显示test\_input.txt 文件在 Alluxio 中，各参数含义为文件的大小、是否被持久化、创建日期、Alluxio中这个文件的缓存占比、文件名。

-   使用cat命令打印文件的内容。

    **alluxio fs cat /test\_input.txt**

    命令执行后回显：

    ```
    Test Alluxio
    ```


## Alluxio中的挂载功能<a name="section0330205781418"></a>

Alluxio 通过统一命名空间的特性统一了对存储系统的访问。详情请参考：[https://docs.alluxio.io/os/user/2.0/cn/advanced/Namespace-Management.html](https://docs.alluxio.io/os/user/2.0/cn/advanced/Namespace-Management.html)

这个特性允许用户挂载不同的存储系统到Alluxio命名空间中并且通过Alluxio命名空间无缝地跨存储系统访问文件。

1.  在 Alluxio 中创建一个目录作为挂载点。

    ```
    alluxio fs mkdir /mnt
    Successfully created directory /mnt
    ```

2.  挂载一个已有的OBS桶到Alluxio（前提：给集群配置有OBS OperateAccess权限的委托，具体请参见[ECS委托方式访问OBS](ECS委托方式访问OBS.md)）。此处以obs-mrstest桶为例，请根据实际情况替换桶名。

    ```
    alluxio fs mount /mnt/obs obs://obs-mrstest/data
    Mounted obs://obs-mrstest/data at /mnt/obs
    ```

3.  通过Alluxio命名空间列出OBS桶中的文件。使用**ls**命令列出OBS挂载目录下的文件。

    ```
    alluxio fs ls /mnt/obs
    38       PERSISTED 11-28-2019 17:42:54:554   0% /mnt/obs/hive_load.txt
    12       PERSISTED 11-28-2019 17:43:07:743   0% /mnt/obs/test_input.txt
    ```

    新挂载的文件和目录也可以通过Alluxio WebUI查看。

4.  挂载完成后，通过 Alluxio 统一命名空间，可以无缝地从不同存储系统中交互数据。例如，使用ls -R命令，递归地列举出一个目录下的所有文件。

    ```
    alluxio fs ls -R /
            0       PERSISTED 11-28-2019 11:15:19:719  DIR /app-logs
            1       PERSISTED 11-28-2019 11:18:36:885  DIR /apps
            1       PERSISTED 11-28-2019 11:18:40:209  DIR /apps/templeton
    239440292       PERSISTED 11-28-2019 11:18:40:209   0% /apps/templeton/hive.tar.gz
    .....
            1       PERSISTED 11-28-2019 19:00:23:879  DIR /mnt
            2       PERSISTED 11-28-2019 19:00:23:879  DIR /mnt/obs
           38       PERSISTED 11-28-2019 17:42:54:554   0% /mnt/obs/hive_load.txt
           12       PERSISTED 11-28-2019 17:43:07:743   0% /mnt/obs/test_input.txt
    .....
    ```

    输出显示了Alluxio文件系统根目录（默认值是HDFS的根目录，即hdfs://hacluster/）中来源于挂载存储系统的所有文件。/app-logs和/apps目录在HDFS文件系统中，/mnt/obs/目录在 OBS 中。


## 用Alluxio加速数据访问<a name="section784202117153"></a>

由于Alluxio利用内存存储数据，它可以加速数据的访问。例如：

1.  上传一个文件test\_data.csv（文件是一份记录了食谱的样本）到obs-mrstest桶的/data目录下。通过**ls**命令显示文件状态：

    alluxio fs ls /mnt/obs/test\_data.csv

    ```
    294520189       PERSISTED 11-28-2019 19:38:55:000   0% /mnt/obs/test_data.csv
    ```

    输出显示了该文件在Alluxio中缓存占比为0%，即不在Alluxio内存中。

2.  统计该文件中单词"milk"出现的次数，并计算耗时。

    time alluxio fs cat /mnt/obs/test\_data.csv | grep -c milk

    ```
    52180
    
    real    0m10.765s
    user    0m5.540s
    sys     0m0.696s
    ```

3.  第一次读取数据后会将数据放在内存中，Alluxio再次读取时可以提高访问该数据的速度。例如：在通过**cat**命令获取文件后，用**ls**命令再查看文件的状态。

    alluxio fs ls /mnt/obs/test\_data.csv

    ```
    294520189       PERSISTED 11-28-2019 19:38:55:000 100% /mnt/obs/test_data.csv
    ```

    输出显示文件已经 100% 被加载到 Alluxio 中，

4.  再次访问该文件，统计单词“eggs”出现的次数，并计算耗时。

    time alluxio fs cat /mnt/obs/test\_data.csv | grep -c eggs

    ```
    59510
    
    real    0m5.777s
    user    0m5.992s
    sys     0m0.592s
    ```

    对比两次耗时可以看出存储在Alluxio内存中的数据，数据访问耗时明显缩短。


