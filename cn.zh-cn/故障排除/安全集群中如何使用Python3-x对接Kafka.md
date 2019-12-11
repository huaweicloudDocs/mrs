# 安全集群中如何使用Python3.x对接Kafka？<a name="ZH-CN_TOPIC_0168547249"></a>

## 用户问题<a name="section18305143583116"></a>

通过Python3.x环境如何对接开启Kerberos认证的Kafka集群？

## 问题现象<a name="section117424454313"></a>

客户想使用Python3.x的环境对接开启Kerberos认证的Kafka的集群，没有相关操作指导。

## 原因分析<a name="section1237061220324"></a>

MRS开发指南中没有Kafka组件在Python环境下的指导。

## 处理步骤<a name="section1296711131821"></a>

1.  登录Maste1节点，执行如下命令，配置华为云欧拉镜像源。

    **wget http://mirrors.myhuaweicloud.com/repo/mirrors\_source.sh && sh mirrors\_source.sh**

2.  执行如下命令，编译Python3.x。

    **yum groupinstall "Development tools" -y**

    **yum -y install zlib zlib-devel**

    **yum -y install bzip2 bzip2-devel**

    **yum -y install ncurses ncurses-devel**

    **yum -y install readline readline-devel**

    **yum -y install openssl openssl-devel**

    **yum -y install openssl-static**

    **yum -y install xz lzma xz-devel**

    **yum -y install sqlite sqlite-devel**

    **yum -y install gdbm gdbm-devel**

    **yum -y install tk tk-devel**

    **yum -y install libffi libffi-devel**

3.  编译成功后，执行如下命令，下载解压Python3.x的tgz包。

    **wget https://www.python.org/ftp/python/3.6.7/Python-3.6.7.tgz**

    **tar -zxvf Python-3.6.7.tgz**

    **cd Python-3.6.7**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Python3.x的tgz包也可以去Python官网下载。推荐使用Python-3.6.X版本，3.7版本无法使用rdd的take函数。  

4.  <a name="li14481457182514"></a>执行如下命令，设置Python3.x的配置信息及编译安装，安装到/opt/Bigdata/python3目录下。

    **./configure --prefix=/opt/Bigdata/python3 --enable-shared CFLAGS=-fPIC**

    **make && make install**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >安装的目录可以自定义。  

5.  执行如下命令，配置Python3.x变量。

    **echo "/opt/Bigdata/python3/lib" \>\> /etc/ld.so.conf**

    **ldconfig**

    **ln -s /opt/Bigdata/python3/bin/python3 /usr/bin/python3**

    **ln -s /opt/Bigdata/python3/bin/pip3 /usr/bin/pip3**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >配置变量的目录需要跟[4](#li14481457182514)中安装的目录保持一致。  

6.  配置成功后，执行如下命令，在Python3.x环境中安装kafka组件。

    **cp /usr/include/gssapi/\* /home/omm/kerberos/include/gssapi/**

    **pip3 install kafka-python**

    **pip3 install gssapi**

7.  安装成功后，执行**source /opt/client/bigdata\_env**命令，登录MRS客户端。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >登录kinit kafka用户的用户名和密码为登录MRS Manager的账号密码。  

8.  执行Python3.x脚本样例。

    脚本样例：

    ```
    producer：
    from kafka import KafkaProducer
    producer = KafkaProducer(bootstrap_servers=["broker_ip:21007"],
    security_protocol="SASL_PLAINTEXT",
    sasl_mechanism="GSSAPI",
    sasl_kerberos_service_name="kafka",
    sasl_kerberos_domain_name="hadoop.hadoop.com")
    for _ in range(100):
    response = producer.send("test-topic", b"testmessage")
    result = response.get(timeout=50)
    print(result)
    
    consumer：
    from kafka import KafkaConsumer
    consumer = KafkaConsumer("test-topic",
    bootstrap_servers=["broker_ip:21007"],
    group_id="test-group",
    enable_auto_commit="true",
    security_protocol="SASL_PLAINTEXT",
    sasl_mechanism="GSSAPI",
    sasl_kerberos_service_name="kafka",
    sasl_kerberos_domain_name="hadoop.hadoop.com")
    for message in consumer:
    print(message)
    ```


