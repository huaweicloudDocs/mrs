# 准备MySQL数据库连接的驱动<a name="ZH-CN_TOPIC_0173178238"></a>

## 操作场景<a name="s78832e8225994ed19fa40912fae39571"></a>

Loader作为批量数据导出的组件，可以通过关系型数据库导入、导出数据。

## 前提条件<a name="s5a9e83ac3b8841a49f5613d1971a74d6"></a>

已准备业务数据。

## 操作步骤<a name="s626c74c010b843ca9b1e640ab095bf5f"></a>

1.  从mysql官网下载mysql jdbc驱动程序“mysql-connector-java-5.1.21.jar“。
2.  将“mysql-connector-java-5.1.21.jar“上传至MRS master 主备节点loader安装目录
    -   针对MRS 1.8.0之前版本，上传至“/opt/Bigdata/FusionInsight/FusionInsight-Sqoop-1.99.7/FusionInsight-Sqoop-1.99.7/server/jdbc“
    -   针对MRS 1.8.5及之后版本，上传至“/opt/Bigdata/MRS\_XXX/install/FusionInsight-Sqoop-1.99.7/FusionInsight-Sqoop-1.99.7/server/jdbc/“

        其中“XXX“为MRS版本号，请根据实际情况修改。

3.  修改“mysql-connector-java-5.1.21.jar“包属主为“omm:wheel“。
4.  修改配置文件“jdbc.properties“。

    将“MYSQL“的键值修改为上传的jdbc驱动包名“mysql-connector-java-5.1.21.jar“，例如：MYSQL=mysql-connector-java-5.1.21.jar。

5.  重启Loader服务

