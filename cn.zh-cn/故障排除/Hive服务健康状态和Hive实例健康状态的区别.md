# Hive服务健康状态和Hive实例健康状态的区别<a name="ZH-CN_TOPIC_0207461488"></a>

## 问题现象<a name="zh-cn_topic_0167275780_section76101932145418"></a>

Hive服务健康状态和Hive实例健康状态的区别是什么？

## 解决方案<a name="zh-cn_topic_0167275780_section3854911102212"></a>

Hive服务的健康状态（也就是在services界面看到的健康状态）有Good，Bad，Partially Healthy，Unknown四种状态 ，四种状态除了取决于Hive本身服务的可用性（会用简单的sql来检测Hive服务的可用性），还取决于Hive服务所依赖的其他组件的服务状态。

Hive实例分为Hiveserver和Metastore两种，健康状态有Good，Concerning ，Unknown三种状态，这三种状态是通过jmx通信来判定，与实例通信正常时为Good，通信异常时为Concerning，无法通信时为Unknown。

