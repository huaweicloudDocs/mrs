# Hue上有job在运行<a name="ZH-CN_TOPIC_0169495351"></a>

## 用户问题<a name="zh-cn_topic_0135447911_section18305143583116"></a>

客户查到Hue上有job在运行。

## 问题现象<a name="zh-cn_topic_0135447911_section117424454313"></a>

客户的MRS装好后， Hue上查到有Job在运行 ，并且目前在运行的job并不是客户操作的。

![](figures/zh-cn_image_0135451387.jpg)

## 原因分析<a name="zh-cn_topic_0135447911_section1237061220324"></a>

此Job为Spark启动之后，系统自身连接jdbc的一个任务，是常驻的。

## 处理步骤<a name="zh-cn_topic_0135447911_section520813413313"></a>

非问题，无需处理。

