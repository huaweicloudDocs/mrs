# 切换Ranger鉴权<a name="admin_guide_000415"></a>

## 操作场景<a name="section129911458858"></a>

新安装的安全模式集群默认即安装了Ranger服务并启用了Ranger鉴权，用户可以通过组件的权限插件对组件资源的访问设置细粒度的安全访问策略。若不需使用Ranger进行鉴权，管理员可在服务页面手动停用Ranger鉴权，停用Ranger鉴权后，访问组件资源时系统将继续基于FusionInsight Manager的角色模型进行权限控制。

从历史版本升级的集群，用户访问组件资源时默认不使用Ranger鉴权，管理员可在安装了Ranger服务后手动启用Ranger鉴权。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   安全模式集群中，支持使用Ranger鉴权的组件包括：HDFS、Yarn、Kafka、Hive、HBase、Storm、Spark2x、Impala。
>-   非安全模式集群中，Ranger可以支持基于OS用户进行组件资源的权限控制，支持启用Ranger鉴权的组件包括：HBase、HDFS、Hive、Spark2x、Yarn。
>-   启用Ranger鉴权后，该组件所有鉴权将由Ranger统一管理，原鉴权插件设置的权限将会失效（HDFS与Yarn的组件ACL规则仍将生效），请谨慎操作，建议提前在Ranger上做好权限部署。
>-   停用Ranger鉴权后，该组件所有鉴权将由组件自身权限插件管理，Ranger上设置的权限将会失效，请谨慎操作，建议提前在Manager上做好权限部署。

## 启用Ranger鉴权<a name="section3763331141310"></a>

1.  登录FusionInsight Manager。
2.  选择“集群 \>  服务”。
3.  单击服务视图中指定的服务名称。
4.  在服务详情页面单击“更多”，选择“启用Ranger鉴权”。
5.  输入当前登录的用户密码确认身份，单击“确定“。
6.  在服务列表，重启配置过期的服务。

## 停用Ranger鉴权<a name="section15295192185211"></a>

1.  登录FusionInsight Manager。
2.  选择“集群 \>  服务”。
3.  单击服务视图中指定的服务名称。
4.  在服务详情页面单击“更多”，选择“停用Ranger鉴权”。
5.  输入当前登录的用户密码确认身份，单击“确定“，在弹出框中单击“确定”。
6.  在服务列表，重启配置过期的服务。

