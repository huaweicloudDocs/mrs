# Knox进程占用内存高<a name="mrs_03_0267"></a>

## 用户问题<a name="section18305143583116"></a>

knox进程占用内存高

## 问题现象<a name="section117424454313"></a>

主Master节点内存使用率高，用**top -c**命令查看到占用内存较高的进程中有knox进程，且此进程占用内存超过4G。

## 原因分析<a name="section1237061220324"></a>

knox进程没有单独配置内存，进程会自动根据系统内存大小按照比例划分可用内存，导致knox占用内存大。

## 处理步骤<a name="section10553131817918"></a>

1.  以root用户分别登录Master节点。
2.  打开文件“/opt/knox/bin/gateway.sh“，查找APP\_MEM\_OPTS，并设置该参数的值为：“-Xms3072m -Xmx4096m“。
3.  登录Manager页面，单击“主机管理“，找到主Master节点的IP（即主机名称前带有实心五角星的节点），并登录该节点后台。
4.  执行如下命令重启进程。

    **su - omm**

    **sh /opt/knox/bin/restart-knox.sh**


