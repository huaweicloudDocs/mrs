# Hive服务重启失败<a name="mrs_03_0260"></a>

## 用户问题<a name="section18305143583116"></a>

修改Hive服务配置后，保存配置失败，Manager页面Hive服务的配置状态为配置失败。

## 问题现象<a name="section117424454313"></a>

用户A在MRS节点后台上打开了Hive相关配置文件且未关闭，此时用户B在MRS Manager页面的“服务管理”中修改Hive配置项，保存配置并重启Hive服务，此时保存配置失败，并且Hive服务启动失败。

## 原因分析<a name="section1237061220324"></a>

由于用户B在MRS Manager页面修改配置时，配置文件被用户A在MRS节点后台打开，导致该配置文件不能被替换，最终导致Hive服务启动失败。

## 处理步骤<a name="section520813413313"></a>

1.  用户需要首先手动关闭集群节点后台打开的Hive配置文件。
2.  在MRS Manager页面重新修改Hive的配置并保存配置。
3.  重启Hive服务。

