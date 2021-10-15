# 配置HDFS映射方式对接OBS文件系统<a name="mrs_01_0769"></a>

通过HDFS地址映射到OBS地址的方式，支持将HDFS中的数据迁移到OBS后，不需要变动业务逻辑中的数据地址，即可完成数据访问。

例如将HDFS文件系统的数据迁移到OBS服务中，通过使用HDFS地址映射功能简单配置即可实现客户端无需修改自己的的业务代码逻辑的情况下，访问存储到OBS的数据。或将元数据信息从HDFS文件系统部分迁移到OBS服务中，通过使用HDFS地址映射功能简单配置即可实现既能访问存储在OBS的数据也能访问存储在HDFS文件系统的数据。

该功能不支持使用WebHdfsFileSystem \(A FileSystem for HDFS over the web.\)的rest api访问的场景。

>![](public_sys-resources/icon-caution.gif) **注意：** 
>请勿通过HDFS服务端修改配置文件，否则可能会引起HDFS服务重启异常。

## 通过Hadoop客户端命令操作HDFS（/path方式或hdfs://namespace/path方式）<a name="section921111193114"></a>

1.  分别登录所有Master节点，执行如下配置。
2.  执行如下命令编辑HDFS用到的core-site.xml文件。

    **vim /opt/client/HDFS/hadoop/etc/hadoop/core-site.xml**

3.  在core-site.xml文件中增加如下内容。

    ```
    <property>
    <name>fs.hdfs.mounttable.hacluster.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapperFileSystem</value>
    </property>
    <property>
    <name>fs.obs.endpoint</name>
    <value>obs endpoint</value>
    </property>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   **obs endpoint**为OBS对应的endpoint，具体请从[终端节点及区域](https://developer.huaweicloud.com/endpoint?OBS)获取。

4.  使用**hdfs://namespace/**方式访问数据。

    **hadoop fs -mkdir -p hdfs://hacluster/var/test**

    **hadoop fs -put abc.txt hdfs://hacluster/var/test/**

    **hadoop fs -ls hdfs://hacluster/var/test**

5.  使用hadoop命令行（不加namespace）方式访问数据。

    **hadoop fs -mkdir -p /var/test**

    **hadoop fs -put abc.txt /var/test/**

    **hadoop fs -ls /var/test**


## 通过Hadoop客户端命令操作HDFS（hdfs://namenodeIp:port/path）<a name="section121915376510"></a>

1.  分别登录所有Master节点，执行如下配置。
2.  执行如下命令编辑HDFS用到的core-site.xml文件。

    **vim /opt/client/HDFS/hadoop/etc/hadoop/core-site.xml**

3.  在core-site.xml文件中增加如下内容。

    ```
    <property>
    <name>fs.hdfs.mounttable.hacluster.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.mounttable.namenodeIp1:port.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.mounttable.namenodeIp2:port.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapperFileSystem</value>
    </property>
    <property>
    <name>fs.obs.endpoint</name>
    <value>obs endpoint</value>
    </property>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   **obs endpoint**为OBS对应的endpoint，具体请从[终端节点及区域](https://developer.huaweicloud.com/endpoint?OBS)获取。
    >-   **namenodeIp**为HDFS的NameNode实例的IP地址，**port**为HDFS的NameNode RPC端口号，默认值为9820，所有NameNode实例的IP地址均需配置在core-site.xml文件中。


## 通过Hadoop客户端命令执行MR作业<a name="section199281166203"></a>

1.  分别登录所有Master节点，执行如下配置。
2.  执行如下命令编辑HDFS用到的core-site.xml文件。

    **vim /opt/client/HDFS/hadoop/etc/hadoop/core-site.xml**

3.  在core-site.xml文件中增加如下内容。

    ```
    <property>
    <name>fs.hdfs.mounttable.hacluster.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapperFileSystem</value>
    </property>
    <property>
    <name>fs.obs.endpoint</name>
    <value>obs endpoint</value>
    </property>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   **obs endpoint**为OBS对应的endpoint，具体请从[终端节点及区域](https://developer.huaweicloud.com/endpoint?OBS)获取。

4.  执行如下命令编辑yarn用到的core-site.xml文件。

    **vim /opt/client/Yarn/config/core-site.xml**

5.  在core-site.xml文件中增加如下内容。

    ```
    <property>
    <name>fs.hdfs.mounttable.hacluster.link./var</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapperFileSystem</value>
    </property>
    <property>
    <name>fs.obs.endpoint</name>
    <value>obs endpoint</value>
    </property>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   **obs endpoint**为OBS对应的endpoint，具体请从[终端节点及区域](https://developer.huaweicloud.com/endpoint?OBS)获取。


## 通过hive beeline jdbc访问HDFS数据<a name="section1580765733215"></a>

前提条件：

-   集群默认的文件系统是HDFS。即fs.defaultFS的配置项是**hdfs：//**开始。
-   集群已配置默认委托，可参考如下步骤配置。
    1.  在集群详情页的“概览”页签，单击委托右侧的“管理委托”选择并绑定MRS\_ECS\_DEFAULT\_AGENCY委托。
    2.  在“节点管理”页签单击所有的节点名称，进入弹性云服务器详情页面，确保所有节点均已绑定MRS\_ECS\_DEFAULT\_AGENCY委托。


具体配置：

1.  登录服务配置页面。
    -   针对MRS 3.x之前版本，登录集群详情页面，选择“组件管理 \> Hive \> 服务配置”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

    -   针对MRS 3.x及之后版本，登录FusionInsight Manager页面，具体请参见[访问FusionInsight Manager（MRS 3.x及之后版本）](访问FusionInsight-Manager（MRS-3-x及之后版本）.md)，选择“集群 \> 服务 \> Hive \> 配置”。

2.  将“基础配置”切换为“全部配置”。
3.  在“Hive \> 自定义”的“core.site.customized.configs”中增加如下配置。

    -   fs.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapperFileSystem
    -   fs.hdfs.mounttable.hacluster.link./yy = obs://obs-test/job/yy

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
        >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
        >-   映射的键”.link”字符串后的目录不能使用如下在Hive启动过程中使用的目录及其子目录。
        >    -   /tmp/hive-scratch
        >    -   /tmp/hive
        >    -   /apps
        >    -   /datasets
        >    -   /mrs


    **图 1**  MRS Manager上修改Hive自定义配置<a name="fig633732712259"></a>  
    ![](figures/MRS-Manager上修改Hive自定义配置.png "MRS-Manager上修改Hive自定义配置")

    **图 2**  FusionInsight Manager上修改Hive自定义配置<a name="fig623463420015"></a>  
    ![](figures/FusionInsight-Manager上修改Hive自定义配置.png "FusionInsight-Manager上修改Hive自定义配置")

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。

## 通过presto\_cli.sh jdbc访问HDFS数据<a name="section1565512587343"></a>

前提条件：

-   集群默认的文件系统是HDFS。即fs.defaultFS的配置项是**hdfs：//**开始。
-   集群已配置默认委托，可参考如下步骤配置。
    1.  在集群详情页的“概览”页签，单击委托右侧的“管理委托”选择并绑定MRS\_ECS\_DEFAULT\_AGENCY委托。
    2.  在“节点管理”页签单击所有的节点名称，进入弹性云服务器详情页面，确保所有节点均已绑定MRS\_ECS\_DEFAULT\_AGENCY委托。

-   MRS 1.9.2版本集群。

具体配置：

1.  在集群详情页，选择“组件管理”页签。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

2.  选择“Presto \> 服务配置”。
3.  将“基础配置”切换为“全部配置”。
4.  在“Presto \> Hive”的“core.site.customized.configs”中增加如下配置。

    -   fs.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapperFileSystem
    -   fs.hdfs.mounttable.hacluster.link./yy = obs://obs-test/job/yy
    -   为使用虚拟机的用户增加如下对应配置：

        -   若使用root用户访问数据：fs.hdfs.mounttable.hacluster.link./tmp/presto-root = obs://obs-test/job/presto\_root/
        -   若使用omm用户访问数据：fs.hdfs.mounttable.hacluster.link./tmp/presto-omm = obs://obs-test/job/presto\_omm/
        -   若使用其他用户访问数据，替换对应用户名即可：fs.hdfs.mounttable.hacluster.link./tmp/presto-\{用户名\} = obs://obs-test/job/presto\_\{用户名\}/

        **图 3**  Presto配置<a name="fig7853193375613"></a>  
        ![](figures/Presto配置.png "Presto配置")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。

5.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Presto服务。

## 通过MRS服务安装的Flink组件提交作业<a name="section215814228817"></a>

1.  登录服务配置页面。
    -   针对MRS 3.x之前版本，登录集群详情页面，选择“组件管理 \> Yarn \> 服务配置”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

    -   针对MRS 3.x及之后版本，登录FusionInsight Manager页面，具体请参见[访问FusionInsight Manager（MRS 3.x及之后版本）](访问FusionInsight-Manager（MRS-3-x及之后版本）.md)，选择“集群 \> 服务 \> Yarn \> 配置”。

2.  将“基础配置”切换为“全部配置”。
3.  在“Yarn \> 自定义”的“yarn.core-site.customized.configs”中增加如下配置。

    -   fs.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapperFileSystem
    -   fs.hdfs.mounttable.hacluster.link./yy = obs://obs-test/job/yy

    **图 4**  MRS Manager上修改Yarn配置<a name="fig838095797"></a>  
    ![](figures/MRS-Manager上修改Yarn配置.png "MRS-Manager上修改Yarn配置")

    **图 5**  FusionInsight Manager上修改Yarn配置<a name="fig74411017175817"></a>  
    ![](figures/FusionInsight-Manager上修改Yarn配置.png "FusionInsight-Manager上修改Yarn配置")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   Flink在启动时会读取HADOOP\_HOME下的配置文件，如果在HADOOP\_HOME配置文件中已经配置了OBS映射关系，则会导致Flink提交作业时报类找不到的错误，可以通过执行如下命令将HADOOP\_HOME下的包拷贝到Flink的lib目录下，并将提交任务用户的权限修改为对该目录拥有读权限来解决该问题（jar包名称会因集群按本不同而有所不同，执行如下命令无需关注）。
    >    **cp $HADOOP\_HOME/share/hadoop/hdfs/lib/\*-wrapper-file-system-\*.jar $FLINK\_HOME/lib/**
    >    **chmod 755 $FLINK\_HOME/lib/\*-wrapper-file-system-\*.jar**

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Yarn服务。

## 提交Spark作业或者执行Spark SQL<a name="section1354662433714"></a>

1.  分别登录所有Master节点，执行如下配置。
2.  执行如下命令编辑Spark用到的core-site.xml文件。

    **vim /opt/client/Spark/spark/conf/core-site.xml**

3.  在core-site.xml文件中增加如下内容。

    ```
    <property>
    <name>fs.hdfs.mounttable.hacluster.link./yy</name>
    <value>obs://obs-test/job/yy</value>
    </property>
    <property>
    <name>fs.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapperFileSystem</value>
    </property>
    <property>
    <name>fs.AbstractFileSystem.hdfs.impl</name>
    <value>com.huawei.hadoop.MRSHDFSWrapper</value>
    </property>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   MRS 1.9.2版本无需添加如下内容。
    >    ```
    >    <property>
    >    <name>fs.AbstractFileSystem.hdfs.impl</name>
    >    <value>com.huawei.hadoop.MRSHDFSWrapper</value>
    >    </property>
    >    ```


## 通过spark beeline jdbc访问HDFS数据<a name="section8988194311315"></a>

前提条件：

-   集群默认的文件系统是HDFS。即fs.defaultFS的配置项是**hdfs：//**开始。
-   集群已配置默认委托，可参考如下步骤配置。
    1.  在集群详情页的“概览”页签，单击委托右侧的“管理委托”选择并绑定MRS\_ECS\_DEFAULT\_AGENCY委托。
    2.  在“节点管理”页签单击所有的节点名称，进入弹性云服务器详情页面，确保所有节点均已绑定MRS\_ECS\_DEFAULT\_AGENCY委托。


具体配置：

1.  登录服务配置页面。
    -   针对MRS 3.x之前版本，登录集群详情页面，选择“组件管理 \> Spark \> 服务配置”。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的“单击同步”进行IAM用户同步）。

    -   针对MRS 3.x及之后版本，登录FusionInsight Manager页面，具体请参见[访问FusionInsight Manager（MRS 3.x及之后版本）](访问FusionInsight-Manager（MRS-3-x及之后版本）.md)，选择“集群 \> 服务 \> Spark2x \> 配置”。

2.  将“基础配置”切换为“全部配置”，角色设置为“JDBCServer”。
3.  在“JDBCServer \> 自定义”的“spark.core-site.customized.configs”中增加如下配置。

    -   fs.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapperFileSystem
    -   fs.hdfs.mounttable.hacluster.link./yy = obs://obs-test/job/yy
    -   fs.AbstractFileSystem.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapper

    **图 6**  MRS Manager上修改Spark配置<a name="fig1861054712520"></a>  
    ![](figures/MRS-Manager上修改Spark配置.png "MRS-Manager上修改Spark配置")

    **图 7**  FusionInsight Manager上修改Spark配置<a name="fig102914438555"></a>  
    ![](figures/FusionInsight-Manager上修改Spark配置.png "FusionInsight-Manager上修改Spark配置")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   **hacluster**为core-site.xml配置中fs.defaultFS的值的namespace，若修改了默认fs.defaultFS配置的namespace，**hacluster**修改对应的值即可。
    >-   **obs://obs-test/job/yy**为待访问的数据在OBS文件系统中的目录，请根据实际值修改。
    >-   MRS 1.9.2版本无需添加如下参数。
    >    -   fs.AbstractFileSystem.hdfs.impl = com.huawei.hadoop.MRSHDFSWrapper

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Spark服务。

