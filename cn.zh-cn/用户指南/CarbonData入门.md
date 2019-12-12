# CarbonData入门<a name="ZH-CN_TOPIC_0173178189"></a>

本章节介绍使用Spark CarbonData的基本流程，所有任务场景基于spark-beeline环境。CarbonData快速入门包含以下任务：

1.  连接到Spark

    在对CarbonData进行任何操作之前，需要先连接到Spark。

2.  创建CarbonData表

    连接CarbonData之后，需要创建CarbonData Table，用于加载数据和执行查询操作。

3.  加载数据到CarbonData表

    用户从HDFS中的CSV文件加载数据到所创建的表中。

4.  在CarbonData中查询数据

    在CarbonData表加载数据之后，用户可以执行所需的查询操作，例如groupby或者where等。


## 前提条件<a name="sf10b35613afe4c6d8c13a2e169220750"></a>

已刷新客户端。

## 操作步骤<a name="s868bc997d49740f7a96d0f6915b2dac5"></a>

1.  连接到Spark CarbonData。
    1.  根据业务情况，准备好客户端，并登录安装客户端的节点。

        例如在Master2节点更新客户端，则在该节点登录客户端，具体参见[使用MRS客户端](使用MRS客户端.md)。

    2.  切换用户与配置环境变量。

        **sudo su - omm**

        **source /opt/client/bigdata\_env**

    3.  启用Kerberos认证的集群，执行以下命令认证用户身份。未启用Kerberos认证集群无需执行。

        **kinit** _**Spark组件用户名**_

        用户需要加入“hive“组。

    4.  执行以下命令，连接到Spark运行环境：

        **spark-beeline**

2.  执行命令创建CarbonData表。

    CarbonData表可用于加载数据和执行查询操作，例如执行以下命令创建CarbonData表：

    **CREATE TABLE x1 \(imei string, deviceInformationId int, mac string, productdate timestamp, updatetime timestamp, gamePointId double, contractNumber double\)**

    **STORED BY 'org.apache.carbondata.format'**

    **TBLPROPERTIES \('DICTIONARY\_EXCLUDE'='mac','DICTIONARY\_INCLUDE'='deviceInformationId'\);**

    命令执行结果如下：

    ```
    +---------+--+
    | result  |
    +---------+--+
    +---------+--+
    No rows selected (1.551 seconds)
    ```

3.  从CSV文件加载数据到CarbonData表。

    根据所要求的参数运行命令从CSV文件加载数据，且仅支持CSV文件。**LOAD**命令中配置的CSV列名，需要和CarbonData表列名相同，顺序也要对应。CSV文件中的数据的列数，以及数据格式需要和CarbonData表匹配。

    文件需要保存在HDFS中。用户可以将文件上传到OBS，并在MRS管理控制台“File Management“将文件从OBS导入HDFS。如果集群启用了Kerberos认证，则需要在工作环境准备CSV文件，然后可以使用开源HDFS命令将文件从工作环境导入HDFS，并设置Spark组件用户在HDFS中对文件有读取和执行的权限。

    例如，HDFS的“tmp“目录有一个文件“data.csv“，内容如下：

    ```
    x123,111,dd,2017-04-20 08:51:27,2017-04-20 07:56:51,2222,33333
    ```

    执行导入命令：

    **LOAD DATA inpath 'hdfs://hacluster/tmp/data.csv' into table x1 options\('DELIMITER'=',','QUOTECHAR'='"','FILEHEADER'='imei, deviceinformationid,mac,productdate,updatetime,gamepointid,contractnumber'\);**

    命令执行结果如下：

    ```
    +---------+--+
    | Result  |
    +---------+--+
    +---------+--+
    No rows selected (3.039 seconds)
    ```

4.  在CarbonData中查询数据。

    -   **获取记录数**

        为了获取在CarbonData table中的记录数，可以执行以下命令。

        **select count\(\*\) from x1;**

    -   **使用Groupby查询**

        为了获取不重复的“deviceinformationid“记录数，可以执行以下命令。

        **select deviceinformationid,count \(distinct deviceinformationid\) from x1 group by deviceinformationid;**

    -   **使用条件查询**

        为了获取特定**deviceinformationid**的记录，可以执行以下命令。

        **select \* from x1 where deviceinformationid='111';**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >在执行数据查询操作后，如果查询结果中某一列的结果含有中文字等其他非英文字符，会导致查询结果中的列不能对齐，这是由于不同语言的字符在显示时所占的字宽不尽相同。  

5.  执行以下命令退出Spark运行环境。

    **!quit**


