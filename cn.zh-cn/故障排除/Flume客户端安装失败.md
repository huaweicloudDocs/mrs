# Flume客户端安装失败<a name="mrs_03_0053"></a>

## 问题现象<a name="zh-cn_topic_0167275049_sd64242caa665405798481482f49ab0ee"></a>

安装Flume客户端失败，提示JAVA\_HOME is null或flume has been installed。

```
CST 2016-08-31 17:02:51 [flume-client install]: JAVA_HOME is null in current user,please install the JDK and set the JAVA_HOME
CST 2016-08-31 17:02:51 [flume-client install]: check environment failed.
CST 2016-08-31 17:02:51 [flume-client install]: check param failed.
CST 2016-08-31 17:02:51 [flume-client install]: install flume client failed.
```

```
CST 2016-08-31 17:03:58 [flume-client install]: flume has been installed
CST 2016-08-31 17:03:58 [flume-client install]: check path failed.
CST 2016-08-31 17:03:58 [flume-client install]: check param failed.
CST 2016-08-31 17:03:58 [flume-client install]: install flume client failed.
```

## 原因分析<a name="zh-cn_topic_0167275049_s4871ca6d7a6b47b1a0f8266b84631f32"></a>

-   Flume客户端安装时会检查环境变量，如果没有可用的JAVA，会报JAVA\_HOME is null错误并且退出安装。
-   如果指定的目录下已经安装有flume，客户端安装时会报flume has been installed并退出安装。

## 解决办法<a name="zh-cn_topic_0167275049_section4599086017025"></a>

1.  如果报JAVA\_HOME is null错误，需要使用命令：

    **export JAVA\_HOME=**_java路径_

    设置JAVA\_HOME，重新运行安装脚本。

2.  如果指定的目录下已经安装有Flume客户端，需要先卸载已经存在的Flume客户端，或指定其他目录安装。

