# DBServer启动失败<a name="mrs_03_0128"></a>

## 问题背景与现象<a name="zh-cn_topic_0167274908_sd64242caa665405798481482f49ab0ee"></a>

DBService组件启动失败，重启还是失败，实例状态一直为正在恢复状态。

**图 1**  DBService 的状态<a name="zh-cn_topic_0167274908_fig233855783611"></a>  
![](figures/DBService-的状态.png "DBService-的状态")

## 原因分析<a name="zh-cn_topic_0167274908_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

1.  查看DBService的日志/var/log/Bigdata/dbservice/DB/gs\_ctl-current.log，报如下错误。

    ![](figures/zh-cn_image_0264281926.jpg)

2.  检查发现/tmp权限不正确，正确的权限应该为777。

    ![](figures/zh-cn_image_0264281718.jpg)


## 解决办法<a name="zh-cn_topic_0167274908_section4599086017025"></a>

1.  修改/tmp权限为777。
2.  重新启动DBService组件。

