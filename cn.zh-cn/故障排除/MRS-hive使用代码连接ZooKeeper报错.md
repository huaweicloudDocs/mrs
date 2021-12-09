# MRS hive使用代码连接ZooKeeper报错<a name="mrs_03_0216"></a>

## 用户问题<a name="section18305143583116"></a>

MRS hive连接ZooKeeper报错。

## 问题现象<a name="section117424454313"></a>

客户使用MRS 1.8集群的hive1.2.1通过hive的jdbc接口连接MRS集群成功，但是客户使用MRS 1.9.0集群的hive2.3.2，通过hive的jdbc接口连接MRS集群进行计算任务报错。报错信息如下：

```
Caused by: org.apache.zookeeper.KeeperException$ConnectionLossException: KeeperErrorCode = ConnectionLoss for /hiveserver2
```

## 原因分析<a name="section1237061220324"></a>

MRS 1.8版本和开源版本认证方式一样，在hive的url中直接将Kerberos认证的文件传进去进行认证。而在MRS 1.9版本中，此方法行不通，需要先进行Kerberos认证，并且需要获取一些别的配置信息，然后再进行url拼接。

## 处理步骤<a name="section520813413313"></a>

请参考官方MRS 1.9样例工程中中hive-examples的认证连接，样例地址请参考[开发指南](https://support.huaweicloud.com/devg-mrs/mrs_06_0002.html)。

## 建议与总结<a name="section8898183420"></a>

客户在官方MRS 1.9的样例基础进行代码开发。

