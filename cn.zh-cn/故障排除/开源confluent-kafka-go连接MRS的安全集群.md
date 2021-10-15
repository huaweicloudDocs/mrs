# 开源confluent-kafka-go连接MRS的安全集群<a name="mrs_03_0223"></a>

## 用户问题<a name="section18305143583116"></a>

开源confluent-kafka-go如何连接MRS的安全集群？

## 问题现象<a name="section117424454313"></a>

开源confluent-kafka-go连接MRS的安全集群失败。

## 原因分析<a name="section1237061220324"></a>

confluent-kafka-go依赖的库librdkafka默认将broker所在hostname作为了server princple的一部分来使用，导致认证失败。

## 处理步骤<a name="section980318484317"></a>

librdkafka具体修改步骤：

1.  librdkafka源码地址：[https://github.com/edenhill/librdkafka](https://github.com/edenhill/librdkafka)。
2.  在src/rdkafka\_conf.c文件中增加sasl.kerberos.service.name配置项。

    ```
     "Kerberos principal name that Kafka runs as.",            .sdef = "kafka" },          { _RK_GLOBAL, "sasl.kerberos.principal", _RK_C_STR,            _RK(sasl.principal),            "This client´s Kerberos principal name.",            .sdef = "kafkaclient" }, +        { _RK_GLOBAL, "sasl.kerberos.domain.name", _RK_C_STR, +          _RK(sasl.domain_name), +          "This cluster´s Kerberos domain name.", +          .sdef = "hadoop.hadoop.com" },   #ifndef _MSC_VER          { _RK_GLOBAL, "sasl.kerberos.kinit.cmd", _RK_C_STR,            _RK(sasl.kinit_cmd),            "Full kerberos kinit command string, %{config.prop.name} is replaced "            "by corresponding config object value, %{broker.name} returns the "            "broker´s hostname.", -          .sdef = "kinit -S \"%{sasl.kerberos.service.name}/%{broker.name}\" " +          .sdef = "kinit -S \"%{sasl.kerberos.service.name}/%{sasl.kerberos.domain.name}\" "            "-k -t \"%{sasl.kerberos.keytab}\" %{sasl.kerberos.principal}" },          { _RK_GLOBAL, "sasl.kerberos.keytab", _RK_C_STR,            _RK(sasl.keytab),            "Path to Kerberos keytab file. Uses system default if not set."            "**NOTE**: This is not automatically used but must be added to the "            "template in sasl.kerberos.kinit.cmd as "
    ```

3.  在src/rdkafka\_conf.h文件中增加domain\_name字段。

    ```
    --- src\rdkafka_conf.h        2017-10-17 11:20:56.000000000 +0800 +++ src\rdkafka_conf.h        2017-10-25 16:26:34.000000000 +0800 @@ -118,12 +118,13 @@          struct {                  const struct rd_kafka_sasl_provider *provider;                  char *principal;                  char *mechanisms;                  char *service_name; +                                char *domain_name;                  char *kinit_cmd;                  char *keytab;                  int   relogin_min_time;                  char *username;                  char *password; #if WITH_SASL_SCRAM
    ```

4.  在src/rdkafka\_sasl\_cyrus.c文件中将hostname替换成domainName。

    ```
    --- src\rdkafka_sasl.c        2017-10-17 11:20:56.000000000 +0800 +++ src\rdkafka_sasl.c        2017-10-25 16:09:38.000000000 +0800 @@ -192,13 +192,14 @@                              rk->rk_conf.sasl.mechanisms,                              rk->rk_conf.api_version_request ? "" :                              ": try api.version.request=true");                  return -1;          } -        rd_strdupa(&hostname, rktrans->rktrans_rkb->rkb_nodename); +        //rd_strdupa(&hostname, rktrans->rktrans_rkb->rkb_nodename); +                rd_strdupa(&hostname, rk->rk_conf.sasl.domain_name);          if ((t = strchr(hostname, ´:´)))                  *t = ´\0´;  /* remove ":port" */
    ```

5.  重新编译librdkafka（请确保已安装libsasl2-dev），具体步骤参考[https://github.com/edenhill/librdkafka/tree/v0.11.1](https://github.com/edenhill/librdkafka/tree/v0.11.1)。

    **./configure make make install**

6.  使用客户端时增加如下配置项。

    ```
    "security.protocol": "SASL_PLAINTEXT", 
    "sasl.kerberos.service.name": "kafka", 
    "sasl.kerberos.keytab": "/opt/nemon/user.keytab",  
    "sasl.kerberos.principal": "nemon@HADOOP.COM", 
    "sasl.kerberos.domain.name": "hadoop.hadoop.com",
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >MRS 2.1.x及之前版本：
    >-   sasl.kerberos.keytab：可通过在MRS Manager界面选择“系统设置 \> 用户管理“，在对应用户所在行的“操作”列选择“更多 \>下载认证凭据“，保存后解压得到用户的user.keytab文件。
    >-   sasl.kerberos.principal：请填写实际用户名。
    >-   sasl.kerberos.domain.name：domain的命名规则为hadoop. toLowerCase\(realm\)，假设集群的域名（default\_realm）为huawei.com时，domain的值为hadoop.huawei.com。可通过MRS Manager界面选择“服务管理\> KrbServer \>   \>  服务配置 \> 全部配置“  ，搜索并查看default\_realm的值。
    >MRS 3.x及后续版本：
    >-   sasl.kerberos.keytab：可通过在FusionInsight Manager界面选择“系统 \> 权限 \> 用户“，在对应用户所在行的“操作”列选择“更多 \>下载认证凭据“，保存后解压得到用户的user.keytab文件。
    >-   sasl.kerberos.principal：请填写实际用户名。
    >-   sasl.kerberos.domain.name：domain的命名规则为hadoop. toLowerCase\(realm\)，假设集群的域名（default\_realm）为huawei.com时，domain的值为hadoop.huawei.com。可通过FusionInsight Manager界面选择“集群 \> 服务 \> KrbServer \>   \>  配置 \> 全部配置“  ，搜索并查看default\_realm的值。


