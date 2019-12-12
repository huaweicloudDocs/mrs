# Shell操作命令<a name="ZH-CN_TOPIC_0176876283"></a>

在使用Flink的Shell脚本前，首先需要执行以下操作：

1.  安装Flink客户端，例如安装目录为“/opt/client”。
2.  初始化环境变量。

    **source /opt/client/bigdata\_env**

3.  如果当前集群已启用Kerberos认证，执行以下命令认证当前用户。如果当前集群未启用Kerberos认证，则无需执行此命令。

    **kinit** _业务用户_

4.  参考表[表1](#table65101640171215)运行相关命令。

    **表 1**  Flink Shell命令参考

    <a name="table65101640171215"></a>
    <table><thead align="left"><tr id="row266514404129"><th class="cellrowborder" valign="top" width="19.01190119011901%" id="mcps1.2.4.1.1"><p id="p2149115918167"><a name="p2149115918167"></a><a name="p2149115918167"></a><strong id="b814975918160"><a name="b814975918160"></a><a name="b814975918160"></a>命令</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="47.65476547654765%" id="mcps1.2.4.1.2"><p id="p1149105911160"><a name="p1149105911160"></a><a name="p1149105911160"></a><strong id="b1414995961613"><a name="b1414995961613"></a><a name="b1414995961613"></a>参数说明</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p41492597169"><a name="p41492597169"></a><a name="p41492597169"></a><strong id="b7149359151616"><a name="b7149359151616"></a><a name="b7149359151616"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1666534011216"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p76657406128"><a name="p76657406128"></a><a name="p76657406128"></a>yarn-session.sh</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p866544013122"><a name="p866544013122"></a><a name="p866544013122"></a>必选</p>
    <p id="p1666114051213"><a name="p1666114051213"></a><a name="p1666114051213"></a>-n,--container &lt;arg&gt;：启动yarn集群所包含的taskmanager数。</p>
    <p id="p18666134031218"><a name="p18666134031218"></a><a name="p18666134031218"></a>可选</p>
    <p id="p196669401122"><a name="p196669401122"></a><a name="p196669401122"></a>-D &lt;arg&gt;：动态参数配置。</p>
    <p id="p156661540141215"><a name="p156661540141215"></a><a name="p156661540141215"></a>-d,--detached：关闭交互模式，启动一个分离的Flink YARN session。</p>
    <p id="p5666174051214"><a name="p5666174051214"></a><a name="p5666174051214"></a>-id,--applicationId &lt;arg&gt;：绑定到一个已经运行的Yarn session。</p>
    <p id="p4666124011215"><a name="p4666124011215"></a><a name="p4666124011215"></a>-j,--jar &lt;arg&gt;：设置用户jar包路径。</p>
    <p id="p1166624051218"><a name="p1166624051218"></a><a name="p1166624051218"></a>-jm,--jobManagerMemory &lt;arg&gt;：为JobManager设置内存。</p>
    <p id="p1366624081213"><a name="p1366624081213"></a><a name="p1366624081213"></a>-nm,--name &lt;arg&gt;：为Yarn application自定义名称。</p>
    <p id="p13666340171211"><a name="p13666340171211"></a><a name="p13666340171211"></a>-q,--query：查询可用的Yarn 资源。</p>
    <p id="p15666154041213"><a name="p15666154041213"></a><a name="p15666154041213"></a>-qu,--queue &lt;arg&gt;：指定YARN 队列。</p>
    <p id="p13666154016129"><a name="p13666154016129"></a><a name="p13666154016129"></a>-s,--slots &lt;arg&gt;：设置每个Taskmanager的SLOT个数。</p>
    <p id="p266618404129"><a name="p266618404129"></a><a name="p266618404129"></a>-t,--ship &lt;arg&gt;：指定待发送文件的目录。</p>
    <p id="p106661040151219"><a name="p106661040151219"></a><a name="p106661040151219"></a>-tm,--taskManagerMemory &lt;arg&gt;：为TaskManager设置内存。</p>
    <p id="p186668401122"><a name="p186668401122"></a><a name="p186668401122"></a>-z,--zookeeperNamespace &lt;args&gt;：指定zookeeper的namespace。-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1866634041219"><a name="p1866634041219"></a><a name="p1866634041219"></a>启动一个常驻的Flink集群，接受来自Flink客户端的任务。</p>
    </td>
    </tr>
    <tr id="row566634012127"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p17666174011213"><a name="p17666174011213"></a><a name="p17666174011213"></a>flink run</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p1166619405122"><a name="p1166619405122"></a><a name="p1166619405122"></a>-c,--class &lt;classname&gt;：指定一个类作为程序运行的入口点。</p>
    <p id="p116661540121211"><a name="p116661540121211"></a><a name="p116661540121211"></a>-C,--classpath &lt;url&gt;：指定classpath。</p>
    <p id="p466644016122"><a name="p466644016122"></a><a name="p466644016122"></a>-d,--detached：以分离方式运行job。</p>
    <p id="p466611406123"><a name="p466611406123"></a><a name="p466611406123"></a>-m,--jobmanager &lt;host:port&gt;：指定JobManager。</p>
    <p id="p9666040101211"><a name="p9666040101211"></a><a name="p9666040101211"></a>-p,--parallelism &lt;parallelism&gt;：指定job并行度，会覆盖配置文件中配置的并行度参数。</p>
    <p id="p1666617401121"><a name="p1666617401121"></a><a name="p1666617401121"></a>-q,--sysoutLogging：禁止flink日志输出至控制台。</p>
    <p id="p4666164041210"><a name="p4666164041210"></a><a name="p4666164041210"></a>-s,--fromSavepoint &lt;savepointPath&gt;：指定用于恢复job的savepoint路径。</p>
    <p id="p14666154051215"><a name="p14666154051215"></a><a name="p14666154051215"></a>-z,--zookeeperNamespace &lt;zookeeperNamespace&gt;：指定zookeeper的namespace。</p>
    <p id="p666624031220"><a name="p666624031220"></a><a name="p666624031220"></a>-yD &lt;arg&gt;：动态参数配置。</p>
    <p id="p36666403129"><a name="p36666403129"></a><a name="p36666403129"></a>-yd,--yarndetached：以分离模式启动。</p>
    <p id="p2666140151214"><a name="p2666140151214"></a><a name="p2666140151214"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定到yarn session运行job。</p>
    <p id="p11666134091215"><a name="p11666134091215"></a><a name="p11666134091215"></a>-yj,--yarnjar &lt;arg&gt;：设置Flink jar文件路径。</p>
    <p id="p12666240121218"><a name="p12666240121218"></a><a name="p12666240121218"></a>-yjm,--yarnjobManagerMemory &lt;arg&gt;：为JobManager设置内存（MB）。</p>
    <p id="p11666640161217"><a name="p11666640161217"></a><a name="p11666640161217"></a>-yn,--yarncontainer &lt;arg&gt;：指定集群启动所需container数量。</p>
    <p id="p0666134071220"><a name="p0666134071220"></a><a name="p0666134071220"></a>-ynm,--yarnname &lt;arg&gt;：为Yarn application自定义名称。</p>
    <p id="p166604012125"><a name="p166604012125"></a><a name="p166604012125"></a>-yq,--yarnquery：查询可用的YARN资源（内存、CPU）。</p>
    <p id="p26661240121211"><a name="p26661240121211"></a><a name="p26661240121211"></a>-yqu,--yarnqueue &lt;arg&gt;：指定YARN队列。</p>
    <p id="p86669405127"><a name="p86669405127"></a><a name="p86669405127"></a>-ys,--yarnslots：设置每个TaskManager的SLOT个数。</p>
    <p id="p26665407124"><a name="p26665407124"></a><a name="p26665407124"></a>-yt,--yarnship &lt;arg&gt;：指定待发送文件的路径。</p>
    <p id="p966624015128"><a name="p966624015128"></a><a name="p966624015128"></a>-ytm,--yarntaskManagerMemory &lt;arg&gt;：为TaskManager设置内存（MB）。</p>
    <p id="p7666154041216"><a name="p7666154041216"></a><a name="p7666154041216"></a>-yz,--yarnzookeeperNamespace &lt;arg&gt;：指定zookeeper的namespace，需与yarn-session.sh -z 保持一致。</p>
    <p id="p8666134011217"><a name="p8666134011217"></a><a name="p8666134011217"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p20666144013122"><a name="p20666144013122"></a><a name="p20666144013122"></a>Flink提交作业。</p>
    <p id="p6666164041220"><a name="p6666164041220"></a><a name="p6666164041220"></a>1."-y*"参数是指yarn-cluster模式下使用。</p>
    <p id="p866617403121"><a name="p866617403121"></a><a name="p866617403121"></a>2.非"-y*"参数用户在用该命令提交任务前需要先用yarn-session启动Flink集群。</p>
    </td>
    </tr>
    <tr id="row196662400129"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p146666406129"><a name="p146666406129"></a><a name="p146666406129"></a>flink info</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p166661040141215"><a name="p166661040141215"></a><a name="p166661040141215"></a>-c,--class &lt;classname&gt;：指定一个类作为程序运行的入口点。</p>
    <p id="p6666194051216"><a name="p6666194051216"></a><a name="p6666194051216"></a>-p,--parallelism &lt;parallelism&gt;：指定程序运行的并行度。</p>
    <p id="p1666540181218"><a name="p1666540181218"></a><a name="p1666540181218"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定至YARN session。</p>
    <p id="p1766615404129"><a name="p1766615404129"></a><a name="p1766615404129"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p15666940161210"><a name="p15666940161210"></a><a name="p15666940161210"></a>显示所运行程序的执行计划（JSON）</p>
    </td>
    </tr>
    <tr id="row1966620404121"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p26661440181210"><a name="p26661440181210"></a><a name="p26661440181210"></a>flink list</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p1666704016124"><a name="p1666704016124"></a><a name="p1666704016124"></a>-m,--jobmanager &lt;host:port&gt;：指定JobManager。</p>
    <p id="p1966716406124"><a name="p1966716406124"></a><a name="p1966716406124"></a>-r,--running：仅显示running状态的Job。</p>
    <p id="p1066718409128"><a name="p1066718409128"></a><a name="p1066718409128"></a>-s,--scheduled：仅显示scheduled状态的Job。</p>
    <p id="p7667104031218"><a name="p7667104031218"></a><a name="p7667104031218"></a>-z,--zookeeperNamespace &lt;zookeeperNamespace&gt;：指定zookeeper的namespace。</p>
    <p id="p8667840141220"><a name="p8667840141220"></a><a name="p8667840141220"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定YARN session。</p>
    <p id="p76671940201213"><a name="p76671940201213"></a><a name="p76671940201213"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p1066710408129"><a name="p1066710408129"></a><a name="p1066710408129"></a>查询集群中运行的程序。</p>
    </td>
    </tr>
    <tr id="row196671040171216"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p76674408126"><a name="p76674408126"></a><a name="p76674408126"></a>flink stop</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p206671040131217"><a name="p206671040131217"></a><a name="p206671040131217"></a>-m,--jobmanager &lt;host:port&gt;：指定JobManager。</p>
    <p id="p066724011128"><a name="p066724011128"></a><a name="p066724011128"></a>-z,--zookeeperNamespace &lt;zookeeperNamespace&gt;：指定zookeeper的namespace。</p>
    <p id="p366710405126"><a name="p366710405126"></a><a name="p366710405126"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定YARN session。</p>
    <p id="p1766713402129"><a name="p1766713402129"></a><a name="p1766713402129"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p6310236191215"><a name="p6310236191215"></a><a name="p6310236191215"></a>强制停止一个运行中的Job（仅支持streaming jobs、业务代码 source 端需要 implenments StoppableFunction）</p>
    </td>
    </tr>
    <tr id="row20667144020128"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p66671140171214"><a name="p66671140171214"></a><a name="p66671140171214"></a>flink cancel</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p176671640161210"><a name="p176671640161210"></a><a name="p176671640161210"></a>-m,--jobmanager &lt;host:port&gt;：指定JobManager。</p>
    <p id="p3667204017121"><a name="p3667204017121"></a><a name="p3667204017121"></a>-s,--withSavepoint &lt;targetDirectory&gt;：取消Job时触发savepoint，默认目录state.savepoints.dir</p>
    <p id="p14667040201212"><a name="p14667040201212"></a><a name="p14667040201212"></a>-z,--zookeeperNamespace &lt;zookeeperNamespace&gt;：指定zookeeper的namespace。</p>
    <p id="p466717409125"><a name="p466717409125"></a><a name="p466717409125"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定YARN session。</p>
    <p id="p266714019127"><a name="p266714019127"></a><a name="p266714019127"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p14667174010127"><a name="p14667174010127"></a><a name="p14667174010127"></a>取消一个运行中Job</p>
    </td>
    </tr>
    <tr id="row2667340161211"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p36673402126"><a name="p36673402126"></a><a name="p36673402126"></a>flink savepoint</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p1466719406125"><a name="p1466719406125"></a><a name="p1466719406125"></a>-d,--dispose &lt;arg&gt;：指定savepoint的保存目录。</p>
    <p id="p116677406121"><a name="p116677406121"></a><a name="p116677406121"></a>-m,--jobmanager &lt;host:port&gt;：指定JobManager。</p>
    <p id="p76673402128"><a name="p76673402128"></a><a name="p76673402128"></a>-z,--zookeeperNamespace &lt;zookeeperNamespace&gt;：指定zookeeper的namespace。</p>
    <p id="p206678404125"><a name="p206678404125"></a><a name="p206678404125"></a>-yid,--yarnapplicationId &lt;arg&gt;：绑定YARN session。</p>
    <p id="p1667114012124"><a name="p1667114012124"></a><a name="p1667114012124"></a>-h：获取帮助。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p26671340111212"><a name="p26671340111212"></a><a name="p26671340111212"></a>触发一个savepoint</p>
    </td>
    </tr>
    <tr id="row196671440191210"><td class="cellrowborder" valign="top" width="19.01190119011901%" headers="mcps1.2.4.1.1 "><p id="p1966894016124"><a name="p1966894016124"></a><a name="p1966894016124"></a><strong id="b666864041212"><a name="b666864041212"></a><a name="b666864041212"></a>source</strong><em id="i18668104081219"><a name="i18668104081219"></a><a name="i18668104081219"></a>客户端安装目录</em><strong id="b566844018122"><a name="b566844018122"></a><a name="b566844018122"></a>/bigdata_env</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="47.65476547654765%" headers="mcps1.2.4.1.2 "><p id="p19668124071210"><a name="p19668124071210"></a><a name="p19668124071210"></a>无</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p106686404129"><a name="p106686404129"></a><a name="p106686404129"></a>导入客户端环境变量。</p>
    <p id="p866810404126"><a name="p866810404126"></a><a name="p866810404126"></a>使用限制：如果用户使用自定义脚本（例如A.sh）并在脚本中调用该命令，则脚本A.sh不能传入参数。如果确实需要给A.sh传入参数，则需采用二次调用方式。</p>
    <p id="p15668840141212"><a name="p15668840141212"></a><a name="p15668840141212"></a>例如A.sh中调用B.sh，在B.sh中调用该命令。A.sh可以传入参数，B.sh不能传入参数。</p>
    </td>
    </tr>
    </tbody>
    </table>


