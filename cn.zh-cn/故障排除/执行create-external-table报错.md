# 执行create external table报错<a name="mrs_03_0163"></a>

## 问题现象<a name="zh-cn_topic_0167274372_s0ce3988f42514f54905b33982eba7684"></a>

执行命令：create external table xx\(xx int\) stored as textfile location '/tmp/aaa/aaa'，报以下错误：

```
Permission denied. Principal [name=fantasy, type=USER] does not have following privileges on Object [type=DFS_URI, name=/tmp/aaa/aaa] for operation CREATETABLE : [SELECT, INSERT, DELETE, OBJECT OWNERSHIP] (state=42000,code=40000)
```

## 原因分析<a name="zh-cn_topic_0167274372_section1645144113716"></a>

当前登录的用户不具备该目录或者其父目录的读写权限。创建外部表时，会判断当前用户对指定的目录以及该目录下其它目录和文件是否有读写权限，如果该目录不存在，会去判断其父目录，依次类推。如果一直不满足就会报权限不足。而不是报指定的目录不存在。

## 解决方案<a name="zh-cn_topic_0167274372_sa5dd6e2141ca471db7612d677f97ddfc"></a>

请确认当前用户为路径“/tmp/aaa/aaa”的owner有读写权限，如果该路径不存在，确认对其父路径有读写权限。

