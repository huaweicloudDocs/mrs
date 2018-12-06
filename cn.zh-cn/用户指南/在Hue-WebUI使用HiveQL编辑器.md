# 在Hue WebUI使用HiveQL编辑器<a name="ZH-CN_TOPIC_0050661079"></a>

## 操作场景<a name="zh-cn_topic_0050044337_section18334049192439"></a>

-   针对MRS 1.8.1之前的集群，MRS集群启用Kerberos认证后，用户需要使用图形化界面在集群中执行HiveQL语句时，可以通过Hue完成任务。
-   针对MRS 1.8.1及之后的集群，用户需要使用图形化界面在集群中执行HiveQL语句时，可以通过Hue完成任务。

## 前提条件<a name="zh-cn_topic_0050044337_section16114624192542"></a>

启用Kerberos认证时，MRS集群管理员已分配用户使用Hive的权限。具体请参见[创建用户](创建用户-安全.md)。

## 访问“Query Editors“<a name="section26788191145057"></a>

1.  访问Hue WebUI，然后选择“Query Editors  \>  Hive“进入“Hive“。

    “Hive“支持以下功能：

    -   执行和管理HiveQL语句。
    -   在“保存的查询”中查看当前访问用户已保存的HiveQL语句。
    -   在“查询历史”中查看当前访问用户执行过的HiveQL语句。

2.  单击![](figures/zh-cn_image_0058539874.jpg)可以显示Hive中所有的数据库。

## 执行HiveQL语句<a name="section5938223214523"></a>

1.  访问“Query Editors“。
2.  在“数据库“选择一个Hive中的数据库，默认数据库为“default“。

    系统将自动显示数据中的所有表。可以输入表名关键字，系统会自动搜索包含此关键字的全部表。

3.  单击指定的表名，可以显示表中所有的列。

    光标移动到表所在的行，单击![](figures/zh-cn_image_0056734373.jpg)  可以查看列的详细信息。

4.  在HiveQL语句编辑区输入查询语句。

    单击![](figures/zh-cn_image_0058539895.jpg)并选择“解释“，编辑器将分析输入的查询语句是否有语法错误以及执行计划，如果存在语法错误则显示“Error while compiling statement“。

5.  选择HiveQL语句执行的引擎。
    -   “mr“表示语句使用MapReduce计算框架执行语句。
    -   “spark“表示语句使用Spark计算框架执行语句。

6.  单击  ![](figures/zh-cn_image_0058539896.jpg)  开始执行HiveQL语句。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果希望下次继续使用已输入的HiveQL语句，请单击![](figures/zh-cn_image_0058539897.jpg)保存。  
    >-   格式化HiveQL语句，请单击![](figures/zh-cn_image_0058539898.jpg)选择“格式化“。  
    >-   删除已输入的HiveQL语句，请单击![](figures/zh-cn_image_0058539899.jpg)选择“清除“。  
    >-   清空已输入的语句并执行一个新的语句，请单击  ![](figures/zh-cn_image_0058539900.jpg)  选择“新查询“。  


## 查看执行结果<a name="section3491749914539"></a>

1.  在“Hive“的执行区，默认显示“查询历史“。
2.  单击结果查看已执行的语句。

## 管理查询语句<a name="section53760602145325"></a>

1.  访问“Query Editors“。
2.  单击“保存的查询“。

    单击一条已保存的语句，系统会自动将其填充至编辑区中。


## 修改在Hue使用“Query Editors“的会话配置<a name="section62596142145356"></a>

1.  在“Hive“页签，单击 ![](figures/zh-cn_image_0058541093.jpg)。
2.  在“文件“的右侧单击 ![](figures/zh-cn_image_0058541094.jpg)  ，然后单击 ![](figures/zh-cn_image_0058541095.jpg)  指定该文件的存储目录。

    可以单击  ![](figures/zh-cn_image_0058541096.jpg)  新增加一个文件资源。

3.  在“函数“的右侧单击 ![](figures/zh-cn_image_0058541097.jpg)  ，输入用户自定义的名称和函数的类名称。

    可以单击  ![](figures/zh-cn_image_0058541098.jpg)  新增加一个自定义函数。

4.  在“设置“的右侧单击 ![](figures/zh-cn_image_0058541099.jpg)  ，在“设置“的“键“输入Hive的参数名，在“值“输入对应的参数值，则当前Hive会话会以用户定义的配置连接Hive。

    可以单击  ![](figures/zh-cn_image_0058541100.jpg)  新增加一个参数。


