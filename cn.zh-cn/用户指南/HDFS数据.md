# HDFS数据<a name="mrs_01_0445"></a>

## 打通数据传输通道<a name="section2349182854814"></a>

-   当源集群与目标集群部署在同一区域的不同VPC时，请创建两个VPC之间的网络连接，打通网络层面的数据传输通道。请参见[VPC对等连接](https://support.huaweicloud.com/usermanual-vpc/zh-cn_topic_0046655036.html)。
-   当源集群与目标集群部署在同一VPC但属于不同安全组时，在VPC管理控制台，为每个安全组分别添加安全组规则。规则的“协议”为“ANY”，“方向”为“入方向”，“源地址”为“安全组”且是对端集群的安全组。
    -   为源集群的安全组添加入方向规则，源地址选择目标集群的安全组。
    -   为目标集群的安全组添加入方向规则，源地址选择源集群的安全组。

-   当源集群与目标集群部署在同一VPC同一安全组且两个集群都开启了Kerberos认证，请参考[配置跨集群互信](配置跨集群互信.md)章节为两个集群配置互信。

## HDFS数据备份<a name="section2055013210328"></a>

根据源集群与目标集群分别所处的区域及网络连通性，可分为以下几种数据备份场景：

-   <a name="li529181519336"></a>同Region

    当源集群与目标集群处于同一Region时，根据[打通数据传输通道](准备工作.md#section2349182854814)进行网络配置，打通网络传输通道。使用Distcp工具执行如下命令将源集群的HDFS、HBase、Hive数据文件以及Hive元数据备份文件拷贝至目的集群。

    ```
    $HADOOP_HOME/bin/hadoop distcp <src> <dist> -p
    ```

    其中，各参数的含义如下。

    -   _$HADOOP\_HOME_：目的集群Hadoop客户端安装目录
    -   <src\>：源集群HDFS目录
    -   <dist\>：目的集群HDFS目录

-   不同Region

    当源集群与目标集群处于不同Region时，用Distcp工具将源集群数据拷贝到OBS，借助OBS跨区域复制功能（请参见[跨区域复制](https://support.huaweicloud.com/ugobs-obs/obs_41_0034.html)）将数据复制到对应目的集群所在Region的OBS，然后通过Distcp工具将OBS数据拷贝到目的集群的HDFS上。由于执行Distcp无法为OBS上的文件设置权限、属主/组等信息，因此当前场景在进行数据导出时也需要将HDFS的元数据信息进行导出并拷贝，以防HDFS文件属性信息丢失。

-   线下集群向云迁移

    线下集群可以通过如下两种方式将数据迁移至云：

    -   云专线（DC）

        为源集群与目标集群之间建立[云专线](https://www.huaweicloud.com/product/dc.html)，打通线下集群出口网关与线上VPC之间的网络，然后参考[同Region](#li529181519336)执行Distcp进行拷贝。

    -   数据快递服务（DES）

        对于TB或PB级数据上云的场景，华为云提供[数据快递服务 DES](https://www.huaweicloud.com/product/des.html)。将线下集群数据及已导出的元数据拷贝到DES盒子，快递服务将数据递送到华为云机房，然后通过[云数据迁移 CDM](https://www.huaweicloud.com/product/cdm.html)将DES盒子数据拷贝到HDFS。



## HDFS元数据备份<a name="section1960610451314"></a>

HDFS数据需要导出的元数据信息包括文件及文件夹的权限和属主/组信息。可通过如下HDFS客户端命令导出。

```
$HADOOP_HOME/bin/hdfs dfs –ls –R <migrating_path> > /tmp/hdfs_meta.txt
```

其中，各参数的含义如下。

-   _$HADOOP\_HOME_：源集群Hadoop客户端安装目录
-   _<migrating\_path\>_：HDFS上待迁移的数据目录
-   /tmp/hdfs\_meta.txt：导出的元数据信息保存在本地的路径。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果源集群与目标集群网络互通，且以超级管理员身份运行hadoop distcp命令进行数据拷贝，可以添加参数“-p”让distcp在拷贝数据的同时在目标集群上分别恢复相应文件的元数据信息。因此在这种场景下可直接跳过本步骤。

## HDFS文件属性恢复<a name="section16356182920517"></a>

根据导出的权限信息在目的集群的后台使用HDFS命令对文件的权限及属主/组信息进行恢复。

```
$HADOOP_HOME/bin/hdfs dfs –chmod <MODE> <path>
$HADOOP_HOME/bin/hdfs dfs –chown <OWNER> <path>
```

