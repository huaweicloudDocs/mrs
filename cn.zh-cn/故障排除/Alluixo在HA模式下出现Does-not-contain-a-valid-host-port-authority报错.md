# Alluixo在HA模式下出现Does not contain a valid host:port authority报错<a name="mrs_03_0204"></a>

## 用户问题<a name="section7422205115512"></a>

安全集群Alluixo在HA模式下出现Does not contain a valid host:port authority的报错，如何处理？

## 问题现象<a name="section7749157195512"></a>

安全集群中，Alluixo在HA模式下出现Does not contain a valid host:port authority的报错。

![](figures/zh-cn_image_0264281925.png)

## 原因分析<a name="section893314412561"></a>

org.apache.hadoop.security.SecurityUtil.buildDTServiceName不支持在uri中填写多个alluxiomaster的地址。

## 处理步骤<a name="section1637769105619"></a>

使用alluxio:///或者alluxio://<主AlluxioMaster的ip或hostname\>:19998/进行访问。

