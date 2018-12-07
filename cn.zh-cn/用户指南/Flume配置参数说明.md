# Flume配置参数说明<a name="ZH-CN_TOPIC_0069282321"></a>

## 基本介绍<a name="zh-cn_topic_0066459131_zh-cn_topic_0038340298_section35878706173614"></a>

使用Flume需要配置Source、Channel和Sink，各模块配置参数说明可通过本节内容了解。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分配置可能需要填写加密后的信息，请参见[使用Flume客户端加密工具](使用Flume客户端加密工具.md#ZH-CN_TOPIC_0069282320)。  

## 常用Source配置<a name="zh-cn_topic_0066459131_zh-cn_topic_0038340298_section53515518173747"></a>

-   **Avro Source**

    Avro Source监听Avro端口，接收外部Avro客户端数据并放入配置的Channel中。常用配置如[下表](#zh-cn_topic_0066459131_table47534913165858)所示：

    **表 1**  Avro Source常用配置

    <a name="zh-cn_topic_0066459131_table47534913165858"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row66371858165858"><th class="cellrowborder" valign="top" width="30.209999999999997%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p6548005165858"><a name="zh-cn_topic_0066459131_p6548005165858"></a><a name="zh-cn_topic_0066459131_p6548005165858"></a><strong id="zh-cn_topic_0066459131_b52923339165858"><a name="zh-cn_topic_0066459131_b52923339165858"></a><a name="zh-cn_topic_0066459131_b52923339165858"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p8766906165858"><a name="zh-cn_topic_0066459131_p8766906165858"></a><a name="zh-cn_topic_0066459131_p8766906165858"></a><strong id="zh-cn_topic_0066459131_b60626424165858"><a name="zh-cn_topic_0066459131_b60626424165858"></a><a name="zh-cn_topic_0066459131_b60626424165858"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="49.79%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p15732486165858"><a name="zh-cn_topic_0066459131_p15732486165858"></a><a name="zh-cn_topic_0066459131_p15732486165858"></a><strong id="zh-cn_topic_0066459131_b39030756165858"><a name="zh-cn_topic_0066459131_b39030756165858"></a><a name="zh-cn_topic_0066459131_b39030756165858"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row54950335165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p7411414165858"><a name="zh-cn_topic_0066459131_p7411414165858"></a><a name="zh-cn_topic_0066459131_p7411414165858"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p34212313165858"><a name="zh-cn_topic_0066459131_p34212313165858"></a><a name="zh-cn_topic_0066459131_p34212313165858"></a><strong id="zh-cn_topic_0066459131_b63453691165858"><a name="zh-cn_topic_0066459131_b63453691165858"></a><a name="zh-cn_topic_0066459131_b63453691165858"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p19734002165858"><a name="zh-cn_topic_0066459131_p19734002165858"></a><a name="zh-cn_topic_0066459131_p19734002165858"></a>与之相连的Channel，可以配置多个。<span id="zh-cn_topic_0066459131_ph27503069194341"><a name="zh-cn_topic_0066459131_ph27503069194341"></a><a name="zh-cn_topic_0066459131_ph27503069194341"></a>用空格隔开。</span></p>
    <p id="zh-cn_topic_0066459131_p938226317465"><a name="zh-cn_topic_0066459131_p938226317465"></a><a name="zh-cn_topic_0066459131_p938226317465"></a>在单个代理流程中，是通过channel连接sources和sinks。一个source实例对应多个channels，但一个sink实例只能对应一个channel。</p>
    <p id="zh-cn_topic_0066459131_p194537817528"><a name="zh-cn_topic_0066459131_p194537817528"></a><a name="zh-cn_topic_0066459131_p194537817528"></a>格式如下：</p>
    <p id="zh-cn_topic_0066459131_p15697904175225"><a name="zh-cn_topic_0066459131_p15697904175225"></a><a name="zh-cn_topic_0066459131_p15697904175225"></a><strong id="zh-cn_topic_0066459131_b45893098175748"><a name="zh-cn_topic_0066459131_b45893098175748"></a><a name="zh-cn_topic_0066459131_b45893098175748"></a>&lt;Agent &gt;.sources.&lt;Source&gt;.channels = &lt;channel1&gt; &lt;channel2&gt; &lt;channel3&gt;...</strong></p>
    <p id="zh-cn_topic_0066459131_p62153834175521"><a name="zh-cn_topic_0066459131_p62153834175521"></a><a name="zh-cn_topic_0066459131_p62153834175521"></a><strong id="zh-cn_topic_0066459131_b26353437175748"><a name="zh-cn_topic_0066459131_b26353437175748"></a><a name="zh-cn_topic_0066459131_b26353437175748"></a>&lt;Agent &gt;.sinks.&lt;Sink&gt;.channels = &lt;channel1&gt;</strong></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row60451203165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p24790973165858"><a name="zh-cn_topic_0066459131_p24790973165858"></a><a name="zh-cn_topic_0066459131_p24790973165858"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p61911796165858"><a name="zh-cn_topic_0066459131_p61911796165858"></a><a name="zh-cn_topic_0066459131_p61911796165858"></a>avro</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p48799571165858"><a name="zh-cn_topic_0066459131_p48799571165858"></a><a name="zh-cn_topic_0066459131_p48799571165858"></a>类型，需设置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue24215317141339"><a name="zh-cn_topic_0066459131_parmvalue24215317141339"></a><a name="zh-cn_topic_0066459131_parmvalue24215317141339"></a>“avro”</span>。<span id="zh-cn_topic_0066459131_ph1157815194516"><a name="zh-cn_topic_0066459131_ph1157815194516"></a><a name="zh-cn_topic_0066459131_ph1157815194516"></a>每一种source的类型都为相应的固定值。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row41600313165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p7189921165858"><a name="zh-cn_topic_0066459131_p7189921165858"></a><a name="zh-cn_topic_0066459131_p7189921165858"></a>bind</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p45512717165858"><a name="zh-cn_topic_0066459131_p45512717165858"></a><a name="zh-cn_topic_0066459131_p45512717165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p62651421165858"><a name="zh-cn_topic_0066459131_p62651421165858"></a><a name="zh-cn_topic_0066459131_p62651421165858"></a>绑定<span id="zh-cn_topic_0066459131_ph2081514419461"><a name="zh-cn_topic_0066459131_ph2081514419461"></a><a name="zh-cn_topic_0066459131_ph2081514419461"></a>和source</span>关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row61443009165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p38858504165858"><a name="zh-cn_topic_0066459131_p38858504165858"></a><a name="zh-cn_topic_0066459131_p38858504165858"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p60531106165858"><a name="zh-cn_topic_0066459131_p60531106165858"></a><a name="zh-cn_topic_0066459131_p60531106165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4072573165858"><a name="zh-cn_topic_0066459131_p4072573165858"></a><a name="zh-cn_topic_0066459131_p4072573165858"></a>绑定端口<span id="zh-cn_topic_0066459131_ph274785194617"><a name="zh-cn_topic_0066459131_ph274785194617"></a><a name="zh-cn_topic_0066459131_ph274785194617"></a>号</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row24435072165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p16116169165858"><a name="zh-cn_topic_0066459131_p16116169165858"></a><a name="zh-cn_topic_0066459131_p16116169165858"></a>ssl</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p30341308165858"><a name="zh-cn_topic_0066459131_p30341308165858"></a><a name="zh-cn_topic_0066459131_p30341308165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p43127071184626"><a name="zh-cn_topic_0066459131_p43127071184626"></a><a name="zh-cn_topic_0066459131_p43127071184626"></a>是否使用SSL加密。</p>
    <a name="zh-cn_topic_0066459131_ul10440892184632"></a><a name="zh-cn_topic_0066459131_ul10440892184632"></a><ul id="zh-cn_topic_0066459131_ul10440892184632"><li><span id="zh-cn_topic_0066459131_ph9409405184639"><a name="zh-cn_topic_0066459131_ph9409405184639"></a><a name="zh-cn_topic_0066459131_ph9409405184639"></a>true</span></li><li><span id="zh-cn_topic_0066459131_ph898969184636"><a name="zh-cn_topic_0066459131_ph898969184636"></a><a name="zh-cn_topic_0066459131_ph898969184636"></a>false</span></li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row26810406165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p18589059165858"><a name="zh-cn_topic_0066459131_p18589059165858"></a><a name="zh-cn_topic_0066459131_p18589059165858"></a>truststore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p29318825165858"><a name="zh-cn_topic_0066459131_p29318825165858"></a><a name="zh-cn_topic_0066459131_p29318825165858"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p26014631165858"><a name="zh-cn_topic_0066459131_p26014631165858"></a><a name="zh-cn_topic_0066459131_p26014631165858"></a>Java信任库类型。<span id="zh-cn_topic_0066459131_ph42131643184653"><a name="zh-cn_topic_0066459131_ph42131643184653"></a><a name="zh-cn_topic_0066459131_ph42131643184653"></a>填写JKS或其他java支持的truststore类型。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row49991787165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p39967070165858"><a name="zh-cn_topic_0066459131_p39967070165858"></a><a name="zh-cn_topic_0066459131_p39967070165858"></a>truststore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p16107200165858"><a name="zh-cn_topic_0066459131_p16107200165858"></a><a name="zh-cn_topic_0066459131_p16107200165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p29614839165858"><a name="zh-cn_topic_0066459131_p29614839165858"></a><a name="zh-cn_topic_0066459131_p29614839165858"></a>Java信任库文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row19008973165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p47272903165858"><a name="zh-cn_topic_0066459131_p47272903165858"></a><a name="zh-cn_topic_0066459131_p47272903165858"></a>truststore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3899936165858"><a name="zh-cn_topic_0066459131_p3899936165858"></a><a name="zh-cn_topic_0066459131_p3899936165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p47459434165858"><a name="zh-cn_topic_0066459131_p47459434165858"></a><a name="zh-cn_topic_0066459131_p47459434165858"></a>Java信任库密码。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row39437395165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p36863031165858"><a name="zh-cn_topic_0066459131_p36863031165858"></a><a name="zh-cn_topic_0066459131_p36863031165858"></a>keystore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p33115505165858"><a name="zh-cn_topic_0066459131_p33115505165858"></a><a name="zh-cn_topic_0066459131_p33115505165858"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p65110231165858"><a name="zh-cn_topic_0066459131_p65110231165858"></a><a name="zh-cn_topic_0066459131_p65110231165858"></a>密钥存储类型。<span id="zh-cn_topic_0066459131_ph65287091184731"><a name="zh-cn_topic_0066459131_ph65287091184731"></a><a name="zh-cn_topic_0066459131_ph65287091184731"></a>填写JKS或其他java支持的truststore类型。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row55191628165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p19392235165858"><a name="zh-cn_topic_0066459131_p19392235165858"></a><a name="zh-cn_topic_0066459131_p19392235165858"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p27267232165858"><a name="zh-cn_topic_0066459131_p27267232165858"></a><a name="zh-cn_topic_0066459131_p27267232165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p61162206165858"><a name="zh-cn_topic_0066459131_p61162206165858"></a><a name="zh-cn_topic_0066459131_p61162206165858"></a>密钥存储文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row16082959165858"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p26962604165858"><a name="zh-cn_topic_0066459131_p26962604165858"></a><a name="zh-cn_topic_0066459131_p26962604165858"></a>keystore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p36487334165858"><a name="zh-cn_topic_0066459131_p36487334165858"></a><a name="zh-cn_topic_0066459131_p36487334165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2684068165858"><a name="zh-cn_topic_0066459131_p2684068165858"></a><a name="zh-cn_topic_0066459131_p2684068165858"></a>密钥存储密码。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Spooling Source**

    Spooling Source监控并传输目录下新增的文件，可实现准实时数据传输。常用配置如[表 2 Spooling Source常用配置](#zh-cn_topic_0066459131_table4444705165858)所示：

    **表 2**  Spooling Source常用配置

    <a name="zh-cn_topic_0066459131_table4444705165858"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row59477353165858"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p56995381165858"><a name="zh-cn_topic_0066459131_p56995381165858"></a><a name="zh-cn_topic_0066459131_p56995381165858"></a><strong id="zh-cn_topic_0066459131_b65985143165858"><a name="zh-cn_topic_0066459131_b65985143165858"></a><a name="zh-cn_topic_0066459131_b65985143165858"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p9246390165858"><a name="zh-cn_topic_0066459131_p9246390165858"></a><a name="zh-cn_topic_0066459131_p9246390165858"></a><strong id="zh-cn_topic_0066459131_b53223159165858"><a name="zh-cn_topic_0066459131_b53223159165858"></a><a name="zh-cn_topic_0066459131_b53223159165858"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p29731945165858"><a name="zh-cn_topic_0066459131_p29731945165858"></a><a name="zh-cn_topic_0066459131_p29731945165858"></a><strong id="zh-cn_topic_0066459131_b10760089165858"><a name="zh-cn_topic_0066459131_b10760089165858"></a><a name="zh-cn_topic_0066459131_b10760089165858"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row65508580165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p52936269165858"><a name="zh-cn_topic_0066459131_p52936269165858"></a><a name="zh-cn_topic_0066459131_p52936269165858"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p59979390165858"><a name="zh-cn_topic_0066459131_p59979390165858"></a><a name="zh-cn_topic_0066459131_p59979390165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p26492387165858"><a name="zh-cn_topic_0066459131_p26492387165858"></a><a name="zh-cn_topic_0066459131_p26492387165858"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row64023627165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p52706315165858"><a name="zh-cn_topic_0066459131_p52706315165858"></a><a name="zh-cn_topic_0066459131_p52706315165858"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p41353155165858"><a name="zh-cn_topic_0066459131_p41353155165858"></a><a name="zh-cn_topic_0066459131_p41353155165858"></a>spooldir</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p61271243165858"><a name="zh-cn_topic_0066459131_p61271243165858"></a><a name="zh-cn_topic_0066459131_p61271243165858"></a>类型，需设置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue24904333141454"><a name="zh-cn_topic_0066459131_parmvalue24904333141454"></a><a name="zh-cn_topic_0066459131_parmvalue24904333141454"></a>“spooldir”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row45209134165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p39341736165858"><a name="zh-cn_topic_0066459131_p39341736165858"></a><a name="zh-cn_topic_0066459131_p39341736165858"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p32564048165858"><a name="zh-cn_topic_0066459131_p32564048165858"></a><a name="zh-cn_topic_0066459131_p32564048165858"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p20442245165858"><a name="zh-cn_topic_0066459131_p20442245165858"></a><a name="zh-cn_topic_0066459131_p20442245165858"></a>线程监控阈值，更新时间大于阈值时会重新启动该Source，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2076700165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4229026165858"><a name="zh-cn_topic_0066459131_p4229026165858"></a><a name="zh-cn_topic_0066459131_p4229026165858"></a>spoolDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p7006805165858"><a name="zh-cn_topic_0066459131_p7006805165858"></a><a name="zh-cn_topic_0066459131_p7006805165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p30680304165858"><a name="zh-cn_topic_0066459131_p30680304165858"></a><a name="zh-cn_topic_0066459131_p30680304165858"></a>监控目录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row10938284165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p18690304165858"><a name="zh-cn_topic_0066459131_p18690304165858"></a><a name="zh-cn_topic_0066459131_p18690304165858"></a>fileSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p37519623165858"><a name="zh-cn_topic_0066459131_p37519623165858"></a><a name="zh-cn_topic_0066459131_p37519623165858"></a>.COMPLETED</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p19190643165858"><a name="zh-cn_topic_0066459131_p19190643165858"></a><a name="zh-cn_topic_0066459131_p19190643165858"></a>文件传输完成后添加的后缀。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row9590333165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p31335697165858"><a name="zh-cn_topic_0066459131_p31335697165858"></a><a name="zh-cn_topic_0066459131_p31335697165858"></a>deletePolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p55163495165858"><a name="zh-cn_topic_0066459131_p55163495165858"></a><a name="zh-cn_topic_0066459131_p55163495165858"></a>never</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p39058110165858"><a name="zh-cn_topic_0066459131_p39058110165858"></a><a name="zh-cn_topic_0066459131_p39058110165858"></a>文件传输完成后源文件删除策略，支持<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue7366704141535"><a name="zh-cn_topic_0066459131_parmvalue7366704141535"></a><a name="zh-cn_topic_0066459131_parmvalue7366704141535"></a>“never”</span>或<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue50857170141537"><a name="zh-cn_topic_0066459131_parmvalue50857170141537"></a><a name="zh-cn_topic_0066459131_parmvalue50857170141537"></a>“immediate”</span>。<span id="zh-cn_topic_0066459131_ph60821681195338"><a name="zh-cn_topic_0066459131_ph60821681195338"></a><a name="zh-cn_topic_0066459131_ph60821681195338"></a>分别别是从不删除和立即删除。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row18538167165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p19204140165858"><a name="zh-cn_topic_0066459131_p19204140165858"></a><a name="zh-cn_topic_0066459131_p19204140165858"></a>ignorePattern</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p12031483165858"><a name="zh-cn_topic_0066459131_p12031483165858"></a><a name="zh-cn_topic_0066459131_p12031483165858"></a>^$</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p35026055165858"><a name="zh-cn_topic_0066459131_p35026055165858"></a><a name="zh-cn_topic_0066459131_p35026055165858"></a>忽略文件的正则表达式表示。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row26492231165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p32625776165858"><a name="zh-cn_topic_0066459131_p32625776165858"></a><a name="zh-cn_topic_0066459131_p32625776165858"></a>trackerDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p25442194165858"><a name="zh-cn_topic_0066459131_p25442194165858"></a><a name="zh-cn_topic_0066459131_p25442194165858"></a>.flumespool</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p47551820165858"><a name="zh-cn_topic_0066459131_p47551820165858"></a><a name="zh-cn_topic_0066459131_p47551820165858"></a>传输过程中元数据存储路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row55343398165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p37103492165858"><a name="zh-cn_topic_0066459131_p37103492165858"></a><a name="zh-cn_topic_0066459131_p37103492165858"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p52592899165858"><a name="zh-cn_topic_0066459131_p52592899165858"></a><a name="zh-cn_topic_0066459131_p52592899165858"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p32166422165858"><a name="zh-cn_topic_0066459131_p32166422165858"></a><a name="zh-cn_topic_0066459131_p32166422165858"></a>Source传输粒度。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row61374960165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p28328536165858"><a name="zh-cn_topic_0066459131_p28328536165858"></a><a name="zh-cn_topic_0066459131_p28328536165858"></a>decodeErrorPolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p12910061165858"><a name="zh-cn_topic_0066459131_p12910061165858"></a><a name="zh-cn_topic_0066459131_p12910061165858"></a>FAIL</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p39082035165858"><a name="zh-cn_topic_0066459131_p39082035165858"></a><a name="zh-cn_topic_0066459131_p39082035165858"></a>编码错误策略。</p>
    <p id="zh-cn_topic_0066459131_p65566343195917"><a name="zh-cn_topic_0066459131_p65566343195917"></a><a name="zh-cn_topic_0066459131_p65566343195917"></a>可选FAIL、REPLACE、IGNORE。</p>
    <p id="zh-cn_topic_0066459131_p53226180195917"><a name="zh-cn_topic_0066459131_p53226180195917"></a><a name="zh-cn_topic_0066459131_p53226180195917"></a>FAIL：抛出异常并让解析失败。</p>
    <p id="zh-cn_topic_0066459131_p9273576195917"><a name="zh-cn_topic_0066459131_p9273576195917"></a><a name="zh-cn_topic_0066459131_p9273576195917"></a>REPLACE：将不能识别的字符用其它字符代替，通常是字符U+FFFD。</p>
    <p id="zh-cn_topic_0066459131_p16353324195917"><a name="zh-cn_topic_0066459131_p16353324195917"></a><a name="zh-cn_topic_0066459131_p16353324195917"></a>IGNORE：直接丢弃不能解析的字符串。</p>
    <div class="note" id="zh-cn_topic_0066459131_note11528273165858"><a name="zh-cn_topic_0066459131_note11528273165858"></a><a name="zh-cn_topic_0066459131_note11528273165858"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0066459131_p16194000165858"><a name="zh-cn_topic_0066459131_p16194000165858"></a><a name="zh-cn_topic_0066459131_p16194000165858"></a>如果文件中有编码错误，请配置“decodeErrorPolicy”为“REPLACE”或“IGNORE”，Flume遇到编码错误将跳过编码错误，继续采集后续日志。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5283633165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p15503736165858"><a name="zh-cn_topic_0066459131_p15503736165858"></a><a name="zh-cn_topic_0066459131_p15503736165858"></a>deserializer</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p47843066165858"><a name="zh-cn_topic_0066459131_p47843066165858"></a><a name="zh-cn_topic_0066459131_p47843066165858"></a>LINE</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p50083153165858"><a name="zh-cn_topic_0066459131_p50083153165858"></a><a name="zh-cn_topic_0066459131_p50083153165858"></a>文件解析器，值为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue48095200165858"><a name="zh-cn_topic_0066459131_parmvalue48095200165858"></a><a name="zh-cn_topic_0066459131_parmvalue48095200165858"></a>“LINE”</span>或&nbsp;<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue30203621165858"><a name="zh-cn_topic_0066459131_parmvalue30203621165858"></a><a name="zh-cn_topic_0066459131_parmvalue30203621165858"></a>“BufferedLine”</span>。</p>
    <a name="zh-cn_topic_0066459131_ul9178779165858"></a><a name="zh-cn_topic_0066459131_ul9178779165858"></a><ul id="zh-cn_topic_0066459131_ul9178779165858"><li>配置为<span class="parmname" id="zh-cn_topic_0066459131_parmname30574237165858"><a name="zh-cn_topic_0066459131_parmname30574237165858"></a><a name="zh-cn_topic_0066459131_parmname30574237165858"></a>“LINE”</span>时，对从文件读取的字符逐个转码。</li><li>配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue60594146165858"><a name="zh-cn_topic_0066459131_parmvalue60594146165858"></a><a name="zh-cn_topic_0066459131_parmvalue60594146165858"></a>“BufferedLine”</span>时，对文件读取的一行或多行的字符进行批量转码，性能更优。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row101653165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p47552698165858"><a name="zh-cn_topic_0066459131_p47552698165858"></a><a name="zh-cn_topic_0066459131_p47552698165858"></a>deserializer.maxLineLength</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p26563301165858"><a name="zh-cn_topic_0066459131_p26563301165858"></a><a name="zh-cn_topic_0066459131_p26563301165858"></a>2048</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4143777165858"><a name="zh-cn_topic_0066459131_p4143777165858"></a><a name="zh-cn_topic_0066459131_p4143777165858"></a>按行解析最大长度。<span id="zh-cn_topic_0066459131_ph3445326520954"><a name="zh-cn_topic_0066459131_ph3445326520954"></a><a name="zh-cn_topic_0066459131_ph3445326520954"></a>0到 2,147,483,647。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3547782165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p914884165858"><a name="zh-cn_topic_0066459131_p914884165858"></a><a name="zh-cn_topic_0066459131_p914884165858"></a>deserializer.maxBatchLine</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p6996800165858"><a name="zh-cn_topic_0066459131_p6996800165858"></a><a name="zh-cn_topic_0066459131_p6996800165858"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p29869961165858"><a name="zh-cn_topic_0066459131_p29869961165858"></a><a name="zh-cn_topic_0066459131_p29869961165858"></a>按行解析最多行数，如果行数设置为多行，<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue25864894141636"><a name="zh-cn_topic_0066459131_parmvalue25864894141636"></a><a name="zh-cn_topic_0066459131_parmvalue25864894141636"></a>“maxLineLength”</span>也应该设置为相应的倍数。<span id="zh-cn_topic_0066459131_ph13521665201040"><a name="zh-cn_topic_0066459131_ph13521665201040"></a><a name="zh-cn_topic_0066459131_ph13521665201040"></a>例如maxBatchLine设置为2，</span><span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue21513046201040"><a name="zh-cn_topic_0066459131_parmvalue21513046201040"></a><a name="zh-cn_topic_0066459131_parmvalue21513046201040"></a>“maxLineLength”</span><span id="zh-cn_topic_0066459131_ph252765220117"><a name="zh-cn_topic_0066459131_ph252765220117"></a><a name="zh-cn_topic_0066459131_ph252765220117"></a>相应的设置为2048*2为4096。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row55856274165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p31930044165858"><a name="zh-cn_topic_0066459131_p31930044165858"></a><a name="zh-cn_topic_0066459131_p31930044165858"></a>selector.type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p36196771165858"><a name="zh-cn_topic_0066459131_p36196771165858"></a><a name="zh-cn_topic_0066459131_p36196771165858"></a>replicating</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p26104894185154"><a name="zh-cn_topic_0066459131_p26104894185154"></a><a name="zh-cn_topic_0066459131_p26104894185154"></a>选择器类型，支持<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue44409926185154"><a name="zh-cn_topic_0066459131_parmvalue44409926185154"></a><a name="zh-cn_topic_0066459131_parmvalue44409926185154"></a>“replicating”</span>或<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue64145014185154"><a name="zh-cn_topic_0066459131_parmvalue64145014185154"></a><a name="zh-cn_topic_0066459131_parmvalue64145014185154"></a>“multiplexing”</span>。</p>
    <a name="zh-cn_topic_0066459131_ul6400299118520"></a><a name="zh-cn_topic_0066459131_ul6400299118520"></a><ul id="zh-cn_topic_0066459131_ul6400299118520"><li><span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue4974761218521"><a name="zh-cn_topic_0066459131_parmvalue4974761218521"></a><a name="zh-cn_topic_0066459131_parmvalue4974761218521"></a>“replicating”</span><span id="zh-cn_topic_0066459131_ph4507532618521"><a name="zh-cn_topic_0066459131_ph4507532618521"></a><a name="zh-cn_topic_0066459131_ph4507532618521"></a>表示同样的内容会发给每一个channel。</span></li><li><span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue4884342118520"><a name="zh-cn_topic_0066459131_parmvalue4884342118520"></a><a name="zh-cn_topic_0066459131_parmvalue4884342118520"></a>“multiplexing”</span><span id="zh-cn_topic_0066459131_ph3693760518520"><a name="zh-cn_topic_0066459131_ph3693760518520"></a><a name="zh-cn_topic_0066459131_ph3693760518520"></a>表示根据分发规则，有选择地发给某些channel。</span></li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row53398608165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p32944424165858"><a name="zh-cn_topic_0066459131_p32944424165858"></a><a name="zh-cn_topic_0066459131_p32944424165858"></a>interceptors</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p51252676165858"><a name="zh-cn_topic_0066459131_p51252676165858"></a><a name="zh-cn_topic_0066459131_p51252676165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p57826052165858"><a name="zh-cn_topic_0066459131_p57826052165858"></a><a name="zh-cn_topic_0066459131_p57826052165858"></a>拦截器配置。<span id="zh-cn_topic_0066459131_ph14219645203313"><a name="zh-cn_topic_0066459131_ph14219645203313"></a><a name="zh-cn_topic_0066459131_ph14219645203313"></a>详细配置可参考</span><a href="https://flume.apache.org/FlumeUserGuide.html#flume-interceptors" target="_blank" rel="noopener noreferrer">flume官方文档</a><span id="zh-cn_topic_0066459131_ph60867944203313"><a name="zh-cn_topic_0066459131_ph60867944203313"></a><a name="zh-cn_topic_0066459131_ph60867944203313"></a>。</span></p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Spooling Source在按行读取过程中，会忽略掉每一个Event的最后一个换行符，该换行符所占用的数据量指标不会被Flume统计。  

-   **Kafka Source**

    Kafka Source从Kafka的topic中消费数据，可以设置多个Source消费同一个topic的数据，每个Source会消费topic的不同partitions。常用配置如[表 3 Kafka Source常用配置](#zh-cn_topic_0066459131_table66332718165858)所示：

    **表 3**  Kafka Source常用配置

    <a name="zh-cn_topic_0066459131_table66332718165858"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row2701445165858"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p6856167165858"><a name="zh-cn_topic_0066459131_p6856167165858"></a><a name="zh-cn_topic_0066459131_p6856167165858"></a><strong id="zh-cn_topic_0066459131_b15674877165858"><a name="zh-cn_topic_0066459131_b15674877165858"></a><a name="zh-cn_topic_0066459131_b15674877165858"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p32090104165858"><a name="zh-cn_topic_0066459131_p32090104165858"></a><a name="zh-cn_topic_0066459131_p32090104165858"></a><strong id="zh-cn_topic_0066459131_b18478648165858"><a name="zh-cn_topic_0066459131_b18478648165858"></a><a name="zh-cn_topic_0066459131_b18478648165858"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p39801566165858"><a name="zh-cn_topic_0066459131_p39801566165858"></a><a name="zh-cn_topic_0066459131_p39801566165858"></a><strong id="zh-cn_topic_0066459131_b49161638165858"><a name="zh-cn_topic_0066459131_b49161638165858"></a><a name="zh-cn_topic_0066459131_b49161638165858"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row30727146165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p17490455165858"><a name="zh-cn_topic_0066459131_p17490455165858"></a><a name="zh-cn_topic_0066459131_p17490455165858"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p7440766165858"><a name="zh-cn_topic_0066459131_p7440766165858"></a><a name="zh-cn_topic_0066459131_p7440766165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p65831202165858"><a name="zh-cn_topic_0066459131_p65831202165858"></a><a name="zh-cn_topic_0066459131_p65831202165858"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row17674776165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p8108863165858"><a name="zh-cn_topic_0066459131_p8108863165858"></a><a name="zh-cn_topic_0066459131_p8108863165858"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p52838201165858"><a name="zh-cn_topic_0066459131_p52838201165858"></a><a name="zh-cn_topic_0066459131_p52838201165858"></a>org.apache.flume.source.kafka.KafkaSource</p>
    <p id="zh-cn_topic_0066459131_p5781768165858"><a name="zh-cn_topic_0066459131_p5781768165858"></a><a name="zh-cn_topic_0066459131_p5781768165858"></a></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p65670062165858"><a name="zh-cn_topic_0066459131_p65670062165858"></a><a name="zh-cn_topic_0066459131_p65670062165858"></a>类型，需设置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue20881627141749"><a name="zh-cn_topic_0066459131_parmvalue20881627141749"></a><a name="zh-cn_topic_0066459131_parmvalue20881627141749"></a>“org.apache.flume.source.kafka.KafkaSource”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row65757327165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p24855258165858"><a name="zh-cn_topic_0066459131_p24855258165858"></a><a name="zh-cn_topic_0066459131_p24855258165858"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p10022165858"><a name="zh-cn_topic_0066459131_p10022165858"></a><a name="zh-cn_topic_0066459131_p10022165858"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p811818165858"><a name="zh-cn_topic_0066459131_p811818165858"></a><a name="zh-cn_topic_0066459131_p811818165858"></a>线程监控阈值，更新时间大于阈值时重新启动该Source，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row39640477165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p54945037165858"><a name="zh-cn_topic_0066459131_p54945037165858"></a><a name="zh-cn_topic_0066459131_p54945037165858"></a>nodatatime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p21363046165858"><a name="zh-cn_topic_0066459131_p21363046165858"></a><a name="zh-cn_topic_0066459131_p21363046165858"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p52685171165858"><a name="zh-cn_topic_0066459131_p52685171165858"></a><a name="zh-cn_topic_0066459131_p52685171165858"></a>告警阈值，从Kafka中订阅不到数据的时长大于阈值时发送告警，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row57749760165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p21219976165858"><a name="zh-cn_topic_0066459131_p21219976165858"></a><a name="zh-cn_topic_0066459131_p21219976165858"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p41096487165858"><a name="zh-cn_topic_0066459131_p41096487165858"></a><a name="zh-cn_topic_0066459131_p41096487165858"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p40481175165858"><a name="zh-cn_topic_0066459131_p40481175165858"></a><a name="zh-cn_topic_0066459131_p40481175165858"></a>每次写入Channel的Event数量。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row59984126165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p49985793165858"><a name="zh-cn_topic_0066459131_p49985793165858"></a><a name="zh-cn_topic_0066459131_p49985793165858"></a>batchDurationMillis</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p22317393165858"><a name="zh-cn_topic_0066459131_p22317393165858"></a><a name="zh-cn_topic_0066459131_p22317393165858"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p62878381165858"><a name="zh-cn_topic_0066459131_p62878381165858"></a><a name="zh-cn_topic_0066459131_p62878381165858"></a>每次消费topic数据的最大时长，单位：毫秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row15032872165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2986230165858"><a name="zh-cn_topic_0066459131_p2986230165858"></a><a name="zh-cn_topic_0066459131_p2986230165858"></a>keepTopicInHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p40558097165858"><a name="zh-cn_topic_0066459131_p40558097165858"></a><a name="zh-cn_topic_0066459131_p40558097165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p63980437165858"><a name="zh-cn_topic_0066459131_p63980437165858"></a><a name="zh-cn_topic_0066459131_p63980437165858"></a>是否在Event Header中保存topic，如果保存，Kafka Sink配置的topic将无效。</p>
    <a name="zh-cn_topic_0066459131_ul2024986318536"></a><a name="zh-cn_topic_0066459131_ul2024986318536"></a><ul id="zh-cn_topic_0066459131_ul2024986318536"><li>true</li><li>false</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row53367061165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1078128165858"><a name="zh-cn_topic_0066459131_p1078128165858"></a><a name="zh-cn_topic_0066459131_p1078128165858"></a>keepPartitionInHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p20219552165858"><a name="zh-cn_topic_0066459131_p20219552165858"></a><a name="zh-cn_topic_0066459131_p20219552165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p27170996165858"><a name="zh-cn_topic_0066459131_p27170996165858"></a><a name="zh-cn_topic_0066459131_p27170996165858"></a>是否在Event Header中保存partitionID，如果保存，Kafka Sink将写入对应的Partition。</p>
    <a name="zh-cn_topic_0066459131_ul19800981185321"></a><a name="zh-cn_topic_0066459131_ul19800981185321"></a><ul id="zh-cn_topic_0066459131_ul19800981185321"><li>true</li><li>false</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5283362165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p10541501165858"><a name="zh-cn_topic_0066459131_p10541501165858"></a><a name="zh-cn_topic_0066459131_p10541501165858"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p48555259165858"><a name="zh-cn_topic_0066459131_p48555259165858"></a><a name="zh-cn_topic_0066459131_p48555259165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p40661946165858"><a name="zh-cn_topic_0066459131_p40661946165858"></a><a name="zh-cn_topic_0066459131_p40661946165858"></a>brokers地址列表，多个地址用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row46916407165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p47550260165858"><a name="zh-cn_topic_0066459131_p47550260165858"></a><a name="zh-cn_topic_0066459131_p47550260165858"></a>kafka.consumer.group.id</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p26365867165858"><a name="zh-cn_topic_0066459131_p26365867165858"></a><a name="zh-cn_topic_0066459131_p26365867165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p55260511165858"><a name="zh-cn_topic_0066459131_p55260511165858"></a><a name="zh-cn_topic_0066459131_p55260511165858"></a>Kafka消费者组ID。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row30235524165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p19594484165858"><a name="zh-cn_topic_0066459131_p19594484165858"></a><a name="zh-cn_topic_0066459131_p19594484165858"></a>kafka.topics</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p43649406165858"><a name="zh-cn_topic_0066459131_p43649406165858"></a><a name="zh-cn_topic_0066459131_p43649406165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p45941025165858"><a name="zh-cn_topic_0066459131_p45941025165858"></a><a name="zh-cn_topic_0066459131_p45941025165858"></a>订阅的kafka topic列表，用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row66393406165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3684261165858"><a name="zh-cn_topic_0066459131_p3684261165858"></a><a name="zh-cn_topic_0066459131_p3684261165858"></a>kafka.topics.regex</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p29989707165858"><a name="zh-cn_topic_0066459131_p29989707165858"></a><a name="zh-cn_topic_0066459131_p29989707165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p13247239165858"><a name="zh-cn_topic_0066459131_p13247239165858"></a><a name="zh-cn_topic_0066459131_p13247239165858"></a>符合正则表达式的topic会被订阅，优先级高于“kafka.topics”，如果配置将覆盖“kafka.topics”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5354854165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p60669748165858"><a name="zh-cn_topic_0066459131_p60669748165858"></a><a name="zh-cn_topic_0066459131_p60669748165858"></a>kafka.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p15302578165858"><a name="zh-cn_topic_0066459131_p15302578165858"></a><a name="zh-cn_topic_0066459131_p15302578165858"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p31549280165858"><a name="zh-cn_topic_0066459131_p31549280165858"></a><a name="zh-cn_topic_0066459131_p31549280165858"></a>Kafka安全协议，未启用Kerberos集群中须配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue1584126214285"><a name="zh-cn_topic_0066459131_parmvalue1584126214285"></a><a name="zh-cn_topic_0066459131_parmvalue1584126214285"></a>“PLAINTEXT”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5062018165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p48193690165858"><a name="zh-cn_topic_0066459131_p48193690165858"></a><a name="zh-cn_topic_0066459131_p48193690165858"></a>Other Kafka Consumer Properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p11374808165858"><a name="zh-cn_topic_0066459131_p11374808165858"></a><a name="zh-cn_topic_0066459131_p11374808165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p48944259165858"><a name="zh-cn_topic_0066459131_p48944259165858"></a><a name="zh-cn_topic_0066459131_p48944259165858"></a>其他Kafka配置，可以接受任意Kafka支持的消费参数配置，配置需要加前缀<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue1668877142822"><a name="zh-cn_topic_0066459131_parmvalue1668877142822"></a><a name="zh-cn_topic_0066459131_parmvalue1668877142822"></a>“.kafka”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Taildir Source**

    Taildir Source监控目录下文件的变化并自动读取文件内容，可实现实时数据传输，常用配置如[下表](#zh-cn_topic_0066459131_table12090109165858)所示：

    **表 4**  Taildir Source常用配置

    <a name="zh-cn_topic_0066459131_table12090109165858"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row8415242165858"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p11034998165858"><a name="zh-cn_topic_0066459131_p11034998165858"></a><a name="zh-cn_topic_0066459131_p11034998165858"></a><strong id="zh-cn_topic_0066459131_b62088586142850"><a name="zh-cn_topic_0066459131_b62088586142850"></a><a name="zh-cn_topic_0066459131_b62088586142850"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p21419658165858"><a name="zh-cn_topic_0066459131_p21419658165858"></a><a name="zh-cn_topic_0066459131_p21419658165858"></a><strong id="zh-cn_topic_0066459131_b63119599142850"><a name="zh-cn_topic_0066459131_b63119599142850"></a><a name="zh-cn_topic_0066459131_b63119599142850"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p57270701165858"><a name="zh-cn_topic_0066459131_p57270701165858"></a><a name="zh-cn_topic_0066459131_p57270701165858"></a><strong id="zh-cn_topic_0066459131_b12413917142850"><a name="zh-cn_topic_0066459131_b12413917142850"></a><a name="zh-cn_topic_0066459131_b12413917142850"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row18096031165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p27805057165858"><a name="zh-cn_topic_0066459131_p27805057165858"></a><a name="zh-cn_topic_0066459131_p27805057165858"></a><span id="zh-cn_topic_0066459131_ph10545991165858"><a name="zh-cn_topic_0066459131_ph10545991165858"></a><a name="zh-cn_topic_0066459131_ph10545991165858"></a>channels</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3009922165858"><a name="zh-cn_topic_0066459131_p3009922165858"></a><a name="zh-cn_topic_0066459131_p3009922165858"></a><span id="zh-cn_topic_0066459131_ph37617138165858"><a name="zh-cn_topic_0066459131_ph37617138165858"></a><a name="zh-cn_topic_0066459131_ph37617138165858"></a>-</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p42477136165858"><a name="zh-cn_topic_0066459131_p42477136165858"></a><a name="zh-cn_topic_0066459131_p42477136165858"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row40163456165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p56492439165858"><a name="zh-cn_topic_0066459131_p56492439165858"></a><a name="zh-cn_topic_0066459131_p56492439165858"></a><span id="zh-cn_topic_0066459131_ph28646559165858"><a name="zh-cn_topic_0066459131_ph28646559165858"></a><a name="zh-cn_topic_0066459131_ph28646559165858"></a>type</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p12484831165858"><a name="zh-cn_topic_0066459131_p12484831165858"></a><a name="zh-cn_topic_0066459131_p12484831165858"></a>taildir</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4638367165858"><a name="zh-cn_topic_0066459131_p4638367165858"></a><a name="zh-cn_topic_0066459131_p4638367165858"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue5331992314304"><a name="zh-cn_topic_0066459131_parmvalue5331992314304"></a><a name="zh-cn_topic_0066459131_parmvalue5331992314304"></a>“taildir”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row34970280165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p25926788165858"><a name="zh-cn_topic_0066459131_p25926788165858"></a><a name="zh-cn_topic_0066459131_p25926788165858"></a>filegroups</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p19695097165858"><a name="zh-cn_topic_0066459131_p19695097165858"></a><a name="zh-cn_topic_0066459131_p19695097165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p51799010165858"><a name="zh-cn_topic_0066459131_p51799010165858"></a><a name="zh-cn_topic_0066459131_p51799010165858"></a>设置采集文件目录分组名字，分组名字中间使用空格间隔。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row35788116165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p46297065165858"><a name="zh-cn_topic_0066459131_p46297065165858"></a><a name="zh-cn_topic_0066459131_p46297065165858"></a>filegroups.&lt;filegroupName&gt;.parentDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p59074756165858"><a name="zh-cn_topic_0066459131_p59074756165858"></a><a name="zh-cn_topic_0066459131_p59074756165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p20325936165858"><a name="zh-cn_topic_0066459131_p20325936165858"></a><a name="zh-cn_topic_0066459131_p20325936165858"></a>父目录，需要配置为绝对路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row14961997165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p53657595165858"><a name="zh-cn_topic_0066459131_p53657595165858"></a><a name="zh-cn_topic_0066459131_p53657595165858"></a>filegroups.&lt;filegroupName&gt;.filePattern</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p51297959165858"><a name="zh-cn_topic_0066459131_p51297959165858"></a><a name="zh-cn_topic_0066459131_p51297959165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p61494048165858"><a name="zh-cn_topic_0066459131_p61494048165858"></a><a name="zh-cn_topic_0066459131_p61494048165858"></a>相对父目录的文件路径，可以包含目录，支持正则表达式，须与父目录联合使用。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row26190241165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p440251165858"><a name="zh-cn_topic_0066459131_p440251165858"></a><a name="zh-cn_topic_0066459131_p440251165858"></a>positionFile</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p35660370165858"><a name="zh-cn_topic_0066459131_p35660370165858"></a><a name="zh-cn_topic_0066459131_p35660370165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2808849165858"><a name="zh-cn_topic_0066459131_p2808849165858"></a><a name="zh-cn_topic_0066459131_p2808849165858"></a>传输过程中元数据存储路径</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row30913895165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p34385583165858"><a name="zh-cn_topic_0066459131_p34385583165858"></a><a name="zh-cn_topic_0066459131_p34385583165858"></a>headers.&lt;filegroupName&gt;.&lt;headerKey&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p33768827165858"><a name="zh-cn_topic_0066459131_p33768827165858"></a><a name="zh-cn_topic_0066459131_p33768827165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p50920427165858"><a name="zh-cn_topic_0066459131_p50920427165858"></a><a name="zh-cn_topic_0066459131_p50920427165858"></a>设置某一个分组采集数据时Event中的key-value值。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row50604927165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p9789606165858"><a name="zh-cn_topic_0066459131_p9789606165858"></a><a name="zh-cn_topic_0066459131_p9789606165858"></a>byteOffsetHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p54760608165858"><a name="zh-cn_topic_0066459131_p54760608165858"></a><a name="zh-cn_topic_0066459131_p54760608165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6424283165858"><a name="zh-cn_topic_0066459131_p6424283165858"></a><a name="zh-cn_topic_0066459131_p6424283165858"></a>是否在每一个Event头中携带该Event在源文件中的位置信息，该信息保存在<span class="parmname" id="zh-cn_topic_0066459131_parmname13735603144136"><a name="zh-cn_topic_0066459131_parmname13735603144136"></a><a name="zh-cn_topic_0066459131_parmname13735603144136"></a>“byteoffset”</span>变量中。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row56206414165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p52791159165858"><a name="zh-cn_topic_0066459131_p52791159165858"></a><a name="zh-cn_topic_0066459131_p52791159165858"></a>skipToEnd</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p48225482165858"><a name="zh-cn_topic_0066459131_p48225482165858"></a><a name="zh-cn_topic_0066459131_p48225482165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p13949978165858"><a name="zh-cn_topic_0066459131_p13949978165858"></a><a name="zh-cn_topic_0066459131_p13949978165858"></a>Flume在重启后是否直接定位到文件最新的位置处，以读取最新的数据。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row59043204165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p36095681165858"><a name="zh-cn_topic_0066459131_p36095681165858"></a><a name="zh-cn_topic_0066459131_p36095681165858"></a>idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p38069063165858"><a name="zh-cn_topic_0066459131_p38069063165858"></a><a name="zh-cn_topic_0066459131_p38069063165858"></a>120000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p63695269165858"><a name="zh-cn_topic_0066459131_p63695269165858"></a><a name="zh-cn_topic_0066459131_p63695269165858"></a>设置读取文件的空闲时间，单位：毫秒。如果在该时间内文件内容没有变更，关闭掉该文件，关闭后如果该文件有数据写入，重新打开并读取数据。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1430489165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p61626796165858"><a name="zh-cn_topic_0066459131_p61626796165858"></a><a name="zh-cn_topic_0066459131_p61626796165858"></a>writePosInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p25714542165858"><a name="zh-cn_topic_0066459131_p25714542165858"></a><a name="zh-cn_topic_0066459131_p25714542165858"></a>3000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2503173165858"><a name="zh-cn_topic_0066459131_p2503173165858"></a><a name="zh-cn_topic_0066459131_p2503173165858"></a>设置将元数据写入到文件的周期，单位：毫秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row36931275165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p12874405165858"><a name="zh-cn_topic_0066459131_p12874405165858"></a><a name="zh-cn_topic_0066459131_p12874405165858"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p36193886165858"><a name="zh-cn_topic_0066459131_p36193886165858"></a><a name="zh-cn_topic_0066459131_p36193886165858"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p46023688165858"><a name="zh-cn_topic_0066459131_p46023688165858"></a><a name="zh-cn_topic_0066459131_p46023688165858"></a>批次写入Channel的Event数量。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row10510974165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p38643278165858"><a name="zh-cn_topic_0066459131_p38643278165858"></a><a name="zh-cn_topic_0066459131_p38643278165858"></a><span id="zh-cn_topic_0066459131_ph63946021165858"><a name="zh-cn_topic_0066459131_ph63946021165858"></a><a name="zh-cn_topic_0066459131_ph63946021165858"></a>monTime</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p52335749165858"><a name="zh-cn_topic_0066459131_p52335749165858"></a><a name="zh-cn_topic_0066459131_p52335749165858"></a><span id="zh-cn_topic_0066459131_ph43097785165858"><a name="zh-cn_topic_0066459131_ph43097785165858"></a><a name="zh-cn_topic_0066459131_ph43097785165858"></a>0（不开启）</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p34926953165858"><a name="zh-cn_topic_0066459131_p34926953165858"></a><a name="zh-cn_topic_0066459131_p34926953165858"></a><span id="zh-cn_topic_0066459131_ph4588674114422"><a name="zh-cn_topic_0066459131_ph4588674114422"></a><a name="zh-cn_topic_0066459131_ph4588674114422"></a>线程监控阈值，更新时间</span>大于<span id="zh-cn_topic_0066459131_ph5132004214426"><a name="zh-cn_topic_0066459131_ph5132004214426"></a><a name="zh-cn_topic_0066459131_ph5132004214426"></a>阈值时重新启动该Source，单位：秒。</span></p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Http Source**

    Http Source接收外部HTTP客户端发送过来的数据，并放入配置的Channel中，常用配置如[下表](#zh-cn_topic_0066459131_table62079280165858)所示：

    **表 5**  Http Source常用配置

    <a name="zh-cn_topic_0066459131_table62079280165858"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row8601656165858"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p65304253165858"><a name="zh-cn_topic_0066459131_p65304253165858"></a><a name="zh-cn_topic_0066459131_p65304253165858"></a><strong id="zh-cn_topic_0066459131_b28440537144225"><a name="zh-cn_topic_0066459131_b28440537144225"></a><a name="zh-cn_topic_0066459131_b28440537144225"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p55153116165858"><a name="zh-cn_topic_0066459131_p55153116165858"></a><a name="zh-cn_topic_0066459131_p55153116165858"></a><strong id="zh-cn_topic_0066459131_b21982181144225"><a name="zh-cn_topic_0066459131_b21982181144225"></a><a name="zh-cn_topic_0066459131_b21982181144225"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p38217400165858"><a name="zh-cn_topic_0066459131_p38217400165858"></a><a name="zh-cn_topic_0066459131_p38217400165858"></a><strong id="zh-cn_topic_0066459131_b35726270144225"><a name="zh-cn_topic_0066459131_b35726270144225"></a><a name="zh-cn_topic_0066459131_b35726270144225"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row2768965165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p25645508165858"><a name="zh-cn_topic_0066459131_p25645508165858"></a><a name="zh-cn_topic_0066459131_p25645508165858"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p64020293165858"><a name="zh-cn_topic_0066459131_p64020293165858"></a><a name="zh-cn_topic_0066459131_p64020293165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p18261283165858"><a name="zh-cn_topic_0066459131_p18261283165858"></a><a name="zh-cn_topic_0066459131_p18261283165858"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row10301585165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p24920692165858"><a name="zh-cn_topic_0066459131_p24920692165858"></a><a name="zh-cn_topic_0066459131_p24920692165858"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5310135165858"><a name="zh-cn_topic_0066459131_p5310135165858"></a><a name="zh-cn_topic_0066459131_p5310135165858"></a>http</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p27467828165858"><a name="zh-cn_topic_0066459131_p27467828165858"></a><a name="zh-cn_topic_0066459131_p27467828165858"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue21078288144245"><a name="zh-cn_topic_0066459131_parmvalue21078288144245"></a><a name="zh-cn_topic_0066459131_parmvalue21078288144245"></a>“http”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row29730514165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p25605403165858"><a name="zh-cn_topic_0066459131_p25605403165858"></a><a name="zh-cn_topic_0066459131_p25605403165858"></a>bind</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p60771756165858"><a name="zh-cn_topic_0066459131_p60771756165858"></a><a name="zh-cn_topic_0066459131_p60771756165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5617627514431"><a name="zh-cn_topic_0066459131_p5617627514431"></a><a name="zh-cn_topic_0066459131_p5617627514431"></a>绑定关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4964297165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p66248041165858"><a name="zh-cn_topic_0066459131_p66248041165858"></a><a name="zh-cn_topic_0066459131_p66248041165858"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p64491137165858"><a name="zh-cn_topic_0066459131_p64491137165858"></a><a name="zh-cn_topic_0066459131_p64491137165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p56399593165858"><a name="zh-cn_topic_0066459131_p56399593165858"></a><a name="zh-cn_topic_0066459131_p56399593165858"></a>绑定端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row25974460165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p44678678165858"><a name="zh-cn_topic_0066459131_p44678678165858"></a><a name="zh-cn_topic_0066459131_p44678678165858"></a>handler</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p62203166165858"><a name="zh-cn_topic_0066459131_p62203166165858"></a><a name="zh-cn_topic_0066459131_p62203166165858"></a>org.apache.flume.source.http.JSONHandler</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p39467760144425"><a name="zh-cn_topic_0066459131_p39467760144425"></a><a name="zh-cn_topic_0066459131_p39467760144425"></a>http请求的消息解析方式，支持以下两种：</p>
    <a name="zh-cn_topic_0066459131_ul19634310144429"></a><a name="zh-cn_topic_0066459131_ul19634310144429"></a><ul id="zh-cn_topic_0066459131_ul19634310144429"><li><span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue36925268144447"><a name="zh-cn_topic_0066459131_parmvalue36925268144447"></a><a name="zh-cn_topic_0066459131_parmvalue36925268144447"></a>“org.apache.flume.source.http.JSONHandler”</span>：表示Json格式解析。</li><li><span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue19892477144521"><a name="zh-cn_topic_0066459131_parmvalue19892477144521"></a><a name="zh-cn_topic_0066459131_parmvalue19892477144521"></a>“org.apache.flume.sink.solr.morphline.BlobHandler”</span>：表示二进制Blob块解析。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row23178554165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p32443552165858"><a name="zh-cn_topic_0066459131_p32443552165858"></a><a name="zh-cn_topic_0066459131_p32443552165858"></a>handler.*</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p10682035165858"><a name="zh-cn_topic_0066459131_p10682035165858"></a><a name="zh-cn_topic_0066459131_p10682035165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p59938478165858"><a name="zh-cn_topic_0066459131_p59938478165858"></a><a name="zh-cn_topic_0066459131_p59938478165858"></a>设置handler的参数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row7599322165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p7280398165858"><a name="zh-cn_topic_0066459131_p7280398165858"></a><a name="zh-cn_topic_0066459131_p7280398165858"></a>enableSSL</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p52841333165858"><a name="zh-cn_topic_0066459131_p52841333165858"></a><a name="zh-cn_topic_0066459131_p52841333165858"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p52289601165858"><a name="zh-cn_topic_0066459131_p52289601165858"></a><a name="zh-cn_topic_0066459131_p52289601165858"></a>http协议是否启用SSL。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row22653691165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1285039165858"><a name="zh-cn_topic_0066459131_p1285039165858"></a><a name="zh-cn_topic_0066459131_p1285039165858"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p36979301165858"><a name="zh-cn_topic_0066459131_p36979301165858"></a><a name="zh-cn_topic_0066459131_p36979301165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p42533404165858"><a name="zh-cn_topic_0066459131_p42533404165858"></a><a name="zh-cn_topic_0066459131_p42533404165858"></a>http启用SSL后设置keystore的路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row14169733165858"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2556634165858"><a name="zh-cn_topic_0066459131_p2556634165858"></a><a name="zh-cn_topic_0066459131_p2556634165858"></a>keystorePassword</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5760777165858"><a name="zh-cn_topic_0066459131_p5760777165858"></a><a name="zh-cn_topic_0066459131_p5760777165858"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p63969781165858"><a name="zh-cn_topic_0066459131_p63969781165858"></a><a name="zh-cn_topic_0066459131_p63969781165858"></a>http启用SSL后设置keystore的密码。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **OBS Source**

    OBS Source监控并传输指定桶下新增的文件，可实现准实时数据传输。常用配置如[下表](#zh-cn_topic_0066459131_table10652224151749)所示：

    **表 6**  OBS Source常用配置

    <a name="zh-cn_topic_0066459131_table10652224151749"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row8847958151749"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p45595959151749"><a name="zh-cn_topic_0066459131_p45595959151749"></a><a name="zh-cn_topic_0066459131_p45595959151749"></a><strong id="zh-cn_topic_0066459131_b7710450151749"><a name="zh-cn_topic_0066459131_b7710450151749"></a><a name="zh-cn_topic_0066459131_b7710450151749"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p20566739151749"><a name="zh-cn_topic_0066459131_p20566739151749"></a><a name="zh-cn_topic_0066459131_p20566739151749"></a><strong id="zh-cn_topic_0066459131_b50882931151749"><a name="zh-cn_topic_0066459131_b50882931151749"></a><a name="zh-cn_topic_0066459131_b50882931151749"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p27876766151749"><a name="zh-cn_topic_0066459131_p27876766151749"></a><a name="zh-cn_topic_0066459131_p27876766151749"></a><strong id="zh-cn_topic_0066459131_b49564307151749"><a name="zh-cn_topic_0066459131_b49564307151749"></a><a name="zh-cn_topic_0066459131_b49564307151749"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row55285954151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p48977285151749"><a name="zh-cn_topic_0066459131_p48977285151749"></a><a name="zh-cn_topic_0066459131_p48977285151749"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p7737157151749"><a name="zh-cn_topic_0066459131_p7737157151749"></a><a name="zh-cn_topic_0066459131_p7737157151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p22729961151749"><a name="zh-cn_topic_0066459131_p22729961151749"></a><a name="zh-cn_topic_0066459131_p22729961151749"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3243060151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p61361322151749"><a name="zh-cn_topic_0066459131_p61361322151749"></a><a name="zh-cn_topic_0066459131_p61361322151749"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4211192151749"><a name="zh-cn_topic_0066459131_p4211192151749"></a><a name="zh-cn_topic_0066459131_p4211192151749"></a>http</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5562311151749"><a name="zh-cn_topic_0066459131_p5562311151749"></a><a name="zh-cn_topic_0066459131_p5562311151749"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue50060807151749"><a name="zh-cn_topic_0066459131_parmvalue50060807151749"></a><a name="zh-cn_topic_0066459131_parmvalue50060807151749"></a>“org.apache.flume.source.s3.OBSSource”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row47894079151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p55545403151857"><a name="zh-cn_topic_0066459131_p55545403151857"></a><a name="zh-cn_topic_0066459131_p55545403151857"></a>bucketName</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p29353031151749"><a name="zh-cn_topic_0066459131_p29353031151749"></a><a name="zh-cn_topic_0066459131_p29353031151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p28785320151749"><a name="zh-cn_topic_0066459131_p28785320151749"></a><a name="zh-cn_topic_0066459131_p28785320151749"></a>OBS桶名。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row10571013164213"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p50945724164213"><a name="zh-cn_topic_0066459131_p50945724164213"></a><a name="zh-cn_topic_0066459131_p50945724164213"></a><span id="zh-cn_topic_0066459131_ph63028641164223"><a name="zh-cn_topic_0066459131_ph63028641164223"></a><a name="zh-cn_topic_0066459131_ph63028641164223"></a>prefix</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p32962971164213"><a name="zh-cn_topic_0066459131_p32962971164213"></a><a name="zh-cn_topic_0066459131_p32962971164213"></a><span id="zh-cn_topic_0066459131_ph35675333164230"><a name="zh-cn_topic_0066459131_ph35675333164230"></a><a name="zh-cn_topic_0066459131_ph35675333164230"></a>-</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p52755019164213"><a name="zh-cn_topic_0066459131_p52755019164213"></a><a name="zh-cn_topic_0066459131_p52755019164213"></a><span id="zh-cn_topic_0066459131_ph60487813164359"><a name="zh-cn_topic_0066459131_ph60487813164359"></a><a name="zh-cn_topic_0066459131_ph60487813164359"></a>指定桶下，具体监控的OBS路径。注意不要以斜杠/开头。不设置时，默认监控桶下的根目录。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row57741292151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p12633304151911"><a name="zh-cn_topic_0066459131_p12633304151911"></a><a name="zh-cn_topic_0066459131_p12633304151911"></a>accessKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p11083850151749"><a name="zh-cn_topic_0066459131_p11083850151749"></a><a name="zh-cn_topic_0066459131_p11083850151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p25376656151749"><a name="zh-cn_topic_0066459131_p25376656151749"></a><a name="zh-cn_topic_0066459131_p25376656151749"></a>用户的AK信息。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row27063313151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p55792111151930"><a name="zh-cn_topic_0066459131_p55792111151930"></a><a name="zh-cn_topic_0066459131_p55792111151930"></a>secretKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p59452248151749"><a name="zh-cn_topic_0066459131_p59452248151749"></a><a name="zh-cn_topic_0066459131_p59452248151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p7380505152027"><a name="zh-cn_topic_0066459131_p7380505152027"></a><a name="zh-cn_topic_0066459131_p7380505152027"></a>用户的SK信息，需要配置为密文。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row40358733151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p15683489152017"><a name="zh-cn_topic_0066459131_p15683489152017"></a><a name="zh-cn_topic_0066459131_p15683489152017"></a>backingDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p49179258151749"><a name="zh-cn_topic_0066459131_p49179258151749"></a><a name="zh-cn_topic_0066459131_p49179258151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p35423564152049"><a name="zh-cn_topic_0066459131_p35423564152049"></a><a name="zh-cn_topic_0066459131_p35423564152049"></a>传输过程中元数据存储路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row15545992151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p24655236152057"><a name="zh-cn_topic_0066459131_p24655236152057"></a><a name="zh-cn_topic_0066459131_p24655236152057"></a>endPoint</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p58890339151749"><a name="zh-cn_topic_0066459131_p58890339151749"></a><a name="zh-cn_topic_0066459131_p58890339151749"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5388115151749"><a name="zh-cn_topic_0066459131_p5388115151749"></a><a name="zh-cn_topic_0066459131_p5388115151749"></a>OBS访问地址，需要和MRS在相同的Region，可能是域名或者IP地址形式。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row48493036151749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3239827152239"><a name="zh-cn_topic_0066459131_p3239827152239"></a><a name="zh-cn_topic_0066459131_p3239827152239"></a>basenameHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p61099420152239"><a name="zh-cn_topic_0066459131_p61099420152239"></a><a name="zh-cn_topic_0066459131_p61099420152239"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p10949339152246"><a name="zh-cn_topic_0066459131_p10949339152246"></a><a name="zh-cn_topic_0066459131_p10949339152246"></a>是否在Event Header中保存文件名。<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue52392913154030"><a name="zh-cn_topic_0066459131_parmvalue52392913154030"></a><a name="zh-cn_topic_0066459131_parmvalue52392913154030"></a>“false”</span>表示不保存。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row52791047152231"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p48300691152239"><a name="zh-cn_topic_0066459131_p48300691152239"></a><a name="zh-cn_topic_0066459131_p48300691152239"></a>basenameHeaderKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p20041870152239"><a name="zh-cn_topic_0066459131_p20041870152239"></a><a name="zh-cn_topic_0066459131_p20041870152239"></a>basename</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3012629415231"><a name="zh-cn_topic_0066459131_p3012629415231"></a><a name="zh-cn_topic_0066459131_p3012629415231"></a>指定Event Header保存文件名使用的字段名，即key名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row31604781153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4375389153843"><a name="zh-cn_topic_0066459131_p4375389153843"></a><a name="zh-cn_topic_0066459131_p4375389153843"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p18862208153843"><a name="zh-cn_topic_0066459131_p18862208153843"></a><a name="zh-cn_topic_0066459131_p18862208153843"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p51443851153843"><a name="zh-cn_topic_0066459131_p51443851153843"></a><a name="zh-cn_topic_0066459131_p51443851153843"></a>Source传输粒度。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row63163965153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p55821667153843"><a name="zh-cn_topic_0066459131_p55821667153843"></a><a name="zh-cn_topic_0066459131_p55821667153843"></a>decodeErrorPolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p25261146153843"><a name="zh-cn_topic_0066459131_p25261146153843"></a><a name="zh-cn_topic_0066459131_p25261146153843"></a>FAIL</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p32886966153843"><a name="zh-cn_topic_0066459131_p32886966153843"></a><a name="zh-cn_topic_0066459131_p32886966153843"></a>编码错误策略。</p>
    <div class="note" id="zh-cn_topic_0066459131_note27547246153843"><a name="zh-cn_topic_0066459131_note27547246153843"></a><a name="zh-cn_topic_0066459131_note27547246153843"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0066459131_p46598623153843"><a name="zh-cn_topic_0066459131_p46598623153843"></a><a name="zh-cn_topic_0066459131_p46598623153843"></a>如果文件中有编码错误，请配置“decodeErrorPolicy”为“REPLACE”或“IGNORE”，Flume遇到编码错误将跳过编码错误，继续采集后续日志。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row7018218153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p13311394153843"><a name="zh-cn_topic_0066459131_p13311394153843"></a><a name="zh-cn_topic_0066459131_p13311394153843"></a>deserializer</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4481129153843"><a name="zh-cn_topic_0066459131_p4481129153843"></a><a name="zh-cn_topic_0066459131_p4481129153843"></a>LINE</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p27427160153843"><a name="zh-cn_topic_0066459131_p27427160153843"></a><a name="zh-cn_topic_0066459131_p27427160153843"></a>文件解析器，值为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue45517855153843"><a name="zh-cn_topic_0066459131_parmvalue45517855153843"></a><a name="zh-cn_topic_0066459131_parmvalue45517855153843"></a>“LINE”</span>或&nbsp;<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue7007512153843"><a name="zh-cn_topic_0066459131_parmvalue7007512153843"></a><a name="zh-cn_topic_0066459131_parmvalue7007512153843"></a>“BufferedLine”</span>。</p>
    <a name="zh-cn_topic_0066459131_ul63067614153843"></a><a name="zh-cn_topic_0066459131_ul63067614153843"></a><ul id="zh-cn_topic_0066459131_ul63067614153843"><li>配置为<span class="parmname" id="zh-cn_topic_0066459131_parmname8203098153843"><a name="zh-cn_topic_0066459131_parmname8203098153843"></a><a name="zh-cn_topic_0066459131_parmname8203098153843"></a>“LINE”</span>时，对从文件读取的字符逐个转码。</li><li>配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue60471162153843"><a name="zh-cn_topic_0066459131_parmvalue60471162153843"></a><a name="zh-cn_topic_0066459131_parmvalue60471162153843"></a>“BufferedLine”</span>时，对文件读取的一行或多行的字符进行批量转码，性能更优。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row779802153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p60062429153843"><a name="zh-cn_topic_0066459131_p60062429153843"></a><a name="zh-cn_topic_0066459131_p60062429153843"></a>deserializer.maxLineLength</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p33218567153843"><a name="zh-cn_topic_0066459131_p33218567153843"></a><a name="zh-cn_topic_0066459131_p33218567153843"></a>2048</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6349426153843"><a name="zh-cn_topic_0066459131_p6349426153843"></a><a name="zh-cn_topic_0066459131_p6349426153843"></a>按行解析最大长度。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row52282427153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p65329270153843"><a name="zh-cn_topic_0066459131_p65329270153843"></a><a name="zh-cn_topic_0066459131_p65329270153843"></a>deserializer.maxBatchLine</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p57179513153843"><a name="zh-cn_topic_0066459131_p57179513153843"></a><a name="zh-cn_topic_0066459131_p57179513153843"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1028985153843"><a name="zh-cn_topic_0066459131_p1028985153843"></a><a name="zh-cn_topic_0066459131_p1028985153843"></a>按行解析最多行数，如果行数设置为多行，<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue9260867153843"><a name="zh-cn_topic_0066459131_parmvalue9260867153843"></a><a name="zh-cn_topic_0066459131_parmvalue9260867153843"></a>“maxLineLength”</span>也应该设置为相应的倍数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5809158153844"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p40285838153843"><a name="zh-cn_topic_0066459131_p40285838153843"></a><a name="zh-cn_topic_0066459131_p40285838153843"></a>selector.type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p41927411153843"><a name="zh-cn_topic_0066459131_p41927411153843"></a><a name="zh-cn_topic_0066459131_p41927411153843"></a>replicating</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p40677108153843"><a name="zh-cn_topic_0066459131_p40677108153843"></a><a name="zh-cn_topic_0066459131_p40677108153843"></a>选择器类型，支持<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue30549659153843"><a name="zh-cn_topic_0066459131_parmvalue30549659153843"></a><a name="zh-cn_topic_0066459131_parmvalue30549659153843"></a>“replicating”</span>或<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue6511483153843"><a name="zh-cn_topic_0066459131_parmvalue6511483153843"></a><a name="zh-cn_topic_0066459131_parmvalue6511483153843"></a>“multiplexing”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row60297785153843"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p49250651153843"><a name="zh-cn_topic_0066459131_p49250651153843"></a><a name="zh-cn_topic_0066459131_p49250651153843"></a>interceptors</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p29879771153843"><a name="zh-cn_topic_0066459131_p29879771153843"></a><a name="zh-cn_topic_0066459131_p29879771153843"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4342396153843"><a name="zh-cn_topic_0066459131_p4342396153843"></a><a name="zh-cn_topic_0066459131_p4342396153843"></a>拦截器配置。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 常用Channel配置<a name="zh-cn_topic_0066459131_zh-cn_topic_0038340298_section23871361175649"></a>

-   **Memory Channel**

    Memory Channel使用内存作为缓存区，Events存放在内存队列中。常用配置如[下表](#zh-cn_topic_0066459131_table563148961758)所示：

    **表 7**  Memory Channel常用配置

    <a name="zh-cn_topic_0066459131_table563148961758"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row273904901758"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p194642081758"><a name="zh-cn_topic_0066459131_p194642081758"></a><a name="zh-cn_topic_0066459131_p194642081758"></a><strong id="zh-cn_topic_0066459131_b245323111758"><a name="zh-cn_topic_0066459131_b245323111758"></a><a name="zh-cn_topic_0066459131_b245323111758"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p294379441758"><a name="zh-cn_topic_0066459131_p294379441758"></a><a name="zh-cn_topic_0066459131_p294379441758"></a><strong id="zh-cn_topic_0066459131_b330970441758"><a name="zh-cn_topic_0066459131_b330970441758"></a><a name="zh-cn_topic_0066459131_b330970441758"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p525339371758"><a name="zh-cn_topic_0066459131_p525339371758"></a><a name="zh-cn_topic_0066459131_p525339371758"></a><strong id="zh-cn_topic_0066459131_b356632651758"><a name="zh-cn_topic_0066459131_b356632651758"></a><a name="zh-cn_topic_0066459131_b356632651758"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row46847801758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p40372161758"><a name="zh-cn_topic_0066459131_p40372161758"></a><a name="zh-cn_topic_0066459131_p40372161758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p585790501758"><a name="zh-cn_topic_0066459131_p585790501758"></a><a name="zh-cn_topic_0066459131_p585790501758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p472825921758"><a name="zh-cn_topic_0066459131_p472825921758"></a><a name="zh-cn_topic_0066459131_p472825921758"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue517545314463"><a name="zh-cn_topic_0066459131_parmvalue517545314463"></a><a name="zh-cn_topic_0066459131_parmvalue517545314463"></a>“memory”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row451508771758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p421630201758"><a name="zh-cn_topic_0066459131_p421630201758"></a><a name="zh-cn_topic_0066459131_p421630201758"></a>capacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p597614891758"><a name="zh-cn_topic_0066459131_p597614891758"></a><a name="zh-cn_topic_0066459131_p597614891758"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p88424631758"><a name="zh-cn_topic_0066459131_p88424631758"></a><a name="zh-cn_topic_0066459131_p88424631758"></a>缓存在Channel中的最大Event数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row618955121758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p37047091758"><a name="zh-cn_topic_0066459131_p37047091758"></a><a name="zh-cn_topic_0066459131_p37047091758"></a>transactionCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p316460311758"><a name="zh-cn_topic_0066459131_p316460311758"></a><a name="zh-cn_topic_0066459131_p316460311758"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p131917091758"><a name="zh-cn_topic_0066459131_p131917091758"></a><a name="zh-cn_topic_0066459131_p131917091758"></a>每次存取的最大Event数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row49562201758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p201886971758"><a name="zh-cn_topic_0066459131_p201886971758"></a><a name="zh-cn_topic_0066459131_p201886971758"></a>channelfullcount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p246717781758"><a name="zh-cn_topic_0066459131_p246717781758"></a><a name="zh-cn_topic_0066459131_p246717781758"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p522569711758"><a name="zh-cn_topic_0066459131_p522569711758"></a><a name="zh-cn_topic_0066459131_p522569711758"></a>Channel full次数，达到该次数后发送告警。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **File Channel**

    File Channel使用本地磁盘作为缓存区，Events存放在设置的“dataDirs“配置项文件夹中。常用配置如[下表](#zh-cn_topic_0066459131_table411901301758)所示：

    **表 8**  File Channel常用配置

    <a name="zh-cn_topic_0066459131_table411901301758"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row110135331758"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p498158311758"><a name="zh-cn_topic_0066459131_p498158311758"></a><a name="zh-cn_topic_0066459131_p498158311758"></a><strong id="zh-cn_topic_0066459131_b428177941758"><a name="zh-cn_topic_0066459131_b428177941758"></a><a name="zh-cn_topic_0066459131_b428177941758"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p98456381758"><a name="zh-cn_topic_0066459131_p98456381758"></a><a name="zh-cn_topic_0066459131_p98456381758"></a><strong id="zh-cn_topic_0066459131_b85505001758"><a name="zh-cn_topic_0066459131_b85505001758"></a><a name="zh-cn_topic_0066459131_b85505001758"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p639308151758"><a name="zh-cn_topic_0066459131_p639308151758"></a><a name="zh-cn_topic_0066459131_p639308151758"></a><strong id="zh-cn_topic_0066459131_b592992071758"><a name="zh-cn_topic_0066459131_b592992071758"></a><a name="zh-cn_topic_0066459131_b592992071758"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row494254521758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p196810201758"><a name="zh-cn_topic_0066459131_p196810201758"></a><a name="zh-cn_topic_0066459131_p196810201758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p506588201758"><a name="zh-cn_topic_0066459131_p506588201758"></a><a name="zh-cn_topic_0066459131_p506588201758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p97237401758"><a name="zh-cn_topic_0066459131_p97237401758"></a><a name="zh-cn_topic_0066459131_p97237401758"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue10129776145144"><a name="zh-cn_topic_0066459131_parmvalue10129776145144"></a><a name="zh-cn_topic_0066459131_parmvalue10129776145144"></a>“file”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row24527011758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p421758891758"><a name="zh-cn_topic_0066459131_p421758891758"></a><a name="zh-cn_topic_0066459131_p421758891758"></a>checkpointDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p608038491758"><a name="zh-cn_topic_0066459131_p608038491758"></a><a name="zh-cn_topic_0066459131_p608038491758"></a>${BIGDATA_DATA_HOME}/flume/checkpoint</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p389699911758"><a name="zh-cn_topic_0066459131_p389699911758"></a><a name="zh-cn_topic_0066459131_p389699911758"></a>检查点存放路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row523443101758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p220743101758"><a name="zh-cn_topic_0066459131_p220743101758"></a><a name="zh-cn_topic_0066459131_p220743101758"></a>dataDirs</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p431886571758"><a name="zh-cn_topic_0066459131_p431886571758"></a><a name="zh-cn_topic_0066459131_p431886571758"></a>${BIGDATA_DATA_HOME}/flume/data</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p271583691758"><a name="zh-cn_topic_0066459131_p271583691758"></a><a name="zh-cn_topic_0066459131_p271583691758"></a>数据缓存路径，设置多个路径可提升性能，中间用逗号分开。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row558510841758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p13367481758"><a name="zh-cn_topic_0066459131_p13367481758"></a><a name="zh-cn_topic_0066459131_p13367481758"></a>maxFileSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p411677971758"><a name="zh-cn_topic_0066459131_p411677971758"></a><a name="zh-cn_topic_0066459131_p411677971758"></a>2146435071</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p462572661758"><a name="zh-cn_topic_0066459131_p462572661758"></a><a name="zh-cn_topic_0066459131_p462572661758"></a>单个缓存文件的最大值，单位：字节。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row584997671758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p328977111758"><a name="zh-cn_topic_0066459131_p328977111758"></a><a name="zh-cn_topic_0066459131_p328977111758"></a>minimumRequiredSpace</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p474689261758"><a name="zh-cn_topic_0066459131_p474689261758"></a><a name="zh-cn_topic_0066459131_p474689261758"></a>524288000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p197778221758"><a name="zh-cn_topic_0066459131_p197778221758"></a><a name="zh-cn_topic_0066459131_p197778221758"></a>缓冲区空闲空间最小值，单位：字节。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row158897891758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p567358561758"><a name="zh-cn_topic_0066459131_p567358561758"></a><a name="zh-cn_topic_0066459131_p567358561758"></a>capacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p322015841758"><a name="zh-cn_topic_0066459131_p322015841758"></a><a name="zh-cn_topic_0066459131_p322015841758"></a>1000000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p581914841758"><a name="zh-cn_topic_0066459131_p581914841758"></a><a name="zh-cn_topic_0066459131_p581914841758"></a>缓存在Channel中的最大Event数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row541284311758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p87903811758"><a name="zh-cn_topic_0066459131_p87903811758"></a><a name="zh-cn_topic_0066459131_p87903811758"></a>transactionCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p409322801758"><a name="zh-cn_topic_0066459131_p409322801758"></a><a name="zh-cn_topic_0066459131_p409322801758"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p271803961758"><a name="zh-cn_topic_0066459131_p271803961758"></a><a name="zh-cn_topic_0066459131_p271803961758"></a>每次存取的最大Event数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row232546281758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p173938391758"><a name="zh-cn_topic_0066459131_p173938391758"></a><a name="zh-cn_topic_0066459131_p173938391758"></a>channelfullcount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p667237271758"><a name="zh-cn_topic_0066459131_p667237271758"></a><a name="zh-cn_topic_0066459131_p667237271758"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p359127871758"><a name="zh-cn_topic_0066459131_p359127871758"></a><a name="zh-cn_topic_0066459131_p359127871758"></a>Channel full次数，达到该次数后发送告警。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Memory File Channel**

    Memory File Channel同时使用内存和本地磁盘作为缓存区，消息可持久化，性能优于File Channel，接近Memory Channel的性能。常用配置如[下表](#zh-cn_topic_0066459131_table103262951758)所示：

    **表 9**  Memory File Channel常用配置

    <a name="zh-cn_topic_0066459131_table103262951758"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row300690821758"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p320572941758"><a name="zh-cn_topic_0066459131_p320572941758"></a><a name="zh-cn_topic_0066459131_p320572941758"></a><strong id="zh-cn_topic_0066459131_b35619211758"><a name="zh-cn_topic_0066459131_b35619211758"></a><a name="zh-cn_topic_0066459131_b35619211758"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p158830191758"><a name="zh-cn_topic_0066459131_p158830191758"></a><a name="zh-cn_topic_0066459131_p158830191758"></a><strong id="zh-cn_topic_0066459131_b465040221758"><a name="zh-cn_topic_0066459131_b465040221758"></a><a name="zh-cn_topic_0066459131_b465040221758"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p359969161758"><a name="zh-cn_topic_0066459131_p359969161758"></a><a name="zh-cn_topic_0066459131_p359969161758"></a><strong id="zh-cn_topic_0066459131_b114561971758"><a name="zh-cn_topic_0066459131_b114561971758"></a><a name="zh-cn_topic_0066459131_b114561971758"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row575515151758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p196765481758"><a name="zh-cn_topic_0066459131_p196765481758"></a><a name="zh-cn_topic_0066459131_p196765481758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p502965381758"><a name="zh-cn_topic_0066459131_p502965381758"></a><a name="zh-cn_topic_0066459131_p502965381758"></a>org.apache.flume.channel.MemoryFileChannel</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p247371421758"><a name="zh-cn_topic_0066459131_p247371421758"></a><a name="zh-cn_topic_0066459131_p247371421758"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue474878141758"><a name="zh-cn_topic_0066459131_parmvalue474878141758"></a><a name="zh-cn_topic_0066459131_parmvalue474878141758"></a>“org.apache.flume.channel.MemoryFileChannel”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row445730011758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p482015931758"><a name="zh-cn_topic_0066459131_p482015931758"></a><a name="zh-cn_topic_0066459131_p482015931758"></a>capacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p120149941758"><a name="zh-cn_topic_0066459131_p120149941758"></a><a name="zh-cn_topic_0066459131_p120149941758"></a>50000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p336904631758"><a name="zh-cn_topic_0066459131_p336904631758"></a><a name="zh-cn_topic_0066459131_p336904631758"></a>Channel缓存容量：缓存在Channel中的最大Event数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row472554621758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p656126921758"><a name="zh-cn_topic_0066459131_p656126921758"></a><a name="zh-cn_topic_0066459131_p656126921758"></a>transactionCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p130278271758"><a name="zh-cn_topic_0066459131_p130278271758"></a><a name="zh-cn_topic_0066459131_p130278271758"></a>5000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p486210911758"><a name="zh-cn_topic_0066459131_p486210911758"></a><a name="zh-cn_topic_0066459131_p486210911758"></a>事务缓存容量：一次事务能处理的最大Event数。</p>
    <a name="zh-cn_topic_0066459131_ul336429511570"></a><a name="zh-cn_topic_0066459131_ul336429511570"></a><ul id="zh-cn_topic_0066459131_ul336429511570"><li>此参数值需要大于Source和Sink的<span class="parmname" id="zh-cn_topic_0066459131_parmname283073581570"><a name="zh-cn_topic_0066459131_parmname283073581570"></a><a name="zh-cn_topic_0066459131_parmname283073581570"></a>“batchSize”</span>。</li><li>事务缓存容量必须小于或等于Channel缓存容量。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row664174811758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p226459771758"><a name="zh-cn_topic_0066459131_p226459771758"></a><a name="zh-cn_topic_0066459131_p226459771758"></a>subqueueByteCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p223848741758"><a name="zh-cn_topic_0066459131_p223848741758"></a><a name="zh-cn_topic_0066459131_p223848741758"></a>20971520</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p12355441758"><a name="zh-cn_topic_0066459131_p12355441758"></a><a name="zh-cn_topic_0066459131_p12355441758"></a>每个subqueue最多保存多少大小的Event，单位：字节。</p>
    <p id="zh-cn_topic_0066459131_p111199011758"><a name="zh-cn_topic_0066459131_p111199011758"></a><a name="zh-cn_topic_0066459131_p111199011758"></a>Memory File Channel采用queue和subqueue两级缓存，event保存在subqueue，subqueue保存在queue。</p>
    <p id="zh-cn_topic_0066459131_p213092601758"><a name="zh-cn_topic_0066459131_p213092601758"></a><a name="zh-cn_topic_0066459131_p213092601758"></a>subqueue能保存多少event，由<span class="parmname" id="zh-cn_topic_0066459131_parmname329702501758"><a name="zh-cn_topic_0066459131_parmname329702501758"></a><a name="zh-cn_topic_0066459131_parmname329702501758"></a>“subqueueCapacity”</span>和<span class="parmname" id="zh-cn_topic_0066459131_parmname282968011758"><a name="zh-cn_topic_0066459131_parmname282968011758"></a><a name="zh-cn_topic_0066459131_parmname282968011758"></a>“subqueueInterval”</span>两个参数决定，<span class="parmname" id="zh-cn_topic_0066459131_parmname533446171758"><a name="zh-cn_topic_0066459131_parmname533446171758"></a><a name="zh-cn_topic_0066459131_parmname533446171758"></a>“subqueueCapacity”</span>限制subqueue内的Event总容量，<span class="parmname" id="zh-cn_topic_0066459131_parmname103395081758"><a name="zh-cn_topic_0066459131_parmname103395081758"></a><a name="zh-cn_topic_0066459131_parmname103395081758"></a>“subqueueInterval”</span>限制subqueue保存Event的时长，只有subqueue达到<span class="parmname" id="zh-cn_topic_0066459131_parmname259467161758"><a name="zh-cn_topic_0066459131_parmname259467161758"></a><a name="zh-cn_topic_0066459131_parmname259467161758"></a>“subqueueCapacity”</span>或<span class="parmname" id="zh-cn_topic_0066459131_parmname321938571758"><a name="zh-cn_topic_0066459131_parmname321938571758"></a><a name="zh-cn_topic_0066459131_parmname321938571758"></a>“subqueueInterval”</span>上限时，subqueue内的Event才会发往目的地。</p>
    <div class="note" id="zh-cn_topic_0066459131_note323031391758"><a name="zh-cn_topic_0066459131_note323031391758"></a><a name="zh-cn_topic_0066459131_note323031391758"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0066459131_p483284801758"><a name="zh-cn_topic_0066459131_p483284801758"></a><a name="zh-cn_topic_0066459131_p483284801758"></a><span class="parmname" id="zh-cn_topic_0066459131_parmname575656141758"><a name="zh-cn_topic_0066459131_parmname575656141758"></a><a name="zh-cn_topic_0066459131_parmname575656141758"></a>“subqueueByteCapacity”</span>必须大于一个batchsize内的Event总容量。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row628096961758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p608864221758"><a name="zh-cn_topic_0066459131_p608864221758"></a><a name="zh-cn_topic_0066459131_p608864221758"></a>subqueueInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p328531271758"><a name="zh-cn_topic_0066459131_p328531271758"></a><a name="zh-cn_topic_0066459131_p328531271758"></a>2000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p438576621758"><a name="zh-cn_topic_0066459131_p438576621758"></a><a name="zh-cn_topic_0066459131_p438576621758"></a>每个subqueue最多保存一段多长时间的Event，单位：毫秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row518704081758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p284163581758"><a name="zh-cn_topic_0066459131_p284163581758"></a><a name="zh-cn_topic_0066459131_p284163581758"></a>keep-alive</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p200236381758"><a name="zh-cn_topic_0066459131_p200236381758"></a><a name="zh-cn_topic_0066459131_p200236381758"></a>3</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p113019911758"><a name="zh-cn_topic_0066459131_p113019911758"></a><a name="zh-cn_topic_0066459131_p113019911758"></a>当事务缓存或Channel缓存满时，Put、Take线程等待时间。单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row640992271758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p641804901758"><a name="zh-cn_topic_0066459131_p641804901758"></a><a name="zh-cn_topic_0066459131_p641804901758"></a>dataDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p312372291758"><a name="zh-cn_topic_0066459131_p312372291758"></a><a name="zh-cn_topic_0066459131_p312372291758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p471876001758"><a name="zh-cn_topic_0066459131_p471876001758"></a><a name="zh-cn_topic_0066459131_p471876001758"></a>缓存本地文件存储目录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row235042541758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p400221351758"><a name="zh-cn_topic_0066459131_p400221351758"></a><a name="zh-cn_topic_0066459131_p400221351758"></a>byteCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p205675391758"><a name="zh-cn_topic_0066459131_p205675391758"></a><a name="zh-cn_topic_0066459131_p205675391758"></a>JVM最大内存的80%</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p553579301758"><a name="zh-cn_topic_0066459131_p553579301758"></a><a name="zh-cn_topic_0066459131_p553579301758"></a>Channel缓存容量。单位：字节。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row178516881758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p102116951758"><a name="zh-cn_topic_0066459131_p102116951758"></a><a name="zh-cn_topic_0066459131_p102116951758"></a>compression-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p218409721758"><a name="zh-cn_topic_0066459131_p218409721758"></a><a name="zh-cn_topic_0066459131_p218409721758"></a>None</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p565586961758"><a name="zh-cn_topic_0066459131_p565586961758"></a><a name="zh-cn_topic_0066459131_p565586961758"></a>消息压缩格式：<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue242883261758"><a name="zh-cn_topic_0066459131_parmvalue242883261758"></a><a name="zh-cn_topic_0066459131_parmvalue242883261758"></a>“None”</span>或<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue172683451758"><a name="zh-cn_topic_0066459131_parmvalue172683451758"></a><a name="zh-cn_topic_0066459131_parmvalue172683451758"></a>“Snappy”</span>。配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue211973801758"><a name="zh-cn_topic_0066459131_parmvalue211973801758"></a><a name="zh-cn_topic_0066459131_parmvalue211973801758"></a>“Snappy”</span>时，可以对Snappy压缩格式的Event消息体进行解压。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row567206941758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p264474701758"><a name="zh-cn_topic_0066459131_p264474701758"></a><a name="zh-cn_topic_0066459131_p264474701758"></a>channelfullcount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p618703141758"><a name="zh-cn_topic_0066459131_p618703141758"></a><a name="zh-cn_topic_0066459131_p618703141758"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p454394981758"><a name="zh-cn_topic_0066459131_p454394981758"></a><a name="zh-cn_topic_0066459131_p454394981758"></a>Channel full次数，达到该次数后发送告警</p>
    </td>
    </tr>
    </tbody>
    </table>

    Memory File Channel配置样例：

    ```
    server.channels.c1.type = org.apache.flume.channel.MemoryFileChannel
    server.channels.c1.dataDir = /opt/flume/mfdata
    server.channels.c1.subqueueByteCapacity = 20971520
    server.channels.c1.subqueueInterval=2000
    server.channels.c1.capacity = 500000
    server.channels.c1.transactionCapacity = 40000
    ```

-   **Kafka Channel**

    Kafka Channel使用kafka集群缓存数据，Kafka提供高可用、多副本，以防Flume或Kafka Broker崩溃，Channel中的数据会立即被Sink消费。常用配置如[表 10 Kafka Channel 常用配置](#zh-cn_topic_0066459131_table335778401758)所示

    **表 10**  Kafka Channel 常用配置

    <a name="zh-cn_topic_0066459131_table335778401758"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row612814511758"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p105045311758"><a name="zh-cn_topic_0066459131_p105045311758"></a><a name="zh-cn_topic_0066459131_p105045311758"></a><strong id="zh-cn_topic_0066459131_b22155036151028"><a name="zh-cn_topic_0066459131_b22155036151028"></a><a name="zh-cn_topic_0066459131_b22155036151028"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p73927981758"><a name="zh-cn_topic_0066459131_p73927981758"></a><a name="zh-cn_topic_0066459131_p73927981758"></a><strong id="zh-cn_topic_0066459131_b60111743151032"><a name="zh-cn_topic_0066459131_b60111743151032"></a><a name="zh-cn_topic_0066459131_b60111743151032"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p206406681758"><a name="zh-cn_topic_0066459131_p206406681758"></a><a name="zh-cn_topic_0066459131_p206406681758"></a><strong id="zh-cn_topic_0066459131_b47308518151038"><a name="zh-cn_topic_0066459131_b47308518151038"></a><a name="zh-cn_topic_0066459131_b47308518151038"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row390125921758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p648505311758"><a name="zh-cn_topic_0066459131_p648505311758"></a><a name="zh-cn_topic_0066459131_p648505311758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p184016431758"><a name="zh-cn_topic_0066459131_p184016431758"></a><a name="zh-cn_topic_0066459131_p184016431758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p601339601758"><a name="zh-cn_topic_0066459131_p601339601758"></a><a name="zh-cn_topic_0066459131_p601339601758"></a>类型，需配置为 <span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue141380911758"><a name="zh-cn_topic_0066459131_parmvalue141380911758"></a><a name="zh-cn_topic_0066459131_parmvalue141380911758"></a>“org.apache.flume.channel.kafka.KafkaChannel”</span>.。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row262684051758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p155690131758"><a name="zh-cn_topic_0066459131_p155690131758"></a><a name="zh-cn_topic_0066459131_p155690131758"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p531305751758"><a name="zh-cn_topic_0066459131_p531305751758"></a><a name="zh-cn_topic_0066459131_p531305751758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p86093461758"><a name="zh-cn_topic_0066459131_p86093461758"></a><a name="zh-cn_topic_0066459131_p86093461758"></a>kafka broker列表。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row207310471758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p350890541758"><a name="zh-cn_topic_0066459131_p350890541758"></a><a name="zh-cn_topic_0066459131_p350890541758"></a>kafka.topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p236411081758"><a name="zh-cn_topic_0066459131_p236411081758"></a><a name="zh-cn_topic_0066459131_p236411081758"></a>flume-channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p358816321758"><a name="zh-cn_topic_0066459131_p358816321758"></a><a name="zh-cn_topic_0066459131_p358816321758"></a>Channel用来缓存数据的topic。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row620382791758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p523617011758"><a name="zh-cn_topic_0066459131_p523617011758"></a><a name="zh-cn_topic_0066459131_p523617011758"></a>kafka.consumer.group.id</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p134394111758"><a name="zh-cn_topic_0066459131_p134394111758"></a><a name="zh-cn_topic_0066459131_p134394111758"></a>flume</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p148504811758"><a name="zh-cn_topic_0066459131_p148504811758"></a><a name="zh-cn_topic_0066459131_p148504811758"></a>Kafka消费者组ID。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row238201871758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p214736031758"><a name="zh-cn_topic_0066459131_p214736031758"></a><a name="zh-cn_topic_0066459131_p214736031758"></a>parseAsFlumeEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p616402731758"><a name="zh-cn_topic_0066459131_p616402731758"></a><a name="zh-cn_topic_0066459131_p616402731758"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p268062201758"><a name="zh-cn_topic_0066459131_p268062201758"></a><a name="zh-cn_topic_0066459131_p268062201758"></a>是否解析为Flume event。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row294738421758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p130550941758"><a name="zh-cn_topic_0066459131_p130550941758"></a><a name="zh-cn_topic_0066459131_p130550941758"></a>migrateZookeeperOffsets</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p508296631758"><a name="zh-cn_topic_0066459131_p508296631758"></a><a name="zh-cn_topic_0066459131_p508296631758"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p235620001758"><a name="zh-cn_topic_0066459131_p235620001758"></a><a name="zh-cn_topic_0066459131_p235620001758"></a>当Kafka没有存储offset时，是否从ZooKeeper中查找，并提交到Kafka。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row376874591758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p639379881758"><a name="zh-cn_topic_0066459131_p639379881758"></a><a name="zh-cn_topic_0066459131_p639379881758"></a>kafka.consumer.auto.offset.reset</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p115945781758"><a name="zh-cn_topic_0066459131_p115945781758"></a><a name="zh-cn_topic_0066459131_p115945781758"></a>latest</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p667456361758"><a name="zh-cn_topic_0066459131_p667456361758"></a><a name="zh-cn_topic_0066459131_p667456361758"></a>当没有offset记录时，从指定的位置消费数据。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row518227331758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p36428141758"><a name="zh-cn_topic_0066459131_p36428141758"></a><a name="zh-cn_topic_0066459131_p36428141758"></a>kafka.producer.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p266325551758"><a name="zh-cn_topic_0066459131_p266325551758"></a><a name="zh-cn_topic_0066459131_p266325551758"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p97533361758"><a name="zh-cn_topic_0066459131_p97533361758"></a><a name="zh-cn_topic_0066459131_p97533361758"></a>Kafka生产者安全协议。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row65820401758"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p637514191758"><a name="zh-cn_topic_0066459131_p637514191758"></a><a name="zh-cn_topic_0066459131_p637514191758"></a>kafka.consumer.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p635912801758"><a name="zh-cn_topic_0066459131_p635912801758"></a><a name="zh-cn_topic_0066459131_p635912801758"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p37359357151214"><a name="zh-cn_topic_0066459131_p37359357151214"></a><a name="zh-cn_topic_0066459131_p37359357151214"></a>Kafka消费者安全协议。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 常用Sink配置<a name="zh-cn_topic_0066459131_zh-cn_topic_0038340298_section1225443174935"></a>

-   **HDFS Sink**

    HDFS Sink将数据写入HDFS。常用配置如[下表](#zh-cn_topic_0066459131_table2079428517533)所示：

    **表 11**  HDFS Sink常用配置

    <a name="zh-cn_topic_0066459131_table2079428517533"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row6476489417533"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p3308639117533"><a name="zh-cn_topic_0066459131_p3308639117533"></a><a name="zh-cn_topic_0066459131_p3308639117533"></a><strong id="zh-cn_topic_0066459131_b2604588717533"><a name="zh-cn_topic_0066459131_b2604588717533"></a><a name="zh-cn_topic_0066459131_b2604588717533"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p2789749017533"><a name="zh-cn_topic_0066459131_p2789749017533"></a><a name="zh-cn_topic_0066459131_p2789749017533"></a><strong id="zh-cn_topic_0066459131_b6275204417533"><a name="zh-cn_topic_0066459131_b6275204417533"></a><a name="zh-cn_topic_0066459131_b6275204417533"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p328508017533"><a name="zh-cn_topic_0066459131_p328508017533"></a><a name="zh-cn_topic_0066459131_p328508017533"></a><strong id="zh-cn_topic_0066459131_b4510425117533"><a name="zh-cn_topic_0066459131_b4510425117533"></a><a name="zh-cn_topic_0066459131_b4510425117533"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row3163915817533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1146506117533"><a name="zh-cn_topic_0066459131_p1146506117533"></a><a name="zh-cn_topic_0066459131_p1146506117533"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3653061917533"><a name="zh-cn_topic_0066459131_p3653061917533"></a><a name="zh-cn_topic_0066459131_p3653061917533"></a><strong id="zh-cn_topic_0066459131_b5625474017533"><a name="zh-cn_topic_0066459131_b5625474017533"></a><a name="zh-cn_topic_0066459131_b5625474017533"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p619013817533"><a name="zh-cn_topic_0066459131_p619013817533"></a><a name="zh-cn_topic_0066459131_p619013817533"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3287558717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1631696617533"><a name="zh-cn_topic_0066459131_p1631696617533"></a><a name="zh-cn_topic_0066459131_p1631696617533"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4660583117533"><a name="zh-cn_topic_0066459131_p4660583117533"></a><a name="zh-cn_topic_0066459131_p4660583117533"></a>hdfs</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1697596117533"><a name="zh-cn_topic_0066459131_p1697596117533"></a><a name="zh-cn_topic_0066459131_p1697596117533"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue33124174151328"><a name="zh-cn_topic_0066459131_parmvalue33124174151328"></a><a name="zh-cn_topic_0066459131_parmvalue33124174151328"></a>“hdfs”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row354350917533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2744483317533"><a name="zh-cn_topic_0066459131_p2744483317533"></a><a name="zh-cn_topic_0066459131_p2744483317533"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p843901117533"><a name="zh-cn_topic_0066459131_p843901117533"></a><a name="zh-cn_topic_0066459131_p843901117533"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1247131417533"><a name="zh-cn_topic_0066459131_p1247131417533"></a><a name="zh-cn_topic_0066459131_p1247131417533"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1872652217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3189158617533"><a name="zh-cn_topic_0066459131_p3189158617533"></a><a name="zh-cn_topic_0066459131_p3189158617533"></a>hdfs.path</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3308166317533"><a name="zh-cn_topic_0066459131_p3308166317533"></a><a name="zh-cn_topic_0066459131_p3308166317533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6236902817533"><a name="zh-cn_topic_0066459131_p6236902817533"></a><a name="zh-cn_topic_0066459131_p6236902817533"></a>HDFS路径。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5524570517533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3432097517533"><a name="zh-cn_topic_0066459131_p3432097517533"></a><a name="zh-cn_topic_0066459131_p3432097517533"></a>hdfs.inUseSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2853556817533"><a name="zh-cn_topic_0066459131_p2853556817533"></a><a name="zh-cn_topic_0066459131_p2853556817533"></a>.tmp</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2967970317533"><a name="zh-cn_topic_0066459131_p2967970317533"></a><a name="zh-cn_topic_0066459131_p2967970317533"></a>正在写入的HDFS文件后缀。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3005033717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2744930317533"><a name="zh-cn_topic_0066459131_p2744930317533"></a><a name="zh-cn_topic_0066459131_p2744930317533"></a>hdfs.rollInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p880104717533"><a name="zh-cn_topic_0066459131_p880104717533"></a><a name="zh-cn_topic_0066459131_p880104717533"></a>30</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4179621617533"><a name="zh-cn_topic_0066459131_p4179621617533"></a><a name="zh-cn_topic_0066459131_p4179621617533"></a>按时间滚动文件，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2923697017533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p201758517533"><a name="zh-cn_topic_0066459131_p201758517533"></a><a name="zh-cn_topic_0066459131_p201758517533"></a>hdfs.rollSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2920668217533"><a name="zh-cn_topic_0066459131_p2920668217533"></a><a name="zh-cn_topic_0066459131_p2920668217533"></a>1024</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1693104017533"><a name="zh-cn_topic_0066459131_p1693104017533"></a><a name="zh-cn_topic_0066459131_p1693104017533"></a>按大小滚动文件，单位：字节。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1787233717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p6180614017533"><a name="zh-cn_topic_0066459131_p6180614017533"></a><a name="zh-cn_topic_0066459131_p6180614017533"></a>hdfs.rollCount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4024144817533"><a name="zh-cn_topic_0066459131_p4024144817533"></a><a name="zh-cn_topic_0066459131_p4024144817533"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3833185217533"><a name="zh-cn_topic_0066459131_p3833185217533"></a><a name="zh-cn_topic_0066459131_p3833185217533"></a>按Event个数滚动文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3629870317533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2663331117533"><a name="zh-cn_topic_0066459131_p2663331117533"></a><a name="zh-cn_topic_0066459131_p2663331117533"></a>hdfs.idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p981461617533"><a name="zh-cn_topic_0066459131_p981461617533"></a><a name="zh-cn_topic_0066459131_p981461617533"></a>0</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5678643717533"><a name="zh-cn_topic_0066459131_p5678643717533"></a><a name="zh-cn_topic_0066459131_p5678643717533"></a>自动关闭空闲文件超时时间，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4287709017533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5825287417533"><a name="zh-cn_topic_0066459131_p5825287417533"></a><a name="zh-cn_topic_0066459131_p5825287417533"></a>hdfs.batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2086234517533"><a name="zh-cn_topic_0066459131_p2086234517533"></a><a name="zh-cn_topic_0066459131_p2086234517533"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1212840917533"><a name="zh-cn_topic_0066459131_p1212840917533"></a><a name="zh-cn_topic_0066459131_p1212840917533"></a>每次写入HDFS的Event个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row337576017533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5034949117533"><a name="zh-cn_topic_0066459131_p5034949117533"></a><a name="zh-cn_topic_0066459131_p5034949117533"></a>hdfs.kerberosPrincipal</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5177693117533"><a name="zh-cn_topic_0066459131_p5177693117533"></a><a name="zh-cn_topic_0066459131_p5177693117533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3318185517533"><a name="zh-cn_topic_0066459131_p3318185517533"></a><a name="zh-cn_topic_0066459131_p3318185517533"></a>认证HDFS的Kerberos用户名，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3583133817533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3038184817533"><a name="zh-cn_topic_0066459131_p3038184817533"></a><a name="zh-cn_topic_0066459131_p3038184817533"></a>hdfs.kerberosKeytab</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4501064317533"><a name="zh-cn_topic_0066459131_p4501064317533"></a><a name="zh-cn_topic_0066459131_p4501064317533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2198347917533"><a name="zh-cn_topic_0066459131_p2198347917533"></a><a name="zh-cn_topic_0066459131_p2198347917533"></a>认证HDFS的Kerberos keytab路径，未启用Kerberos认证集群不配置</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4959539917533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5404659417533"><a name="zh-cn_topic_0066459131_p5404659417533"></a><a name="zh-cn_topic_0066459131_p5404659417533"></a>hdfs.fileCloseByEndEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1569800217533"><a name="zh-cn_topic_0066459131_p1569800217533"></a><a name="zh-cn_topic_0066459131_p1569800217533"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6357863017533"><a name="zh-cn_topic_0066459131_p6357863017533"></a><a name="zh-cn_topic_0066459131_p6357863017533"></a>收到最后一个Event时是否关闭文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4046792617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4370540717533"><a name="zh-cn_topic_0066459131_p4370540717533"></a><a name="zh-cn_topic_0066459131_p4370540717533"></a>hdfs.batchCallTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5047708517533"><a name="zh-cn_topic_0066459131_p5047708517533"></a><a name="zh-cn_topic_0066459131_p5047708517533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6211212417533"><a name="zh-cn_topic_0066459131_p6211212417533"></a><a name="zh-cn_topic_0066459131_p6211212417533"></a>每次写入HDFS超时控制时间，单位：毫秒。</p>
    <p id="zh-cn_topic_0066459131_p6502618017533"><a name="zh-cn_topic_0066459131_p6502618017533"></a><a name="zh-cn_topic_0066459131_p6502618017533"></a>当不配置此参数时，对每个Event写入HDFS进行超时控制。当<span class="parmname" id="zh-cn_topic_0066459131_parmname2213821217533"><a name="zh-cn_topic_0066459131_parmname2213821217533"></a><a name="zh-cn_topic_0066459131_parmname2213821217533"></a>“hdfs.batchSize”</span>大于0时，配置此参数可以提升写入HDFS性能。</p>
    <div class="note" id="zh-cn_topic_0066459131_note298511717533"><a name="zh-cn_topic_0066459131_note298511717533"></a><a name="zh-cn_topic_0066459131_note298511717533"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0066459131_p3015784117533"><a name="zh-cn_topic_0066459131_p3015784117533"></a><a name="zh-cn_topic_0066459131_p3015784117533"></a><span class="parmname" id="zh-cn_topic_0066459131_parmname4836471017533"><a name="zh-cn_topic_0066459131_parmname4836471017533"></a><a name="zh-cn_topic_0066459131_parmname4836471017533"></a>“hdfs.batchCallTimeout”</span>设置多长时间需要考虑<span class="parmname" id="zh-cn_topic_0066459131_parmname3262921217533"><a name="zh-cn_topic_0066459131_parmname3262921217533"></a><a name="zh-cn_topic_0066459131_parmname3262921217533"></a>“hdfs.batchSize”</span>的大小，<span class="parmname" id="zh-cn_topic_0066459131_parmname2522745317533"><a name="zh-cn_topic_0066459131_parmname2522745317533"></a><a name="zh-cn_topic_0066459131_parmname2522745317533"></a>“hdfs.batchSize”</span>越大，<span class="parmname" id="zh-cn_topic_0066459131_parmname2572049217533"><a name="zh-cn_topic_0066459131_parmname2572049217533"></a><a name="zh-cn_topic_0066459131_parmname2572049217533"></a>“hdfs.batchCallTimeout”</span>也要调整更长时间，设置过短时间容易导致数据写入HDFS失败。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4513599117533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2866702217533"><a name="zh-cn_topic_0066459131_p2866702217533"></a><a name="zh-cn_topic_0066459131_p2866702217533"></a>serializer.appendNewline</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4032743117533"><a name="zh-cn_topic_0066459131_p4032743117533"></a><a name="zh-cn_topic_0066459131_p4032743117533"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4529647717533"><a name="zh-cn_topic_0066459131_p4529647717533"></a><a name="zh-cn_topic_0066459131_p4529647717533"></a>将一个Event写入HDFS后是否追加换行符（'\n'），如果追加该换行符，该换行符所占用的数据量指标不会被HDFS Sink统计。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Avro Sink**

    Avro Sink把events转化为Avro events并发送到配置的主机的监听端口。常用配置如[下表](#zh-cn_topic_0066459131_table5909011917533)所示

    **表 12**  Avro Sink常用配置

    <a name="zh-cn_topic_0066459131_table5909011917533"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row3369589217533"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p660555417533"><a name="zh-cn_topic_0066459131_p660555417533"></a><a name="zh-cn_topic_0066459131_p660555417533"></a><strong id="zh-cn_topic_0066459131_b6038627417533"><a name="zh-cn_topic_0066459131_b6038627417533"></a><a name="zh-cn_topic_0066459131_b6038627417533"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p5072004717533"><a name="zh-cn_topic_0066459131_p5072004717533"></a><a name="zh-cn_topic_0066459131_p5072004717533"></a><strong id="zh-cn_topic_0066459131_b6528788417533"><a name="zh-cn_topic_0066459131_b6528788417533"></a><a name="zh-cn_topic_0066459131_b6528788417533"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p6503934917533"><a name="zh-cn_topic_0066459131_p6503934917533"></a><a name="zh-cn_topic_0066459131_p6503934917533"></a><strong id="zh-cn_topic_0066459131_b1468313417533"><a name="zh-cn_topic_0066459131_b1468313417533"></a><a name="zh-cn_topic_0066459131_b1468313417533"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row1474865317533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4501272017533"><a name="zh-cn_topic_0066459131_p4501272017533"></a><a name="zh-cn_topic_0066459131_p4501272017533"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p6514724917533"><a name="zh-cn_topic_0066459131_p6514724917533"></a><a name="zh-cn_topic_0066459131_p6514724917533"></a><strong id="zh-cn_topic_0066459131_b2215166417533"><a name="zh-cn_topic_0066459131_b2215166417533"></a><a name="zh-cn_topic_0066459131_b2215166417533"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4243581117533"><a name="zh-cn_topic_0066459131_p4243581117533"></a><a name="zh-cn_topic_0066459131_p4243581117533"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6591262317533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p6562901917533"><a name="zh-cn_topic_0066459131_p6562901917533"></a><a name="zh-cn_topic_0066459131_p6562901917533"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1435033317533"><a name="zh-cn_topic_0066459131_p1435033317533"></a><a name="zh-cn_topic_0066459131_p1435033317533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2152634817533"><a name="zh-cn_topic_0066459131_p2152634817533"></a><a name="zh-cn_topic_0066459131_p2152634817533"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue42137187151551"><a name="zh-cn_topic_0066459131_parmvalue42137187151551"></a><a name="zh-cn_topic_0066459131_parmvalue42137187151551"></a>“avro”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5386547617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5634270017533"><a name="zh-cn_topic_0066459131_p5634270017533"></a><a name="zh-cn_topic_0066459131_p5634270017533"></a>hostname</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p35597717533"><a name="zh-cn_topic_0066459131_p35597717533"></a><a name="zh-cn_topic_0066459131_p35597717533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2883415817533"><a name="zh-cn_topic_0066459131_p2883415817533"></a><a name="zh-cn_topic_0066459131_p2883415817533"></a>绑定关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row306784317533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1502724117533"><a name="zh-cn_topic_0066459131_p1502724117533"></a><a name="zh-cn_topic_0066459131_p1502724117533"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p924698617533"><a name="zh-cn_topic_0066459131_p924698617533"></a><a name="zh-cn_topic_0066459131_p924698617533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1080843317533"><a name="zh-cn_topic_0066459131_p1080843317533"></a><a name="zh-cn_topic_0066459131_p1080843317533"></a>监听端口。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4814989917533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2761059317533"><a name="zh-cn_topic_0066459131_p2761059317533"></a><a name="zh-cn_topic_0066459131_p2761059317533"></a>batch-size</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2186553717533"><a name="zh-cn_topic_0066459131_p2186553717533"></a><a name="zh-cn_topic_0066459131_p2186553717533"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2627808217533"><a name="zh-cn_topic_0066459131_p2627808217533"></a><a name="zh-cn_topic_0066459131_p2627808217533"></a>批次发送的Event个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4394291617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3069591517533"><a name="zh-cn_topic_0066459131_p3069591517533"></a><a name="zh-cn_topic_0066459131_p3069591517533"></a>ssl</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p334117217533"><a name="zh-cn_topic_0066459131_p334117217533"></a><a name="zh-cn_topic_0066459131_p334117217533"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p219951417533"><a name="zh-cn_topic_0066459131_p219951417533"></a><a name="zh-cn_topic_0066459131_p219951417533"></a>是否使用SSL加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2627919517533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5994192617533"><a name="zh-cn_topic_0066459131_p5994192617533"></a><a name="zh-cn_topic_0066459131_p5994192617533"></a>truststore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2345784217533"><a name="zh-cn_topic_0066459131_p2345784217533"></a><a name="zh-cn_topic_0066459131_p2345784217533"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2103704617533"><a name="zh-cn_topic_0066459131_p2103704617533"></a><a name="zh-cn_topic_0066459131_p2103704617533"></a>Java信任库类型。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2523949717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3518616917533"><a name="zh-cn_topic_0066459131_p3518616917533"></a><a name="zh-cn_topic_0066459131_p3518616917533"></a>truststore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3150747417533"><a name="zh-cn_topic_0066459131_p3150747417533"></a><a name="zh-cn_topic_0066459131_p3150747417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p196860717533"><a name="zh-cn_topic_0066459131_p196860717533"></a><a name="zh-cn_topic_0066459131_p196860717533"></a>Java信任库文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1399905217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2582888417533"><a name="zh-cn_topic_0066459131_p2582888417533"></a><a name="zh-cn_topic_0066459131_p2582888417533"></a>truststore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1176485117533"><a name="zh-cn_topic_0066459131_p1176485117533"></a><a name="zh-cn_topic_0066459131_p1176485117533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1342889917533"><a name="zh-cn_topic_0066459131_p1342889917533"></a><a name="zh-cn_topic_0066459131_p1342889917533"></a>Java信任库密码。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3563709817533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5888260517533"><a name="zh-cn_topic_0066459131_p5888260517533"></a><a name="zh-cn_topic_0066459131_p5888260517533"></a>keystore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p476166117533"><a name="zh-cn_topic_0066459131_p476166117533"></a><a name="zh-cn_topic_0066459131_p476166117533"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5015023317533"><a name="zh-cn_topic_0066459131_p5015023317533"></a><a name="zh-cn_topic_0066459131_p5015023317533"></a>密钥存储类型。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6088478817533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5229843417533"><a name="zh-cn_topic_0066459131_p5229843417533"></a><a name="zh-cn_topic_0066459131_p5229843417533"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p831478117533"><a name="zh-cn_topic_0066459131_p831478117533"></a><a name="zh-cn_topic_0066459131_p831478117533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p240867317533"><a name="zh-cn_topic_0066459131_p240867317533"></a><a name="zh-cn_topic_0066459131_p240867317533"></a>密钥存储文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row118572917533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1109218817533"><a name="zh-cn_topic_0066459131_p1109218817533"></a><a name="zh-cn_topic_0066459131_p1109218817533"></a>keystore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2605204417533"><a name="zh-cn_topic_0066459131_p2605204417533"></a><a name="zh-cn_topic_0066459131_p2605204417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2984080017533"><a name="zh-cn_topic_0066459131_p2984080017533"></a><a name="zh-cn_topic_0066459131_p2984080017533"></a>密钥存储密码</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **HBase Sink**

    HBase Sink将数据写入到HBase中。常用配置如[下表](#zh-cn_topic_0066459131_table3075886317533)所示：

    **表 13**  HBase Sink常用配置

    <a name="zh-cn_topic_0066459131_table3075886317533"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row1477999117533"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p1837940317533"><a name="zh-cn_topic_0066459131_p1837940317533"></a><a name="zh-cn_topic_0066459131_p1837940317533"></a><strong id="zh-cn_topic_0066459131_b4678139817533"><a name="zh-cn_topic_0066459131_b4678139817533"></a><a name="zh-cn_topic_0066459131_b4678139817533"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p4392121617533"><a name="zh-cn_topic_0066459131_p4392121617533"></a><a name="zh-cn_topic_0066459131_p4392121617533"></a><strong id="zh-cn_topic_0066459131_b1233667517533"><a name="zh-cn_topic_0066459131_b1233667517533"></a><a name="zh-cn_topic_0066459131_b1233667517533"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p763900917533"><a name="zh-cn_topic_0066459131_p763900917533"></a><a name="zh-cn_topic_0066459131_p763900917533"></a><strong id="zh-cn_topic_0066459131_b84877817533"><a name="zh-cn_topic_0066459131_b84877817533"></a><a name="zh-cn_topic_0066459131_b84877817533"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row5282707217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5632859317533"><a name="zh-cn_topic_0066459131_p5632859317533"></a><a name="zh-cn_topic_0066459131_p5632859317533"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p6002859917533"><a name="zh-cn_topic_0066459131_p6002859917533"></a><a name="zh-cn_topic_0066459131_p6002859917533"></a><strong id="zh-cn_topic_0066459131_b6632216717533"><a name="zh-cn_topic_0066459131_b6632216717533"></a><a name="zh-cn_topic_0066459131_b6632216717533"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3047834717533"><a name="zh-cn_topic_0066459131_p3047834717533"></a><a name="zh-cn_topic_0066459131_p3047834717533"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row973895017533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p568160617533"><a name="zh-cn_topic_0066459131_p568160617533"></a><a name="zh-cn_topic_0066459131_p568160617533"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5755697517533"><a name="zh-cn_topic_0066459131_p5755697517533"></a><a name="zh-cn_topic_0066459131_p5755697517533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3160340417533"><a name="zh-cn_topic_0066459131_p3160340417533"></a><a name="zh-cn_topic_0066459131_p3160340417533"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue50391314151643"><a name="zh-cn_topic_0066459131_parmvalue50391314151643"></a><a name="zh-cn_topic_0066459131_parmvalue50391314151643"></a>“hbase”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2993673717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2054168917533"><a name="zh-cn_topic_0066459131_p2054168917533"></a><a name="zh-cn_topic_0066459131_p2054168917533"></a>table</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5326410417533"><a name="zh-cn_topic_0066459131_p5326410417533"></a><a name="zh-cn_topic_0066459131_p5326410417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1942519217533"><a name="zh-cn_topic_0066459131_p1942519217533"></a><a name="zh-cn_topic_0066459131_p1942519217533"></a>HBase表名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6054421517533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p99517817533"><a name="zh-cn_topic_0066459131_p99517817533"></a><a name="zh-cn_topic_0066459131_p99517817533"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1350055417533"><a name="zh-cn_topic_0066459131_p1350055417533"></a><a name="zh-cn_topic_0066459131_p1350055417533"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1980306217533"><a name="zh-cn_topic_0066459131_p1980306217533"></a><a name="zh-cn_topic_0066459131_p1980306217533"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5172396117533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p802703117533"><a name="zh-cn_topic_0066459131_p802703117533"></a><a name="zh-cn_topic_0066459131_p802703117533"></a>columnFamily</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4620979417533"><a name="zh-cn_topic_0066459131_p4620979417533"></a><a name="zh-cn_topic_0066459131_p4620979417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5200584617533"><a name="zh-cn_topic_0066459131_p5200584617533"></a><a name="zh-cn_topic_0066459131_p5200584617533"></a>HBase列族名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3091574217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p6286247317533"><a name="zh-cn_topic_0066459131_p6286247317533"></a><a name="zh-cn_topic_0066459131_p6286247317533"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5869556117533"><a name="zh-cn_topic_0066459131_p5869556117533"></a><a name="zh-cn_topic_0066459131_p5869556117533"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5671998117533"><a name="zh-cn_topic_0066459131_p5671998117533"></a><a name="zh-cn_topic_0066459131_p5671998117533"></a>每次写入HBase的Event个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row2279139517533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p980622217533"><a name="zh-cn_topic_0066459131_p980622217533"></a><a name="zh-cn_topic_0066459131_p980622217533"></a>kerberosPrincipal</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5610652417533"><a name="zh-cn_topic_0066459131_p5610652417533"></a><a name="zh-cn_topic_0066459131_p5610652417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4833463517533"><a name="zh-cn_topic_0066459131_p4833463517533"></a><a name="zh-cn_topic_0066459131_p4833463517533"></a>认证HBase的Kerberos用户名，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3935012817533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p379596517533"><a name="zh-cn_topic_0066459131_p379596517533"></a><a name="zh-cn_topic_0066459131_p379596517533"></a>kerberosKeytab</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3903776417533"><a name="zh-cn_topic_0066459131_p3903776417533"></a><a name="zh-cn_topic_0066459131_p3903776417533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p794234417533"><a name="zh-cn_topic_0066459131_p794234417533"></a><a name="zh-cn_topic_0066459131_p794234417533"></a>认证HBase的Kerberos keytab路径，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Kafka Sink**

    Kafka Sink将数据写入到Kafka中。常用配置如[下表](#zh-cn_topic_0066459131_table4052439217533)所示：

    **表 14**  Kafka Sink常用配置

    <a name="zh-cn_topic_0066459131_table4052439217533"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row1712888917533"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p565891217533"><a name="zh-cn_topic_0066459131_p565891217533"></a><a name="zh-cn_topic_0066459131_p565891217533"></a><strong id="zh-cn_topic_0066459131_b808530817533"><a name="zh-cn_topic_0066459131_b808530817533"></a><a name="zh-cn_topic_0066459131_b808530817533"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p3170621317533"><a name="zh-cn_topic_0066459131_p3170621317533"></a><a name="zh-cn_topic_0066459131_p3170621317533"></a><strong id="zh-cn_topic_0066459131_b5571869517533"><a name="zh-cn_topic_0066459131_b5571869517533"></a><a name="zh-cn_topic_0066459131_b5571869517533"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p2838062017533"><a name="zh-cn_topic_0066459131_p2838062017533"></a><a name="zh-cn_topic_0066459131_p2838062017533"></a><strong id="zh-cn_topic_0066459131_b1806648317533"><a name="zh-cn_topic_0066459131_b1806648317533"></a><a name="zh-cn_topic_0066459131_b1806648317533"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row6507698217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4526278717533"><a name="zh-cn_topic_0066459131_p4526278717533"></a><a name="zh-cn_topic_0066459131_p4526278717533"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4611977317533"><a name="zh-cn_topic_0066459131_p4611977317533"></a><a name="zh-cn_topic_0066459131_p4611977317533"></a><strong id="zh-cn_topic_0066459131_b4240712117533"><a name="zh-cn_topic_0066459131_b4240712117533"></a><a name="zh-cn_topic_0066459131_b4240712117533"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4471415717533"><a name="zh-cn_topic_0066459131_p4471415717533"></a><a name="zh-cn_topic_0066459131_p4471415717533"></a>与之相连的Channel</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row916384417533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4882192717533"><a name="zh-cn_topic_0066459131_p4882192717533"></a><a name="zh-cn_topic_0066459131_p4882192717533"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p6226197517533"><a name="zh-cn_topic_0066459131_p6226197517533"></a><a name="zh-cn_topic_0066459131_p6226197517533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1005518717533"><a name="zh-cn_topic_0066459131_p1005518717533"></a><a name="zh-cn_topic_0066459131_p1005518717533"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue54180481151747"><a name="zh-cn_topic_0066459131_parmvalue54180481151747"></a><a name="zh-cn_topic_0066459131_parmvalue54180481151747"></a>“org.apache.flume.sink.kafka.KafkaSink”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4383340617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1536574017533"><a name="zh-cn_topic_0066459131_p1536574017533"></a><a name="zh-cn_topic_0066459131_p1536574017533"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3666544717533"><a name="zh-cn_topic_0066459131_p3666544717533"></a><a name="zh-cn_topic_0066459131_p3666544717533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1711124317533"><a name="zh-cn_topic_0066459131_p1711124317533"></a><a name="zh-cn_topic_0066459131_p1711124317533"></a>Kafkabrokers列表，多个用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3124108317533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5895634217533"><a name="zh-cn_topic_0066459131_p5895634217533"></a><a name="zh-cn_topic_0066459131_p5895634217533"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1073440617533"><a name="zh-cn_topic_0066459131_p1073440617533"></a><a name="zh-cn_topic_0066459131_p1073440617533"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6418053817533"><a name="zh-cn_topic_0066459131_p6418053817533"></a><a name="zh-cn_topic_0066459131_p6418053817533"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6547925617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1273429117533"><a name="zh-cn_topic_0066459131_p1273429117533"></a><a name="zh-cn_topic_0066459131_p1273429117533"></a>kafka.topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2484465717533"><a name="zh-cn_topic_0066459131_p2484465717533"></a><a name="zh-cn_topic_0066459131_p2484465717533"></a>default-flume-topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p6626024017533"><a name="zh-cn_topic_0066459131_p6626024017533"></a><a name="zh-cn_topic_0066459131_p6626024017533"></a>数据写入的topic。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6300127717533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5244239417533"><a name="zh-cn_topic_0066459131_p5244239417533"></a><a name="zh-cn_topic_0066459131_p5244239417533"></a>flumeBatchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1997553717533"><a name="zh-cn_topic_0066459131_p1997553717533"></a><a name="zh-cn_topic_0066459131_p1997553717533"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p740582917533"><a name="zh-cn_topic_0066459131_p740582917533"></a><a name="zh-cn_topic_0066459131_p740582917533"></a>每次写入Kafka的Event个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row6445154617533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3014058617533"><a name="zh-cn_topic_0066459131_p3014058617533"></a><a name="zh-cn_topic_0066459131_p3014058617533"></a>kafka.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2546843617533"><a name="zh-cn_topic_0066459131_p2546843617533"></a><a name="zh-cn_topic_0066459131_p2546843617533"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4967746317533"><a name="zh-cn_topic_0066459131_p4967746317533"></a><a name="zh-cn_topic_0066459131_p4967746317533"></a>Kafka安全协议，未启用Kerberos认证集群下须配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue33127599151836"><a name="zh-cn_topic_0066459131_parmvalue33127599151836"></a><a name="zh-cn_topic_0066459131_parmvalue33127599151836"></a>“PLAINTEXT”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row260655631508"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p309358951508"><a name="zh-cn_topic_0066459131_p309358951508"></a><a name="zh-cn_topic_0066459131_p309358951508"></a><span id="zh-cn_topic_0066459131_ph1667423615022"><a name="zh-cn_topic_0066459131_ph1667423615022"></a><a name="zh-cn_topic_0066459131_ph1667423615022"></a>kafka.kerberos.domain.name</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p227795341508"><a name="zh-cn_topic_0066459131_p227795341508"></a><a name="zh-cn_topic_0066459131_p227795341508"></a><span id="zh-cn_topic_0066459131_ph252956931517"><a name="zh-cn_topic_0066459131_ph252956931517"></a><a name="zh-cn_topic_0066459131_ph252956931517"></a>-</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p332029861508"><a name="zh-cn_topic_0066459131_p332029861508"></a><a name="zh-cn_topic_0066459131_p332029861508"></a><span id="zh-cn_topic_0066459131_ph5791891715125"><a name="zh-cn_topic_0066459131_ph5791891715125"></a><a name="zh-cn_topic_0066459131_ph5791891715125"></a>Kafka Domain名称。安全集群必填。</span></p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1303549217533"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4319300317533"><a name="zh-cn_topic_0066459131_p4319300317533"></a><a name="zh-cn_topic_0066459131_p4319300317533"></a>Other Kafka Producer Properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p897233717533"><a name="zh-cn_topic_0066459131_p897233717533"></a><a name="zh-cn_topic_0066459131_p897233717533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5567073317533"><a name="zh-cn_topic_0066459131_p5567073317533"></a><a name="zh-cn_topic_0066459131_p5567073317533"></a>其他Kafka配置，可以接受任意Kafka支持的生产参数配置，配置需要加前缀<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue24113161151851"><a name="zh-cn_topic_0066459131_parmvalue24113161151851"></a><a name="zh-cn_topic_0066459131_parmvalue24113161151851"></a>“.kafka”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **OBS Sink**

    OBS Sink将数据写入OBS。由于和HDFS使用了相同的文件系统接口，因此，配置参数也大致相同。常用配置如[下表](#zh-cn_topic_0066459131_table4713287117555)所示：

    **表 15**  OBS Sink常用配置

    <a name="zh-cn_topic_0066459131_table4713287117555"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0066459131_row1431180717555"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p1840572417555"><a name="zh-cn_topic_0066459131_p1840572417555"></a><a name="zh-cn_topic_0066459131_p1840572417555"></a><strong id="zh-cn_topic_0066459131_b3143379417555"><a name="zh-cn_topic_0066459131_b3143379417555"></a><a name="zh-cn_topic_0066459131_b3143379417555"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p6310938517555"><a name="zh-cn_topic_0066459131_p6310938517555"></a><a name="zh-cn_topic_0066459131_p6310938517555"></a><strong id="zh-cn_topic_0066459131_b3111355617555"><a name="zh-cn_topic_0066459131_b3111355617555"></a><a name="zh-cn_topic_0066459131_b3111355617555"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p3717011117555"><a name="zh-cn_topic_0066459131_p3717011117555"></a><a name="zh-cn_topic_0066459131_p3717011117555"></a><strong id="zh-cn_topic_0066459131_b6609554417555"><a name="zh-cn_topic_0066459131_b6609554417555"></a><a name="zh-cn_topic_0066459131_b6609554417555"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0066459131_row5213886517555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p6249850617555"><a name="zh-cn_topic_0066459131_p6249850617555"></a><a name="zh-cn_topic_0066459131_p6249850617555"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2921418717555"><a name="zh-cn_topic_0066459131_p2921418717555"></a><a name="zh-cn_topic_0066459131_p2921418717555"></a><strong id="zh-cn_topic_0066459131_b6160109417555"><a name="zh-cn_topic_0066459131_b6160109417555"></a><a name="zh-cn_topic_0066459131_b6160109417555"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2363274317555"><a name="zh-cn_topic_0066459131_p2363274317555"></a><a name="zh-cn_topic_0066459131_p2363274317555"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1136810317555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4840117017555"><a name="zh-cn_topic_0066459131_p4840117017555"></a><a name="zh-cn_topic_0066459131_p4840117017555"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2818071017555"><a name="zh-cn_topic_0066459131_p2818071017555"></a><a name="zh-cn_topic_0066459131_p2818071017555"></a>hdfs</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p93613717555"><a name="zh-cn_topic_0066459131_p93613717555"></a><a name="zh-cn_topic_0066459131_p93613717555"></a>类型，需配置为<span class="parmvalue" id="zh-cn_topic_0066459131_parmvalue842524117555"><a name="zh-cn_topic_0066459131_parmvalue842524117555"></a><a name="zh-cn_topic_0066459131_parmvalue842524117555"></a>“hdfs”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row871831017555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3509449917555"><a name="zh-cn_topic_0066459131_p3509449917555"></a><a name="zh-cn_topic_0066459131_p3509449917555"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2408215217555"><a name="zh-cn_topic_0066459131_p2408215217555"></a><a name="zh-cn_topic_0066459131_p2408215217555"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p449731017555"><a name="zh-cn_topic_0066459131_p449731017555"></a><a name="zh-cn_topic_0066459131_p449731017555"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row4047579517555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5731394017555"><a name="zh-cn_topic_0066459131_p5731394017555"></a><a name="zh-cn_topic_0066459131_p5731394017555"></a>hdfs.path</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p1191759517555"><a name="zh-cn_topic_0066459131_p1191759517555"></a><a name="zh-cn_topic_0066459131_p1191759517555"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p2580110117555"><a name="zh-cn_topic_0066459131_p2580110117555"></a><a name="zh-cn_topic_0066459131_p2580110117555"></a>OBS路径。格式s3a://AK:SK@桶/路径/ 例如 s3a://AK:SK@obs-nemon-sink/obs-sink/</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3088332317555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1852121117555"><a name="zh-cn_topic_0066459131_p1852121117555"></a><a name="zh-cn_topic_0066459131_p1852121117555"></a>hdfs.inUseSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2382313217555"><a name="zh-cn_topic_0066459131_p2382313217555"></a><a name="zh-cn_topic_0066459131_p2382313217555"></a>.tmp</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p5062554117555"><a name="zh-cn_topic_0066459131_p5062554117555"></a><a name="zh-cn_topic_0066459131_p5062554117555"></a>正在写入的OBS文件后缀。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5297669317555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p6325372617555"><a name="zh-cn_topic_0066459131_p6325372617555"></a><a name="zh-cn_topic_0066459131_p6325372617555"></a>hdfs.rollInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2327818017555"><a name="zh-cn_topic_0066459131_p2327818017555"></a><a name="zh-cn_topic_0066459131_p2327818017555"></a>30</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p648439817555"><a name="zh-cn_topic_0066459131_p648439817555"></a><a name="zh-cn_topic_0066459131_p648439817555"></a>按时间滚动文件，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5835958417555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2950586817555"><a name="zh-cn_topic_0066459131_p2950586817555"></a><a name="zh-cn_topic_0066459131_p2950586817555"></a>hdfs.rollSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4116510417555"><a name="zh-cn_topic_0066459131_p4116510417555"></a><a name="zh-cn_topic_0066459131_p4116510417555"></a>1024</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4603915717555"><a name="zh-cn_topic_0066459131_p4603915717555"></a><a name="zh-cn_topic_0066459131_p4603915717555"></a>按大小滚动文件，单位：字节。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row1169923517555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p811401217555"><a name="zh-cn_topic_0066459131_p811401217555"></a><a name="zh-cn_topic_0066459131_p811401217555"></a>hdfs.rollCount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p5325524117555"><a name="zh-cn_topic_0066459131_p5325524117555"></a><a name="zh-cn_topic_0066459131_p5325524117555"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1870728317555"><a name="zh-cn_topic_0066459131_p1870728317555"></a><a name="zh-cn_topic_0066459131_p1870728317555"></a>按Event个数滚动文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3414782217555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1451018917555"><a name="zh-cn_topic_0066459131_p1451018917555"></a><a name="zh-cn_topic_0066459131_p1451018917555"></a>hdfs.idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p3447468517555"><a name="zh-cn_topic_0066459131_p3447468517555"></a><a name="zh-cn_topic_0066459131_p3447468517555"></a>0</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4098611817555"><a name="zh-cn_topic_0066459131_p4098611817555"></a><a name="zh-cn_topic_0066459131_p4098611817555"></a>自动关闭空闲文件超时时间，单位：秒。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3333074317555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p1543562317555"><a name="zh-cn_topic_0066459131_p1543562317555"></a><a name="zh-cn_topic_0066459131_p1543562317555"></a>hdfs.batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p4232592317555"><a name="zh-cn_topic_0066459131_p4232592317555"></a><a name="zh-cn_topic_0066459131_p4232592317555"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p584776417555"><a name="zh-cn_topic_0066459131_p584776417555"></a><a name="zh-cn_topic_0066459131_p584776417555"></a>每次写入OBS的Event个数。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5262988417555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p3516223117555"><a name="zh-cn_topic_0066459131_p3516223117555"></a><a name="zh-cn_topic_0066459131_p3516223117555"></a>hdfs.calltimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2956847517555"><a name="zh-cn_topic_0066459131_p2956847517555"></a><a name="zh-cn_topic_0066459131_p2956847517555"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p4623623817555"><a name="zh-cn_topic_0066459131_p4623623817555"></a><a name="zh-cn_topic_0066459131_p4623623817555"></a>和OBS交互的超时时间。单位毫秒。由于OBS rename等操作实际是拷贝文件，因此需要将这个超时时间调整的尽量大，比如1000000。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3178019517555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p2405900917555"><a name="zh-cn_topic_0066459131_p2405900917555"></a><a name="zh-cn_topic_0066459131_p2405900917555"></a>hdfs.fileCloseByEndEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p262275217555"><a name="zh-cn_topic_0066459131_p262275217555"></a><a name="zh-cn_topic_0066459131_p262275217555"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1111639217555"><a name="zh-cn_topic_0066459131_p1111639217555"></a><a name="zh-cn_topic_0066459131_p1111639217555"></a>收到最后一个Event时是否关闭文件。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row3293866617555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p5078630517555"><a name="zh-cn_topic_0066459131_p5078630517555"></a><a name="zh-cn_topic_0066459131_p5078630517555"></a>hdfs.batchCallTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2005006917555"><a name="zh-cn_topic_0066459131_p2005006917555"></a><a name="zh-cn_topic_0066459131_p2005006917555"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p1344289317555"><a name="zh-cn_topic_0066459131_p1344289317555"></a><a name="zh-cn_topic_0066459131_p1344289317555"></a>每次写入OBS超时控制时间，单位：毫秒。</p>
    <p id="zh-cn_topic_0066459131_p5387717817555"><a name="zh-cn_topic_0066459131_p5387717817555"></a><a name="zh-cn_topic_0066459131_p5387717817555"></a>当不配置此参数时，对每个Event写入OBS进行超时控制。当<span class="parmname" id="zh-cn_topic_0066459131_parmname1513256217555"><a name="zh-cn_topic_0066459131_parmname1513256217555"></a><a name="zh-cn_topic_0066459131_parmname1513256217555"></a>“hdfs.batchSize”</span>大于0时，配置此参数可以提升写入OBS性能。</p>
    <div class="note" id="zh-cn_topic_0066459131_note197533217555"><a name="zh-cn_topic_0066459131_note197533217555"></a><a name="zh-cn_topic_0066459131_note197533217555"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0066459131_p1777799517555"><a name="zh-cn_topic_0066459131_p1777799517555"></a><a name="zh-cn_topic_0066459131_p1777799517555"></a><span class="parmname" id="zh-cn_topic_0066459131_parmname2578423117555"><a name="zh-cn_topic_0066459131_parmname2578423117555"></a><a name="zh-cn_topic_0066459131_parmname2578423117555"></a>“hdfs.batchCallTimeout”</span>设置多长时间需要考虑<span class="parmname" id="zh-cn_topic_0066459131_parmname3073148917555"><a name="zh-cn_topic_0066459131_parmname3073148917555"></a><a name="zh-cn_topic_0066459131_parmname3073148917555"></a>“hdfs.batchSize”</span>的大小，<span class="parmname" id="zh-cn_topic_0066459131_parmname814794617555"><a name="zh-cn_topic_0066459131_parmname814794617555"></a><a name="zh-cn_topic_0066459131_parmname814794617555"></a>“hdfs.batchSize”</span>越大，<span class="parmname" id="zh-cn_topic_0066459131_parmname622265117555"><a name="zh-cn_topic_0066459131_parmname622265117555"></a><a name="zh-cn_topic_0066459131_parmname622265117555"></a>“hdfs.batchCallTimeout”</span>也要调整更长时间，设置过短时间容易导致数据写入OBS失败。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0066459131_row5600386117555"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p4001889717555"><a name="zh-cn_topic_0066459131_p4001889717555"></a><a name="zh-cn_topic_0066459131_p4001889717555"></a>serializer.appendNewline</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p2030522117555"><a name="zh-cn_topic_0066459131_p2030522117555"></a><a name="zh-cn_topic_0066459131_p2030522117555"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p3411023417555"><a name="zh-cn_topic_0066459131_p3411023417555"></a><a name="zh-cn_topic_0066459131_p3411023417555"></a>将一个Event写入OBS后是否追加换行符（'\n'），如果追加该换行符，该换行符所占用的数据量指标不会被OBS Sink统计。</p>
    </td>
    </tr>
    </tbody>
    </table>


