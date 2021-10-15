# 加固LDAP<a name="admin_guide_000280"></a>

## 配置LDAP防火墙策略<a name="zh-cn_topic_0263899212_s7fbcd39f59004fd2badcda3c3314fd88"></a>

在双平面组网的集群中，由于LDAP部署在业务平面中，为保证LDAP数据安全，建议通过配置整个集群对外的防火墙策略，关闭LDAP相关端口。

1.  登录FusionInsight Manager。
2.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer \> 配置”。
3.  查看“LDAP\_SERVER\_PORT”参数值，即为LdapServer的服务端口。
4.  根据客户的实际防火墙环境，配置整个集群对外的防火墙策略，将该端口关闭，以保证数据安全。

## 开启LDAP审计日志输出<a name="zh-cn_topic_0263899212_se0dd555ca94e4ed5ba7cb5932de3bc09"></a>

用户可以通过设置LDAP服务的审计日志输出级别，将审计内容输出至系统日志信息中（如“/var/log/messages”），用于查看用户的活动信息及操作指令信息。

>![](public_sys-resources/icon-note.gif) **说明：** 
>LDAP的审计日志开启后，会产生大量日志信息，严重影响集群性能，请谨慎开启。

1.  登录任一LdapServer节点。
2.  执行以下命令，编辑“slapd.conf.consumer”文件，将“loglevel”的值设置为“256”（loglevel定义可以在OS上使用**man slapd.conf**命令查看）。

    **cd $\{BIGDATA\_HOME\}/FusionInsight\_BASE\_8.1.0.1/install/FusionInsight-ldapserver-2.7.0/ldapserver/local/template**

    **vi slapd.conf.consumer**

    ```
    ... 
    pidfile         [PID_FILE_SLAPD_PID] 
    argsfile        [PID_FILE_SLAPD_ARGS] 
    loglevel   256 
    ...
    ```

3.  登录FusionInsight Manager，选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer \> 更多 \> 重启服务”，验证当前用户身份后重启服务。

