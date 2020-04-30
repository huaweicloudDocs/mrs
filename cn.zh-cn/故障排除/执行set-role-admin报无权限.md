# 执行set role admin报无权限<a name="ZH-CN_TOPIC_0207461484"></a>

## 问题现象<a name="zh-cn_topic_0167275844_s4062da02d4d340ed9dbd38c42c5a7475"></a>

执行命令：

**set role admin**

报下述错误：

```
0: jdbc:hive2://192.168.42.26:21066/> set role admin;
Error: Error while processing statement: FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.DDLTask. dmp_B doesn't belong to role admin (state=08S01,code=1)
```

## 原因分析<a name="zh-cn_topic_0167275844_section1645144113716"></a>

当前登录的用户不具有Hive的admin角色的权限。

## 解决方案<a name="zh-cn_topic_0167275844_sf8f53c018c784bab9ca84e6d32b5d35d"></a>

1.  登录MRS Manager页面，单击“系统配置 \> 角色管理 \> 添加角色”，添加一个拥有Hive Admin Privilege权限的角色。
2.  在MRS Manager页面，单击“系统配置 \> 用户管理 ”。
3.  在指定用户对应的“操作”列单击“修改”。
4.  为用户绑定拥有Hive Admin Privilege权限的角色，并单击“确定”完成权限添加。

