# Hive启动失败问题的原因有哪些？<a name="ZH-CN_TOPIC_0187803458"></a>

Hive启动失败最常见的原因是metastore实例无法连接上DBservice。可以查看metastore日志中具体的错误信息。目前总结连不上DBservice原因主要有：

## 可能原因1<a name="zh-cn_topic_0167275490_se7e9e5b0295a4053b8aa4a0957914b99"></a>

DBservice没有初始化好Hive的元数据库hivemeta。

## 处理步骤1<a name="zh-cn_topic_0167275490_s413879046ac24481af58c58cd9983db4"></a>

1.  执行以下命令：

    **source /opt/Bigdata/MRS\_XXX/install/dbservice/.dbservice\_profile**

    **gsql -h 192.168.0.44（DB的浮动ip）-p 20051 -d hivemeta -U hive -W HiveUser@**

2.  如果不能正确进入交互界面，说明数据库初始化失败。如果报如下错误说明在DBservice所在的节点的配置文件可能丢失了hivemeta的配置。

    ```
    org.postgresql.util.PSQLException: FATAL: no pg_hba.conf entry for host "192.168.0.146", database "HIVEMETA"。
    ```

3.  编辑“/srv/BigData/dbdata\_service/data/pg\_hba.conf“，在文件最后面追加**host hivemeta hive 0.0.0.0/0 sha256**配置。
4.  执行**source /opt/Bigdata/MRS\_XXX/install/dbservice/.dbservice\_profile**命令配置环境变量。
5.  执行**gs\_ctl -D $GAUSSDATA reload  \#**  使修改后的配置生效。

## 可能原因2<a name="zh-cn_topic_0167275490_s3575bb96b24e4814b39e7a64ace006d4"></a>

DBservice的浮动IP配置有误，导致metastore节点IP无法正确连接浮动IP，或者是在与该ip建立互信的时候失败导致metastore启动失败。

## 处理步骤2<a name="zh-cn_topic_0167275490_s38dd22fb180b4f30a5963e4b82e54145"></a>

DBservice的浮动IP配置需要同网段内没有被使用过的ip，也就是在配置前ping不通的ip，请修改DBService浮动IP配置。

