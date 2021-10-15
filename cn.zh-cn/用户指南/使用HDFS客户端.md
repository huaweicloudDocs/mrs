# 使用HDFS客户端<a name="mrs_01_24188"></a>

## 操作场景<a name="zh-cn_topic_0265698398_se9608011680e423ca403d5207c374daa"></a>

该任务指导用户在运维场景或业务场景中使用HDFS客户端。

## 前提条件<a name="zh-cn_topic_0265698398_sa8a135a114cf4cbc8674242bd0cfebd7"></a>

-   已安装客户端。

    例如安装目录为“/opt/hadoopclient”，以下操作的客户端目录只是举例，请根据实际安装目录修改。

-   各组件业务用户由系统管理员根据业务需要创建。安全模式下，“机机”用户需要下载keytab文件。“人机”用户第一次登录时需修改密码。（普通模式不涉及）

## 使用HDFS客户端<a name="zh-cn_topic_0265698398_s729d2c48e7354c7bb15884e152e37570"></a>

1.  安装客户端。
    -   MRS 3.x之前版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0091.html)章节。
    -   MRS 3.x及之后版本请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。

2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  如果集群为安全模式，执行以下命令进行用户认证。普通模式集群无需执行用户认证。

    **kinit **_组件业务用户_

6.  直接执行HDFS Shell命令。例如：

    **hdfs dfs -ls /**


## HDFS客户端常用命令<a name="zh-cn_topic_0265698398_section1462718419"></a>

常用的HDFS客户端命令如下表所示。

更多命令可参考[https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/CommandsManual.html\#User\_Commands](https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/CommandsManual.html#User_Commands)

**表 1**  HDFS客户端常用命令

<a name="zh-cn_topic_0265698398_table122538012428"></a>
<table><thead align="left"><tr id="zh-cn_topic_0265698398_row142532012426"><th class="cellrowborder" valign="top" width="32.769999999999996%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0265698398_p122532016422"><a name="zh-cn_topic_0265698398_p122532016422"></a><a name="zh-cn_topic_0265698398_p122532016422"></a>命令</p>
</th>
<th class="cellrowborder" valign="top" width="22.53%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0265698398_p162532064218"><a name="zh-cn_topic_0265698398_p162532064218"></a><a name="zh-cn_topic_0265698398_p162532064218"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="44.7%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0265698398_p19381142414424"><a name="zh-cn_topic_0265698398_p19381142414424"></a><a name="zh-cn_topic_0265698398_p19381142414424"></a>样例</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0265698398_row825370154217"><td class="cellrowborder" valign="top" width="32.769999999999996%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0265698398_p73441050124515"><a name="zh-cn_topic_0265698398_p73441050124515"></a><a name="zh-cn_topic_0265698398_p73441050124515"></a><strong id="zh-cn_topic_0265698398_b251971517467"><a name="zh-cn_topic_0265698398_b251971517467"></a><a name="zh-cn_topic_0265698398_b251971517467"></a>hdfs dfs -mkdir</strong> <em id="zh-cn_topic_0265698398_i184614716503"><a name="zh-cn_topic_0265698398_i184614716503"></a><a name="zh-cn_topic_0265698398_i184614716503"></a>文件夹名称</em></p>
</td>
<td class="cellrowborder" valign="top" width="22.53%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0265698398_p14343750114520"><a name="zh-cn_topic_0265698398_p14343750114520"></a><a name="zh-cn_topic_0265698398_p14343750114520"></a>创建文件夹</p>
</td>
<td class="cellrowborder" valign="top" width="44.7%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0265698398_p10507828134610"><a name="zh-cn_topic_0265698398_p10507828134610"></a><a name="zh-cn_topic_0265698398_p10507828134610"></a><strong id="zh-cn_topic_0265698398_b1550710285462"><a name="zh-cn_topic_0265698398_b1550710285462"></a><a name="zh-cn_topic_0265698398_b1550710285462"></a>hdfs dfs -mkdir /tmp/mydir</strong></p>
</td>
</tr>
<tr id="zh-cn_topic_0265698398_row20253701428"><td class="cellrowborder" valign="top" width="32.769999999999996%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0265698398_p19253180204218"><a name="zh-cn_topic_0265698398_p19253180204218"></a><a name="zh-cn_topic_0265698398_p19253180204218"></a><strong id="zh-cn_topic_0265698398_b10296201617453"><a name="zh-cn_topic_0265698398_b10296201617453"></a><a name="zh-cn_topic_0265698398_b10296201617453"></a>hdfs dfs -ls</strong> <em id="zh-cn_topic_0265698398_i18303121395017"><a name="zh-cn_topic_0265698398_i18303121395017"></a><a name="zh-cn_topic_0265698398_i18303121395017"></a>文件夹名称</em></p>
</td>
<td class="cellrowborder" valign="top" width="22.53%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0265698398_p182538014216"><a name="zh-cn_topic_0265698398_p182538014216"></a><a name="zh-cn_topic_0265698398_p182538014216"></a>查看文件夹</p>
</td>
<td class="cellrowborder" valign="top" width="44.7%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0265698398_p118764654513"><a name="zh-cn_topic_0265698398_p118764654513"></a><a name="zh-cn_topic_0265698398_p118764654513"></a><strong id="zh-cn_topic_0265698398_b198744624515"><a name="zh-cn_topic_0265698398_b198744624515"></a><a name="zh-cn_topic_0265698398_b198744624515"></a>hdfs dfs -ls /tmp</strong></p>
</td>
</tr>
<tr id="zh-cn_topic_0265698398_row3253608426"><td class="cellrowborder" valign="top" width="32.769999999999996%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0265698398_p17651195517480"><a name="zh-cn_topic_0265698398_p17651195517480"></a><a name="zh-cn_topic_0265698398_p17651195517480"></a><strong id="zh-cn_topic_0265698398_b135271910154910"><a name="zh-cn_topic_0265698398_b135271910154910"></a><a name="zh-cn_topic_0265698398_b135271910154910"></a>hdfs dfs -put</strong> <em id="zh-cn_topic_0265698398_i1449832285017"><a name="zh-cn_topic_0265698398_i1449832285017"></a><a name="zh-cn_topic_0265698398_i1449832285017"></a>客户端节点上本地文件</em></p>
</td>
<td class="cellrowborder" valign="top" width="22.53%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0265698398_p166501855104816"><a name="zh-cn_topic_0265698398_p166501855104816"></a><a name="zh-cn_topic_0265698398_p166501855104816"></a>上传本地文件到HDFS指定路径</p>
</td>
<td class="cellrowborder" valign="top" width="44.7%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0265698398_p4381224154220"><a name="zh-cn_topic_0265698398_p4381224154220"></a><a name="zh-cn_topic_0265698398_p4381224154220"></a><strong id="zh-cn_topic_0265698398_b1235793518513"><a name="zh-cn_topic_0265698398_b1235793518513"></a><a name="zh-cn_topic_0265698398_b1235793518513"></a>hdfs dfs -put /opt/test.txt /tmp</strong></p>
<p id="zh-cn_topic_0265698398_p86791037195116"><a name="zh-cn_topic_0265698398_p86791037195116"></a><a name="zh-cn_topic_0265698398_p86791037195116"></a>上传客户端节点<span class="filepath" id="zh-cn_topic_0265698398_filepath0651255175220"><a name="zh-cn_topic_0265698398_filepath0651255175220"></a><a name="zh-cn_topic_0265698398_filepath0651255175220"></a>“/opt/tests.txt”</span>文件到HDFS的<span class="filepath" id="zh-cn_topic_0265698398_filepath883416112533"><a name="zh-cn_topic_0265698398_filepath883416112533"></a><a name="zh-cn_topic_0265698398_filepath883416112533"></a>“/tmp”</span>路径下</p>
</td>
</tr>
<tr id="zh-cn_topic_0265698398_row2025313010422"><td class="cellrowborder" valign="top" width="32.769999999999996%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0265698398_p112541001425"><a name="zh-cn_topic_0265698398_p112541001425"></a><a name="zh-cn_topic_0265698398_p112541001425"></a><strong id="zh-cn_topic_0265698398_b12856934135312"><a name="zh-cn_topic_0265698398_b12856934135312"></a><a name="zh-cn_topic_0265698398_b12856934135312"></a>hdfs dfs -get</strong> <em id="zh-cn_topic_0265698398_i1234994885018"><a name="zh-cn_topic_0265698398_i1234994885018"></a><a name="zh-cn_topic_0265698398_i1234994885018"></a>hdfs指定文件 </em><em id="zh-cn_topic_0265698398_i3152356175316"><a name="zh-cn_topic_0265698398_i3152356175316"></a><a name="zh-cn_topic_0265698398_i3152356175316"></a>客户端节点上</em><em id="zh-cn_topic_0265698398_i2688113832918"><a name="zh-cn_topic_0265698398_i2688113832918"></a><a name="zh-cn_topic_0265698398_i2688113832918"></a>指定路径</em></p>
</td>
<td class="cellrowborder" valign="top" width="22.53%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0265698398_p22541020427"><a name="zh-cn_topic_0265698398_p22541020427"></a><a name="zh-cn_topic_0265698398_p22541020427"></a>下载HDFS文件到本地指定路径</p>
</td>
<td class="cellrowborder" valign="top" width="44.7%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0265698398_p2381424154211"><a name="zh-cn_topic_0265698398_p2381424154211"></a><a name="zh-cn_topic_0265698398_p2381424154211"></a><strong id="zh-cn_topic_0265698398_b5974131017541"><a name="zh-cn_topic_0265698398_b5974131017541"></a><a name="zh-cn_topic_0265698398_b5974131017541"></a>hdfs dfs -get /tmp/test.txt /opt/</strong></p>
<p id="zh-cn_topic_0265698398_p74164123545"><a name="zh-cn_topic_0265698398_p74164123545"></a><a name="zh-cn_topic_0265698398_p74164123545"></a>下载HDFS的<span class="filepath" id="zh-cn_topic_0265698398_filepath1888121165511"><a name="zh-cn_topic_0265698398_filepath1888121165511"></a><a name="zh-cn_topic_0265698398_filepath1888121165511"></a>“/tmp/test.txt”</span>文件到客户端节点的<span class="filepath" id="zh-cn_topic_0265698398_filepath6997192318555"><a name="zh-cn_topic_0265698398_filepath6997192318555"></a><a name="zh-cn_topic_0265698398_filepath6997192318555"></a>“/opt”</span>路径下</p>
</td>
</tr>
<tr id="zh-cn_topic_0265698398_row225414054213"><td class="cellrowborder" valign="top" width="32.769999999999996%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0265698398_p7206115664812"><a name="zh-cn_topic_0265698398_p7206115664812"></a><a name="zh-cn_topic_0265698398_p7206115664812"></a><strong id="zh-cn_topic_0265698398_b157571485477"><a name="zh-cn_topic_0265698398_b157571485477"></a><a name="zh-cn_topic_0265698398_b157571485477"></a>hdfs dfs -rm -r -f </strong> <em id="zh-cn_topic_0265698398_i189891456361"><a name="zh-cn_topic_0265698398_i189891456361"></a><a name="zh-cn_topic_0265698398_i189891456361"></a>hdfs指定文件夹</em></p>
</td>
<td class="cellrowborder" valign="top" width="22.53%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0265698398_p120625694814"><a name="zh-cn_topic_0265698398_p120625694814"></a><a name="zh-cn_topic_0265698398_p120625694814"></a>删除文件夹</p>
</td>
<td class="cellrowborder" valign="top" width="44.7%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0265698398_p123811524114215"><a name="zh-cn_topic_0265698398_p123811524114215"></a><a name="zh-cn_topic_0265698398_p123811524114215"></a><strong id="zh-cn_topic_0265698398_b29910183718"><a name="zh-cn_topic_0265698398_b29910183718"></a><a name="zh-cn_topic_0265698398_b29910183718"></a>hdfs dfs -rm -r -f /tmp/mydir</strong></p>
<p id="zh-cn_topic_0265698398_p1943205452317"><a name="zh-cn_topic_0265698398_p1943205452317"></a><a name="zh-cn_topic_0265698398_p1943205452317"></a></p>
</td>
</tr>
</tbody>
</table>

## 客户端常见使用问题<a name="zh-cn_topic_0265698398_section29499362105048"></a>

1.  当执行HDFS客户端命令时，客户端程序异常退出，报“java.lang.OutOfMemoryError”的错误。

    这个问题是由于HDFS客户端运行时的所需的内存超过了HDFS客户端设置的内存上限（默认为128MB）。可以通过修改“_<客户端安装路径\>_/HDFS/component\_env”中的“CLIENT\_GC\_OPTS“来修改HDFS客户端的内存上限。例如，需要设置该内存上限为1GB，则设置：

    ```
    CLIENT_GC_OPTS="-Xmx1G"
    ```

    在修改完后，使用如下命令刷新客户端配置，使之生效：

    **source **<_客户端安装路径_\>/**bigdata\_env**

2.  如何设置HDFS客户端运行时的日志级别？

    HDFS客户端运行时的日志是默认输出到Console控制台的，其级别默认是INFO级别。有的时候为了定位问题，需要开启DEBUG级别日志，可以通过导出一个环境变量来设置，命令如下：

    **export HADOOP\_ROOT\_LOGGER=DEBUG,console**

    在执行完上面命令后，再执行HDFS Shell命令时，即可打印出DEBUG级别日志。

    如果想恢复INFO级别日志，可执行如下命令：

    **export HADOOP\_ROOT\_LOGGER=INFO,console**


