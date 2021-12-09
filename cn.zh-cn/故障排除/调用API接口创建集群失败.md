# 调用API接口创建集群失败<a name="mrs_03_0052"></a>

## 用户问题<a name="section18305143583116"></a>

按照参考文档[创建集群并执行作业](https://support.huaweicloud.com/api-mrs/mrs_02_0028.html)，调用创建集群接口：POST /v1.1/\{project\_id\}/run-job-flow 返回500。

## 问题现象<a name="section117424454313"></a>

调用创建集群接口：POST /v1.1/\{project\_id\}/run-job-flow 返回500。

## 原因分析<a name="section1237061220324"></a>

用户没有创建集群的权限。

## 处理步骤<a name="section7778103963815"></a>

检查是否拥有创建MRS集群的权限，可参考文档[权限管理](https://support.huaweicloud.com/productdesc-mrs/mrs_08_0033.html)。

