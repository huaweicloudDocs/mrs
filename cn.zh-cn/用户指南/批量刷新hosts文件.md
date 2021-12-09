# 批量刷新hosts文件<a name="admin_guide_000024"></a>

## 操作场景<a name="section872044116116"></a>

在FusionInsight Manager界面上下载的客户端包中包含客户端批量升级工具，该工具在提供批量升级客户端功能的同时，也提供了轻量级的批量刷新客户端所在节点“/etc/hosts“文件的功能。

## 前提条件<a name="section15722105592216"></a>

更新前准备请参考[批量升级客户端](批量升级客户端.md)章节“客户端升级前准备”步骤。

## 批量更新hosts文件<a name="section205956116520"></a>

1.  检查需要更新“/etc/hosts“文件的节点的配置用户是否为“root“。
    -   是，执行[2](#li11411382418)。
    -   否，更改配置用户为“root“，再执行[2](#li11411382418)。

2.  <a name="li11411382418"></a>执行**sh client\_batch\_upgrade.sh -r -f /tmp/FusionInsight-Client/FusionInsight\_Cluster\_1\_Services\_Client.tar**，批量刷新客户端所在节点的“/etc/hosts“文件。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   执行批量刷新“/etc/hosts“文件时，输入的客户端包可以是完整客户端，也可以是仅包含配置文件的客户端软件包，推荐使用仅包含配置文件的客户端软件包。
    >-   需要更新“/etc/hosts“文件的主机所配置的用户必须为**root**用户，否则会刷新失败。


