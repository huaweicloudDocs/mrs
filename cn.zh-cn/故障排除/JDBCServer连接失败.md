# JDBCServer连接失败<a name="mrs_03_0286"></a>

## 问题现象<a name="section117424454313"></a>

-   提示ha-cluster不识别（unknowHost或者必须加上端口）
-   提示连接JDBCServer失败

## 原因分析<a name="section1237061220324"></a>

-   问题1：使用**spark-beeline**命令连接JDBCServer，因为MRS\_3.0以前的JDBCServer是ha模式，因此需要使用特定的url和MRS spark的自带的jar包来连接JDBCServer。
-   问题2：确认JDBCServer服务是否正常，查看对应的端口是否正常监听。

## 处理步骤<a name="section16530919173311"></a>

-   问题1：需要使用特定的url和MRS Spark的自带的jar包来连接JDBCServer。
-   问题2：确认JDBCServer服务是否正常，查看对应的端口是否正常监听。

