# 使用ClickHouse客户端<a name="mrs_01_24184"></a>

ClickHouse是面向联机分析处理的列式数据库，支持SQL查询，且查询性能好，特别是基于大宽表的聚合分析查询性能非常优异，比其他分析型数据库速度快一个数量级。

## 前提条件<a name="zh-cn_topic_0288563858_section19493164011271"></a>

已安装客户端，例如安装目录为“/opt/hadoopclient”。以下操作的客户端目录只是举例，请根据实际安装目录修改。在使用客户端前，需要先下载并更新客户端配置文件，确认Manager的主管理节点后才能使用客户端。

## 操作步骤<a name="zh-cn_topic_0288563858_section10873172642318"></a>

1.  安装客户端，具体请参考[安装客户端](https://support.huaweicloud.com/usermanual-mrs/mrs_01_0090.html)章节。
2.  以客户端安装用户，登录安装客户端的节点。
3.  执行以下命令，切换到客户端安装目录。

    **cd /opt/hadoopclient**

4.  执行以下命令配置环境变量。

    **source bigdata\_env**

5.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户，当前用户需要具有创建ClickHouse表的权限，具体请参见[ClickHouse用户及权限管理](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_24057.html)章节，为用户绑定对应角色。如果当前集群未启用Kerberos认证，则无需执行本步骤。

    **kinit **_组件业务用户_

    例如，**kinit **clickhouseuser。

6.  执行ClickHouse组件的客户端命令。

    执行**clickhouse -h**，查看ClickHouse组件命令帮助。

    回显信息如下：

    ```
    Use one of the following commands:
    clickhouse local [args] 
    clickhouse client [args] 
    clickhouse benchmark [args] 
    clickhouse server [args] 
    clickhouse performance-test [args] 
    clickhouse extract-from-config [args] 
    clickhouse compressor [args] 
    clickhouse format [args] 
    clickhouse copier [args] 
    clickhouse obfuscator [args]
    ...
    ```

    详细命令使用请参考：[https://clickhouse.tech/docs/zh/operations/](https://clickhouse.tech/docs/zh/operations/)。

    MRS 3.1.0及之后版本，使用**clickhouse client**命令连接ClickHouse服务端：

    -   例如，当前集群未启用Kerberos认证，使用ssl安全方式登录：

        **clickhouse client --host **_ClickHouse的实例IP _**--user **_用户名_** --password **_密码_** --port **9440  **--secure**

    -   例如，当前集群已启用Kerberos认证，使用ssl安全方式登录。

        Kerberos集群场景下没有默认用户，必须在Manager上创建用户，详细参考[ClickHouse用户及权限管理](https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_24057.html)。

        使用kinit认证成功后，客户端登录时可以不携带--user和--password参数，即使用kinit认证的用户登录。

        **clickhouse client --host **_ClickHouse的实例IP _** --port **9440  **--secure**

        相关参数使用说明如下表：

        **表 1**  clickhouse client命令行参数说明

        <a name="zh-cn_topic_0288563858_table119111511421"></a>
        <table><thead align="left"><tr id="zh-cn_topic_0288563858_row20911551726"><th class="cellrowborder" valign="top" width="17.4%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0288563858_p139119514212"><a name="zh-cn_topic_0288563858_p139119514212"></a><a name="zh-cn_topic_0288563858_p139119514212"></a>参数名</p>
        </th>
        <th class="cellrowborder" valign="top" width="82.6%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0288563858_p69113512213"><a name="zh-cn_topic_0288563858_p69113512213"></a><a name="zh-cn_topic_0288563858_p69113512213"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="zh-cn_topic_0288563858_row109120510213"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p149129515210"><a name="zh-cn_topic_0288563858_p149129515210"></a><a name="zh-cn_topic_0288563858_p149129515210"></a>--host</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p391265116215"><a name="zh-cn_topic_0288563858_p391265116215"></a><a name="zh-cn_topic_0288563858_p391265116215"></a>服务端的host名称，默认是localhost。您可以选择使用ClickHouse实例所在节点主机名或者IP地址。</p>
        <div class="note" id="zh-cn_topic_0288563858_note1375961741617"><a name="zh-cn_topic_0288563858_note1375961741617"></a><a name="zh-cn_topic_0288563858_note1375961741617"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0288563858_p8386192542315"><a name="zh-cn_topic_0288563858_p8386192542315"></a><a name="zh-cn_topic_0288563858_p8386192542315"></a>ClickHouse的实例IP地址可登录集群FusionInsight Manager，然后选择“集群 &gt;  服务 &gt; ClickHouse &gt; 实例”，获取ClickHouseServer实例对应的业务IP地址。</p>
        </div></div>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row16912115113219"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p6912135116212"><a name="zh-cn_topic_0288563858_p6912135116212"></a><a name="zh-cn_topic_0288563858_p6912135116212"></a>--port</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p14912155110214"><a name="zh-cn_topic_0288563858_p14912155110214"></a><a name="zh-cn_topic_0288563858_p14912155110214"></a>连接的端口。</p>
        <a name="zh-cn_topic_0288563858_ul591217510216"></a><a name="zh-cn_topic_0288563858_ul591217510216"></a><ul id="zh-cn_topic_0288563858_ul591217510216"><li>如果使用ssl安全连接则默认端口为9440，并且需要携带参数--secure。具体的端口值可通过ClickHouseServer实例配置搜索<span class="parmname" id="zh-cn_topic_0288563858_parmname11912155115216"><a name="zh-cn_topic_0288563858_parmname11912155115216"></a><a name="zh-cn_topic_0288563858_parmname11912155115216"></a>“tcp_port_secure”</span>参数获取。</li><li>如果使用非ssl安全连接则默认端口为9000，不需要携带参数--secure。具体的端口值可通过ClickHouseServer实例配置搜索<span class="parmname" id="zh-cn_topic_0288563858_parmname16912051521"><a name="zh-cn_topic_0288563858_parmname16912051521"></a><a name="zh-cn_topic_0288563858_parmname16912051521"></a>“tcp_port”</span>参数获取。</li></ul>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row69122514219"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p891210511522"><a name="zh-cn_topic_0288563858_p891210511522"></a><a name="zh-cn_topic_0288563858_p891210511522"></a>--user</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p209121751323"><a name="zh-cn_topic_0288563858_p209121751323"></a><a name="zh-cn_topic_0288563858_p209121751323"></a>用户名。</p>
        <p id="zh-cn_topic_0288563858_p119121251324"><a name="zh-cn_topic_0288563858_p119121251324"></a><a name="zh-cn_topic_0288563858_p119121251324"></a>可以在Manager上创建该用户名并绑定对应的角色权限，具体可以参考<span id="zh-cn_topic_0288563858_ph091211511925"><a name="zh-cn_topic_0288563858_ph091211511925"></a><a name="zh-cn_topic_0288563858_ph091211511925"></a><a href="https://support.huaweicloud.com/cmpntguide-mrs/mrs_01_24057.html" target="_blank" rel="noopener noreferrer">ClickHouse用户及权限管理</a><span id="zh-cn_topic_0288563858_ph491220517217"><a name="zh-cn_topic_0288563858_ph491220517217"></a><a name="zh-cn_topic_0288563858_ph491220517217"></a><span id="zh-cn_topic_0288563858_ph791318511827"><a name="zh-cn_topic_0288563858_ph791318511827"></a><a name="zh-cn_topic_0288563858_ph791318511827"></a></span></span></span>。</p>
        <a name="zh-cn_topic_0288563858_ul189139517212"></a><a name="zh-cn_topic_0288563858_ul189139517212"></a><ul id="zh-cn_topic_0288563858_ul189139517212"><li>如果当前集群已启用Kerberos认证，使用kinit认证成功后，客户端登录时可以不携带--user和--password参数，即使用kinit认证的用户登录。Kerberos集群场景下没有默认用户，必须在Manager上创建该用户名。</li><li>如果当前集群未启用Kerberos认证，客户端登录时可以指定Manager上创建的用户和密码。不携带用户和密码参数时则默认使用<strong id="zh-cn_topic_0288563858_b99131451126"><a name="zh-cn_topic_0288563858_b99131451126"></a><a name="zh-cn_topic_0288563858_b99131451126"></a>default</strong>用户登录。</li></ul>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row8913175113212"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p891375117214"><a name="zh-cn_topic_0288563858_p891375117214"></a><a name="zh-cn_topic_0288563858_p891375117214"></a>--password</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p16922351923"><a name="zh-cn_topic_0288563858_p16922351923"></a><a name="zh-cn_topic_0288563858_p16922351923"></a>密码。 默认值：空字符串。该参数和--user参数配套使用，可以在Manager上创建用户名时设置该密码。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1092265118219"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p119225512214"><a name="zh-cn_topic_0288563858_p119225512214"></a><a name="zh-cn_topic_0288563858_p119225512214"></a>--query</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p179223516217"><a name="zh-cn_topic_0288563858_p179223516217"></a><a name="zh-cn_topic_0288563858_p179223516217"></a>使用非交互模式查询。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1592217511225"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p19221551421"><a name="zh-cn_topic_0288563858_p19221551421"></a><a name="zh-cn_topic_0288563858_p19221551421"></a>--database</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p8922151827"><a name="zh-cn_topic_0288563858_p8922151827"></a><a name="zh-cn_topic_0288563858_p8922151827"></a>默认当前操作的数据库。默认值：服务端默认的配置（默认是default）。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row6922115116212"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p199224511022"><a name="zh-cn_topic_0288563858_p199224511022"></a><a name="zh-cn_topic_0288563858_p199224511022"></a>--multiline</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p1092220511625"><a name="zh-cn_topic_0288563858_p1092220511625"></a><a name="zh-cn_topic_0288563858_p1092220511625"></a>如果指定，允许多行语句查询（Enter仅代表换行，不代表查询语句完结）。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1992245115217"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p49236511726"><a name="zh-cn_topic_0288563858_p49236511726"></a><a name="zh-cn_topic_0288563858_p49236511726"></a>--multiquery</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p15923251226"><a name="zh-cn_topic_0288563858_p15923251226"></a><a name="zh-cn_topic_0288563858_p15923251226"></a>如果指定，允许处理用;号分隔的多个查询，只在非交互模式下生效。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1792314519216"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p1192320511621"><a name="zh-cn_topic_0288563858_p1192320511621"></a><a name="zh-cn_topic_0288563858_p1192320511621"></a>--format</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p1192314511221"><a name="zh-cn_topic_0288563858_p1192314511221"></a><a name="zh-cn_topic_0288563858_p1192314511221"></a>使用指定的默认格式输出结果。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row99236515210"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p392311512214"><a name="zh-cn_topic_0288563858_p392311512214"></a><a name="zh-cn_topic_0288563858_p392311512214"></a>--vertical</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p13923851528"><a name="zh-cn_topic_0288563858_p13923851528"></a><a name="zh-cn_topic_0288563858_p13923851528"></a>如果指定，默认情况下使用垂直格式输出结果。在这种格式中，每个值都在单独的行上打印，适用显示宽表的场景。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1923105118211"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p69239516220"><a name="zh-cn_topic_0288563858_p69239516220"></a><a name="zh-cn_topic_0288563858_p69239516220"></a>--time</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p14923251123"><a name="zh-cn_topic_0288563858_p14923251123"></a><a name="zh-cn_topic_0288563858_p14923251123"></a>如果指定，非交互模式下会打印查询执行的时间到stderr中。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row1292318515213"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p15923185117213"><a name="zh-cn_topic_0288563858_p15923185117213"></a><a name="zh-cn_topic_0288563858_p15923185117213"></a>--stacktrace</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p17923551123"><a name="zh-cn_topic_0288563858_p17923551123"></a><a name="zh-cn_topic_0288563858_p17923551123"></a>如果指定，如果出现异常，会打印堆栈跟踪信息。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row2923195117220"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p2923165115217"><a name="zh-cn_topic_0288563858_p2923165115217"></a><a name="zh-cn_topic_0288563858_p2923165115217"></a>--config-file</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p59231751824"><a name="zh-cn_topic_0288563858_p59231751824"></a><a name="zh-cn_topic_0288563858_p59231751824"></a>配置文件的名称。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row169231511325"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p1492312511129"><a name="zh-cn_topic_0288563858_p1492312511129"></a><a name="zh-cn_topic_0288563858_p1492312511129"></a>--secure</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p1892316518213"><a name="zh-cn_topic_0288563858_p1892316518213"></a><a name="zh-cn_topic_0288563858_p1892316518213"></a>如果指定，将通过ssl安全模式连接到服务器。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row129231511426"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p20923105119211"><a name="zh-cn_topic_0288563858_p20923105119211"></a><a name="zh-cn_topic_0288563858_p20923105119211"></a>--history_file</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p992319510214"><a name="zh-cn_topic_0288563858_p992319510214"></a><a name="zh-cn_topic_0288563858_p992319510214"></a>存放命令历史的文件的路径。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0288563858_row169231151920"><td class="cellrowborder" valign="top" width="17.4%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0288563858_p209231151825"><a name="zh-cn_topic_0288563858_p209231151825"></a><a name="zh-cn_topic_0288563858_p209231151825"></a>--param_&lt;name&gt;</p>
        </td>
        <td class="cellrowborder" valign="top" width="82.6%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0288563858_p292345113211"><a name="zh-cn_topic_0288563858_p292345113211"></a><a name="zh-cn_topic_0288563858_p292345113211"></a>带有参数的查询，并将值从客户端传递给服务器。具体用法详见<a href="https://clickhouse.tech/docs/zh/interfaces/cli/#cli-queries-with-parameters" target="_blank" rel="noopener noreferrer">https://clickhouse.tech/docs/zh/interfaces/cli/#cli-queries-with-parameters</a>。</p>
        </td>
        </tr>
        </tbody>
        </table>



