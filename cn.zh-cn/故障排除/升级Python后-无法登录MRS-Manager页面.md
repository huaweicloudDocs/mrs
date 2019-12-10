# 升级Python后，无法登录MRS Manager页面<a name="ZH-CN_TOPIC_0169515038"></a>

## 用户问题<a name="section18305143583116"></a>

升级Python后，登录不进去MRS Manager页面。

## 问题现象<a name="section117424454313"></a>

自行升级Python后，使用admin账号且密码正确的情况下登录不进去MRS Manager页面。

## 原因分析<a name="section1237061220324"></a>

用户升级Python版本到Python3.x的过程中，修改了openssl的文件目录权限，导致LdapServer服务无法正常启动，从而引起登录认证失败。

## 处理步骤<a name="section11955164018283"></a>

1.  以root用户登录集群的Master节点。
2.  执行**chmod 755 /usr/bin/openssl**命令，修改**/usr/bin/openssl**的文件目录权限为755。
3.  执行**su omm**命令，切换到omm用户。
4.  执行**openssl**命令，查看是否能够进入openssl模式。

    如果能够成功进入，则表示权限修改成功，如果不能进入，则表示权限未修改成功。

    如果权限未修改成功，请检查执行的命令是否正确，或者联系运维人员。

5.  权限修改成功后会重启LdapServer服务，请等待LdapServer服务重启成功后，重新登录MRS Manager。

## 建议与总结<a name="section8898183420"></a>

自行安装的软件建议和系统的分开，系统软件升级可能造成兼容性问题。

