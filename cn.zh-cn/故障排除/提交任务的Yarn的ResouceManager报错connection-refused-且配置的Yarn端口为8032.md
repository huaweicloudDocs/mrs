# 提交任务的Yarn的ResouceManager报错connection refused，且配置的Yarn端口为8032<a name="mrs_03_0306"></a>

## 用户问题<a name="section18305143583116"></a>

请求提交任务的Yarn的ResouceManager报错connection refused，且配置的Yarn端口为8032。

## 问题现象<a name="section117424454313"></a>

MRS的Yarn ResouceManager中的一个节点无法连接，且配置的Yarn端口为8032。

## 原因分析<a name="section1237061220324"></a>

该业务应用在集群外部运行，且使用的是老集群的客户端，配的Yarn端口是8032，与MRS服务的Yarn ResouceManager实际端口不同。从而使请求提交任务的Yarn的ResouceManager报错connection refused。

## 处理步骤<a name="section11584183192710"></a>

1.  请参考[更新客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_24213.html)操作，更新MRS服务客户端。
2.  然后重试提交作业。

