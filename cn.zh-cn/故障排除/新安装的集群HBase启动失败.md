# 新安装的集群HBase启动失败<a name="ZH-CN_TOPIC_0187794913"></a>

## 问题背景<a name="zh-cn_topic_0167276450_sf76e408f8ea44020bf3de33c280bc079"></a>

新安装的集群HBase启动失败，查看RegionServer日志报如下错误：

```
2018-02-24 16:53:03,863 | ERROR | regionserver/host3/187.6.71.69:21302 | Master passed us a different hostname to use; was=host3, but now=187-6-71-69 | org.apache.hadoop.hbase.regionserver.HRegionServer.handleReportForDutyResponse(HRegionServer.java:1386)
```

## 原因分析<a name="zh-cn_topic_0167276450_s2d857902554344b38f9d1ff9130b2ce3"></a>

/etc/hosts中同一个IP地址配置了多个主机名映射关系。

## 解决办法<a name="zh-cn_topic_0167276450_section1455043221018"></a>

1.  修改/etc/host中IP与主机名的映射关系，配置正确。
2.  重新启动HBase组件。

