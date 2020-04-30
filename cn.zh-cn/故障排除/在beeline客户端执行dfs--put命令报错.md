# 在beeline客户端执行dfs  -put命令报错<a name="ZH-CN_TOPIC_0207461483"></a>

## 问题现象<a name="zh-cn_topic_0167275857_sac9215e0f0624a89b2c0f99ff94d9f59"></a>

执行命令：

**dfs -put /opt/kv1.txt /tmp/kv1.txt**

报以下错误：

```
Permission denied. Principal [name=admin, type=USER] does not have following privileges onObject[type=COMMAND_PARAMS,name=[-put, /opt/kv1.txt, /tmp/kv1.txt]] for operation DFS : [ADMIN PRIVILEGE] (state=,code=1)
```

## 原因分析<a name="zh-cn_topic_0167275857_section1645144113716"></a>

当前登录的用户不具备操作此命令的权限。

## 解决方案<a name="zh-cn_topic_0167275857_sc78d3c2086d0445c87cf8b87ff6096dd"></a>

如果登录的当前用户具有admin角色，请用set role admin来切换成admin角色操作。如果不具备admin角色，在MRS Manager页面的“系统设置\> 用户管理”中给用户绑定对应角色的权限。

