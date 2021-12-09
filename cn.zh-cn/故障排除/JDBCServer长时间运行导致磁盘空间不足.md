# JDBCServer长时间运行导致磁盘空间不足<a name="mrs_03_0277"></a>

## 用户问题<a name="section18305143583116"></a>

连接Spark的JDBCServer服务提交spark-sql任务到yarn集群上，在运行一段时间以后会出现Core节点的数据盘被占满的情况。

## 问题现象<a name="section117424454313"></a>

客户连接Spark的JDBCServer服务提交spark-sql任务到yarn集群上，在运行一段时间以后会出现Core节点的数据盘被占满的情况。

后台查看磁盘使用情况，主要是JDBCServer服务的APP临时文件（shuffle生成的文件）太多，并且没有进行清理占用了大量内存。

## 原因分析<a name="section1237061220324"></a>

查询Core节点有大量文件的目录，发现大部分都是类似“blockmgr-033707b6-fbbb-45b4-8e3a-128c9bcfa4bf”的目录，里面存放了计算过程中产生的shuffle临时文件。

因为JDBCServer启动了Spark的动态资源分配功能，已经将shuffle托管给NodeManager，NodeManager只会按照APP的运行周期来管理这些文件，并不会关注单个executor所在的container是否存在。因此，只有在APP结束的时候才会清理这些临时文件。任务运行时间较长时导致临时文件过多占用了大量磁盘空间。

## 处理步骤<a name="section13681131311116"></a>

启动一个定时任务来清理超过一定时间的shuffle文件，例如每个整点清理超过6个小时的文件：

1.  创建脚本“clean\_appcache.sh“，若存在多个数据盘，请根据实际情况修改BASE\_LOC中data1的值。
    -   安全集群

        ```
        #!/bin/bash
        BASE_LOC=/srv/BigData/hadoop/data1/nm/localdir/usercache/spark/appcache/application_*/blockmgr* 
        find $BASE_LOC/ -mmin +360 -exec rmdir {} \;
        find $BASE_LOC/ -mmin +360 -exec rm {} \;
        ```

    -   普通集群

        ```
        #!/bin/bash
        BASE_LOC=/srv/BigData/hadoop/data1/nm/localdir/usercache/omm/appcache/application_*/blockmgr* 
        find $BASE_LOC/ -mmin +360 -exec rmdir {} \;
        find $BASE_LOC/ -mmin +360 -exec rm {} \;
        ```

2.  修改脚本权限。

    **chmod 755 clean\_appcache.sh**

3.  增加一个定时任务来启动清理脚本，脚本路径请根据实际脚本存放位置修改。

    查看定时任务：crontab -l

    编辑定时任务：crontab -e

    ```
    0 * * * * sh /root/clean_appcache.sh > /dev/null 2>&1
    ```


