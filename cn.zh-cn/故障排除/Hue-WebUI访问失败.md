# Hue WebUI访问失败<a name="mrs_03_0208"></a>

## 用户问题<a name="section18305143583116"></a>

访问Hue WebUI跳转到错误的页面。

## 问题现象<a name="section117424454313"></a>

查看hue web ui报错如下：

```
503 Service Unavailable
The server is temporarily unable to service your requster due to maintenance downtime or capacity problems.Please try again later.
```

## 原因分析<a name="section1237061220324"></a>

-   hue配置过期。
-   MRS 2.0.1及之后版本的单Master节点集群中，Hue服务需要手动修改配置。

## 处理步骤<a name="section9602125852418"></a>

1.  登录Master节点。
2.  执行**hostname -i**获取本机IP。
3.  执行如下命令获取“HUE\_FLOAT\_IP”的地址：

    **grep "HUE\_FLOAT\_IP" $\{BIGDATA\_HOME\}/_MRS_\_Current/1\_\*/etc\*/ENV\_VARS**,其中_MRS_以实际文件名为准。

4.  比较本机IP和“HUE\_FLOAT\_IP”的值是否相同，若不相同，请修改“HUE\_FLOAT\_IP”的值为本机IP。
5.  重启Hue服务。

