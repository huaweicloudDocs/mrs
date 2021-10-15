# Hue界面无法加载HBase表<a name="mrs_03_0209"></a>

## 用户问题<a name="section18305143583116"></a>

用户在Hue界面将hive数据导入hbase后，报检测不到hbase表的错误。

## 问题现象<a name="section117424454313"></a>

Kerberos集群中，IAM子账户权限不足导致无法加载hbase表。

## 原因分析<a name="section1237061220324"></a>

IAM子账户权限不足。

## 处理步骤<a name="section185969433257"></a>

MRS Manager界面操作：

1.  登录[MRS Manager](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0102.html)。
2.  选择“系统管理 \> 用户管理”。
3.  在使用的用户所在行的单击“修改”。
4.  为用户添加supergroup组。
5.  单击“确定”完成修改操作。

FusionInsight Manager界面操作：

1.  登录FusionInsight Manager。
2.  选择“系统 \> 权限 \> 用户”。
3.  在使用的用户所在行单击“修改”。
4.  为用户添加supergroup组。
5.  单击“确定”完成修改操作。

## 建议与总结<a name="section8898183420"></a>

如果是开启Kerberos认证的集群，页面出现 No data available优先排查权限问题。

