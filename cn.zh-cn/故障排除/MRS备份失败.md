# MRS备份失败<a name="ZH-CN_TOPIC_0168547256"></a>

## 用户问题<a name="section18305143583116"></a>

MRS备份总是失败。

## 问题现象<a name="section117424454313"></a>

MRS备份总是失败。

## 原因分析<a name="section1237061220324"></a>

备份目录软链接到系统盘，系统盘满了之后备份便会失败。

## 处理步骤<a name="section2089094716116"></a>

1.  检查备份目录是否软链接到系统盘。
    1.  以root用户登录集群主备Master节点。
    2.  执行**df -h**命令查看磁盘情况，检查系统盘的存储情况。
    3.  执行  **ll /srv/BigData/LocalBackup**命令， 查看备份目录是否软连接到**/opt/Bigdata/LocalBackup**。

        检查备份文件是否软链接到系统盘且系统盘空间是否足够。如果软链接到系统盘且系统盘空间不足，请执行[步骤2](#li18234525101912)。如果否，说明不是由于系统盘空间不足导致，请联系技术服务。

2.  <a name="li18234525101912"></a>将历史备份数据移到数据盘的新目录中。
    1.  以root用户登录Master节点。
    2.  执行**su - omm**命令，切换到omm用户。
    3.  执行**rm -rf /srv/BigData/LocalBackup**命令，删除备份目录软连接。
    4.  执行**mkdir -p /srv/BigData/LocalBackup**命令，创建备份目录。
    5.  执行**mv  /opt/Bigdata/LocalBackup/\* /srv/BigData/LocalBackup/**命令，将历史备份数据移到新目录。


