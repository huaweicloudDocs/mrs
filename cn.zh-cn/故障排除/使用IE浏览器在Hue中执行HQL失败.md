# 使用IE浏览器在Hue中执行HQL失败<a name="mrs_03_0159"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276173_sd64242caa665405798481482f49ab0ee"></a>

使用IE浏览器在Hue中访问Hive Editor并执行所有HQL失败，界面提示“There was an error with your query.”。

## 原因分析<a name="zh-cn_topic_0167276173_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

IE浏览器存在功能问题，不支持在307重定向中处理含有form data的AJAX POST请求，建议更换兼容的浏览器。

## 解决办法<a name="zh-cn_topic_0167276173_section6285336214518"></a>

使用Google Chrome浏览器21及以上版本。

