# 用户连接impala-shell失败<a name="ZH-CN_TOPIC_0203029723"></a>

## 用户问题<a name="section2029414539714"></a>

用户连接impala-shell失败。

## 问题现象<a name="section1999616579715"></a>

用户在“组件管理”页面修改任意组件的配置并重启服务后，连接impala-shell，会出现连接失败，报错no such file/directory。![](figures/zh-cn_image_0203033467.png)

## 原因分析<a name="section18356981781"></a>

修改服务配置并重启服务后，部分服务的目录结构会删除并重新创建，如服务的etc目录等。如果重启服务前所在的目录为etc或者其子目录，由于重启后目录重建，仍在原来目录执行impala-shell时会产生某些系统变量或者参数无法找到的情况，所以连接impala-shell连接失败。

## 处理步骤<a name="section1473916780"></a>

任意切换到存在的目录，重新连接impala-shell即可。

