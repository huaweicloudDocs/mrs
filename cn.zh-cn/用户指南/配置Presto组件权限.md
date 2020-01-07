# 配置Presto组件权限<a name="ZH-CN_TOPIC_0193467693"></a>

配置Presto权限在MRS 2.0.5及之后版本支持。

## 安全集群配置Presto组件权限<a name="section03361729163916"></a>

安全集群默认已经开放Presto组件Hive Catalog授权，权限配置如下：

1.  参考[访问MRS Manager](访问MRS-Manager.md)页面登录MRS Manager页面。
2.  选择“系统设置 \> 角色管理”，配置拥有Hive数据库/表权限的角色并为用户绑定该角色。

## 普通集群配置Presto组件权限<a name="section1790764493916"></a>

普通集群默认不开放Presto授权，需要手动配置，操作如下：

1.  登录MRS集群详情页面。
2.  选择“组件管理 \> Hive”。设置“参数类别”为“全部配置”，进入Hive配置界面修改参数配置。
3.  搜索并修改如下参数。
    -   hive.security.authorization.enabled配置为true
    -   hive.security.authorization.manager配置为org.apache.hadoop.hive.ql.security.authorization.plugin.sqlstd.SQLStdHiveAuthorizerFactory

4.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Hive服务。
5.  选择“组件管理 \> Presto”。设置“参数类别”为“全部配置”，进入Presto配置界面修改参数配置。
6.  搜索并修改参数hive.security，配置为sql-standard-with-group。
7.  单击“保存配置”，并勾选“重新启动受影响的服务或实例。”重启Presto服务。
8.  参考[访问MRS Manager](访问MRS-Manager.md)页面登录MRS Manager页面。
9.  选择“系统设置 \> OMS数据库密码修改 \> 重启OMS服务”。
10. 选择“系统设置 \> 角色管理”，配置拥有Hive数据库/表权限的角色并为用户绑定该角色。

