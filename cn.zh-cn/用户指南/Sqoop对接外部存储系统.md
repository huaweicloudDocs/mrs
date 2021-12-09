# Sqoop对接外部存储系统<a name="mrs_01_24294"></a>

## sqoop export \(HDFS 到 MySQL\)<a name="section965720188362"></a>

1.  登录客户端所在节点。
2.  执行如下命令初始化环境变量。

    **source /opt/client/bigdata\_env**

3.  使用sqoop命令操作sqoop客户端。

    **sqoop export --connect jdbc:mysql://10.100.231.134:3306/test --username root --password xxxxxx --table component13 -export-dir  hdfs://hacluster/user/hive/warehouse/component\_test3 --fields-terminated-by ',' -m 1**

    **表 1**  参数说明

    <a name="zh-cn_topic_0265001068_table1935416343262"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0265001068_row63546345263"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0265001068_p10355193412269"><a name="zh-cn_topic_0265001068_p10355193412269"></a><a name="zh-cn_topic_0265001068_p10355193412269"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0265001068_p935514341262"><a name="zh-cn_topic_0265001068_p935514341262"></a><a name="zh-cn_topic_0265001068_p935514341262"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0265001068_row33551345265"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p13554346261"><a name="zh-cn_topic_0265001068_p13554346261"></a><a name="zh-cn_topic_0265001068_p13554346261"></a>-direct</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p235583482615"><a name="zh-cn_topic_0265001068_p235583482615"></a><a name="zh-cn_topic_0265001068_p235583482615"></a>快速模式，利用了数据库的导入工具，如MySQL的mysqlimport，可以比jdbc连接的方式更为高效的将数据导入到关系数据库中。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row435553402612"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p235510345260"><a name="zh-cn_topic_0265001068_p235510345260"></a><a name="zh-cn_topic_0265001068_p235510345260"></a>-export-dir &lt;dir&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p035512342267"><a name="zh-cn_topic_0265001068_p035512342267"></a><a name="zh-cn_topic_0265001068_p035512342267"></a>存放数据的HDFS的源目录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row764065102911"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p20640251295"><a name="zh-cn_topic_0265001068_p20640251295"></a><a name="zh-cn_topic_0265001068_p20640251295"></a>-m或-num-mappers &lt;n&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1364118582912"><a name="zh-cn_topic_0265001068_p1364118582912"></a><a name="zh-cn_topic_0265001068_p1364118582912"></a>启动n个map来并行导入数据，默认是4个，该值请勿高于集群的最大Map数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row483935202916"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p198391156297"><a name="zh-cn_topic_0265001068_p198391156297"></a><a name="zh-cn_topic_0265001068_p198391156297"></a>-table &lt;table-name&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1583915132915"><a name="zh-cn_topic_0265001068_p1583915132915"></a><a name="zh-cn_topic_0265001068_p1583915132915"></a>要导入的目的关系数据库表。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row83619615290"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p13361563297"><a name="zh-cn_topic_0265001068_p13361563297"></a><a name="zh-cn_topic_0265001068_p13361563297"></a>-update-key &lt;col-name&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p153612620294"><a name="zh-cn_topic_0265001068_p153612620294"></a><a name="zh-cn_topic_0265001068_p153612620294"></a>后面接条件列名，通过该参数可以将关系数据库中已经存在的数据进行更新操作，类似于关系数据库中的update操作。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row9925201310329"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1292501316321"><a name="zh-cn_topic_0265001068_p1292501316321"></a><a name="zh-cn_topic_0265001068_p1292501316321"></a>-update-mode &lt;mode&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p7925151310325"><a name="zh-cn_topic_0265001068_p7925151310325"></a><a name="zh-cn_topic_0265001068_p7925151310325"></a>更新模式，有两个值updateonly和默认的allowinsert，该参数只能在关系数据表里不存在要导入的记录时才能使用，比如要导入的hdfs中有一条id=1的记录，如果在表里已经有一条记录id=2，那么更新会失败。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1142121423214"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p20142161412328"><a name="zh-cn_topic_0265001068_p20142161412328"></a><a name="zh-cn_topic_0265001068_p20142161412328"></a>-input-null-string &lt;null-string&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p3142151417320"><a name="zh-cn_topic_0265001068_p3142151417320"></a><a name="zh-cn_topic_0265001068_p3142151417320"></a>可选参数，如果没有指定，则字符串null将被使用。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1753451418320"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1553481413214"><a name="zh-cn_topic_0265001068_p1553481413214"></a><a name="zh-cn_topic_0265001068_p1553481413214"></a>-input-null-non-string &lt;null-string&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1349161103316"><a name="zh-cn_topic_0265001068_p1349161103316"></a><a name="zh-cn_topic_0265001068_p1349161103316"></a>可选参数，如果没有指定，则字符串null将被使用。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row22072218339"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p62076213334"><a name="zh-cn_topic_0265001068_p62076213334"></a><a name="zh-cn_topic_0265001068_p62076213334"></a>-staging-table &lt;staging-table-name&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1425543111392"><a name="zh-cn_topic_0265001068_p1425543111392"></a><a name="zh-cn_topic_0265001068_p1425543111392"></a>创建一个与导入目标表同样数据结构的表，将所有数据先存放在该表中，然后由该表通过一次事务将结果写入到目标表中。</p>
    <p id="zh-cn_topic_0265001068_p14519132453513"><a name="zh-cn_topic_0265001068_p14519132453513"></a><a name="zh-cn_topic_0265001068_p14519132453513"></a>该参数是用来保证在数据导入关系数据库表的过程中的事务安全性，因为在导入的过程中可能会有多个事务，那么一个事务失败会影响到其它事务，比如导入的数据会出现错误或出现重复的记录等等情况，那么通过该参数可以避免这种情况。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row119891622173318"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p119894223336"><a name="zh-cn_topic_0265001068_p119894223336"></a><a name="zh-cn_topic_0265001068_p119894223336"></a>-clear-staging-table</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p298962233319"><a name="zh-cn_topic_0265001068_p298962233319"></a><a name="zh-cn_topic_0265001068_p298962233319"></a>如果该staging-table非空，则通过该参数可以在运行导入前清除staging-table里的数据。</p>
    </td>
    </tr>
    </tbody>
    </table>


## sqoop import（MySQL 到 Hive表）<a name="section181591913617"></a>

1.  登录客户端所在节点。
2.  执行如下命令初始化环境变量。

    **source /opt/client/bigdata\_env**

3.  使用sqoop命令操作sqoop客户端。

    **sqoop import --connect jdbc:mysql://10.100.231.134:3306/test --username root --password xxxxxx --table component  --hive-import --hive-table component\_test2  --delete-target-dir --fields-terminated-by "," -m 1 --as-textfile**

    **表 2**  参数说明

    <a name="zh-cn_topic_0265001068_table69791040193719"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0265001068_row1980040193716"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0265001068_p5980144017379"><a name="zh-cn_topic_0265001068_p5980144017379"></a><a name="zh-cn_topic_0265001068_p5980144017379"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="70%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0265001068_p3980154013720"><a name="zh-cn_topic_0265001068_p3980154013720"></a><a name="zh-cn_topic_0265001068_p3980154013720"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0265001068_row2980240113717"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p115245103719"><a name="zh-cn_topic_0265001068_p115245103719"></a><a name="zh-cn_topic_0265001068_p115245103719"></a>-append</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p162164511370"><a name="zh-cn_topic_0265001068_p162164511370"></a><a name="zh-cn_topic_0265001068_p162164511370"></a>将数据追加到hdfs中已经存在的dataset中。使用该参数，sqoop将把数据先导入到一个临时目录中，然后重新给文件命名到一个正式的目录中，以避免和该目录中已存在的文件重名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row17854184723710"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p28558479378"><a name="zh-cn_topic_0265001068_p28558479378"></a><a name="zh-cn_topic_0265001068_p28558479378"></a>-as-avrodatafile</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1285512472374"><a name="zh-cn_topic_0265001068_p1285512472374"></a><a name="zh-cn_topic_0265001068_p1285512472374"></a>将数据导入到一个Avro数据文件中。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1465104815379"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p965144816375"><a name="zh-cn_topic_0265001068_p965144816375"></a><a name="zh-cn_topic_0265001068_p965144816375"></a>-as-sequencefile</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1651748163715"><a name="zh-cn_topic_0265001068_p1651748163715"></a><a name="zh-cn_topic_0265001068_p1651748163715"></a>将数据导入到一个sequence文件中。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1926104817377"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p5261174883713"><a name="zh-cn_topic_0265001068_p5261174883713"></a><a name="zh-cn_topic_0265001068_p5261174883713"></a>-as-textfile</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p14261174863718"><a name="zh-cn_topic_0265001068_p14261174863718"></a><a name="zh-cn_topic_0265001068_p14261174863718"></a>将数据导入到一个普通文本文件中，生成该文本文件后，可以在hive中通过sql语句查询出结果。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row54531448193713"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p445310485374"><a name="zh-cn_topic_0265001068_p445310485374"></a><a name="zh-cn_topic_0265001068_p445310485374"></a>-boundary-query &lt;statement&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1787412258308"><a name="zh-cn_topic_0265001068_p1787412258308"></a><a name="zh-cn_topic_0265001068_p1787412258308"></a>边界查询，在导入前先通过SQL查询得到一个结果集，然后导入的数据就是该结果集内的数据，格式如：<strong id="zh-cn_topic_0265001068_b1887442523014"><a name="zh-cn_topic_0265001068_b1887442523014"></a><a name="zh-cn_topic_0265001068_b1887442523014"></a>-boundary-query  'select id,creationdate from person where id = 3'</strong>，表示导入的数据为id=3的记录，或者<strong id="zh-cn_topic_0265001068_b19874625103010"><a name="zh-cn_topic_0265001068_b19874625103010"></a><a name="zh-cn_topic_0265001068_b19874625103010"></a>select min(&lt;split-by&gt;), max(&lt;split-by&gt;) from &lt;table name&gt;</strong>。</p>
    <p id="zh-cn_topic_0265001068_p851112455405"><a name="zh-cn_topic_0265001068_p851112455405"></a><a name="zh-cn_topic_0265001068_p851112455405"></a>注意：查询的字段中不能有数据类型为字符串的字段，否则会报错：java.sql.SQLException: Invalid value for getLong()。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row2030893319405"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p4308173316407"><a name="zh-cn_topic_0265001068_p4308173316407"></a><a name="zh-cn_topic_0265001068_p4308173316407"></a>-columns&lt;col,col,col…&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1830813337408"><a name="zh-cn_topic_0265001068_p1830813337408"></a><a name="zh-cn_topic_0265001068_p1830813337408"></a>指定要导入的字段值，格式如：-columns id,username</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1495163314010"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1049573354014"><a name="zh-cn_topic_0265001068_p1049573354014"></a><a name="zh-cn_topic_0265001068_p1049573354014"></a>-direct</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p4495133144019"><a name="zh-cn_topic_0265001068_p4495133144019"></a><a name="zh-cn_topic_0265001068_p4495133144019"></a>快速模式，利用了数据库的导入工具，如MySQL的mysqlimport，可以比jdbc连接的方式更为高效的将数据导入到关系数据库中。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row969343354012"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p2693333124019"><a name="zh-cn_topic_0265001068_p2693333124019"></a><a name="zh-cn_topic_0265001068_p2693333124019"></a>-direct-split-size</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p13693113313406"><a name="zh-cn_topic_0265001068_p13693113313406"></a><a name="zh-cn_topic_0265001068_p13693113313406"></a>在使用上面direct直接导入的基础上，对导入的流按字节数分块，特别是使用直连模式从PostgreSQL导入数据时，可以将一个到达设定大小的文件分为几个独立的文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1188033394014"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p588083324019"><a name="zh-cn_topic_0265001068_p588083324019"></a><a name="zh-cn_topic_0265001068_p588083324019"></a>-inline-lob-limit</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p818317333419"><a name="zh-cn_topic_0265001068_p818317333419"></a><a name="zh-cn_topic_0265001068_p818317333419"></a>设定大对象数据类型的最大值。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row55323484012"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1153113417408"><a name="zh-cn_topic_0265001068_p1153113417408"></a><a name="zh-cn_topic_0265001068_p1153113417408"></a>-m或-num-mappers</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p65414317419"><a name="zh-cn_topic_0265001068_p65414317419"></a><a name="zh-cn_topic_0265001068_p65414317419"></a>启动n个map来并行导入数据，默认是4个，该值请勿高于集群的最大Map数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row92281434114011"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p18228103494017"><a name="zh-cn_topic_0265001068_p18228103494017"></a><a name="zh-cn_topic_0265001068_p18228103494017"></a>-query，-e&lt;statement&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p2615165853314"><a name="zh-cn_topic_0265001068_p2615165853314"></a><a name="zh-cn_topic_0265001068_p2615165853314"></a>从查询结果中导入数据，该参数使用时必须指定-target-dir、-hive-table，在查询语句中一定要有where条件且在where条件中需要包含$CONDITIONS。</p>
    <p id="zh-cn_topic_0265001068_p171631111428"><a name="zh-cn_topic_0265001068_p171631111428"></a><a name="zh-cn_topic_0265001068_p171631111428"></a>示例：-query 'select * from person where $CONDITIONS ' -target-dir /user/hive/warehouse/person -hive-table person</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row9695323428"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p156954254220"><a name="zh-cn_topic_0265001068_p156954254220"></a><a name="zh-cn_topic_0265001068_p156954254220"></a>-split-by&lt;column-name&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p11696622420"><a name="zh-cn_topic_0265001068_p11696622420"></a><a name="zh-cn_topic_0265001068_p11696622420"></a>表的列名，用来切分工作单元，一般后面跟主键ID。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row48921429421"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p78927274210"><a name="zh-cn_topic_0265001068_p78927274210"></a><a name="zh-cn_topic_0265001068_p78927274210"></a>-table &lt;table-name&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p11538925144217"><a name="zh-cn_topic_0265001068_p11538925144217"></a><a name="zh-cn_topic_0265001068_p11538925144217"></a>关系数据库表名，数据从该表中获取。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row198115314429"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p98253174214"><a name="zh-cn_topic_0265001068_p98253174214"></a><a name="zh-cn_topic_0265001068_p98253174214"></a>-target-dir &lt;dir&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p08216364215"><a name="zh-cn_topic_0265001068_p08216364215"></a><a name="zh-cn_topic_0265001068_p08216364215"></a>指定hdfs路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row102567344216"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1225612317423"><a name="zh-cn_topic_0265001068_p1225612317423"></a><a name="zh-cn_topic_0265001068_p1225612317423"></a>-warehouse-dir &lt;dir&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p1925623104212"><a name="zh-cn_topic_0265001068_p1925623104212"></a><a name="zh-cn_topic_0265001068_p1925623104212"></a>与<strong id="zh-cn_topic_0265001068_b119491256113516"><a name="zh-cn_topic_0265001068_b119491256113516"></a><a name="zh-cn_topic_0265001068_b119491256113516"></a>-target-dir</strong>不能同时使用，指定数据导入的存放目录，适用于导入hdfs，不适合导入hive目录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row154084364217"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1440814313426"><a name="zh-cn_topic_0265001068_p1440814313426"></a><a name="zh-cn_topic_0265001068_p1440814313426"></a>-where</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p61971518435"><a name="zh-cn_topic_0265001068_p61971518435"></a><a name="zh-cn_topic_0265001068_p61971518435"></a>从关系数据库导入数据时的查询条件，示例：-where 'id = 2'</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row29405142439"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p8940121416436"><a name="zh-cn_topic_0265001068_p8940121416436"></a><a name="zh-cn_topic_0265001068_p8940121416436"></a>-z,-compress</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p189405148437"><a name="zh-cn_topic_0265001068_p189405148437"></a><a name="zh-cn_topic_0265001068_p189405148437"></a>压缩参数，默认数据不压缩，通过该参数可以使用gzip压缩算法对数据进行压缩，适用于SequenceFile，text文本文件，和Avro文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row6171121518436"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p12171111544313"><a name="zh-cn_topic_0265001068_p12171111544313"></a><a name="zh-cn_topic_0265001068_p12171111544313"></a>–compression-codec</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p01714159438"><a name="zh-cn_topic_0265001068_p01714159438"></a><a name="zh-cn_topic_0265001068_p01714159438"></a>Hadoop压缩编码，默认为gzip。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row938818155432"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p6388171513431"><a name="zh-cn_topic_0265001068_p6388171513431"></a><a name="zh-cn_topic_0265001068_p6388171513431"></a>–null-string &lt;null-string&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p978615331812"><a name="zh-cn_topic_0265001068_p978615331812"></a><a name="zh-cn_topic_0265001068_p978615331812"></a>替换null字符串，如果没有指定，则字符串null将被使用。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row1062914408437"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1562944018439"><a name="zh-cn_topic_0265001068_p1562944018439"></a><a name="zh-cn_topic_0265001068_p1562944018439"></a>–null-non-string&lt;null-string&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p05571122921"><a name="zh-cn_topic_0265001068_p05571122921"></a><a name="zh-cn_topic_0265001068_p05571122921"></a>替换非String的null字符串，如果没有指定，则字符串null将被使用。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row263271034413"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1633131074411"><a name="zh-cn_topic_0265001068_p1633131074411"></a><a name="zh-cn_topic_0265001068_p1633131074411"></a>-check-column (col)</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p14633141019442"><a name="zh-cn_topic_0265001068_p14633141019442"></a><a name="zh-cn_topic_0265001068_p14633141019442"></a>增量导入参数，用来作为判断的列名，如id。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row168371910204411"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p1533542174115"><a name="zh-cn_topic_0265001068_p1533542174115"></a><a name="zh-cn_topic_0265001068_p1533542174115"></a>-incremental (mode) append</p>
    <p id="zh-cn_topic_0265001068_p8837510154413"><a name="zh-cn_topic_0265001068_p8837510154413"></a><a name="zh-cn_topic_0265001068_p8837510154413"></a>或lastmodified</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p37993124218"><a name="zh-cn_topic_0265001068_p37993124218"></a><a name="zh-cn_topic_0265001068_p37993124218"></a>增量导入参数。</p>
    <p id="zh-cn_topic_0265001068_p1685417545416"><a name="zh-cn_topic_0265001068_p1685417545416"></a><a name="zh-cn_topic_0265001068_p1685417545416"></a>append：追加，比如对大于last-value指定的值之后的记录进行追加导入。</p>
    <p id="zh-cn_topic_0265001068_p683741014416"><a name="zh-cn_topic_0265001068_p683741014416"></a><a name="zh-cn_topic_0265001068_p683741014416"></a>lastmodified：最后的修改时间，追加last-value指定的日期之后的记录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0265001068_row71091341194419"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0265001068_p18109641154414"><a name="zh-cn_topic_0265001068_p18109641154414"></a><a name="zh-cn_topic_0265001068_p18109641154414"></a>-last-value (value)</p>
    </td>
    <td class="cellrowborder" valign="top" width="70%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0265001068_p10982452164414"><a name="zh-cn_topic_0265001068_p10982452164414"></a><a name="zh-cn_topic_0265001068_p10982452164414"></a>增量导入参数，指定自从上次导入后列的最大值（大于该指定的值），也可以自己设定某一值。</p>
    </td>
    </tr>
    </tbody>
    </table>


## Sqoop使用样例<a name="section736118202362"></a>

-   sqoop import（MySQL到HDFS）

    **sqoop import --connect jdbc:mysql://10.100.231.134:3306/test --username root --password Qwerasdf@987 --query 'SELECT \* FROM component where $CONDITIONS and component\_id ="MRS 1.0\_002"'  --target-dir /tmp/component\_test --delete-target-dir --fields-terminated-by "," -m 1 --as-textfile**

-   sqoop export （obs到MySQL）

    **sqoop export --connect jdbc:mysql://10.100.231.134:3306/test --username root --password Qwerasdf@987  --table component14  -export-dir obs://obs-file-bucket/xx/part-m-00000 --fields-terminated-by ',' -m 1**

-   sqoop import（MySQL到obs）

    **sqoop import --connect jdbc:mysql://10.100.231.134:3306/test --username root --password Qwerasdf@987 --table component  --target-dir obs://obs-file-bucket/xx --delete-target-dir --fields-terminated-by "," -m 1 --as-textfile**

-   sqoop import（MySQL到Hive外obs表）

    **sqoop import --connect jdbc:mysql://10.100.231.134:3306/test --username root --password Qwerasdf@987 --table component  --hive-import --hive-table component\_test01 --fields-terminated-by "," -m 1 --as-textfile**


