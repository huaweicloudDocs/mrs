# 通过beeline创建UDF时候报错<a name="ZH-CN_TOPIC_0207461485"></a>

## 问题现象<a name="zh-cn_topic_0167276125_s97a4fd8fa6a04bc5b12606588b5827f6"></a>

执行命令：

**create function fn\_test3 as 'test.MyUDF' using jar 'hdfs:///tmp/udf2/MyUDF.jar'**

报以下错误：

```
Error: Error while compiling statement: FAILED: HiveAccessControlException Permission denied: Principal [name=admin, type=USER] does not have following privileges for operation CREATEFUNCTION [[ADMIN PRIVILEGE] on Object [type=DATABASE, name=default], [ADMIN PRIVILEGE] on Object [type=FUNCTION, name=default.fn_test3]] (state=42000,code=40000)
```

## 原因分析<a name="zh-cn_topic_0167276125_section1645144113716"></a>

Hive中创建永久函数需要特殊的role admin。

## 解决方案<a name="zh-cn_topic_0167276125_s8b5967b905e74dcca053160b32a38b60"></a>

在执行语句前执行**set role admin命令**即可解决。

