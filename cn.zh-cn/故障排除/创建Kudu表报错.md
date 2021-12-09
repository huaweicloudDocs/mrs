# 创建Kudu表报错<a name="mrs_03_0316"></a>

## 用户问题<a name="section2029414539714"></a>

创建Kudu表报错。

## 问题现象<a name="section1999616579715"></a>

新建了集群，在创建表时，报错“\[Cloudera\]ImpalaJDBCDriver ERROR processing query/statement. Error Code: 0, SQL state: TStatus\(statusCode:ERROR\_STATUS, sqlState:HY000, errorMessage:AnalysisException: Table property 'kudu.master\_addresses' is required when the impalad startup flag -kudu\_master\_hosts is not used.”

## 原因分析<a name="section18356981781"></a>

客户未在impala sql中指定kudu.master\_addresses地址导致报错：Table property 'kudu.master\_addresses' is required when the impalad startup flag -kudu\_master\_hosts is not used.

## 处理步骤<a name="section1473916780"></a>

参考[使用Impala操作Kudu](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_24058.html)文档在创建Kudu表时指定“kudu.master\_addresses”地址。

