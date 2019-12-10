# 使用Storm-JDBC插件开发Oracle写入Bolt，发现数据无法写入<a name="ZH-CN_TOPIC_0183415885"></a>

## 现象描述<a name="zh-cn_topic_0167275190_sd2de281c3a2e46329e3c488c1b54fd23"></a>

使用Storm-JDBC插件开发Oracle写入Bolt，发现能连上Oracle数据库，但是无法向Oracle数据库里面写数据。

![](figures/zh-cn_image_0167275602.png)

## 可能原因<a name="zh-cn_topic_0167275190_s857ea6f1c1e445dab07996a583d322cd"></a>

-   拓扑定义异常。
-   数据库表结果定义异常。

## 原因分析<a name="zh-cn_topic_0167275190_section114711357164610"></a>

1.  通过Storm WebUI 查看拓扑DAG图，发现DAG图与拓扑定义一致。

    ![](figures/zh-cn_image_0167275861.png)


1.  查看KeyWordFilter Bolt输出流字段定义和发送消息字段发现一致。

    ![](figures/zh-cn_image_0167274554.png)

    ![](figures/zh-cn_image_0167276131.png)

2.  查看Oracle数据库中表定义，发现字段名为大写，与流定义字段名称不一致。

    ![](figures/zh-cn_image_0167274461.png)

3.  单独调试execute方法，发现抛出字段不存在。

    ![](figures/zh-cn_image_0167275172.png)


## 处理步骤<a name="zh-cn_topic_0167275190_section13132171710514"></a>

修改流定义字段名称为大写，与数据库表定义字段一致。

