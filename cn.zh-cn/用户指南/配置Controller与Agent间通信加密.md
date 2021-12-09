# 配置Controller与Agent间通信加密<a name="admin_guide_000284"></a>

## 操作场景<a name="saa33116f21f2473a9144960266629fdf"></a>

安装集群后Controller和Agent之间需要进行数据通信，在通信的过程中采用了Kerberos认证，出于对集群性能的考虑，通信过程默认不加密，对于一些安全要求较高用户可以采用以下方式进行加密。

## 对系统的影响<a name="s921106f1d45841a9a48d5bf67d9cbc92"></a>

-   执行加密操作时，会自动重启Controller和所有Agent，重启期间会造成FusionInsight Manager暂时中断。
-   大集群下会导致管理节点性能有所下降，建议集群不超过200节点时开启该功能。

## 前提条件<a name="s380461e1b795408bb4fd6b8f418d5c81"></a>

已确认主备管理节点IP。

## 操作步骤<a name="s058e1e0f2bec4ce587f8cdaf308d5f41"></a>

1.  以**omm**用户登录到主管理节点。
2.  执行以下命令，防止超时退出。

    **TMOUT=0**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >执行完本章节操作后，请及时恢复超时退出时间，执行命令**TMOUT=**_超时退出时间_。例如：**TMOUT=600**，表示用户无操作600秒后超时退出。

3.  执行以下命令，切换目录。

    **cd $\{CONTROLLER\_HOME\}/sbin**

4.  执行以下命令启用通信加密：

    **./enableRPCEncrypt.sh -t**

    执行**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**，查看主管理节点Controller的“ResHAStatus”是否为“Normal”，并可以重新登录FusionInsight Manager表示更改成功。

5.  如果需要关闭加密模式，执行以下命令：

    **./enableRPCEncrypt.sh -f**

    执行**sh $\{BIGDATA\_HOME\}/om-server/om/sbin/status-oms.sh**，查看主管理节点Controller的“ResHAStatus”是否为“Normal”，并可以重新登录FusionInsight Manager表示更改成功。


