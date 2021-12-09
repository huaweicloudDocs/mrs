# 执行set role admin报无权限<a name="mrs_03_0165"></a>

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

1.  登录FusionInsight Manager，选择“集群 \> 服务 \> Hive”。
2.  在服务“概览”页面右上角单击“更多”，查看“启用Ranger鉴权”是否置灰。
    -   是，执行[3](#li1833453114611)。
    -   否，执行[8](#li055577135917)。

3.  <a name="li1833453114611"></a>选择“集群 \> 服务 \> Ranger”，单击“基本信息”区域中的“RangerAdmin”，进入Ranger WebUI界面。
4.  单击右上角用户名后，选择“Log Out”，退出当前用户后使用**rangeradmin**用户登录。
5.  在首页中单击“Settings”，选择“Roles”。
6.  单击“Role Name”为“admin”的角色，在“Users”区域，单击“Select User”，选择指定用户名。
7.  点击Add Users按钮，在对应用户名所在行勾选“Is Role Admin”，单击“Save”保存配置，操作结束。
8.  <a name="li055577135917"></a>选择“系统 \> 权限 \> 角色”，添加一个拥有Hive管理员权限的角色。
9.  在FusionInsight Manager页面，选择“系统 \> 权限 \> 用户 ”。
10. 在指定用户对应的“操作”列单击“修改”。
11. 为用户绑定拥有Hive管理员权限的角色，并单击“确定”完成权限添加。

