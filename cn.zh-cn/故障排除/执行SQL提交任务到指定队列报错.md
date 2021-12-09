# 执行SQL提交任务到指定队列报错<a name="mrs_03_0160"></a>

## 问题现象<a name="zh-cn_topic_0167275254_s0e16cb275d0649c4b4d5b7c4e55bc6eb"></a>

执行SQL提交任务到Yarn报如下错误：

```
Failed to submit application_1475400939788_0033 to YARN : org.apache.hadoop.security.AccessControlException: User newtest cannot submit applications to queue root.QueueA
```

## 原因分析<a name="zh-cn_topic_0167275254_section861663118293"></a>

当前登录的用户无YARN队列提交权限。

## 解决方案<a name="zh-cn_topic_0167275254_sbd66bb813b7140758912b4ea6df91b63"></a>

用户无YARN队列提交权限，需要赋予YARN相应队列的提交权限。在Manager页面的“系统 \>权限 \> 用户”中给用户绑定队列提交权限的角色。

