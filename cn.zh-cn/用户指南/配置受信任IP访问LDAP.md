# 配置受信任IP访问LDAP<a name="admin_guide_000274"></a>

## 操作场景<a name="sa6e92d3e96a449ceb538d27eb5a7209f"></a>

默认情况下，部署在OMS和集群中的LDAP服务允许任意IP访问。如果需要只允许受信任的IP地址访问LDAP服务，可以配置iptables过滤列表的INPUT策略。

## 对系统的影响<a name="sa494c29a5201459eb81d0c35196c86ea"></a>

配置受信任IP访问LDAP以后，未配置的IP无法访问LDAP。扩容前，新增加的IP需要配置为受信任的IP。

## 前提条件<a name="s054c83a4f74c4d36a38c0b5cf96a62ac"></a>

-   根据安装规划，收集集群内全部节点的管理平面IP、业务平面IP和所有浮动IP。
-   获取集群内节点的root用户和密码。

## 操作步骤<a name="saeab6358042e4f05986a84acf19d9630"></a>

**配置OMS LDAP信任的IP地址**

1.  确定管理节点IP地址，请参见[登录管理节点](登录管理节点.md)。
2.  登录FusionInsight Manager，请参见[登录管理系统](登录管理系统.md)。
3.  选择“系统  \>  OMS“，在“服务”选择“oldap  \>  修改配置“，查看OMS LDAP端口号，即“Ldap服务监听端口”参数值。默认为“21750”。
4.  以**root**用户通过主管理节点的IP地址登录主管理节点。
5.  <a name="li727167195016"></a>执行以下命令，查看iptables过滤列表中INPUT策略。

    **iptables -L**

    例如未配置任何规则时，INPUT策略显示如下：

    ```
    Chain INPUT (policy ACCEPT) 
    target     prot opt source               destination              
    ```

6.  执行以下命令，将集群使用的所有IP地址配置为受信任的IP。每个IP需要添加一次。

    **iptables -A INPUT -s **_受信任IP__地址 _**-p tcp --dport **_端口号 _**-j ACCEPT**

    例如，将10.0.0.1配置为受信任的IP，可以访问端口21750，执行：

    **iptables -A INPUT -s 10.0.0.1 -p tcp --dport 21750 -j ACCEPT**

7.  执行以下命令，将全部IP地址配置为不受信任的IP。已配置为信任IP不受此规则影响。

    **iptables -A INPUT -p tcp --dport **_端口号 _**-j DROP**

    例如，配置全部IP不能访问端口21750，执行：

    **iptables -A INPUT -p tcp --dport 21750 -j DROP**

8.  执行以下命令，查看iptables过滤列表中修改后INPUT策略。

    **iptables -L**

    例如配置一个受信任IP后，INPUT策略显示如下：

    ```
    Chain INPUT (policy ACCEPT) 
    target     prot opt source               destination          
    ACCEPT     tcp  --  10.0.0.1             anywhere            tcp dpt:21750 
    DROP       tcp  --  anywhere             anywhere            tcp dpt:21750     
    ```

9.  执行以下命令，查看iptables过滤列表中存在的规则及相对应的编号。

    **iptables -L -n --line-number**

    ```
    Chain INPUT (policy ACCEPT) 
    num target     prot opt source               destination          
    1   DROP       tcp  --  0.0.0.0/0            0.0.0.0/0           tcp dpt:21750     
    ```

10. <a name="li28581039195016"></a>根据实际需求，可执行以下命令，删除iptables过滤列表中的规则。

    **iptables -D INPUT **_待删除的编号_

    例如，删除编号为1的规则，执行：

    **iptables -D INPUT 1**

11. 以**root**用户通过备管理节点的IP地址登录备管理节点，并重复[5](#li727167195016)到[10](#li28581039195016)。

**配置集群LDAP信任的IP地址**

1.  登录FusionInsight Manager。
2.  选择“集群 \>  _待操作集群的名称_  \> 服务 \> LdapServer \> 实例”，查看LDAP服务对应的节点。
3.  切换到“配置”，查看集群LDAP端口号，即“LDAP\_SERVER\_PORT”参数值。默认为“21780”。
4.  以**root**用户通过LDAP服务的IP地址登录LDAP节点。
5.  <a name="li41253757195016"></a>执行以下命令，查看iptables过滤列表中INPUT策略。

    **iptables -L**

    例如未配置任何规则时，INPUT策略显示如下：

    ```
    Chain INPUT (policy ACCEPT) 
    target     prot opt source               destination              
    ```

6.  执行以下命令，将集群使用的所有IP地址配置为受信任的IP。每个IP需要添加一次。

    **iptables -A INPUT -s **_受信任IP__地址 _**-p tcp --dport **_端口号 _**-j ACCEPT**

    例如，将10.0.0.1配置为受信任的IP，可以访问端口21780，执行：

    **iptables -A INPUT -s 10.0.0.1 -p tcp --dport 21780 -j ACCEPT**

7.  执行以下命令，将全部IP地址配置为不受信任的IP。已配置为信任IP不受此规则影响。

    **iptables -A INPUT -p tcp --dport **_端口号 _**-j DROP**

    例如，配置全部IP不能访问端口21780，执行：

    **iptables -A INPUT -p tcp --dport 21780 -j DROP**

8.  执行以下命令，查看iptables过滤列表中修改后INPUT策略。

    **iptables -L**

    例如配置一个受信任IP后，INPUT策略显示如下：

    ```
    Chain INPUT (policy ACCEPT) 
    target     prot opt source               destination          
    ACCEPT     tcp  --  10.0.0.1             anywhere            tcp dpt:21780 
    DROP       tcp  --  anywhere             anywhere            tcp dpt:21780     
    ```

9.  执行以下命令，查看iptables过滤列表中存在的规则及相对应的编号。

    **iptables -L -n --line-number**

    ```
    Chain INPUT (policy ACCEPT) 
    num target     prot opt source               destination          
    1   DROP       tcp  --  0.0.0.0/0            0.0.0.0/0           tcp dpt:21780     
    ```

10. <a name="li48007687195016"></a>根据实际需求，可执行以下命令，删除iptables过滤列表中的规则。

    **iptables -D INPUT **_待删除的编号_

    例如，删除编号为1的规则，执行：

    **iptables -D INPUT 1**

11. 以**root**用户通过另一个LDAP服务的IP地址登录LDAP节点，并重复[16](#li41253757195016)到[21](#li48007687195016)。

