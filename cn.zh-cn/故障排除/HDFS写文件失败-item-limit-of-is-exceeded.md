# HDFS写文件失败，item limit of / is exceeded<a name="ZH-CN_TOPIC_0181713166"></a>

## 问题背景与现象<a name="zh-cn_topic_0167276068_s17abfc85203d46d49c2198b46fbb9056"></a>

客户端或者上层组件日志报往HDFS的某目录写文件失败，报错为

The directory item limit of /tmp is exceeded: limit=5 items=5。

## 原因分析<a name="zh-cn_topic_0167276068_sb76c1129bcae439a966c320b8c7a25e1"></a>

1.  查看客户端或者NameNode运行日志“/var/log/Bigdata/hdfs/nn/hadoop-omm-namenode-XXX.log”存在异常提示The directory item limit of /tmp is exceeded:。该错误的含义为/tmp目录的文件数超过1048576的限制。

    ```
    2018-03-14 11:18:21,625 | WARN  | IPC Server handler 62 on 25000 | DIR* NameSystem.startFile: /tmp/test.txt The directory item limit of /tmp is exceeded: limit=1048576 items=1048577 | FSNamesystem.java:2334
    
    ```

2.  该限制是dfs.namenode.fs-limits.max-directory-items参数，定义单个目录下不含递归的最大目录数或者文件数，默认值1048576，取值范围1～6400000。

## 解决办法<a name="zh-cn_topic_0167276068_s710278da7b2445acb80cf9df277a3e3b"></a>

1.  确认该目录不含递归拥有100万以上文件目录是否正常，如果正常，可以将HDFS的参数dfs.namenode.fs-limits.max-directory-items调大并且重启HDFS NameNode生效。
2.  如果该目录下拥有100万文件不正常，需要清理不需要的文件。

