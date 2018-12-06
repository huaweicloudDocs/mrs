# Loader使用简介<a name="ZH-CN_TOPIC_0071958192"></a>

## 使用流程<a name="zh-cn_topic_0070859522_section6076220715724"></a>

通过Loader迁移用户数据时，基本流程如下所示。

1.  访问Hue WebUI的Loader页面。
2.  管理Loader连接。
3.  创建作业，选择数据源的连接以及保存数据的连接。
4.  运行作业，完成数据迁移。

## Loader页面介绍<a name="zh-cn_topic_0070859522_section27711559"></a>

Loader页面是基于开源Sqoop WebUI的图形化数据迁移管理工具，该页面托管在Hue的WebUI中。进入Loader页面请执行以下操作：

1.  访问Hue WebUI，参见[创建连接MRS集群的SSH隧道并配置浏览器](创建连接MRS集群的SSH隧道并配置浏览器.md)。
2.  选择“Data Browsers  \>  Sqoop“。

    默认显示Loader页面中的作业管理界面。


## Loader连接介绍<a name="zh-cn_topic_0070859522_section2860052117429"></a>

Loader连接保存了数据具体位置的相关信息，Loader使用连接来访问数据，或将数据保存到指定的位置。进入Loader连接管理页面请执行以下操作：

1.  进入Loader页面。
2.  单击“管理连接“。

    显示Loader连接管理页面。

    可单击“管理作业“回到作业管理页面。

3.  单击“新建连接“，进入配置页面，并填写参数创建一个Loader连接。

## Loader作业介绍<a name="zh-cn_topic_0070859522_section19103996152412"></a>

Loader作业用于管理数据迁移任务，每个作业包含一个源数据的连接，和一个目的数据的连接，通过从源连接读取数据，再将数据保存到目的连接，完成数据迁移任务。

