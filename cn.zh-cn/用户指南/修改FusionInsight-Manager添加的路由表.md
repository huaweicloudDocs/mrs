# 修改FusionInsight Manager添加的路由表<a name="admin_guide_000183"></a>

## 操作场景<a name="zh-cn_topic_0263899515_scd1f9dafbfde48d79026ad3853fb0f36"></a>

安装FusionInsight Manager时系统会自动在主管理节点上创建2条路由信息，执行**ip rule list**可以查看，如下示例：

```
0:from all lookup local  
32764:from all to 10.10.100.100 lookup ntp_rt   #FusionInsight Manager创建的ntp路由信息（未配置外部NTP时钟源时无此信息） 
32765:from 192.168.0.117 lookup om_rt   #FusionInsight Manager创建的om路由信息 
32766:from all lookup main  
32767:from all lookup default
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>没有配置ntp外部服务器时只会有一条om路由信息“om\_rt“。

如果FusionInsight Manager创建的路由信息与企业网络规划配置的路由信息发生冲突时，管理员可以使用“autoroute.sh”工具禁用或启用Manager创建的路由信息。

## 对系统的影响<a name="zh-cn_topic_0263899515_s1a58f892b6084378b262ab32d1fb1050"></a>

禁用Manager创建的路由信息后，在设置新的路由信息之前，FusionInsight Manager页面无法登录，集群运行不受影响。

## 前提条件<a name="zh-cn_topic_0263899515_sc7134b15fa9647df922b450b894279ee"></a>

已经成功安装Manager。

## 禁用系统创建的路由信息<a name="zh-cn_topic_0263899515_sf4ac118287074ed5abd6263356492f2f"></a>

1.  以**omm**用户登录到主管理节点。执行以下命令，禁用系统创建的路由信息。

    **cd $\{BIGDATA\_HOME\}/om-server/om/sbin**

    **./autoroute.sh disable**

    ```
    Deactivating Route. 
    Route operation (disable) successful.
    ```

2.  执行以下命令，查看运行结果。如下例

    **ip rule list**

    ```
    0:from all lookup local  
    32766:from all lookup main  
    32767:from all lookup default
    ```

3.  执行以下命令，输入**root**用户密码，切换到**root**用户下。

    **su - root**

4.  分别执行以下命令，手动创建新的WS浮动IP路由信息。

    **ip route add **_WS__浮动IP__网段号/WS__浮动IP__子网掩码_** scope link src **_WS__浮动IP_** dev **_WS__浮动IP__对应网卡_** table om\_rt**

    **ip route add default via **_WS__浮动IP__网关_** dev **_WS__浮动IP__对应网卡_** table om\_rt**

    **ip rule add from **_WS__浮动IP_** table om\_rt**

    例如：

    **ip route add 192.168.0.0/255.255.255.0 scope link src 192.168.0.117 dev eth0:ws table om\_rt**

    **ip route add default via 192.168.0.254 dev eth0:ws table om\_rt**

    **ip rule add from 192.168.0.117 table om\_rt**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >当前网络的IP地址模式为IPv6时，应执行**ip -6 route add**命令。

5.  分别执行以下命令，手动创建新的ntp服务路由信息。未配置外部NTP时钟源时，跳过此步骤。

    **ip route add default via **_NtpIP__网关_** dev **_本机IP__对应网卡_** table ntp\_rt**

    **ip rule add to **_ntpIP_** table ntp\_rt**

    _本机IP__对应网卡_是指可与NTP服务器所在网段互通的网卡。

    例如：

    **ip route add default via 10.10.100.254 dev eth0 table ntp\_rt**

    **ip rule add to 10.10.100.100 table ntp\_rt**

6.  执行以下命令，查看运行结果。

    如下例，如产生路由表名为“om\_rt”和“ntp\_rt”的路由信息，则操作成功。

    **ip rule list**

    ```
    0:from all lookup local   
    32764:from all to 10.10.100.100 lookup ntp_rt  #未配置外部NTP时钟源时无此信息
    32765:from 192.168.0.117 lookup om_rt  
    32766:from all lookup main  
    32767:from all lookup default
    ```


## 启用系统创建的路由信息<a name="zh-cn_topic_0263899515_section1898175116193"></a>

1.  以**omm**用户登录到主管理节点。
2.  执行以下命令，启用系统创建的路由信息。

    **cd $\{BIGDATA\_HOME\}/om-server/om/sbin**

    **./autoroute.sh enable**

    ```
    Activating Route. 
    Route operation (enable) successful.
    ```

3.  执行以下命令，查看运行结果。

    如下例，如产生路由表名为“ntp\_rt”和“om\_rt”的两条路由信息，则操作成功。

    **ip rule list**

    ```
    0:from all lookup local  
    32764:from all to 10.10.100.100 lookup ntp_rt  #未配置外部NTP时钟源时无此信息
    32765:from 192.168.0.117 lookup om_rt  
    32766:from all lookup main  
    32767:from all lookup default
    ```


