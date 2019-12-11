# HBase的initial超时保留导致启动失败<a name="ZH-CN_TOPIC_0183415845"></a>

## 问题现象<a name="zh-cn_topic_0167276488_sf1828d9aad52449baacbc463fce418d6"></a>

MRS 1.5.x版本，HBase启动失败提示初始化超时。

## 原因分析<a name="zh-cn_topic_0167276488_sd24bdaecc508454c9eca1923beef3322"></a>

因为之前残留大量RIT事务，而参数“hbase.master.initializationmonitor.timeout“默认300秒，该时间内还未来得及完成初始化，导致Hmater进程主动退出。

![](figures/zh-cn_image_0167275752.png)

## 解决办法<a name="zh-cn_topic_0167276488_s20ac48aedef54d1e9b94cd35ce24a392"></a>

1.  登录MRS Manager页面，选择“服务管理 \> HBase \> 服务配置”，进入HBase配置页面。
2.  “参数类别“选择“全部配置“， 搜索并修改“hbase.master.initializationmonitor.timeout“参数，将参数增大（比如临时改成30分钟）。
3.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”重启服务。

