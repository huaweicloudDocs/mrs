# 管理Loader连接<a name="ZH-CN_TOPIC_0173178699"></a>

## 操作场景<a name="sd0aa691d931c4275be7db53ceb1ede5f"></a>

Loader页面支持创建、查看、编辑和删除连接。

## 前提条件<a name="sf4ee43f1495449978e389f1f20b5705d"></a>

已访问Loader页面，参见[Loader页面介绍](Loader使用简介.md#s12f4baccf3914471bee631d0ca198278)。

## 创建连接<a name="s11a09a35dae6449786ccbf16ec72c5fb"></a>

1.  在Loader页面，单击“管理连接“。
2.  单击“新建连接“，配置连接参数。

    参数介绍具体可参见[Loader连接配置说明](Loader连接配置说明.md)。

3.  单击“保存“。

    如果连接配置，例如IP地址、端口、访问用户等信息不正确，将导致验证连接失败无法保存。另外VPC相关设置，也可能影响网络连通性。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >用户可以直接单击“测试“立即检测连接是否可用。  


## 查看连接<a name="s5cb20b57ea8f40959de85acbc2d317fe"></a>

1.  在Loader页面，单击“管理连接“。
    -   如果集群启用了Kerberos认证，则默认显示所有当前用户创建的连接，不支持显示其他用户的连接。
    -   如果集群未启用Kerberos认证，则显示集群中全部的Loader连接。

2.  在“Sqoop连接“中输入指定连接的名称，可以筛选该连接。

## 编辑连接<a name="s28cd1b53ac2f4667b3bb913714771b26"></a>

1.  在Loader页面，单击“管理连接“。
2.  单击指定连接的名称，进入编辑页面。
3.  <a name="l5be12d652055488480d006943dab4edb"></a>根据业务需要，修改连接配置参数。
4.  单击“测试“。

    如果显示测试成功，则执行[5](#l4e4fbb8553194cc8914e87c2ddde2152)；如果显示不能连接至OBS Server，则需要重复[3](#l5be12d652055488480d006943dab4edb)。

5.  <a name="l4e4fbb8553194cc8914e87c2ddde2152"></a>单击“保存“。

    如果某个Loader作业已集成一个Loader连接，那么编辑连接参数后可能导致Loader作业运行效果也产生变化。


## 删除连接<a name="s74e3c4ae1b884e8d9443b447c50d13a7"></a>

1.  在Loader页面，单击“管理连接“。
2.  在指定连接所在行，单击“删除“。
3.  在弹出的对话框窗口，单击“是，将其删除“。

    如果某个Loader作业已集成一个Loader连接，那么该连接不可以被删除。


