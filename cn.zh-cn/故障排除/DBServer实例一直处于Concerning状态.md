# DBServer实例一直处于Concerning状态<a name="ZH-CN_TOPIC_0181661513"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276412_sd64242caa665405798481482f49ab0ee"></a>

DBServer实例状态一直是concerning状态，重启之后仍然不恢复。

**图 1**  DBServer的实例状态<a name="zh-cn_topic_0167276412_fig879214436425"></a>  
![](figures/DBServer的实例状态.png "DBServer的实例状态")

## 原因分析<a name="zh-cn_topic_0167276412_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

1.  DBService组件会对“/opt/Bigdata/MRS\_2.0.0/install/dbservice/ha/module/harm/plugin/script/gsDB/.startGS.fail”这个文件监控。
2.  如果这个文件中的值大于3就会启动失败，NodeAgent会一直尝试重启该实例，此时仍会失败而且这个值每启动失败一次就会加1。

## 解决办法<a name="zh-cn_topic_0167276412_section4599086017025"></a>

1.  登录MRS Manager管理界面。
2.  停止该DBServer实例。
3.  使用**omm**用户登录到DBServer实例异常的节点。
4.  修改“/opt/Bigdata/MRS\_2.0.0/install/dbservice/ha/module/harm/plugin/script/gsDB/.startGS.fail”配置文件中的值为0。
5.  启动该DBServer实例。

