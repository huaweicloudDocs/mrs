# 配置sql-standard-with-group创建schema失败报Access Denied<a name="ZH-CN_TOPIC_0226678253"></a>

## 用户问题<a name="section7422205115512"></a>

配置sql-standard-with-group创建schema失败，报Access Denied的错误，如何处理？

## 问题现象<a name="section7749157195512"></a>

```
CREATE SCHEMA hive.sf2 WITH (location = 'obs://obs-zy1234/sf2');Query 20200224_031203_00002_g6gzy failed: Access Denied: Cannot create schema sf2
```

## 原因分析<a name="section893314412561"></a>

presto创建schema需要hive的管理者权限。

## 处理步骤<a name="section1637769105619"></a>

-   方法一：
    1.  登录MRS Manager页面，选择“系统设置 \> 用户管理”。
    2.  在对应用户所在行的“操作”列，单击“修改”。
    3.  单击“选择并绑定角色”，为用户添加System\_administrator的权限。
    4.  单击“确定”完成修改。

-   方法二：
    1.  登录MRS Manager页面，选择“系统设置 \> 角色管理”。
    2.  单击“添加角色”，并配置如下参数。
        -   角色名称：配置角色名称，例如hive\_admin。
        -   权限：选择“Hive”，并勾选Hive Admin Privilege。

    3.  单击“确定”保存角色。
    4.  选择“系统设置 \> 用户管理”。
    5.  在对应用户所在行的“操作”列，单击“修改”。
    6.  单击“选择并绑定角色”，为用户添加新创建的hive\_admin的权限。
    7.  单击“确定”完成修改。


