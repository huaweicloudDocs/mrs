# desc描述表过长时，无法显示完整<a name="ZH-CN_TOPIC_0205107313"></a>

## 问题现象<a name="zh-cn_topic_0167274514_section1861111131114"></a>

desc描述表过长时，如何让描述显示完整？

## 处理步骤<a name="zh-cn_topic_0167274514_safa41b7517804de18e601afe452f7453"></a>

1.  启动Hive的beeline时，设置参数maxWidth=20000即可，例如：

    ```
    [root@192-168-1-18 logs]# beeline --maxWidth=2000
    scan complete in 3ms
    Connecting to 
    ……
    Beeline version 1.1.0 by Apache Hive
    ```

2.  （可选）通过**beeline -help**命令查看关于客户端显示的设置。如下：

    ```
      -u <database url>             the JDBC URL to connect to
      -n <username>               the username to connect as
      -p <password>               the password to connect as
      -d <driver class>              the driver class to use
      -i <init file>                  script file for initialization
      -e <query>                  query that should be executed
      -f <exec file>                 script file that should be executed
      --hiveconf property=value       Use value for given property
      --color=[true/false]             control whether color is used for display
      --showHeader=[true/false]       show column names in query results
      --headerInterval=ROWS;         the interval between which heades are displayed
      --fastConnect=[true/false]       skip building table/column list for tab-completion
      --autoCommit=[true/false]       enable/disable automatic transaction commit
      --verbose=[true/false]           show verbose error messages and debug info
      --showWarnings=[true/false]     display connection warnings
      --showNestedErrs=[true/false]    display nested errors
      --numberFormat=[pattern]        format numbers using DecimalFormat pattern
      --force=[true/false]              continue running script even after errors
      --maxWidth=MAXWIDTH          the maximum width of the terminal
      --maxColumnWidth=MAXCOLWIDTH    the maximum width to use when displaying columns
      --silent=[true/false]           be more silent
      --autosave=[true/false]         automatically save preferences
      --outputformat=[table/vertical/csv2/tsv2/dsv/csv/tsv]  format mode for result display
                                       Note that csv, and tsv are deprecated - use csv2, tsv2 instead
      --truncateTable=[true/false]    truncate table column when it exceeds length
      --delimiterForDSV=DELIMITER     specify the delimiter for delimiter-separated values output format (default: |)
      --isolation=LEVEL               set the transaction isolation level
      --nullemptystring=[true/false]  set to true to get historic behavior of printing null as empty string
      --socketTimeOut=n               socket connection timeout interval, in second. The default value is 300.
    ```


