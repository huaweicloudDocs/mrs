# TEXTFILE类型文件使用ARC4压缩时select结果乱码<a name="ZH-CN_TOPIC_0208559514"></a>

## 问题现象<a name="zh-cn_topic_0167276526_s4062da02d4d340ed9dbd38c42c5a7475"></a>

Hive查询结果表做压缩存储（ARC4），对结果表做select \* 查询时返回结果为乱码。

## 可能原因<a name="zh-cn_topic_0167276526_section917719411478"></a>

Hive默认压缩格式不是ARC4格式或者未开启输出压缩。

## 解决方案<a name="zh-cn_topic_0167276526_sf8f53c018c784bab9ca84e6d32b5d35d"></a>

1.  在select结果乱码时，在beeline中进行如下设置。

    **set mapreduce.output.fileoutputformat.compress.codec=org.apache.hadoop.io.encryption.arc4.ARC4BlockCodec;**

    **set hive.exec.compress.output=true;**

2.  使用块解压的方式先将表导入一个新表中。

    **insert overwrite table tbl\_result select \* from tbl\_source;**

3.  再进行查询。

    **select \* from tbl\_result;**


