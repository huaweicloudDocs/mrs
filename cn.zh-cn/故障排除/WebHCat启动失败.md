# WebHCat启动失败<a name="ZH-CN_TOPIC_0210454009"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276485_section842971116813"></a>

用户修改hostname导致WebHCat启动失败。

查看对应节点WebHCat启动日志（ /var/log/Bigdata/hive/webhcat/hive.log），发现报如下错误

![](figures/zh-cn_image_0167275689.png)

## 原因分析<a name="zh-cn_topic_0167276485_section724010302087"></a>

1.  MRSwebhcat角色的服务端账户中涉及到hostname，如果安装完后再修改hostname，就会导致启动失败。
2.  /etc/hosts中配置了一对多或者多对一的主机名和IP对应关系，导致在执行**hostname**和**hostname -i**获取不到正确的IP和hostname。

## 解决办法<a name="zh-cn_topic_0167276485_section17326135612212"></a>

1.  将修改了节点的hostname全部修改为集群安装前的hostname。
2.  排查WebHCat所在节点的/etc/hosts是否配置正确。
3.  重启WebHCat。

