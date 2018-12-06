# 准备MySQL数据库连接的驱动<a name="ZH-CN_TOPIC_0074561888"></a>

## 操作场景<a name="zh-cn_topic_0074531420_section12643152165020"></a>

Loader作为批量数据导出的组件，可以通过关系型数据库导入、导出数据。

## 前提条件<a name="zh-cn_topic_0074531420_section7432162165123"></a>

已准备业务数据。

## 操作步骤<a name="zh-cn_topic_0074531420_section25349260165149"></a>

1.  从mysql官网下载mysql jdbc驱动程序“mysql-connector-java-5.1.21.jar“。
2.  将“mysql-connector-java-5.1.21.jar“上传至MRS master 主备节点loader安装目录“/opt/Bigdata/FusionInsight/FusionInsight-Sqoop-1.99.7/FusionInsight-Sqoop-1.99.7/server/jdbc“下。
3.  修改“mysql-connector-java-5.1.21.jar“包属主为“omm:wheel“。
4.  修改配置文件“jdbc.properties“。

    将“MYSQL“的键值修改为上传的jdbc驱动包名“mysql-connector-java-5.1.21.jar“，例如：MYSQL=mysql-connector-java-5.1.21.jar。

5.  重启Loader服务

