# Hue（主）无法打开web网页<a name="mrs_03_0174"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276173_sd64242caa665405798481482f49ab0ee"></a>

访问Hue（主）的WebUI界面提示如下：

```
Service Unavailable 
The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again later.
```

## 原因分析<a name="zh-cn_topic_0167276173_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

-   Hue配置过期。
-   MRS 2.0.1及之后版本的单Master节点集群中，Hue服务需要手动修改配置。

## 解决办法<a name="section057843281315"></a>

-   Hue配置过期，重启Hue服务即可。
-   在MRS 2.0.1及之后版本，单Master节点的集群Hue服务需要手动修改配置。
    1.  登录Master节点。
    2.  执行**hostname -i**获取本机IP。
    3.  执行如下命令获取“HUE\_FLOAT\_IP”的地址：

        **grep "HUE\_FLOAT\_IP" $\{BIGDATA\_HOME\}/_MRS_\_Current/1\_\*/etc\*/ENV\_VARS，**

        其中_MRS_以实际文件名为准。

    4.  比较本机IP和“HUE\_FLOAT\_IP”的值是否相同，若不相同，请修改“HUE\_FLOAT\_IP”的值为本机IP。
    5.  重启Hue服务。


