# 端口被占用导致RegionServer启动失败<a name="mrs_03_0066"></a>

## 问题现象<a name="zh-cn_topic_0167275014_s7f8671494bed4bdeb17136db86359327"></a>

Manager页面监控发现RegionServer状态为Restoring。

## 原因分析<a name="zh-cn_topic_0167275014_se44ba4f171a24022a02c97b1203b8c51"></a>

1.  通过查看RegionServer日志（/var/log/Bigdata/hbase/rs/hbase-omm-xxx.log）。
2.  使用**lsof -i:21302**（MRS1.7.X及以后端口号是16020）查看到pid，然后根据pid查看到相应的进程，发现RegionServer的端口被DFSZkFailoverController占用。
3.  查看“/proc/sys/net/ipv4/ip\_local\_port\_range“显示为“9000  65500“，临时端口范围与MRS产品端口范围重叠，因为安装时未进行preinstall操作。

## 解决办法<a name="zh-cn_topic_0167275014_sf44c4148fcbe469a8a2b2598e3c8757d"></a>

1.  执行**kill -9** _DFSZkFailoverController的pid_， 使得其重启后绑定其它端口，然后重启Restoring的RegionServer。

