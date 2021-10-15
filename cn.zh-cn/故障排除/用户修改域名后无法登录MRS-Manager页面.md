# 用户修改域名后无法登录MRS Manager页面<a name="mrs_03_1165"></a>

## 问题现象<a name="section1082220378191"></a>

用户修改域名后，通过console页面无法登录MRS Manager页面，或者登录MRS Manager页面异常。

## 问题原因<a name="section18809125710192"></a>

用户修改域名后，没有刷新executor用户的keytab文件，导致executor进程认证失败后不断循环认证，导致了acs进程内存溢出。

## 解决方案<a name="section15390147132010"></a>

1.  重启acs进程。
    1.  使用root用户登录主管理节点（即MRS集群详情页面“节点管理”页签下实心五角星所在的Master节点）。
    2.  执行如下命令重启进程：

        **su - omm**

        **ps -ef|grep =acs**  （查找acs进程PID）

        **kill -9 **_**PID**_  （PID替换为实际的ID，结束acs进程）

    3.  等待几分钟后执行命令**ps -ef|grep =acs**查询进程是否已经自动启动。

2.  替换executor用户的keytab文件。
    1.  登录MRS Manager页面，选择“系统 \> 用户”，在executor用户所在的“操作”列，单击“下载认证凭据”，解压后获取keytab文件。
    2.  使用root用户登录主管理节点，将获取的keytab替换“/opt/executor/webapps/executor/WEB-INF/classes/user.keytab”文件。

3.  替换knox用户的keytab和conf文件。
    1.  登录MRS Manager页面，选择“系统 \> 用户”，在knox用户所在的“操作”列，单击“下载认证凭据”，解压后获取keytab和conf文件。
    2.  使用root用户登录主管理节点，将获取的keytab替换“/opt/knox/conf/user.keytab”文件。
    3.  修改/opt/knox/conf/krb5JAASLogin.conf中的principal的值，把域名修改为更改后的域名。
    4.  将获取的krb5.conf 替换“/opt/knox/conf/krb5.conf”文件。

4.  备份原有客户端目录

    **mv **_\{客户端目录\}_** /opt/client\_init**

5.  参考[更新客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0089.html)章节，重新安装客户端。
6.  使用root用户登录主备管理节点，执行如下命令，重启knox进程。

    **su - omm**

    **ps -ef | grep gateway | grep -v grep **（查找knox进程PID）

    **kill -9** _PID_（PID替换为实际的ID，结束knox进程）

    **/opt/knox/bin/restart-knox.sh **（启动knox进程）

7.  使用root用户登录主备管理节点，执行如下命令，重启executor进程。

    **su - omm**

    **netstat -anp |grep 8181 |grep LISTEN **（查找executor进程PID）

    **kill -9** _PID_（PID替换为实际的ID，结束executor进程）

    **/opt/executor/bin/startup.sh **（启动executor进程）


