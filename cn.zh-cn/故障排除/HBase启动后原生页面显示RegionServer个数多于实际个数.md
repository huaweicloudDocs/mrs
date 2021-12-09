# HBase启动后原生页面显示RegionServer个数多于实际个数<a name="mrs_03_0142"></a>

## 问题背景<a name="zh-cn_topic_0167275364_sf76e408f8ea44020bf3de33c280bc079"></a>

HBase启动后，HMaster原生页面显示RegionServer个数多于实际RegionServer个数。

查看HMaster原生页面，显示有4个RegionServer在线，如下图示：

![](figures/c00345266-应用组件PDU-02_productdoc2-image-09eac614-0f62-4a4d-8789-ff95adc494dd.jpg)

## 原因分析<a name="zh-cn_topic_0167275364_s2d857902554344b38f9d1ff9130b2ce3"></a>

如下图可以看出，第三行hostname为controller-192-168-1-3节点和第四行hostname为eth0节点为同一RegionServer上报的信息，登录相应节点，查看/etc/hosts文件，发现，对应同一ip，配置两个hostname。如下：

![](figures/c00345266-应用组件PDU-02_productdoc2-image-56aea27b-59a1-40ff-812e-f69442000fed.jpg)

## 解决办法<a name="zh-cn_topic_0167275364_sed4194588b214662be5341d4a1f9ecbd"></a>

登录RegionServer所在节点，修改/etc/hosts文件，同一ip只能对应同一hostname。

