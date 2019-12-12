# Flume配置参数说明<a name="ZH-CN_TOPIC_0173178694"></a>

## 基本介绍<a name="sc054f7820b7a44bf8ff441600796e7a7"></a>

使用Flume需要配置Source、Channel和Sink，各模块配置参数说明可通过本节内容了解。

>![](public_sys-resources/icon-note.gif) **说明：**   
>部分配置可能需要填写加密后的信息，请参见[使用Flume客户端加密工具](使用Flume客户端加密工具.md)。  

## 常用Source配置<a name="s4ad4b577d4164449b1fb6fa42d20f60f"></a>

-   **Avro Source**

    Avro Source监听Avro端口，接收外部Avro客户端数据并放入配置的Channel中。常用配置如[下表](#tb4f2cc56cf3945f7bba26f90f1afaa79)所示：

    **表 1**  Avro Source常用配置

    <a name="tb4f2cc56cf3945f7bba26f90f1afaa79"></a>
    <table><thead align="left"><tr id="r95b12f9e77fe4f10932363bf4cf676cb"><th class="cellrowborder" valign="top" width="30.209999999999997%" id="mcps1.2.4.1.1"><p id="a79d3283c14df4c8ab76e4594c07d91fe"><a name="a79d3283c14df4c8ab76e4594c07d91fe"></a><a name="a79d3283c14df4c8ab76e4594c07d91fe"></a><strong id="ac38afe043f8740c2b3e42f06cb2c76ef"><a name="ac38afe043f8740c2b3e42f06cb2c76ef"></a><a name="ac38afe043f8740c2b3e42f06cb2c76ef"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a074fca8ccf6043aa8fa6ef79a4826302"><a name="a074fca8ccf6043aa8fa6ef79a4826302"></a><a name="a074fca8ccf6043aa8fa6ef79a4826302"></a><strong id="a34efd686ac3044008e17bddea0994a95"><a name="a34efd686ac3044008e17bddea0994a95"></a><a name="a34efd686ac3044008e17bddea0994a95"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="49.79%" id="mcps1.2.4.1.3"><p id="a5969528eca5d4b79951f01ab8cf79e7e"><a name="a5969528eca5d4b79951f01ab8cf79e7e"></a><a name="a5969528eca5d4b79951f01ab8cf79e7e"></a><strong id="ae0874bcd8e6645c69e068f4083e096d5"><a name="ae0874bcd8e6645c69e068f4083e096d5"></a><a name="ae0874bcd8e6645c69e068f4083e096d5"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r31edcca6fe76445fb77d68327851aa77"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="ae6695e92559a4c358a818184e54538a5"><a name="ae6695e92559a4c358a818184e54538a5"></a><a name="ae6695e92559a4c358a818184e54538a5"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a11feb867447c420e98fb7cf2949d06c8"><a name="a11feb867447c420e98fb7cf2949d06c8"></a><a name="a11feb867447c420e98fb7cf2949d06c8"></a><strong id="a8c13f02c4d6f46b6b48fc6b33c0814fb"><a name="a8c13f02c4d6f46b6b48fc6b33c0814fb"></a><a name="a8c13f02c4d6f46b6b48fc6b33c0814fb"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="a3c49c21dcd384a80b88cfd4597cc2342"><a name="a3c49c21dcd384a80b88cfd4597cc2342"></a><a name="a3c49c21dcd384a80b88cfd4597cc2342"></a>与之相连的Channel，可以配置多个。用空格隔开。</p>
    <p id="zh-cn_topic_0066459131_p938226317465"><a name="zh-cn_topic_0066459131_p938226317465"></a><a name="zh-cn_topic_0066459131_p938226317465"></a>在单个代理流程中，是通过channel连接sources和sinks。一个source实例对应多个channels，但一个sink实例只能对应一个channel。</p>
    <p id="zh-cn_topic_0066459131_p194537817528"><a name="zh-cn_topic_0066459131_p194537817528"></a><a name="zh-cn_topic_0066459131_p194537817528"></a>格式如下：</p>
    <p id="a611d0f461d044069bd10cc4e354323b5"><a name="a611d0f461d044069bd10cc4e354323b5"></a><a name="a611d0f461d044069bd10cc4e354323b5"></a><strong id="af8ab924e6e2f44efb108303ea7b156e3"><a name="af8ab924e6e2f44efb108303ea7b156e3"></a><a name="af8ab924e6e2f44efb108303ea7b156e3"></a>&lt;Agent &gt;.sources.&lt;Source&gt;.channels = &lt;channel1&gt; &lt;channel2&gt; &lt;channel3&gt;...</strong></p>
    <p id="afa63d5dc278a4eb3a7b8ef4e3fe933f7"><a name="afa63d5dc278a4eb3a7b8ef4e3fe933f7"></a><a name="afa63d5dc278a4eb3a7b8ef4e3fe933f7"></a><strong id="a0831e4fe4f344c7b9bf50e08c45bf5cb"><a name="a0831e4fe4f344c7b9bf50e08c45bf5cb"></a><a name="a0831e4fe4f344c7b9bf50e08c45bf5cb"></a>&lt;Agent &gt;.sinks.&lt;Sink&gt;.channels = &lt;channel1&gt;</strong></p>
    </td>
    </tr>
    <tr id="r604d95b589e34326b43b8246961c13a2"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="a3426e4f75fe44a6d9dfd6b8a87af0e60"><a name="a3426e4f75fe44a6d9dfd6b8a87af0e60"></a><a name="a3426e4f75fe44a6d9dfd6b8a87af0e60"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a2eea6991e0754b1790b05d8cba519cf4"><a name="a2eea6991e0754b1790b05d8cba519cf4"></a><a name="a2eea6991e0754b1790b05d8cba519cf4"></a>avro</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="adc087181482e49dd89b67dda99d80792"><a name="adc087181482e49dd89b67dda99d80792"></a><a name="adc087181482e49dd89b67dda99d80792"></a>类型，需设置为<span class="parmvalue" id="p82b69c4f4edf432489a0a6ccaa916eee"><a name="p82b69c4f4edf432489a0a6ccaa916eee"></a><a name="p82b69c4f4edf432489a0a6ccaa916eee"></a>“avro”</span>。每一种source的类型都为相应的固定值。</p>
    </td>
    </tr>
    <tr id="r2de7efa6ec874d2a9099dc57c5c749c6"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="a8663055e945c4a48878844456b7eea99"><a name="a8663055e945c4a48878844456b7eea99"></a><a name="a8663055e945c4a48878844456b7eea99"></a>bind</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae1c42f8fd625426b9c0a563b1d030a87"><a name="ae1c42f8fd625426b9c0a563b1d030a87"></a><a name="ae1c42f8fd625426b9c0a563b1d030a87"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="a7c695a28eabd403d9de0f04581d448fc"><a name="a7c695a28eabd403d9de0f04581d448fc"></a><a name="a7c695a28eabd403d9de0f04581d448fc"></a>绑定和source关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="r2db207cff94c415c9f253b4527d8286b"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="a0a625d0e98674d7fafbae79c18ed4a08"><a name="a0a625d0e98674d7fafbae79c18ed4a08"></a><a name="a0a625d0e98674d7fafbae79c18ed4a08"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a53a8125eba28464eb0d79d62b22f37a6"><a name="a53a8125eba28464eb0d79d62b22f37a6"></a><a name="a53a8125eba28464eb0d79d62b22f37a6"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="a2b23da59be8945389e0ed52b4ecdef75"><a name="a2b23da59be8945389e0ed52b4ecdef75"></a><a name="a2b23da59be8945389e0ed52b4ecdef75"></a>绑定端口号。</p>
    </td>
    </tr>
    <tr id="re35f373dc20d47b6a40b838e18aaa06f"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="aae0082c633b143b0962b3f544cc00685"><a name="aae0082c633b143b0962b3f544cc00685"></a><a name="aae0082c633b143b0962b3f544cc00685"></a>ssl</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a1413d624ce174241882aaf9f07a369d2"><a name="a1413d624ce174241882aaf9f07a369d2"></a><a name="a1413d624ce174241882aaf9f07a369d2"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="a4b7eced0ae1c4df290d1469df8b5dd9a"><a name="a4b7eced0ae1c4df290d1469df8b5dd9a"></a><a name="a4b7eced0ae1c4df290d1469df8b5dd9a"></a>是否使用SSL加密。</p>
    <a name="u12585ab92f9840de98769a8f2b04c52f"></a><a name="u12585ab92f9840de98769a8f2b04c52f"></a><ul id="u12585ab92f9840de98769a8f2b04c52f"><li>true</li><li>false</li></ul>
    </td>
    </tr>
    <tr id="r3b13ac897ac64a31afa6d6cd67617a10"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="ac5f4a2d58a734cd69b98d9409dd330f7"><a name="ac5f4a2d58a734cd69b98d9409dd330f7"></a><a name="ac5f4a2d58a734cd69b98d9409dd330f7"></a>truststore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a6c8979bd4f97441b8495e40bab3912a3"><a name="a6c8979bd4f97441b8495e40bab3912a3"></a><a name="a6c8979bd4f97441b8495e40bab3912a3"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="ad5ad2843816949f18cd09a0178c1a457"><a name="ad5ad2843816949f18cd09a0178c1a457"></a><a name="ad5ad2843816949f18cd09a0178c1a457"></a>Java信任库类型。填写JKS或其他java支持的truststore类型。</p>
    </td>
    </tr>
    <tr id="r5e1c7ca9fef0456291a252699801563f"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="afaa4c8155ce34fe4b8f5c183155d0880"><a name="afaa4c8155ce34fe4b8f5c183155d0880"></a><a name="afaa4c8155ce34fe4b8f5c183155d0880"></a>truststore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a70c07e177f024ad98e63aee34fe34aa2"><a name="a70c07e177f024ad98e63aee34fe34aa2"></a><a name="a70c07e177f024ad98e63aee34fe34aa2"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="acbdbde1cae6342558e1672f7c9df0423"><a name="acbdbde1cae6342558e1672f7c9df0423"></a><a name="acbdbde1cae6342558e1672f7c9df0423"></a>Java信任库文件。</p>
    </td>
    </tr>
    <tr id="r0fdf81e55cc14f60839ba95e55219eb0"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="ada4e930e46f54f8b9c085a013e0bf1fd"><a name="ada4e930e46f54f8b9c085a013e0bf1fd"></a><a name="ada4e930e46f54f8b9c085a013e0bf1fd"></a>truststore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a3c3dbb8156fc46f9a863b5f03fafbafc"><a name="a3c3dbb8156fc46f9a863b5f03fafbafc"></a><a name="a3c3dbb8156fc46f9a863b5f03fafbafc"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="addc19a81a38145da8791ada30a3b5fb2"><a name="addc19a81a38145da8791ada30a3b5fb2"></a><a name="addc19a81a38145da8791ada30a3b5fb2"></a>Java信任库密码。</p>
    </td>
    </tr>
    <tr id="r3d274aa843a64fc981c1095fcbbce84d"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="a2f85ba21081645c2833a80fc92246f58"><a name="a2f85ba21081645c2833a80fc92246f58"></a><a name="a2f85ba21081645c2833a80fc92246f58"></a>keystore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a8ad6ac2b9af247f1aef8baee37839a84"><a name="a8ad6ac2b9af247f1aef8baee37839a84"></a><a name="a8ad6ac2b9af247f1aef8baee37839a84"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="afe92623aa1534606b80ba2b5730c5c9b"><a name="afe92623aa1534606b80ba2b5730c5c9b"></a><a name="afe92623aa1534606b80ba2b5730c5c9b"></a>密钥存储类型。填写JKS或其他java支持的truststore类型。</p>
    </td>
    </tr>
    <tr id="r6cacb30f252d4150a66b934c42b7a328"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="aaf504e4a5a384bfeba6ab6f728f7b04a"><a name="aaf504e4a5a384bfeba6ab6f728f7b04a"></a><a name="aaf504e4a5a384bfeba6ab6f728f7b04a"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a9870cb5dcb8740b69b3c7f7324820b36"><a name="a9870cb5dcb8740b69b3c7f7324820b36"></a><a name="a9870cb5dcb8740b69b3c7f7324820b36"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="abbd3c10427c840bbb57113d04eea1053"><a name="abbd3c10427c840bbb57113d04eea1053"></a><a name="abbd3c10427c840bbb57113d04eea1053"></a>密钥存储文件。</p>
    </td>
    </tr>
    <tr id="r07a1888321d248f18b5863917160bafd"><td class="cellrowborder" valign="top" width="30.209999999999997%" headers="mcps1.2.4.1.1 "><p id="aae6b65b8ad7948a2a35c87cdd65c9470"><a name="aae6b65b8ad7948a2a35c87cdd65c9470"></a><a name="aae6b65b8ad7948a2a35c87cdd65c9470"></a>keystore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4f0c3f18eb2a4e75baaeb73fcacde8ed"><a name="a4f0c3f18eb2a4e75baaeb73fcacde8ed"></a><a name="a4f0c3f18eb2a4e75baaeb73fcacde8ed"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.79%" headers="mcps1.2.4.1.3 "><p id="a1c4cb8fab24d42f78422a0b703f57131"><a name="a1c4cb8fab24d42f78422a0b703f57131"></a><a name="a1c4cb8fab24d42f78422a0b703f57131"></a>密钥存储密码。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Spooling Source**

    Spooling Source监控并传输目录下新增的文件，可实现准实时数据传输。常用配置如[表 2 Spooling Source常用配置](#tdcd54cc71aac48129774ab69dce3bc28)所示：

    **表 2**  Spooling Source常用配置

    <a name="tdcd54cc71aac48129774ab69dce3bc28"></a>
    <table><thead align="left"><tr id="rc0a7ef03beb246d9961d0ba76362669c"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="abb31cf27f6e84c60acb0cbb29a7b385c"><a name="abb31cf27f6e84c60acb0cbb29a7b385c"></a><a name="abb31cf27f6e84c60acb0cbb29a7b385c"></a><strong id="a8adfbbaebc0b435f8515edccd6155c50"><a name="a8adfbbaebc0b435f8515edccd6155c50"></a><a name="a8adfbbaebc0b435f8515edccd6155c50"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a189f4169f1e14db38faf0a7101b621bd"><a name="a189f4169f1e14db38faf0a7101b621bd"></a><a name="a189f4169f1e14db38faf0a7101b621bd"></a><strong id="ab506c459c9644c408823c70bfbb664fe"><a name="ab506c459c9644c408823c70bfbb664fe"></a><a name="ab506c459c9644c408823c70bfbb664fe"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="ad1a82f299fcd4f3c959001d0b3e5d079"><a name="ad1a82f299fcd4f3c959001d0b3e5d079"></a><a name="ad1a82f299fcd4f3c959001d0b3e5d079"></a><strong id="a82bd25be4d5648ab8693842fe7fde8de"><a name="a82bd25be4d5648ab8693842fe7fde8de"></a><a name="a82bd25be4d5648ab8693842fe7fde8de"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r925a487476084b679b465db42285b9bc"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="abe6f50be881446dda904535cb3c4a8ee"><a name="abe6f50be881446dda904535cb3c4a8ee"></a><a name="abe6f50be881446dda904535cb3c4a8ee"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a583c71a601294c968e4f2861dd2b683c"><a name="a583c71a601294c968e4f2861dd2b683c"></a><a name="a583c71a601294c968e4f2861dd2b683c"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a49193c0767874180b18f706e7508260e"><a name="a49193c0767874180b18f706e7508260e"></a><a name="a49193c0767874180b18f706e7508260e"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="r6db4a07a872142d7a355bd6011f81ce5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a21d6a328f1e146b49efc4d72cb066435"><a name="a21d6a328f1e146b49efc4d72cb066435"></a><a name="a21d6a328f1e146b49efc4d72cb066435"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aaf43fca4421a4d3c9807cb5ea12e694c"><a name="aaf43fca4421a4d3c9807cb5ea12e694c"></a><a name="aaf43fca4421a4d3c9807cb5ea12e694c"></a>spooldir</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a4db268417ca14f5ab6febf5864691642"><a name="a4db268417ca14f5ab6febf5864691642"></a><a name="a4db268417ca14f5ab6febf5864691642"></a>类型，需设置为<span class="parmvalue" id="p5a0db0cd3a594787957e0677df2cf44c"><a name="p5a0db0cd3a594787957e0677df2cf44c"></a><a name="p5a0db0cd3a594787957e0677df2cf44c"></a>“spooldir”</span>。</p>
    </td>
    </tr>
    <tr id="r64530bf6c0964c4ea52c43fba6c4e789"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a7c9e410235534da385b1dbb00bd40597"><a name="a7c9e410235534da385b1dbb00bd40597"></a><a name="a7c9e410235534da385b1dbb00bd40597"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4e98807e9c9e41efab0261275a5696d9"><a name="a4e98807e9c9e41efab0261275a5696d9"></a><a name="a4e98807e9c9e41efab0261275a5696d9"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae0e09322c15a4dd988cac86fa2bc6f9c"><a name="ae0e09322c15a4dd988cac86fa2bc6f9c"></a><a name="ae0e09322c15a4dd988cac86fa2bc6f9c"></a>线程监控阈值，更新时间大于阈值时会重新启动该Source，单位：秒。</p>
    </td>
    </tr>
    <tr id="r3d8beb99995741f78ed8e8b1a8ad34d6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a7eefd728f119419ca01e559ac5f4c90c"><a name="a7eefd728f119419ca01e559ac5f4c90c"></a><a name="a7eefd728f119419ca01e559ac5f4c90c"></a>spoolDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a6f77ef29b3184e9aaf2fba37b54c15b0"><a name="a6f77ef29b3184e9aaf2fba37b54c15b0"></a><a name="a6f77ef29b3184e9aaf2fba37b54c15b0"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a8383766ae29b41f0b8acb9b4c76ebfaf"><a name="a8383766ae29b41f0b8acb9b4c76ebfaf"></a><a name="a8383766ae29b41f0b8acb9b4c76ebfaf"></a>监控目录。</p>
    </td>
    </tr>
    <tr id="r4020c36fb23640a4bd49c9f64668824a"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="abade680165f44481bd00f45f7bdde449"><a name="abade680165f44481bd00f45f7bdde449"></a><a name="abade680165f44481bd00f45f7bdde449"></a>fileSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a43aa794437b34265bb8ea0d72655b8cc"><a name="a43aa794437b34265bb8ea0d72655b8cc"></a><a name="a43aa794437b34265bb8ea0d72655b8cc"></a>.COMPLETED</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ade3f8d5ac46544999d5ca4805af17059"><a name="ade3f8d5ac46544999d5ca4805af17059"></a><a name="ade3f8d5ac46544999d5ca4805af17059"></a>文件传输完成后添加的后缀。</p>
    </td>
    </tr>
    <tr id="rcd69060d2d5a42b7a3f2ad8df4110a5b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae8cfe98e76244af0897f7744e1a230ce"><a name="ae8cfe98e76244af0897f7744e1a230ce"></a><a name="ae8cfe98e76244af0897f7744e1a230ce"></a>deletePolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a7be5a04556b1463eae321dda172eae05"><a name="a7be5a04556b1463eae321dda172eae05"></a><a name="a7be5a04556b1463eae321dda172eae05"></a>never</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5e463ba36b3341358812417fd4336f75"><a name="a5e463ba36b3341358812417fd4336f75"></a><a name="a5e463ba36b3341358812417fd4336f75"></a>文件传输完成后源文件删除策略，支持<span class="parmvalue" id="p9b0578227a504a38b5692f42fb6179bd"><a name="p9b0578227a504a38b5692f42fb6179bd"></a><a name="p9b0578227a504a38b5692f42fb6179bd"></a>“never”</span>或<span class="parmvalue" id="pe900182f828946b0b1a0d3acff7de43d"><a name="pe900182f828946b0b1a0d3acff7de43d"></a><a name="pe900182f828946b0b1a0d3acff7de43d"></a>“immediate”</span>。分别别是从不删除和立即删除。</p>
    </td>
    </tr>
    <tr id="ra83bb5d5b78c401d8a6bc67be958bf08"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae2f3d448cd4a45839dd6fdb525b7d04a"><a name="ae2f3d448cd4a45839dd6fdb525b7d04a"></a><a name="ae2f3d448cd4a45839dd6fdb525b7d04a"></a>ignorePattern</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a3ebb88c8bd2a44e19edd7467333c15fb"><a name="a3ebb88c8bd2a44e19edd7467333c15fb"></a><a name="a3ebb88c8bd2a44e19edd7467333c15fb"></a>^$</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ad8767aa3e361419e81ba38c61632d600"><a name="ad8767aa3e361419e81ba38c61632d600"></a><a name="ad8767aa3e361419e81ba38c61632d600"></a>忽略文件的正则表达式表示。</p>
    </td>
    </tr>
    <tr id="r70fc585225304949b04f64ab443ccceb"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a399ade1e2b2e49ce819ff091e314c2fd"><a name="a399ade1e2b2e49ce819ff091e314c2fd"></a><a name="a399ade1e2b2e49ce819ff091e314c2fd"></a>trackerDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aba8d643ee7e34585acbf2128399ff029"><a name="aba8d643ee7e34585acbf2128399ff029"></a><a name="aba8d643ee7e34585acbf2128399ff029"></a>.flumespool</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a49999cebe13744cbaafdb4fedf0f1e34"><a name="a49999cebe13744cbaafdb4fedf0f1e34"></a><a name="a49999cebe13744cbaafdb4fedf0f1e34"></a>传输过程中元数据存储路径。</p>
    </td>
    </tr>
    <tr id="r3a8323bc71de44f09a80224f5bfc79d4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a922bf55f330b41488c20d368c021502f"><a name="a922bf55f330b41488c20d368c021502f"></a><a name="a922bf55f330b41488c20d368c021502f"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab21e3e21575a4b0f863ebad413804f87"><a name="ab21e3e21575a4b0f863ebad413804f87"></a><a name="ab21e3e21575a4b0f863ebad413804f87"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae47ef8b64dae43d1b8e98188996ad3ea"><a name="ae47ef8b64dae43d1b8e98188996ad3ea"></a><a name="ae47ef8b64dae43d1b8e98188996ad3ea"></a>Source传输粒度。</p>
    </td>
    </tr>
    <tr id="r921c0ab815764f5096ffbc7f900a7eca"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="af3c790c6b9b94e8f9072dc7e0f4a3486"><a name="af3c790c6b9b94e8f9072dc7e0f4a3486"></a><a name="af3c790c6b9b94e8f9072dc7e0f4a3486"></a>decodeErrorPolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab2f64f30a25c4ea4b225eed8e609de67"><a name="ab2f64f30a25c4ea4b225eed8e609de67"></a><a name="ab2f64f30a25c4ea4b225eed8e609de67"></a>FAIL</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a4bc0f407e387498d8a7aec76f05b1707"><a name="a4bc0f407e387498d8a7aec76f05b1707"></a><a name="a4bc0f407e387498d8a7aec76f05b1707"></a>编码错误策略。</p>
    <p id="a077e503a47b14d85b5ce4b0e335d7bb6"><a name="a077e503a47b14d85b5ce4b0e335d7bb6"></a><a name="a077e503a47b14d85b5ce4b0e335d7bb6"></a>可选FAIL、REPLACE、IGNORE。</p>
    <p id="a8163ceb19cc641f2938f0b5a0742b938"><a name="a8163ceb19cc641f2938f0b5a0742b938"></a><a name="a8163ceb19cc641f2938f0b5a0742b938"></a>FAIL：抛出异常并让解析失败。</p>
    <p id="aac455ea5c34c4038aafc96b77474c949"><a name="aac455ea5c34c4038aafc96b77474c949"></a><a name="aac455ea5c34c4038aafc96b77474c949"></a>REPLACE：将不能识别的字符用其它字符代替，通常是字符U+FFFD。</p>
    <p id="afaa0bc7b08274f1bb1d158243a0d9ce4"><a name="afaa0bc7b08274f1bb1d158243a0d9ce4"></a><a name="afaa0bc7b08274f1bb1d158243a0d9ce4"></a>IGNORE：直接丢弃不能解析的字符串。</p>
    <div class="note" id="nf128abd49e424b61a331d1cbf9bca083"><a name="nf128abd49e424b61a331d1cbf9bca083"></a><a name="nf128abd49e424b61a331d1cbf9bca083"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="ab2824af9101445d1b0040ca6d58eb0e2"><a name="ab2824af9101445d1b0040ca6d58eb0e2"></a><a name="ab2824af9101445d1b0040ca6d58eb0e2"></a>如果文件中有编码错误，请配置“decodeErrorPolicy”为“REPLACE”或“IGNORE”，Flume遇到编码错误将跳过编码错误，继续采集后续日志。</p>
    </div></div>
    </td>
    </tr>
    <tr id="rb75118b3a9cd484c991c79d488887799"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ac697301944934bffb730ad0331e6d8f9"><a name="ac697301944934bffb730ad0331e6d8f9"></a><a name="ac697301944934bffb730ad0331e6d8f9"></a>deserializer</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac3bab9c5a9a54575bb7441b62646cf6d"><a name="ac3bab9c5a9a54575bb7441b62646cf6d"></a><a name="ac3bab9c5a9a54575bb7441b62646cf6d"></a>LINE</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5330c8c8f4d04437909ef3ecb8dd5763"><a name="a5330c8c8f4d04437909ef3ecb8dd5763"></a><a name="a5330c8c8f4d04437909ef3ecb8dd5763"></a>文件解析器，值为<span class="parmvalue" id="p5735c5e8bf184134996963a0e68c223a"><a name="p5735c5e8bf184134996963a0e68c223a"></a><a name="p5735c5e8bf184134996963a0e68c223a"></a>“LINE”</span>或&nbsp;<span class="parmvalue" id="p3187b12b2d3d4f95ae160977e377bc26"><a name="p3187b12b2d3d4f95ae160977e377bc26"></a><a name="p3187b12b2d3d4f95ae160977e377bc26"></a>“BufferedLine”</span>。</p>
    <a name="u94c4fccc4ce0464e97f915ef071157ac"></a><a name="u94c4fccc4ce0464e97f915ef071157ac"></a><ul id="u94c4fccc4ce0464e97f915ef071157ac"><li>配置为<span class="parmname" id="p51041a4b2a4b48ba8a637cf407e7bcb1"><a name="p51041a4b2a4b48ba8a637cf407e7bcb1"></a><a name="p51041a4b2a4b48ba8a637cf407e7bcb1"></a>“LINE”</span>时，对从文件读取的字符逐个转码。</li><li>配置为<span class="parmvalue" id="p50ed58ed0f2e422096be0f74a5ae1b45"><a name="p50ed58ed0f2e422096be0f74a5ae1b45"></a><a name="p50ed58ed0f2e422096be0f74a5ae1b45"></a>“BufferedLine”</span>时，对文件读取的一行或多行的字符进行批量转码，性能更优。</li></ul>
    </td>
    </tr>
    <tr id="rf4cea585325c4720a8cc77f5a78b136e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aadcd567df75b4336b61e78537eca29f5"><a name="aadcd567df75b4336b61e78537eca29f5"></a><a name="aadcd567df75b4336b61e78537eca29f5"></a>deserializer.maxLineLength</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afc6c5d7abeb84915822e4df154c5fd8d"><a name="afc6c5d7abeb84915822e4df154c5fd8d"></a><a name="afc6c5d7abeb84915822e4df154c5fd8d"></a>2048</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a32c66d9ffdd141b49c1abe89b530077a"><a name="a32c66d9ffdd141b49c1abe89b530077a"></a><a name="a32c66d9ffdd141b49c1abe89b530077a"></a>按行解析最大长度。0到 2,147,483,647。</p>
    </td>
    </tr>
    <tr id="r9b55b35a7a024e80abed9b8c08c4f8c2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p914884165858"><a name="zh-cn_topic_0066459131_p914884165858"></a><a name="zh-cn_topic_0066459131_p914884165858"></a>deserializer.maxBatchLine</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a64101eabcddf4e2fa918d8424c462543"><a name="a64101eabcddf4e2fa918d8424c462543"></a><a name="a64101eabcddf4e2fa918d8424c462543"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a96a8654bf81e44809fcf10bee29ca5d1"><a name="a96a8654bf81e44809fcf10bee29ca5d1"></a><a name="a96a8654bf81e44809fcf10bee29ca5d1"></a>按行解析最多行数，如果行数设置为多行，<span class="parmvalue" id="pc2f9bf28d62044899fd69d813f6b7fe8"><a name="pc2f9bf28d62044899fd69d813f6b7fe8"></a><a name="pc2f9bf28d62044899fd69d813f6b7fe8"></a>“maxLineLength”</span>也应该设置为相应的倍数。例如maxBatchLine设置为2，<span class="parmvalue" id="p5bbfdf67e5894df8a9b37562ab4681b7"><a name="p5bbfdf67e5894df8a9b37562ab4681b7"></a><a name="p5bbfdf67e5894df8a9b37562ab4681b7"></a>“maxLineLength”</span>相应的设置为2048*2为4096。</p>
    </td>
    </tr>
    <tr id="ra9fe198347f644aca807b0e0e85d141c"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ad279464d89b44206af6c0a74423a93ec"><a name="ad279464d89b44206af6c0a74423a93ec"></a><a name="ad279464d89b44206af6c0a74423a93ec"></a>selector.type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae0dc7b69f8654d3483fe3ab75133d7bb"><a name="ae0dc7b69f8654d3483fe3ab75133d7bb"></a><a name="ae0dc7b69f8654d3483fe3ab75133d7bb"></a>replicating</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a4a709636b86146a89c0f1b680eaa4c18"><a name="a4a709636b86146a89c0f1b680eaa4c18"></a><a name="a4a709636b86146a89c0f1b680eaa4c18"></a>选择器类型，支持<span class="parmvalue" id="p1b64a3d75bb14f63996977b80e51661b"><a name="p1b64a3d75bb14f63996977b80e51661b"></a><a name="p1b64a3d75bb14f63996977b80e51661b"></a>“replicating”</span>或<span class="parmvalue" id="p315b64c7ea534006820a7553d0ba25ce"><a name="p315b64c7ea534006820a7553d0ba25ce"></a><a name="p315b64c7ea534006820a7553d0ba25ce"></a>“multiplexing”</span>。</p>
    <a name="u7a78d9c83d2b49f4be4ecbcf3d5dc988"></a><a name="u7a78d9c83d2b49f4be4ecbcf3d5dc988"></a><ul id="u7a78d9c83d2b49f4be4ecbcf3d5dc988"><li><span class="parmvalue" id="pd642f62047744352ab9f76e0564b4fc4"><a name="pd642f62047744352ab9f76e0564b4fc4"></a><a name="pd642f62047744352ab9f76e0564b4fc4"></a>“replicating”</span>表示同样的内容会发给每一个channel。</li><li><span class="parmvalue" id="p42395d6736854e3aa1c80023ab77e5a1"><a name="p42395d6736854e3aa1c80023ab77e5a1"></a><a name="p42395d6736854e3aa1c80023ab77e5a1"></a>“multiplexing”</span>表示根据分发规则，有选择地发给某些channel。</li></ul>
    </td>
    </tr>
    <tr id="r923f8ce7ad0a4cf5aaf55f01243ed0aa"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a778e3138fe404571b9efffce2e5df88f"><a name="a778e3138fe404571b9efffce2e5df88f"></a><a name="a778e3138fe404571b9efffce2e5df88f"></a>interceptors</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a328d73fcd3ca47a380b99c237b7ca656"><a name="a328d73fcd3ca47a380b99c237b7ca656"></a><a name="a328d73fcd3ca47a380b99c237b7ca656"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a2bdc73924b2e4d819304c9aac8c304d4"><a name="a2bdc73924b2e4d819304c9aac8c304d4"></a><a name="a2bdc73924b2e4d819304c9aac8c304d4"></a>拦截器配置。详细配置可参考<a href="https://flume.apache.org/FlumeUserGuide.html#flume-interceptors" target="_blank" rel="noopener noreferrer">flume官方文档</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Spooling Source在按行读取过程中，会忽略掉每一个Event的最后一个换行符，该换行符所占用的数据量指标不会被Flume统计。  

-   **Kafka Source**

    Kafka Source从Kafka的topic中消费数据，可以设置多个Source消费同一个topic的数据，每个Source会消费topic的不同partitions。常用配置如[表 3 Kafka Source常用配置](#t1f7ac743f0b646f8844b243a746b6a4d)所示：

    **表 3**  Kafka Source常用配置

    <a name="t1f7ac743f0b646f8844b243a746b6a4d"></a>
    <table><thead align="left"><tr id="rf5739e1e01e648adb3c7ac3c79acf300"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="addf5b78cd82d4f15b70fe78dbd2bb595"><a name="addf5b78cd82d4f15b70fe78dbd2bb595"></a><a name="addf5b78cd82d4f15b70fe78dbd2bb595"></a><strong id="a52fd5301e7e9441fb2976b87178eec75"><a name="a52fd5301e7e9441fb2976b87178eec75"></a><a name="a52fd5301e7e9441fb2976b87178eec75"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a6ba5c809799744499f380e0ba370bee2"><a name="a6ba5c809799744499f380e0ba370bee2"></a><a name="a6ba5c809799744499f380e0ba370bee2"></a><strong id="a92d4975627bf4eb3a31aadd6351c4173"><a name="a92d4975627bf4eb3a31aadd6351c4173"></a><a name="a92d4975627bf4eb3a31aadd6351c4173"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a6561acc5a9ee41f0b7a43b37f6fcf893"><a name="a6561acc5a9ee41f0b7a43b37f6fcf893"></a><a name="a6561acc5a9ee41f0b7a43b37f6fcf893"></a><strong id="ace7f0f90b66c4f528014dd673de30938"><a name="ace7f0f90b66c4f528014dd673de30938"></a><a name="ace7f0f90b66c4f528014dd673de30938"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r936d999c7eaf4077a1739d84df8e216d"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a65a5c12652314886b108352dd7f6471a"><a name="a65a5c12652314886b108352dd7f6471a"></a><a name="a65a5c12652314886b108352dd7f6471a"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aaf48ff00ef0b44128850298d5e3f45c2"><a name="aaf48ff00ef0b44128850298d5e3f45c2"></a><a name="aaf48ff00ef0b44128850298d5e3f45c2"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="af020007f579d477c83a5fef4c0edae18"><a name="af020007f579d477c83a5fef4c0edae18"></a><a name="af020007f579d477c83a5fef4c0edae18"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="r551f68ee2d1f418084436f905ebe1740"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="abcf0d826eac646e39551fa0f0bad7934"><a name="abcf0d826eac646e39551fa0f0bad7934"></a><a name="abcf0d826eac646e39551fa0f0bad7934"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a0f483b2e2a0e4aa490e186b69575588f"><a name="a0f483b2e2a0e4aa490e186b69575588f"></a><a name="a0f483b2e2a0e4aa490e186b69575588f"></a>org.apache.flume.source.kafka.KafkaSource</p>
    <p id="a1bc0a09a53f9494e8df02f94423490da"><a name="a1bc0a09a53f9494e8df02f94423490da"></a><a name="a1bc0a09a53f9494e8df02f94423490da"></a></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ab4458eb89dcb4142b87566b101c95bdb"><a name="ab4458eb89dcb4142b87566b101c95bdb"></a><a name="ab4458eb89dcb4142b87566b101c95bdb"></a>类型，需设置为<span class="parmvalue" id="p4acc8544476942a3ab3ebc6a4e87ca43"><a name="p4acc8544476942a3ab3ebc6a4e87ca43"></a><a name="p4acc8544476942a3ab3ebc6a4e87ca43"></a>“org.apache.flume.source.kafka.KafkaSource”</span>。</p>
    </td>
    </tr>
    <tr id="r33e92b363e57485586a4f1f44612d841"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aa9568c2cd18c46e4a0567a9b2d1ff370"><a name="aa9568c2cd18c46e4a0567a9b2d1ff370"></a><a name="aa9568c2cd18c46e4a0567a9b2d1ff370"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p10022165858"><a name="zh-cn_topic_0066459131_p10022165858"></a><a name="zh-cn_topic_0066459131_p10022165858"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p811818165858"><a name="zh-cn_topic_0066459131_p811818165858"></a><a name="zh-cn_topic_0066459131_p811818165858"></a>线程监控阈值，更新时间大于阈值时重新启动该Source，单位：秒。</p>
    </td>
    </tr>
    <tr id="rce16dade0d01446fbb4f8326a37a32a9"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab2dc8e99ae5745999e671f3c6621c3a5"><a name="ab2dc8e99ae5745999e671f3c6621c3a5"></a><a name="ab2dc8e99ae5745999e671f3c6621c3a5"></a>nodatatime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac14ca43522cb44e3ada01e54c8b6821e"><a name="ac14ca43522cb44e3ada01e54c8b6821e"></a><a name="ac14ca43522cb44e3ada01e54c8b6821e"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a7105dd5d6df34759b162e7534114fedc"><a name="a7105dd5d6df34759b162e7534114fedc"></a><a name="a7105dd5d6df34759b162e7534114fedc"></a>告警阈值，从Kafka中订阅不到数据的时长大于阈值时发送告警，单位：秒。</p>
    </td>
    </tr>
    <tr id="rc50d41d3adaf46f784e2eb7c393f237f"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a60378524c60844f28fa5ad2f7d2d71ac"><a name="a60378524c60844f28fa5ad2f7d2d71ac"></a><a name="a60378524c60844f28fa5ad2f7d2d71ac"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac2b7fde2ccf643ddad2ab0868c0a2aa0"><a name="ac2b7fde2ccf643ddad2ab0868c0a2aa0"></a><a name="ac2b7fde2ccf643ddad2ab0868c0a2aa0"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aac21be4000a44a69bf2ce886f64322e7"><a name="aac21be4000a44a69bf2ce886f64322e7"></a><a name="aac21be4000a44a69bf2ce886f64322e7"></a>每次写入Channel的Event数量。</p>
    </td>
    </tr>
    <tr id="r88260e5cd4d7443783f66a8e0ba7b573"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a345c6b47bce1407fa423aae43a3be796"><a name="a345c6b47bce1407fa423aae43a3be796"></a><a name="a345c6b47bce1407fa423aae43a3be796"></a>batchDurationMillis</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afbcd8d607bba4dbba5ae3202453de613"><a name="afbcd8d607bba4dbba5ae3202453de613"></a><a name="afbcd8d607bba4dbba5ae3202453de613"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae269a13d1cfb401b9b80ea9c5fb87011"><a name="ae269a13d1cfb401b9b80ea9c5fb87011"></a><a name="ae269a13d1cfb401b9b80ea9c5fb87011"></a>每次消费topic数据的最大时长，单位：毫秒。</p>
    </td>
    </tr>
    <tr id="r4bb740cfcaf24696ae6149d3a30ac7e8"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a134b7e65766d4a92aa018705c782a7e6"><a name="a134b7e65766d4a92aa018705c782a7e6"></a><a name="a134b7e65766d4a92aa018705c782a7e6"></a>keepTopicInHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab1d8c7822be74ec9a9766961abaa4f8a"><a name="ab1d8c7822be74ec9a9766961abaa4f8a"></a><a name="ab1d8c7822be74ec9a9766961abaa4f8a"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5da0d1f42d3c472496c31faaa269b167"><a name="a5da0d1f42d3c472496c31faaa269b167"></a><a name="a5da0d1f42d3c472496c31faaa269b167"></a>是否在Event Header中保存topic，如果保存，Kafka Sink配置的topic将无效。</p>
    <a name="u088a8cef109b4d3a9827cc42c273777b"></a><a name="u088a8cef109b4d3a9827cc42c273777b"></a><ul id="u088a8cef109b4d3a9827cc42c273777b"><li>true</li><li>false</li></ul>
    </td>
    </tr>
    <tr id="ra29eef6c4dfb46798c818946039d13f3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a151236c7c7ae41b4b959c1d5e4e7a8b7"><a name="a151236c7c7ae41b4b959c1d5e4e7a8b7"></a><a name="a151236c7c7ae41b4b959c1d5e4e7a8b7"></a>keepPartitionInHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a2e4ad00d070344ee91943d0136410a59"><a name="a2e4ad00d070344ee91943d0136410a59"></a><a name="a2e4ad00d070344ee91943d0136410a59"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a31ac0057a74c415d8420ae6af43eb98d"><a name="a31ac0057a74c415d8420ae6af43eb98d"></a><a name="a31ac0057a74c415d8420ae6af43eb98d"></a>是否在Event Header中保存partitionID，如果保存，Kafka Sink将写入对应的Partition。</p>
    <a name="u489c3e99ba90479491f94a33dccfe381"></a><a name="u489c3e99ba90479491f94a33dccfe381"></a><ul id="u489c3e99ba90479491f94a33dccfe381"><li>true</li><li>false</li></ul>
    </td>
    </tr>
    <tr id="r1179794397874f3a9776a3f96b3e46e6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a0323365ebf6146f9997f36ce5f3038c7"><a name="a0323365ebf6146f9997f36ce5f3038c7"></a><a name="a0323365ebf6146f9997f36ce5f3038c7"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a578a2bd29f6a423e99683500ca0c7c69"><a name="a578a2bd29f6a423e99683500ca0c7c69"></a><a name="a578a2bd29f6a423e99683500ca0c7c69"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a28d56a4673f84747810fb78348570bcf"><a name="a28d56a4673f84747810fb78348570bcf"></a><a name="a28d56a4673f84747810fb78348570bcf"></a>brokers地址列表，多个地址用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="ra7d7b51a04404857b921c4c9d72cbe22"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a012d83c28c3d46349c362554d68ddb77"><a name="a012d83c28c3d46349c362554d68ddb77"></a><a name="a012d83c28c3d46349c362554d68ddb77"></a>kafka.consumer.group.id</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae6bc6f6669094d10ac329acde068fff7"><a name="ae6bc6f6669094d10ac329acde068fff7"></a><a name="ae6bc6f6669094d10ac329acde068fff7"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5b4945ad4ec04df089b814d5d940e14b"><a name="a5b4945ad4ec04df089b814d5d940e14b"></a><a name="a5b4945ad4ec04df089b814d5d940e14b"></a>Kafka消费者组ID。</p>
    </td>
    </tr>
    <tr id="raff3c84724ed482d8a6e749ad73b3a82"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aca73a8fc480541c1b6ee5e583898b5f2"><a name="aca73a8fc480541c1b6ee5e583898b5f2"></a><a name="aca73a8fc480541c1b6ee5e583898b5f2"></a>kafka.topics</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a347fb3f56a674f08ae562b7106e381a5"><a name="a347fb3f56a674f08ae562b7106e381a5"></a><a name="a347fb3f56a674f08ae562b7106e381a5"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae3f84f1e7925419db0f5509d5db3829a"><a name="ae3f84f1e7925419db0f5509d5db3829a"></a><a name="ae3f84f1e7925419db0f5509d5db3829a"></a>订阅的kafka topic列表，用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="r0cfe887829734409a1b2c690d9a7999b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a2e21c6decde042abaf0e5a57cef2151e"><a name="a2e21c6decde042abaf0e5a57cef2151e"></a><a name="a2e21c6decde042abaf0e5a57cef2151e"></a>kafka.topics.regex</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ad35de17590ca48c89c8946682bbb9ff7"><a name="ad35de17590ca48c89c8946682bbb9ff7"></a><a name="ad35de17590ca48c89c8946682bbb9ff7"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a80fdbf0055464e768323e99335570175"><a name="a80fdbf0055464e768323e99335570175"></a><a name="a80fdbf0055464e768323e99335570175"></a>符合正则表达式的topic会被订阅，优先级高于“kafka.topics”，如果配置将覆盖“kafka.topics”。</p>
    </td>
    </tr>
    <tr id="ra49d559fb5354ef6b70167e5db2aa1b4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a7dd1ca88cbad4ee2a32893c345f206f2"><a name="a7dd1ca88cbad4ee2a32893c345f206f2"></a><a name="a7dd1ca88cbad4ee2a32893c345f206f2"></a>kafka.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afd9c0ff0028148758c69751eb5d0c0a6"><a name="afd9c0ff0028148758c69751eb5d0c0a6"></a><a name="afd9c0ff0028148758c69751eb5d0c0a6"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa50e6215245d4f2f9ccf68dd20d52fcd"><a name="aa50e6215245d4f2f9ccf68dd20d52fcd"></a><a name="aa50e6215245d4f2f9ccf68dd20d52fcd"></a>Kafka安全协议，未启用Kerberos集群中须配置为<span class="parmvalue" id="p31a1d721f69b435cbdf0049b426ccdec"><a name="p31a1d721f69b435cbdf0049b426ccdec"></a><a name="p31a1d721f69b435cbdf0049b426ccdec"></a>“PLAINTEXT”</span>。</p>
    </td>
    </tr>
    <tr id="r07668b1271f54024a2340433ff94e6fb"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a58be15400e6f4b07818f53278e9991c8"><a name="a58be15400e6f4b07818f53278e9991c8"></a><a name="a58be15400e6f4b07818f53278e9991c8"></a>Other Kafka Consumer Properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="acfbfe4ca95e147a5ae3588ab63ba990d"><a name="acfbfe4ca95e147a5ae3588ab63ba990d"></a><a name="acfbfe4ca95e147a5ae3588ab63ba990d"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a557ae6cc32c94a0c8247c3c3ce1bd5cc"><a name="a557ae6cc32c94a0c8247c3c3ce1bd5cc"></a><a name="a557ae6cc32c94a0c8247c3c3ce1bd5cc"></a>其他Kafka配置，可以接受任意Kafka支持的消费参数配置，配置需要加前缀<span class="parmvalue" id="pf53e06fc8e7d4a2cbe3f92e1a8acc037"><a name="pf53e06fc8e7d4a2cbe3f92e1a8acc037"></a><a name="pf53e06fc8e7d4a2cbe3f92e1a8acc037"></a>“.kafka”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Taildir Source**

    Taildir Source监控目录下文件的变化并自动读取文件内容，可实现实时数据传输，常用配置如[下表](#t2c85090722c4451682fad2657a7bdc35)所示：

    **表 4**  Taildir Source常用配置

    <a name="t2c85090722c4451682fad2657a7bdc35"></a>
    <table><thead align="left"><tr id="r04e6e8a6c378446da7da5086ed88d715"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a20af2b72d6b04711a71b34480ec06ec6"><a name="a20af2b72d6b04711a71b34480ec06ec6"></a><a name="a20af2b72d6b04711a71b34480ec06ec6"></a><strong id="ae90645de27514b14a28d2efb4e4aee26"><a name="ae90645de27514b14a28d2efb4e4aee26"></a><a name="ae90645de27514b14a28d2efb4e4aee26"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a7d0a1297bc744fea9f884e3a99f3297b"><a name="a7d0a1297bc744fea9f884e3a99f3297b"></a><a name="a7d0a1297bc744fea9f884e3a99f3297b"></a><strong id="ac5490e8aa9894f648abc04f4caf07d13"><a name="ac5490e8aa9894f648abc04f4caf07d13"></a><a name="ac5490e8aa9894f648abc04f4caf07d13"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a31e4fd61aab24cf8bd3c071ef2a4ce41"><a name="a31e4fd61aab24cf8bd3c071ef2a4ce41"></a><a name="a31e4fd61aab24cf8bd3c071ef2a4ce41"></a><strong id="a482ccb6681eb49b78c526ccfc92f8810"><a name="a482ccb6681eb49b78c526ccfc92f8810"></a><a name="a482ccb6681eb49b78c526ccfc92f8810"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r9b778ecf252646ab8fffd7fbf280243a"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aaf9e9494e3b246a583de27cf89d5b75f"><a name="aaf9e9494e3b246a583de27cf89d5b75f"></a><a name="aaf9e9494e3b246a583de27cf89d5b75f"></a><span id="p0b6947e29867421b9919d5f6f5872c66"><a name="p0b6947e29867421b9919d5f6f5872c66"></a><a name="p0b6947e29867421b9919d5f6f5872c66"></a>channels</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a485c777d050543f9b277d515b4e9a90f"><a name="a485c777d050543f9b277d515b4e9a90f"></a><a name="a485c777d050543f9b277d515b4e9a90f"></a><span id="p7031fa9c082b42a2bf22982e967c02c4"><a name="p7031fa9c082b42a2bf22982e967c02c4"></a><a name="p7031fa9c082b42a2bf22982e967c02c4"></a>-</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a58715099e69f4ac781c02691a9f5b1a1"><a name="a58715099e69f4ac781c02691a9f5b1a1"></a><a name="a58715099e69f4ac781c02691a9f5b1a1"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="raa6ae4b8664b4e70a8da14c32432b4d8"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae62ab04fdbc44fa2a7bee5693c621756"><a name="ae62ab04fdbc44fa2a7bee5693c621756"></a><a name="ae62ab04fdbc44fa2a7bee5693c621756"></a><span id="p5bfcbbae00264eb6b6c62097e09e8f11"><a name="p5bfcbbae00264eb6b6c62097e09e8f11"></a><a name="p5bfcbbae00264eb6b6c62097e09e8f11"></a>type</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a830edb6cf7054b12a0ba656d2c299680"><a name="a830edb6cf7054b12a0ba656d2c299680"></a><a name="a830edb6cf7054b12a0ba656d2c299680"></a>taildir</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae440c774df324f2d9516449860c463e8"><a name="ae440c774df324f2d9516449860c463e8"></a><a name="ae440c774df324f2d9516449860c463e8"></a>类型，需配置为<span class="parmvalue" id="p4f94e289493443b1895d2fb7b2f02321"><a name="p4f94e289493443b1895d2fb7b2f02321"></a><a name="p4f94e289493443b1895d2fb7b2f02321"></a>“taildir”</span>。</p>
    </td>
    </tr>
    <tr id="r285c6aa7661043d19e4833ac39114843"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a3d35da52d63d46649d15a29e4871981b"><a name="a3d35da52d63d46649d15a29e4871981b"></a><a name="a3d35da52d63d46649d15a29e4871981b"></a>filegroups</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac8064d8657ee4ab097c35b4857ed4ac9"><a name="ac8064d8657ee4ab097c35b4857ed4ac9"></a><a name="ac8064d8657ee4ab097c35b4857ed4ac9"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a31740878ca4043e2bad1534597c151f3"><a name="a31740878ca4043e2bad1534597c151f3"></a><a name="a31740878ca4043e2bad1534597c151f3"></a>设置采集文件目录分组名字，分组名字中间使用空格间隔。</p>
    </td>
    </tr>
    <tr id="r5bb6544114e446c49983b6e615e5e078"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aba7e8edcefac43a69175e2ee2fd072cc"><a name="aba7e8edcefac43a69175e2ee2fd072cc"></a><a name="aba7e8edcefac43a69175e2ee2fd072cc"></a>filegroups.&lt;filegroupName&gt;.parentDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae2cfeb26bbae45018c5fe10ea82b8ec8"><a name="ae2cfeb26bbae45018c5fe10ea82b8ec8"></a><a name="ae2cfeb26bbae45018c5fe10ea82b8ec8"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a9815719cf3404a5bb79e7adea2cbc3f2"><a name="a9815719cf3404a5bb79e7adea2cbc3f2"></a><a name="a9815719cf3404a5bb79e7adea2cbc3f2"></a>父目录，需要配置为绝对路径。</p>
    </td>
    </tr>
    <tr id="r3708ff735c1e4cda8f7d80817ad2768d"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a869abac9343c4887bf0b1d31f9cdfcea"><a name="a869abac9343c4887bf0b1d31f9cdfcea"></a><a name="a869abac9343c4887bf0b1d31f9cdfcea"></a>filegroups.&lt;filegroupName&gt;.filePattern</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ad2fa7cabbd42470a9207f9cbcd115944"><a name="ad2fa7cabbd42470a9207f9cbcd115944"></a><a name="ad2fa7cabbd42470a9207f9cbcd115944"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a929285d3c75e4213bd8d1055e4fffd0a"><a name="a929285d3c75e4213bd8d1055e4fffd0a"></a><a name="a929285d3c75e4213bd8d1055e4fffd0a"></a>相对父目录的文件路径，可以包含目录，支持正则表达式，须与父目录联合使用。</p>
    </td>
    </tr>
    <tr id="r1245fc762022410ea3e05399bfdf30fa"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p440251165858"><a name="zh-cn_topic_0066459131_p440251165858"></a><a name="zh-cn_topic_0066459131_p440251165858"></a>positionFile</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a75a7cb945c4e44e89575db75f73b955e"><a name="a75a7cb945c4e44e89575db75f73b955e"></a><a name="a75a7cb945c4e44e89575db75f73b955e"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="acfe29b9b8d4e48d28e4bb05a212b1f62"><a name="acfe29b9b8d4e48d28e4bb05a212b1f62"></a><a name="acfe29b9b8d4e48d28e4bb05a212b1f62"></a>传输过程中元数据存储路径</p>
    </td>
    </tr>
    <tr id="ra4c8ebc16e774b859b2fd8ac7e5bc789"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a3528007b997b4a7d87aead7846e6e2fd"><a name="a3528007b997b4a7d87aead7846e6e2fd"></a><a name="a3528007b997b4a7d87aead7846e6e2fd"></a>headers.&lt;filegroupName&gt;.&lt;headerKey&gt;</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="af614e1e22e7b42f785b556ad6331f29c"><a name="af614e1e22e7b42f785b556ad6331f29c"></a><a name="af614e1e22e7b42f785b556ad6331f29c"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a39c7431b12d948b391aafb5fe261f478"><a name="a39c7431b12d948b391aafb5fe261f478"></a><a name="a39c7431b12d948b391aafb5fe261f478"></a>设置某一个分组采集数据时Event中的key-value值。</p>
    </td>
    </tr>
    <tr id="rb89a7fdf6df1407082d59b563f9008c2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a2d7e3d8a4eb14cab9dc77c030cd61a76"><a name="a2d7e3d8a4eb14cab9dc77c030cd61a76"></a><a name="a2d7e3d8a4eb14cab9dc77c030cd61a76"></a>byteOffsetHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a895aaff860a5491dbcf4d37f8bae8f88"><a name="a895aaff860a5491dbcf4d37f8bae8f88"></a><a name="a895aaff860a5491dbcf4d37f8bae8f88"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a167bc9b1f64f4b45b2c247f502569d10"><a name="a167bc9b1f64f4b45b2c247f502569d10"></a><a name="a167bc9b1f64f4b45b2c247f502569d10"></a>是否在每一个Event头中携带该Event在源文件中的位置信息，该信息保存在<span class="parmname" id="p6e660086a567481f9cb7660f10cf19ad"><a name="p6e660086a567481f9cb7660f10cf19ad"></a><a name="p6e660086a567481f9cb7660f10cf19ad"></a>“byteoffset”</span>变量中。</p>
    </td>
    </tr>
    <tr id="r8e7344f01f364d508df3c09aa1f96a88"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a36ec1439b51e4a13a0b799e1547b5ba6"><a name="a36ec1439b51e4a13a0b799e1547b5ba6"></a><a name="a36ec1439b51e4a13a0b799e1547b5ba6"></a>skipToEnd</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="acdeab4d5592a4e4f94768847ff856370"><a name="acdeab4d5592a4e4f94768847ff856370"></a><a name="acdeab4d5592a4e4f94768847ff856370"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a26e143bf898646c1a0743a2ea1bc4560"><a name="a26e143bf898646c1a0743a2ea1bc4560"></a><a name="a26e143bf898646c1a0743a2ea1bc4560"></a>Flume在重启后是否直接定位到文件最新的位置处，以读取最新的数据。</p>
    </td>
    </tr>
    <tr id="rb2a099c6ab4d45bf8a72b17beefc24c7"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a1c3bcf31c1944aa3a6b6ac00359a939e"><a name="a1c3bcf31c1944aa3a6b6ac00359a939e"></a><a name="a1c3bcf31c1944aa3a6b6ac00359a939e"></a>idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="abd724a40f53146d8b3866f7a17721e89"><a name="abd724a40f53146d8b3866f7a17721e89"></a><a name="abd724a40f53146d8b3866f7a17721e89"></a>120000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a049fa63ad3324427b7868908883f243e"><a name="a049fa63ad3324427b7868908883f243e"></a><a name="a049fa63ad3324427b7868908883f243e"></a>设置读取文件的空闲时间，单位：毫秒。如果在该时间内文件内容没有变更，关闭掉该文件，关闭后如果该文件有数据写入，重新打开并读取数据。</p>
    </td>
    </tr>
    <tr id="r4282ca0909a140f2ac9bb24f8420ee96"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a25fb3e740649401ba201c65065735f40"><a name="a25fb3e740649401ba201c65065735f40"></a><a name="a25fb3e740649401ba201c65065735f40"></a>writePosInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4dd2984b49e2423494329fca05cbd68f"><a name="a4dd2984b49e2423494329fca05cbd68f"></a><a name="a4dd2984b49e2423494329fca05cbd68f"></a>3000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a2a77a90f8cd241e788774a5dfa16cfe4"><a name="a2a77a90f8cd241e788774a5dfa16cfe4"></a><a name="a2a77a90f8cd241e788774a5dfa16cfe4"></a>设置将元数据写入到文件的周期，单位：毫秒。</p>
    </td>
    </tr>
    <tr id="r6336d2c0900a4b8cb6da9b41fd4b74fb"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a46b9d3c0153346a2a43328599d8861ad"><a name="a46b9d3c0153346a2a43328599d8861ad"></a><a name="a46b9d3c0153346a2a43328599d8861ad"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a41d48491883f4335bf43e39eacfbc85d"><a name="a41d48491883f4335bf43e39eacfbc85d"></a><a name="a41d48491883f4335bf43e39eacfbc85d"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a2c62944cdb9a48ce8bf3565941e2155f"><a name="a2c62944cdb9a48ce8bf3565941e2155f"></a><a name="a2c62944cdb9a48ce8bf3565941e2155f"></a>批次写入Channel的Event数量。</p>
    </td>
    </tr>
    <tr id="rf9fdd68ae4f34cf08af5a1d2a62964af"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aa4eaa806840f49ac89974f2464f006fb"><a name="aa4eaa806840f49ac89974f2464f006fb"></a><a name="aa4eaa806840f49ac89974f2464f006fb"></a><span id="p3649447c030b418b8caba0e974cc5bd6"><a name="p3649447c030b418b8caba0e974cc5bd6"></a><a name="p3649447c030b418b8caba0e974cc5bd6"></a>monTime</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="af2d5eb39ed9b4be7833262d716b9ea7d"><a name="af2d5eb39ed9b4be7833262d716b9ea7d"></a><a name="af2d5eb39ed9b4be7833262d716b9ea7d"></a><span id="pb9b1a91154a94322b95dea7242ef6547"><a name="pb9b1a91154a94322b95dea7242ef6547"></a><a name="pb9b1a91154a94322b95dea7242ef6547"></a>0（不开启）</span></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a0dd1c41079c54f46bf73836e4434242d"><a name="a0dd1c41079c54f46bf73836e4434242d"></a><a name="a0dd1c41079c54f46bf73836e4434242d"></a><span id="p1109235862d049be9222d4e6e8f9fb76"><a name="p1109235862d049be9222d4e6e8f9fb76"></a><a name="p1109235862d049be9222d4e6e8f9fb76"></a>线程监控阈值，更新时间</span>大于<span id="pc3b3d74a19584405985049c7ce6717c2"><a name="pc3b3d74a19584405985049c7ce6717c2"></a><a name="pc3b3d74a19584405985049c7ce6717c2"></a>阈值时重新启动该Source，单位：秒。</span></p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Http Source**

    Http Source接收外部HTTP客户端发送过来的数据，并放入配置的Channel中，常用配置如[下表](#t033eef1276424185b1cfd10a7d4e024f)所示：

    **表 5**  Http Source常用配置

    <a name="t033eef1276424185b1cfd10a7d4e024f"></a>
    <table><thead align="left"><tr id="rbfd2b8ae09464420a872393daca8a1a0"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a5899ba527015427cb3a770191efde138"><a name="a5899ba527015427cb3a770191efde138"></a><a name="a5899ba527015427cb3a770191efde138"></a><strong id="ae987d4b4ae2c424ea02473fd3fcebd04"><a name="ae987d4b4ae2c424ea02473fd3fcebd04"></a><a name="ae987d4b4ae2c424ea02473fd3fcebd04"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="ae5d4f302edd4472c8beeb9e228f340ea"><a name="ae5d4f302edd4472c8beeb9e228f340ea"></a><a name="ae5d4f302edd4472c8beeb9e228f340ea"></a><strong id="ade302d53a6fd44fc88788382826e53f7"><a name="ade302d53a6fd44fc88788382826e53f7"></a><a name="ade302d53a6fd44fc88788382826e53f7"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a25f09b3888ea4810a6423b31462431c9"><a name="a25f09b3888ea4810a6423b31462431c9"></a><a name="a25f09b3888ea4810a6423b31462431c9"></a><strong id="ac1c0a90961eb4e87bc9e47815c6d34c4"><a name="ac1c0a90961eb4e87bc9e47815c6d34c4"></a><a name="ac1c0a90961eb4e87bc9e47815c6d34c4"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="rb2f4c2fcd26e436c893cd9fd34ff4eda"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="abca43b42e44b4e3a86fa5cbd7b373603"><a name="abca43b42e44b4e3a86fa5cbd7b373603"></a><a name="abca43b42e44b4e3a86fa5cbd7b373603"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac7b945b508b04b2688649f97b3ee602d"><a name="ac7b945b508b04b2688649f97b3ee602d"></a><a name="ac7b945b508b04b2688649f97b3ee602d"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a256de339f97440f09419a69a4deed709"><a name="a256de339f97440f09419a69a4deed709"></a><a name="a256de339f97440f09419a69a4deed709"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="re7931ec8d3f74615b961fcc49a1849b7"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a6825dcc16fba4d34a22566eefe8592db"><a name="a6825dcc16fba4d34a22566eefe8592db"></a><a name="a6825dcc16fba4d34a22566eefe8592db"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac53c48f837b549beaf1633ebe35e48e6"><a name="ac53c48f837b549beaf1633ebe35e48e6"></a><a name="ac53c48f837b549beaf1633ebe35e48e6"></a>http</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a150440c2de204164a9911d02404f72e0"><a name="a150440c2de204164a9911d02404f72e0"></a><a name="a150440c2de204164a9911d02404f72e0"></a>类型，需配置为<span class="parmvalue" id="pbe532b41d9e2474caaee5f63c57a28cf"><a name="pbe532b41d9e2474caaee5f63c57a28cf"></a><a name="pbe532b41d9e2474caaee5f63c57a28cf"></a>“http”</span>。</p>
    </td>
    </tr>
    <tr id="r6bbb3e1c166d4333876a6fa6d655d5fc"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a05bf50afd2ae4872a246b4c331f92f03"><a name="a05bf50afd2ae4872a246b4c331f92f03"></a><a name="a05bf50afd2ae4872a246b4c331f92f03"></a>bind</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a00a0938b2a434d878974ee2281a1ae15"><a name="a00a0938b2a434d878974ee2281a1ae15"></a><a name="a00a0938b2a434d878974ee2281a1ae15"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a99071feaf6ed4158a356dcb686508b58"><a name="a99071feaf6ed4158a356dcb686508b58"></a><a name="a99071feaf6ed4158a356dcb686508b58"></a>绑定关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="rf1ca49dad4084aeda8eb34c740431ed0"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a3ebfb6d139934cc7be875ff24f65140e"><a name="a3ebfb6d139934cc7be875ff24f65140e"></a><a name="a3ebfb6d139934cc7be875ff24f65140e"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a268563dfc02e4effb67f2aaec1e689dc"><a name="a268563dfc02e4effb67f2aaec1e689dc"></a><a name="a268563dfc02e4effb67f2aaec1e689dc"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a6896178fab0840a08ab04c3408110abf"><a name="a6896178fab0840a08ab04c3408110abf"></a><a name="a6896178fab0840a08ab04c3408110abf"></a>绑定端口。</p>
    </td>
    </tr>
    <tr id="rb1617a8ca5f247f59b67b0d0d9fa4272"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a388a24688e2c467e98a5ea8cb9141e16"><a name="a388a24688e2c467e98a5ea8cb9141e16"></a><a name="a388a24688e2c467e98a5ea8cb9141e16"></a>handler</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aba1158ce78144ee6bdc57039e49b7749"><a name="aba1158ce78144ee6bdc57039e49b7749"></a><a name="aba1158ce78144ee6bdc57039e49b7749"></a>org.apache.flume.source.http.JSONHandler</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="af9131cd16db84c8abe357c24527bca90"><a name="af9131cd16db84c8abe357c24527bca90"></a><a name="af9131cd16db84c8abe357c24527bca90"></a>http请求的消息解析方式，支持以下两种：</p>
    <a name="u00adfbb8387b484683bb7cf15f06a64f"></a><a name="u00adfbb8387b484683bb7cf15f06a64f"></a><ul id="u00adfbb8387b484683bb7cf15f06a64f"><li><span class="parmvalue" id="pfa8ba599d4034d19bc5611c8000970ec"><a name="pfa8ba599d4034d19bc5611c8000970ec"></a><a name="pfa8ba599d4034d19bc5611c8000970ec"></a>“org.apache.flume.source.http.JSONHandler”</span>：表示Json格式解析。</li><li><span class="parmvalue" id="pd85fe29a10e84e52b175b075317ce4b0"><a name="pd85fe29a10e84e52b175b075317ce4b0"></a><a name="pd85fe29a10e84e52b175b075317ce4b0"></a>“org.apache.flume.sink.solr.morphline.BlobHandler”</span>：表示二进制Blob块解析。</li></ul>
    </td>
    </tr>
    <tr id="r40b879a3564e40bcb4aad3b457e743bf"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a4d3f859e11ae413b817aa7f194551edc"><a name="a4d3f859e11ae413b817aa7f194551edc"></a><a name="a4d3f859e11ae413b817aa7f194551edc"></a>handler.*</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a0ab182b5779a479c98bf09fb61ea1d98"><a name="a0ab182b5779a479c98bf09fb61ea1d98"></a><a name="a0ab182b5779a479c98bf09fb61ea1d98"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a30cf681c5ca34dc9bb7d3edea49b364f"><a name="a30cf681c5ca34dc9bb7d3edea49b364f"></a><a name="a30cf681c5ca34dc9bb7d3edea49b364f"></a>设置handler的参数。</p>
    </td>
    </tr>
    <tr id="r3541737adb98421a97465575f809592c"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a8cb930a1fa1f473b99c8687f7e0c74e1"><a name="a8cb930a1fa1f473b99c8687f7e0c74e1"></a><a name="a8cb930a1fa1f473b99c8687f7e0c74e1"></a>enableSSL</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4319b837af1443fa95ff221328bcd199"><a name="a4319b837af1443fa95ff221328bcd199"></a><a name="a4319b837af1443fa95ff221328bcd199"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a8f54807f6c5f4f5796d4e87afd88956c"><a name="a8f54807f6c5f4f5796d4e87afd88956c"></a><a name="a8f54807f6c5f4f5796d4e87afd88956c"></a>http协议是否启用SSL。</p>
    </td>
    </tr>
    <tr id="reaa15e33b1844fad9ecec0fa12afed3e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aa6fa25e5dceb473c9779b865e2c76853"><a name="aa6fa25e5dceb473c9779b865e2c76853"></a><a name="aa6fa25e5dceb473c9779b865e2c76853"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a89e4f69ffeda4c1c80aa9c6453ece143"><a name="a89e4f69ffeda4c1c80aa9c6453ece143"></a><a name="a89e4f69ffeda4c1c80aa9c6453ece143"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a8dd16915e1ef4b17b66b8678c576f99b"><a name="a8dd16915e1ef4b17b66b8678c576f99b"></a><a name="a8dd16915e1ef4b17b66b8678c576f99b"></a>http启用SSL后设置keystore的路径。</p>
    </td>
    </tr>
    <tr id="r732edf88e3e047579c702dca2282b2b9"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ad9914f5144104b09aa173bd1df748c71"><a name="ad9914f5144104b09aa173bd1df748c71"></a><a name="ad9914f5144104b09aa173bd1df748c71"></a>keystorePassword</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab299af5bb0314eedac956c309555a5ab"><a name="ab299af5bb0314eedac956c309555a5ab"></a><a name="ab299af5bb0314eedac956c309555a5ab"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5b0ab9d977af4d798534e7a1254b59cc"><a name="a5b0ab9d977af4d798534e7a1254b59cc"></a><a name="a5b0ab9d977af4d798534e7a1254b59cc"></a>http启用SSL后设置keystore的密码。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **OBS Source**

    OBS Source监控并传输指定桶下新增的文件，可实现准实时数据传输。常用配置如[下表](#taeca225e09f94b74ae3f907e9077707d)所示：

    **表 6**  OBS Source常用配置

    <a name="taeca225e09f94b74ae3f907e9077707d"></a>
    <table><thead align="left"><tr id="r02d85be5b2be44fcafd5b0ea476685dc"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a7fb9074c85074e8e99af6623640543d5"><a name="a7fb9074c85074e8e99af6623640543d5"></a><a name="a7fb9074c85074e8e99af6623640543d5"></a><strong id="ad49c39e77014400cb3226d91b3e3429a"><a name="ad49c39e77014400cb3226d91b3e3429a"></a><a name="ad49c39e77014400cb3226d91b3e3429a"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a07be6918e6d74124ae5f8ddd18e90718"><a name="a07be6918e6d74124ae5f8ddd18e90718"></a><a name="a07be6918e6d74124ae5f8ddd18e90718"></a><strong id="a51ad246e6c3d483ca97b26abb571f073"><a name="a51ad246e6c3d483ca97b26abb571f073"></a><a name="a51ad246e6c3d483ca97b26abb571f073"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a085eb96bf0144d7e894dd01c3d7a5497"><a name="a085eb96bf0144d7e894dd01c3d7a5497"></a><a name="a085eb96bf0144d7e894dd01c3d7a5497"></a><strong id="a512dd5f0394d49418e3c2309815bd45f"><a name="a512dd5f0394d49418e3c2309815bd45f"></a><a name="a512dd5f0394d49418e3c2309815bd45f"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="rfee11ca2e70e4e48a792d316168a2eb9"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ad7940b5ba7d54612be2dc88430516fd8"><a name="ad7940b5ba7d54612be2dc88430516fd8"></a><a name="ad7940b5ba7d54612be2dc88430516fd8"></a>channels</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a456a443b38cc432d866ef86f2560b590"><a name="a456a443b38cc432d866ef86f2560b590"></a><a name="a456a443b38cc432d866ef86f2560b590"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="af1275dd0719a453bb430fd9302f6db53"><a name="af1275dd0719a453bb430fd9302f6db53"></a><a name="af1275dd0719a453bb430fd9302f6db53"></a>与之相连的Channel，可以配置多个。</p>
    </td>
    </tr>
    <tr id="r37c25aca52c8480e9435ab2b96fc1dce"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ababf282c4db84f18aa3278a137676037"><a name="ababf282c4db84f18aa3278a137676037"></a><a name="ababf282c4db84f18aa3278a137676037"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a446b7988b6a84e959c123ffcc3b08089"><a name="a446b7988b6a84e959c123ffcc3b08089"></a><a name="a446b7988b6a84e959c123ffcc3b08089"></a>http</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a817222efaf0d4cb1b274def25adcd06b"><a name="a817222efaf0d4cb1b274def25adcd06b"></a><a name="a817222efaf0d4cb1b274def25adcd06b"></a>类型，需配置为<span class="parmvalue" id="pcbc2fc7e779349ddb037c3ec39078705"><a name="pcbc2fc7e779349ddb037c3ec39078705"></a><a name="pcbc2fc7e779349ddb037c3ec39078705"></a>“org.apache.flume.source.s3.OBSSource”</span>。</p>
    </td>
    </tr>
    <tr id="ra11e624aebe94e3a9f205c3c445b2091"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="af852cc652ca74386aba39820f1904867"><a name="af852cc652ca74386aba39820f1904867"></a><a name="af852cc652ca74386aba39820f1904867"></a>bucketName</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a0dc3c5dc137c4002be66a61a42d816ff"><a name="a0dc3c5dc137c4002be66a61a42d816ff"></a><a name="a0dc3c5dc137c4002be66a61a42d816ff"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa47e83916db94d0ea0eb4ee1c17b7396"><a name="aa47e83916db94d0ea0eb4ee1c17b7396"></a><a name="aa47e83916db94d0ea0eb4ee1c17b7396"></a>OBS桶名。</p>
    </td>
    </tr>
    <tr id="r88195edacb5c4f44bfb74c92c547ad73"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ac71deb0fff284a53a8209edd56bf32fd"><a name="ac71deb0fff284a53a8209edd56bf32fd"></a><a name="ac71deb0fff284a53a8209edd56bf32fd"></a>prefix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a46a33ab2abcd471eaed617aac92e5ea6"><a name="a46a33ab2abcd471eaed617aac92e5ea6"></a><a name="a46a33ab2abcd471eaed617aac92e5ea6"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a1098ff04b4a24246804094f222b7edbe"><a name="a1098ff04b4a24246804094f222b7edbe"></a><a name="a1098ff04b4a24246804094f222b7edbe"></a>指定桶下，具体监控的OBS路径。注意不要以斜杠/开头。不设置时，默认监控桶下的根目录。</p>
    </td>
    </tr>
    <tr id="reb0e9c699177411482669ce1d8e3b179"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a007b1ae21e0e4b51b38aac368c7ec0c1"><a name="a007b1ae21e0e4b51b38aac368c7ec0c1"></a><a name="a007b1ae21e0e4b51b38aac368c7ec0c1"></a>accessKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a5a7c86fd24e644029bd62e0197c26082"><a name="a5a7c86fd24e644029bd62e0197c26082"></a><a name="a5a7c86fd24e644029bd62e0197c26082"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a96d9e8cc08a0455d8c6efcb75692ef1d"><a name="a96d9e8cc08a0455d8c6efcb75692ef1d"></a><a name="a96d9e8cc08a0455d8c6efcb75692ef1d"></a>用户的AK信息。</p>
    </td>
    </tr>
    <tr id="r8f0806896ec94c56aaaf39a319fcdb9f"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a81666b9d581c4f078db7597d3493f6a2"><a name="a81666b9d581c4f078db7597d3493f6a2"></a><a name="a81666b9d581c4f078db7597d3493f6a2"></a>secretKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a84bfd4df714e4bad926967f0b1afc040"><a name="a84bfd4df714e4bad926967f0b1afc040"></a><a name="a84bfd4df714e4bad926967f0b1afc040"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a59771b2a1944450a920550fd6530d4b6"><a name="a59771b2a1944450a920550fd6530d4b6"></a><a name="a59771b2a1944450a920550fd6530d4b6"></a>用户的SK信息，需要配置为密文。</p>
    </td>
    </tr>
    <tr id="re6c45dda4f834a608f2a4340bbb8a546"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="afc9e905c692f4e55895a59abfe06c5f5"><a name="afc9e905c692f4e55895a59abfe06c5f5"></a><a name="afc9e905c692f4e55895a59abfe06c5f5"></a>backingDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a63a5124102344157bd06fc8d6323382a"><a name="a63a5124102344157bd06fc8d6323382a"></a><a name="a63a5124102344157bd06fc8d6323382a"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a3cc72f453e8048f5bf578786c73a43f4"><a name="a3cc72f453e8048f5bf578786c73a43f4"></a><a name="a3cc72f453e8048f5bf578786c73a43f4"></a>传输过程中元数据存储路径。</p>
    </td>
    </tr>
    <tr id="r91ff176a299c490dadc77c8b4c47fcc8"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ad73950057cce4123913b1e37f913dc5b"><a name="ad73950057cce4123913b1e37f913dc5b"></a><a name="ad73950057cce4123913b1e37f913dc5b"></a>endPoint</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a03e2629c8f16409ca26fbc9074ad40f3"><a name="a03e2629c8f16409ca26fbc9074ad40f3"></a><a name="a03e2629c8f16409ca26fbc9074ad40f3"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a341f02b4fa694e5faede7297029f1268"><a name="a341f02b4fa694e5faede7297029f1268"></a><a name="a341f02b4fa694e5faede7297029f1268"></a>OBS访问地址，需要和MRS在相同的Region，可能是域名或者IP地址形式。</p>
    </td>
    </tr>
    <tr id="rfd5de18877244becb81b2ff333bade6d"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ac63c84551cdc4df09e5c0513f591372f"><a name="ac63c84551cdc4df09e5c0513f591372f"></a><a name="ac63c84551cdc4df09e5c0513f591372f"></a>basenameHeader</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a33e372ebb8754be49ce80e9569840683"><a name="a33e372ebb8754be49ce80e9569840683"></a><a name="a33e372ebb8754be49ce80e9569840683"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a41f745da756b4140a26d7a8fc40b0a37"><a name="a41f745da756b4140a26d7a8fc40b0a37"></a><a name="a41f745da756b4140a26d7a8fc40b0a37"></a>是否在Event Header中保存文件名。<span class="parmvalue" id="p6c9de2039878454daf7697beaf683f93"><a name="p6c9de2039878454daf7697beaf683f93"></a><a name="p6c9de2039878454daf7697beaf683f93"></a>“false”</span>表示不保存。</p>
    </td>
    </tr>
    <tr id="r6e23371354c14aaea12c78468a35ad89"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aefaa121903eb4150b125a318f2de4499"><a name="aefaa121903eb4150b125a318f2de4499"></a><a name="aefaa121903eb4150b125a318f2de4499"></a>basenameHeaderKey</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4da954747a7c47fb99f49626e5a409e0"><a name="a4da954747a7c47fb99f49626e5a409e0"></a><a name="a4da954747a7c47fb99f49626e5a409e0"></a>basename</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5cbc10c50d24409bbec07fdcb01a8c3e"><a name="a5cbc10c50d24409bbec07fdcb01a8c3e"></a><a name="a5cbc10c50d24409bbec07fdcb01a8c3e"></a>指定Event Header保存文件名使用的字段名，即key名称。</p>
    </td>
    </tr>
    <tr id="rd23c23f6b09d4cca8633f2acce43e10c"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a5b40533265f841f1b698082f331a5920"><a name="a5b40533265f841f1b698082f331a5920"></a><a name="a5b40533265f841f1b698082f331a5920"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4a82209a2b704e99a452b98d293ad400"><a name="a4a82209a2b704e99a452b98d293ad400"></a><a name="a4a82209a2b704e99a452b98d293ad400"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aac8382845cc9433db0e4faff0614b73c"><a name="aac8382845cc9433db0e4faff0614b73c"></a><a name="aac8382845cc9433db0e4faff0614b73c"></a>Source传输粒度。</p>
    </td>
    </tr>
    <tr id="r8e05ced050ef4ce6ba593c831116f166"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a72222bf385524e78874a21b96b35c545"><a name="a72222bf385524e78874a21b96b35c545"></a><a name="a72222bf385524e78874a21b96b35c545"></a>decodeErrorPolicy</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a1a1eaee0e9e04b6081fa185aad3bf59a"><a name="a1a1eaee0e9e04b6081fa185aad3bf59a"></a><a name="a1a1eaee0e9e04b6081fa185aad3bf59a"></a>FAIL</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a058ad8c8fa1942dcb4a86448a96ff5eb"><a name="a058ad8c8fa1942dcb4a86448a96ff5eb"></a><a name="a058ad8c8fa1942dcb4a86448a96ff5eb"></a>编码错误策略。</p>
    <div class="note" id="n31ba833aebbf484a891f73e453b80449"><a name="n31ba833aebbf484a891f73e453b80449"></a><a name="n31ba833aebbf484a891f73e453b80449"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="aba236a6948104af78144209f04669723"><a name="aba236a6948104af78144209f04669723"></a><a name="aba236a6948104af78144209f04669723"></a>如果文件中有编码错误，请配置“decodeErrorPolicy”为“REPLACE”或“IGNORE”，Flume遇到编码错误将跳过编码错误，继续采集后续日志。</p>
    </div></div>
    </td>
    </tr>
    <tr id="rd069cdb445d24e20bc08fd7773803095"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aa21672d3393b4394bae9b5ef7b450920"><a name="aa21672d3393b4394bae9b5ef7b450920"></a><a name="aa21672d3393b4394bae9b5ef7b450920"></a>deserializer</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="acbf84738710c47d99d0c31685891e4a0"><a name="acbf84738710c47d99d0c31685891e4a0"></a><a name="acbf84738710c47d99d0c31685891e4a0"></a>LINE</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aad7909f2a17c46128f1c51d1e6efb18b"><a name="aad7909f2a17c46128f1c51d1e6efb18b"></a><a name="aad7909f2a17c46128f1c51d1e6efb18b"></a>文件解析器，值为<span class="parmvalue" id="pef87c76f9bf2410faddcfd0cb81d89a4"><a name="pef87c76f9bf2410faddcfd0cb81d89a4"></a><a name="pef87c76f9bf2410faddcfd0cb81d89a4"></a>“LINE”</span>或&nbsp;<span class="parmvalue" id="pb5fce066309b4951920a5fa44c7bc4b1"><a name="pb5fce066309b4951920a5fa44c7bc4b1"></a><a name="pb5fce066309b4951920a5fa44c7bc4b1"></a>“BufferedLine”</span>。</p>
    <a name="u8d37c784656249588b864649cbe632af"></a><a name="u8d37c784656249588b864649cbe632af"></a><ul id="u8d37c784656249588b864649cbe632af"><li>配置为<span class="parmname" id="p709631722d8e4c8a8afbe79d458cb606"><a name="p709631722d8e4c8a8afbe79d458cb606"></a><a name="p709631722d8e4c8a8afbe79d458cb606"></a>“LINE”</span>时，对从文件读取的字符逐个转码。</li><li>配置为<span class="parmvalue" id="pafdf476fb69e403eb46367a632c28444"><a name="pafdf476fb69e403eb46367a632c28444"></a><a name="pafdf476fb69e403eb46367a632c28444"></a>“BufferedLine”</span>时，对文件读取的一行或多行的字符进行批量转码，性能更优。</li></ul>
    </td>
    </tr>
    <tr id="r676f649b2d704ec5bf2f4a1f834ac8a1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a2e4af67514004494bc9a8ae66d560a0d"><a name="a2e4af67514004494bc9a8ae66d560a0d"></a><a name="a2e4af67514004494bc9a8ae66d560a0d"></a>deserializer.maxLineLength</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afaa32087e1194e43a98d27519e12936e"><a name="afaa32087e1194e43a98d27519e12936e"></a><a name="afaa32087e1194e43a98d27519e12936e"></a>2048</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="afcf2ef51179848aa9b2f9b6ee8c1da90"><a name="afcf2ef51179848aa9b2f9b6ee8c1da90"></a><a name="afcf2ef51179848aa9b2f9b6ee8c1da90"></a>按行解析最大长度。</p>
    </td>
    </tr>
    <tr id="rfc73bd6496f6400fb220d5ef74a139a1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a3b05ddec90f5477a8dc6c67481d8859a"><a name="a3b05ddec90f5477a8dc6c67481d8859a"></a><a name="a3b05ddec90f5477a8dc6c67481d8859a"></a>deserializer.maxBatchLine</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afef006519d2e4ab0a91e9f9a128d379d"><a name="afef006519d2e4ab0a91e9f9a128d379d"></a><a name="afef006519d2e4ab0a91e9f9a128d379d"></a>1</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ab49b0b782e0d4f918e27125d549097d7"><a name="ab49b0b782e0d4f918e27125d549097d7"></a><a name="ab49b0b782e0d4f918e27125d549097d7"></a>按行解析最多行数，如果行数设置为多行，<span class="parmvalue" id="pa0be739507ed489f87060bce1ce98e8b"><a name="pa0be739507ed489f87060bce1ce98e8b"></a><a name="pa0be739507ed489f87060bce1ce98e8b"></a>“maxLineLength”</span>也应该设置为相应的倍数。</p>
    </td>
    </tr>
    <tr id="re829afbf6e404b9fbfdf5f020c76d8bc"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a76a4a9a4923849e1be2c08382ef11e88"><a name="a76a4a9a4923849e1be2c08382ef11e88"></a><a name="a76a4a9a4923849e1be2c08382ef11e88"></a>selector.type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a3b42670f81274ee09c95dbd237df59d8"><a name="a3b42670f81274ee09c95dbd237df59d8"></a><a name="a3b42670f81274ee09c95dbd237df59d8"></a>replicating</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aea028dd723434c9eb90ae38c13bbfa3d"><a name="aea028dd723434c9eb90ae38c13bbfa3d"></a><a name="aea028dd723434c9eb90ae38c13bbfa3d"></a>选择器类型，支持<span class="parmvalue" id="pf2743f03540f461ca14ae5e5d1424598"><a name="pf2743f03540f461ca14ae5e5d1424598"></a><a name="pf2743f03540f461ca14ae5e5d1424598"></a>“replicating”</span>或<span class="parmvalue" id="p589b53faf6cb4bfba1b8641a66011b88"><a name="p589b53faf6cb4bfba1b8641a66011b88"></a><a name="p589b53faf6cb4bfba1b8641a66011b88"></a>“multiplexing”</span>。</p>
    </td>
    </tr>
    <tr id="rd2bb9b6df2174fc3b6824c8c02098887"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a7dbe41cafdba4beb9b6e52760f07c2f0"><a name="a7dbe41cafdba4beb9b6e52760f07c2f0"></a><a name="a7dbe41cafdba4beb9b6e52760f07c2f0"></a>interceptors</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="adffd6d9d01944bafb0d423140db7586d"><a name="adffd6d9d01944bafb0d423140db7586d"></a><a name="adffd6d9d01944bafb0d423140db7586d"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ab99663b578064af7aafcb9cb9f3b1baf"><a name="ab99663b578064af7aafcb9cb9f3b1baf"></a><a name="ab99663b578064af7aafcb9cb9f3b1baf"></a>拦截器配置。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 常用Channel配置<a name="s252653025d9a4363a2d6f53fa9c1c20d"></a>

-   **Memory Channel**

    Memory Channel使用内存作为缓存区，Events存放在内存队列中。常用配置如[下表](#tc1421df5bc6c415ca490e671ea935f85)所示：

    **表 7**  Memory Channel常用配置

    <a name="tc1421df5bc6c415ca490e671ea935f85"></a>
    <table><thead align="left"><tr id="ra791bc5ce68641fc9257a2a04e53342a"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p194642081758"><a name="zh-cn_topic_0066459131_p194642081758"></a><a name="zh-cn_topic_0066459131_p194642081758"></a><strong id="zh-cn_topic_0066459131_b245323111758"><a name="zh-cn_topic_0066459131_b245323111758"></a><a name="zh-cn_topic_0066459131_b245323111758"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p294379441758"><a name="zh-cn_topic_0066459131_p294379441758"></a><a name="zh-cn_topic_0066459131_p294379441758"></a><strong id="zh-cn_topic_0066459131_b330970441758"><a name="zh-cn_topic_0066459131_b330970441758"></a><a name="zh-cn_topic_0066459131_b330970441758"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p525339371758"><a name="zh-cn_topic_0066459131_p525339371758"></a><a name="zh-cn_topic_0066459131_p525339371758"></a><strong id="zh-cn_topic_0066459131_b356632651758"><a name="zh-cn_topic_0066459131_b356632651758"></a><a name="zh-cn_topic_0066459131_b356632651758"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r2197ee0b8023489c95c9de610c23887e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p40372161758"><a name="zh-cn_topic_0066459131_p40372161758"></a><a name="zh-cn_topic_0066459131_p40372161758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p585790501758"><a name="zh-cn_topic_0066459131_p585790501758"></a><a name="zh-cn_topic_0066459131_p585790501758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p472825921758"><a name="zh-cn_topic_0066459131_p472825921758"></a><a name="zh-cn_topic_0066459131_p472825921758"></a>类型，需配置为<span class="parmvalue" id="pf2d9c3344bf443129fcd4fc2ab0ad90f"><a name="pf2d9c3344bf443129fcd4fc2ab0ad90f"></a><a name="pf2d9c3344bf443129fcd4fc2ab0ad90f"></a>“memory”</span>。</p>
    </td>
    </tr>
    <tr id="ree76cea1cb4b4bc0a2099ad384d0d855"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p421630201758"><a name="zh-cn_topic_0066459131_p421630201758"></a><a name="zh-cn_topic_0066459131_p421630201758"></a>capacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p597614891758"><a name="zh-cn_topic_0066459131_p597614891758"></a><a name="zh-cn_topic_0066459131_p597614891758"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p88424631758"><a name="zh-cn_topic_0066459131_p88424631758"></a><a name="zh-cn_topic_0066459131_p88424631758"></a>缓存在Channel中的最大Event数。</p>
    </td>
    </tr>
    <tr id="rce4169d8c0ee437190c23511cc60dbe5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p37047091758"><a name="zh-cn_topic_0066459131_p37047091758"></a><a name="zh-cn_topic_0066459131_p37047091758"></a>transactionCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p316460311758"><a name="zh-cn_topic_0066459131_p316460311758"></a><a name="zh-cn_topic_0066459131_p316460311758"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p131917091758"><a name="zh-cn_topic_0066459131_p131917091758"></a><a name="zh-cn_topic_0066459131_p131917091758"></a>每次存取的最大Event数。</p>
    </td>
    </tr>
    <tr id="r06153a55cf2942c48cc5e5b7d31cee03"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p201886971758"><a name="zh-cn_topic_0066459131_p201886971758"></a><a name="zh-cn_topic_0066459131_p201886971758"></a>channelfullcount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p246717781758"><a name="zh-cn_topic_0066459131_p246717781758"></a><a name="zh-cn_topic_0066459131_p246717781758"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p522569711758"><a name="zh-cn_topic_0066459131_p522569711758"></a><a name="zh-cn_topic_0066459131_p522569711758"></a>Channel full次数，达到该次数后发送告警。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **File Channel**

    File Channel使用本地磁盘作为缓存区，Events存放在设置的“dataDirs“配置项文件夹中。常用配置如[下表](#td180d6190e86420d8779010b90877938)所示：

    **表 8**  File Channel常用配置

    <a name="td180d6190e86420d8779010b90877938"></a>
    <table><thead align="left"><tr id="rba03767d0a94493f8d32691885da14cb"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p498158311758"><a name="zh-cn_topic_0066459131_p498158311758"></a><a name="zh-cn_topic_0066459131_p498158311758"></a><strong id="zh-cn_topic_0066459131_b428177941758"><a name="zh-cn_topic_0066459131_b428177941758"></a><a name="zh-cn_topic_0066459131_b428177941758"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p98456381758"><a name="zh-cn_topic_0066459131_p98456381758"></a><a name="zh-cn_topic_0066459131_p98456381758"></a><strong id="zh-cn_topic_0066459131_b85505001758"><a name="zh-cn_topic_0066459131_b85505001758"></a><a name="zh-cn_topic_0066459131_b85505001758"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p639308151758"><a name="zh-cn_topic_0066459131_p639308151758"></a><a name="zh-cn_topic_0066459131_p639308151758"></a><strong id="zh-cn_topic_0066459131_b592992071758"><a name="zh-cn_topic_0066459131_b592992071758"></a><a name="zh-cn_topic_0066459131_b592992071758"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="re81019e665f54a70ad25c0f0772a6d38"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p196810201758"><a name="zh-cn_topic_0066459131_p196810201758"></a><a name="zh-cn_topic_0066459131_p196810201758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p506588201758"><a name="zh-cn_topic_0066459131_p506588201758"></a><a name="zh-cn_topic_0066459131_p506588201758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p97237401758"><a name="zh-cn_topic_0066459131_p97237401758"></a><a name="zh-cn_topic_0066459131_p97237401758"></a>类型，需配置为<span class="parmvalue" id="p0a5d7d000b214e89a67d1228896dd2da"><a name="p0a5d7d000b214e89a67d1228896dd2da"></a><a name="p0a5d7d000b214e89a67d1228896dd2da"></a>“file”</span>。</p>
    </td>
    </tr>
    <tr id="r9f939ffdd17540b48e5d05566b7bc5b9"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p421758891758"><a name="zh-cn_topic_0066459131_p421758891758"></a><a name="zh-cn_topic_0066459131_p421758891758"></a>checkpointDir</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p608038491758"><a name="zh-cn_topic_0066459131_p608038491758"></a><a name="zh-cn_topic_0066459131_p608038491758"></a>${BIGDATA_DATA_HOME}/flume/checkpoint</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p389699911758"><a name="zh-cn_topic_0066459131_p389699911758"></a><a name="zh-cn_topic_0066459131_p389699911758"></a>检查点存放路径。</p>
    </td>
    </tr>
    <tr id="r3a88c82306eb402ca801c928f821e725"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p220743101758"><a name="zh-cn_topic_0066459131_p220743101758"></a><a name="zh-cn_topic_0066459131_p220743101758"></a>dataDirs</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p431886571758"><a name="zh-cn_topic_0066459131_p431886571758"></a><a name="zh-cn_topic_0066459131_p431886571758"></a>${BIGDATA_DATA_HOME}/flume/data</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p271583691758"><a name="zh-cn_topic_0066459131_p271583691758"></a><a name="zh-cn_topic_0066459131_p271583691758"></a>数据缓存路径，设置多个路径可提升性能，中间用逗号分开。</p>
    </td>
    </tr>
    <tr id="re8eb79d0858f4b569bd24cf68fb18a66"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p13367481758"><a name="zh-cn_topic_0066459131_p13367481758"></a><a name="zh-cn_topic_0066459131_p13367481758"></a>maxFileSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p411677971758"><a name="zh-cn_topic_0066459131_p411677971758"></a><a name="zh-cn_topic_0066459131_p411677971758"></a>2146435071</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p462572661758"><a name="zh-cn_topic_0066459131_p462572661758"></a><a name="zh-cn_topic_0066459131_p462572661758"></a>单个缓存文件的最大值，单位：字节。</p>
    </td>
    </tr>
    <tr id="r7807c7528a024500ad553bb5c5494066"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p328977111758"><a name="zh-cn_topic_0066459131_p328977111758"></a><a name="zh-cn_topic_0066459131_p328977111758"></a>minimumRequiredSpace</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p474689261758"><a name="zh-cn_topic_0066459131_p474689261758"></a><a name="zh-cn_topic_0066459131_p474689261758"></a>524288000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p197778221758"><a name="zh-cn_topic_0066459131_p197778221758"></a><a name="zh-cn_topic_0066459131_p197778221758"></a>缓冲区空闲空间最小值，单位：字节。</p>
    </td>
    </tr>
    <tr id="r7981be9bee8b46678107cadebb35288c"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p567358561758"><a name="zh-cn_topic_0066459131_p567358561758"></a><a name="zh-cn_topic_0066459131_p567358561758"></a>capacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p322015841758"><a name="zh-cn_topic_0066459131_p322015841758"></a><a name="zh-cn_topic_0066459131_p322015841758"></a>1000000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p581914841758"><a name="zh-cn_topic_0066459131_p581914841758"></a><a name="zh-cn_topic_0066459131_p581914841758"></a>缓存在Channel中的最大Event数。</p>
    </td>
    </tr>
    <tr id="rdc01741f99234fbcb46c299303c50c00"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p87903811758"><a name="zh-cn_topic_0066459131_p87903811758"></a><a name="zh-cn_topic_0066459131_p87903811758"></a>transactionCapacity</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p409322801758"><a name="zh-cn_topic_0066459131_p409322801758"></a><a name="zh-cn_topic_0066459131_p409322801758"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p271803961758"><a name="zh-cn_topic_0066459131_p271803961758"></a><a name="zh-cn_topic_0066459131_p271803961758"></a>每次存取的最大Event数。</p>
    </td>
    </tr>
    <tr id="r2769cd7d5774439284efc3622f36a286"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p173938391758"><a name="zh-cn_topic_0066459131_p173938391758"></a><a name="zh-cn_topic_0066459131_p173938391758"></a>channelfullcount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p667237271758"><a name="zh-cn_topic_0066459131_p667237271758"></a><a name="zh-cn_topic_0066459131_p667237271758"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p359127871758"><a name="zh-cn_topic_0066459131_p359127871758"></a><a name="zh-cn_topic_0066459131_p359127871758"></a>Channel full次数，达到该次数后发送告警。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Kafka Channel**

    Kafka Channel使用kafka集群缓存数据，Kafka提供高可用、多副本，以防Flume或Kafka Broker崩溃，Channel中的数据会立即被Sink消费。常用配置如[表 10 Kafka Channel 常用配置](#ta58e4ea5e98446418e498b81cf0c75b7)所示 

    **表 9**  Kafka Channel 常用配置

    <a name="ta58e4ea5e98446418e498b81cf0c75b7"></a>
    <table><thead align="left"><tr id="rff4c69fc6ac048a3b6106d552dab78a4"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p105045311758"><a name="zh-cn_topic_0066459131_p105045311758"></a><a name="zh-cn_topic_0066459131_p105045311758"></a><strong id="a61555af3d5db41c3a25e5f9712d831b2"><a name="a61555af3d5db41c3a25e5f9712d831b2"></a><a name="a61555af3d5db41c3a25e5f9712d831b2"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0066459131_p73927981758"><a name="zh-cn_topic_0066459131_p73927981758"></a><a name="zh-cn_topic_0066459131_p73927981758"></a><strong id="a8433a23373cd4422a387a594213956f7"><a name="a8433a23373cd4422a387a594213956f7"></a><a name="a8433a23373cd4422a387a594213956f7"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p206406681758"><a name="zh-cn_topic_0066459131_p206406681758"></a><a name="zh-cn_topic_0066459131_p206406681758"></a><strong id="acee38f6d383743328a29455c204b7022"><a name="acee38f6d383743328a29455c204b7022"></a><a name="acee38f6d383743328a29455c204b7022"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="rb209da814106468ba942b148c701ce13"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p648505311758"><a name="zh-cn_topic_0066459131_p648505311758"></a><a name="zh-cn_topic_0066459131_p648505311758"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p184016431758"><a name="zh-cn_topic_0066459131_p184016431758"></a><a name="zh-cn_topic_0066459131_p184016431758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p601339601758"><a name="zh-cn_topic_0066459131_p601339601758"></a><a name="zh-cn_topic_0066459131_p601339601758"></a>类型，需配置为 <span class="parmvalue" id="pa302307c05d1434094a68f30595f6e8d"><a name="pa302307c05d1434094a68f30595f6e8d"></a><a name="pa302307c05d1434094a68f30595f6e8d"></a>“org.apache.flume.channel.kafka.KafkaChannel”</span>.。</p>
    </td>
    </tr>
    <tr id="r93c1fc7e14974e9eafe6c2dafc088962"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p155690131758"><a name="zh-cn_topic_0066459131_p155690131758"></a><a name="zh-cn_topic_0066459131_p155690131758"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p531305751758"><a name="zh-cn_topic_0066459131_p531305751758"></a><a name="zh-cn_topic_0066459131_p531305751758"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p86093461758"><a name="zh-cn_topic_0066459131_p86093461758"></a><a name="zh-cn_topic_0066459131_p86093461758"></a>kafka broker列表。</p>
    </td>
    </tr>
    <tr id="r70c08faa517445f7ab40169a365a998f"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p350890541758"><a name="zh-cn_topic_0066459131_p350890541758"></a><a name="zh-cn_topic_0066459131_p350890541758"></a>kafka.topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p236411081758"><a name="zh-cn_topic_0066459131_p236411081758"></a><a name="zh-cn_topic_0066459131_p236411081758"></a>flume-channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p358816321758"><a name="zh-cn_topic_0066459131_p358816321758"></a><a name="zh-cn_topic_0066459131_p358816321758"></a>Channel用来缓存数据的topic。</p>
    </td>
    </tr>
    <tr id="rdc7cec1d498d49b6a7ab575ced85c934"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p523617011758"><a name="zh-cn_topic_0066459131_p523617011758"></a><a name="zh-cn_topic_0066459131_p523617011758"></a>kafka.consumer.group.id</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p134394111758"><a name="zh-cn_topic_0066459131_p134394111758"></a><a name="zh-cn_topic_0066459131_p134394111758"></a>flume</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p148504811758"><a name="zh-cn_topic_0066459131_p148504811758"></a><a name="zh-cn_topic_0066459131_p148504811758"></a>Kafka消费者组ID。</p>
    </td>
    </tr>
    <tr id="r0f6e374ca98947e69ece2e7fe7db7e71"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p214736031758"><a name="zh-cn_topic_0066459131_p214736031758"></a><a name="zh-cn_topic_0066459131_p214736031758"></a>parseAsFlumeEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p616402731758"><a name="zh-cn_topic_0066459131_p616402731758"></a><a name="zh-cn_topic_0066459131_p616402731758"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p268062201758"><a name="zh-cn_topic_0066459131_p268062201758"></a><a name="zh-cn_topic_0066459131_p268062201758"></a>是否解析为Flume event。</p>
    </td>
    </tr>
    <tr id="r536ea53053c2460096ef10b81b75a5c8"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p130550941758"><a name="zh-cn_topic_0066459131_p130550941758"></a><a name="zh-cn_topic_0066459131_p130550941758"></a>migrateZookeeperOffsets</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p508296631758"><a name="zh-cn_topic_0066459131_p508296631758"></a><a name="zh-cn_topic_0066459131_p508296631758"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p235620001758"><a name="zh-cn_topic_0066459131_p235620001758"></a><a name="zh-cn_topic_0066459131_p235620001758"></a>当Kafka没有存储offset时，是否从ZooKeeper中查找，并提交到Kafka。</p>
    </td>
    </tr>
    <tr id="r92a9c1a1288d4ef6a2c194f130ece84b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p639379881758"><a name="zh-cn_topic_0066459131_p639379881758"></a><a name="zh-cn_topic_0066459131_p639379881758"></a>kafka.consumer.auto.offset.reset</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p115945781758"><a name="zh-cn_topic_0066459131_p115945781758"></a><a name="zh-cn_topic_0066459131_p115945781758"></a>latest</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p667456361758"><a name="zh-cn_topic_0066459131_p667456361758"></a><a name="zh-cn_topic_0066459131_p667456361758"></a>当没有offset记录时，从指定的位置消费数据。</p>
    </td>
    </tr>
    <tr id="r6a4c9130ed67427e9ed6db5f479a821f"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p36428141758"><a name="zh-cn_topic_0066459131_p36428141758"></a><a name="zh-cn_topic_0066459131_p36428141758"></a>kafka.producer.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p266325551758"><a name="zh-cn_topic_0066459131_p266325551758"></a><a name="zh-cn_topic_0066459131_p266325551758"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p97533361758"><a name="zh-cn_topic_0066459131_p97533361758"></a><a name="zh-cn_topic_0066459131_p97533361758"></a>Kafka生产者安全协议。</p>
    </td>
    </tr>
    <tr id="r7a34758ad20540b9964d6b1bb2fe4e86"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p637514191758"><a name="zh-cn_topic_0066459131_p637514191758"></a><a name="zh-cn_topic_0066459131_p637514191758"></a>kafka.consumer.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p635912801758"><a name="zh-cn_topic_0066459131_p635912801758"></a><a name="zh-cn_topic_0066459131_p635912801758"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a74697ecb1be742968c394b9bac8c950f"><a name="a74697ecb1be742968c394b9bac8c950f"></a><a name="a74697ecb1be742968c394b9bac8c950f"></a>Kafka消费者安全协议。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 常用Sink配置<a name="s7d014458bd014b1891c713d57d369f2f"></a>

-   **HDFS Sink**

    HDFS Sink将数据写入HDFS。常用配置如[下表](#t3f4509459f734167afdd0cb20857d2ef)所示：

    **表 10**  HDFS Sink常用配置

    <a name="t3f4509459f734167afdd0cb20857d2ef"></a>
    <table><thead align="left"><tr id="r428a381b672745aab7c2ea64ea8babd5"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a8d2bca0510a541b3a5ccb21798bff2b6"><a name="a8d2bca0510a541b3a5ccb21798bff2b6"></a><a name="a8d2bca0510a541b3a5ccb21798bff2b6"></a><strong id="a150cb57dda5f4e1d8009e004848c318a"><a name="a150cb57dda5f4e1d8009e004848c318a"></a><a name="a150cb57dda5f4e1d8009e004848c318a"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="acc7f6e47f19c44d3a7b7419ff82c8ea9"><a name="acc7f6e47f19c44d3a7b7419ff82c8ea9"></a><a name="acc7f6e47f19c44d3a7b7419ff82c8ea9"></a><strong id="a9648039eec824b63bb3c04fba6030c3f"><a name="a9648039eec824b63bb3c04fba6030c3f"></a><a name="a9648039eec824b63bb3c04fba6030c3f"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p328508017533"><a name="zh-cn_topic_0066459131_p328508017533"></a><a name="zh-cn_topic_0066459131_p328508017533"></a><strong id="a88dae19dc91a4b2c9793e3500716d779"><a name="a88dae19dc91a4b2c9793e3500716d779"></a><a name="a88dae19dc91a4b2c9793e3500716d779"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r6f4b81287cdf4a60978dd11293789afd"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a11db38e8f11e44aeb05a01182c40c055"><a name="a11db38e8f11e44aeb05a01182c40c055"></a><a name="a11db38e8f11e44aeb05a01182c40c055"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a582103f12263427da0905257bd2697dc"><a name="a582103f12263427da0905257bd2697dc"></a><a name="a582103f12263427da0905257bd2697dc"></a><strong id="ac01029686b15427aa8b605de731bfacf"><a name="ac01029686b15427aa8b605de731bfacf"></a><a name="ac01029686b15427aa8b605de731bfacf"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p619013817533"><a name="zh-cn_topic_0066459131_p619013817533"></a><a name="zh-cn_topic_0066459131_p619013817533"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="r0b8083b767f14f068faf94198eecc389"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="af3e90a3bf11d4335a8cb9f2033984bd6"><a name="af3e90a3bf11d4335a8cb9f2033984bd6"></a><a name="af3e90a3bf11d4335a8cb9f2033984bd6"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4a73455e81734c9190ebbbce1decd067"><a name="a4a73455e81734c9190ebbbce1decd067"></a><a name="a4a73455e81734c9190ebbbce1decd067"></a>hdfs</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a265167e9f50f4a399f5dc9926354bb77"><a name="a265167e9f50f4a399f5dc9926354bb77"></a><a name="a265167e9f50f4a399f5dc9926354bb77"></a>类型，需配置为<span class="parmvalue" id="p9018bb8360ee4dc9b82baa044d34ec28"><a name="p9018bb8360ee4dc9b82baa044d34ec28"></a><a name="p9018bb8360ee4dc9b82baa044d34ec28"></a>“hdfs”</span>。</p>
    </td>
    </tr>
    <tr id="rb6cfe4a1765e498cac531919cc241103"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a6a38b53182834d65a3ab52cc50acbaa0"><a name="a6a38b53182834d65a3ab52cc50acbaa0"></a><a name="a6a38b53182834d65a3ab52cc50acbaa0"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p843901117533"><a name="zh-cn_topic_0066459131_p843901117533"></a><a name="zh-cn_topic_0066459131_p843901117533"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa4a8646530a24ba69c552822844aebd0"><a name="aa4a8646530a24ba69c552822844aebd0"></a><a name="aa4a8646530a24ba69c552822844aebd0"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="r1c72034e03d740838cfa8ecf35ae1185"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae65ca687db7643e38536252f8a349a61"><a name="ae65ca687db7643e38536252f8a349a61"></a><a name="ae65ca687db7643e38536252f8a349a61"></a>hdfs.path</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a13d14639b59747c98b003acabf1e32c1"><a name="a13d14639b59747c98b003acabf1e32c1"></a><a name="a13d14639b59747c98b003acabf1e32c1"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a00deeca3d3244cf68e9fe7ae968414ce"><a name="a00deeca3d3244cf68e9fe7ae968414ce"></a><a name="a00deeca3d3244cf68e9fe7ae968414ce"></a>HDFS路径。</p>
    </td>
    </tr>
    <tr id="r07fc2301dfd5446086b9cf6071fd9014"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a1eca519a1fe8438fb2e3409a8d181d6c"><a name="a1eca519a1fe8438fb2e3409a8d181d6c"></a><a name="a1eca519a1fe8438fb2e3409a8d181d6c"></a>hdfs.inUseSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae09cfb564fed4af1800e0a6bf5094316"><a name="ae09cfb564fed4af1800e0a6bf5094316"></a><a name="ae09cfb564fed4af1800e0a6bf5094316"></a>.tmp</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a7ed839e807c0423996251f3c8e06fac0"><a name="a7ed839e807c0423996251f3c8e06fac0"></a><a name="a7ed839e807c0423996251f3c8e06fac0"></a>正在写入的HDFS文件后缀。</p>
    </td>
    </tr>
    <tr id="rab8fc474da824422812d2f37c7d5f408"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="af809d471a241484aa6f1595025978cb6"><a name="af809d471a241484aa6f1595025978cb6"></a><a name="af809d471a241484aa6f1595025978cb6"></a>hdfs.rollInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p880104717533"><a name="zh-cn_topic_0066459131_p880104717533"></a><a name="zh-cn_topic_0066459131_p880104717533"></a>30</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a7f0f6f452a574b95a916b31628c220b6"><a name="a7f0f6f452a574b95a916b31628c220b6"></a><a name="a7f0f6f452a574b95a916b31628c220b6"></a>按时间滚动文件，单位：秒。</p>
    </td>
    </tr>
    <tr id="re2b855b21d1247db932da00aa16ff143"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p201758517533"><a name="zh-cn_topic_0066459131_p201758517533"></a><a name="zh-cn_topic_0066459131_p201758517533"></a>hdfs.rollSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab0daa8c0cdb84cf29a0e5aa6ed504d0f"><a name="ab0daa8c0cdb84cf29a0e5aa6ed504d0f"></a><a name="ab0daa8c0cdb84cf29a0e5aa6ed504d0f"></a>1024</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a0d21426e67d84437b35f2f1f02d1de14"><a name="a0d21426e67d84437b35f2f1f02d1de14"></a><a name="a0d21426e67d84437b35f2f1f02d1de14"></a>按大小滚动文件，单位：字节。</p>
    </td>
    </tr>
    <tr id="r3daec9017b184ece8994115463f9e739"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a7df4d1dd875b4afdb965e00b3296a2bb"><a name="a7df4d1dd875b4afdb965e00b3296a2bb"></a><a name="a7df4d1dd875b4afdb965e00b3296a2bb"></a>hdfs.rollCount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab5859a61079449b493d5039f5b6a4737"><a name="ab5859a61079449b493d5039f5b6a4737"></a><a name="ab5859a61079449b493d5039f5b6a4737"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a40b74d2a8eb04d9ea41ae99b097fb55a"><a name="a40b74d2a8eb04d9ea41ae99b097fb55a"></a><a name="a40b74d2a8eb04d9ea41ae99b097fb55a"></a>按Event个数滚动文件。</p>
    </td>
    </tr>
    <tr id="r115413f2353c4106a84eeb3811f9be60"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="acd88f8cbcc8f48a88ffaf0b39c3fe25e"><a name="acd88f8cbcc8f48a88ffaf0b39c3fe25e"></a><a name="acd88f8cbcc8f48a88ffaf0b39c3fe25e"></a>hdfs.idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p981461617533"><a name="zh-cn_topic_0066459131_p981461617533"></a><a name="zh-cn_topic_0066459131_p981461617533"></a>0</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a6394e611a30143499f441fa5502d4936"><a name="a6394e611a30143499f441fa5502d4936"></a><a name="a6394e611a30143499f441fa5502d4936"></a>自动关闭空闲文件超时时间，单位：秒。</p>
    </td>
    </tr>
    <tr id="r68b30643028b4c9293ca8e33fe69295b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a77d305269b3948c598889cfe46213f47"><a name="a77d305269b3948c598889cfe46213f47"></a><a name="a77d305269b3948c598889cfe46213f47"></a>hdfs.batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a2ee9988a5566422ba6a20544038c8f1e"><a name="a2ee9988a5566422ba6a20544038c8f1e"></a><a name="a2ee9988a5566422ba6a20544038c8f1e"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a7d6ebd7da6bb4bcc8ada3b290fb1d121"><a name="a7d6ebd7da6bb4bcc8ada3b290fb1d121"></a><a name="a7d6ebd7da6bb4bcc8ada3b290fb1d121"></a>每次写入HDFS的Event个数。</p>
    </td>
    </tr>
    <tr id="r1466b090ba4c46fdb8ca140c7c63cac3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a382a357d4a034556a78b9262b85d9868"><a name="a382a357d4a034556a78b9262b85d9868"></a><a name="a382a357d4a034556a78b9262b85d9868"></a>hdfs.kerberosPrincipal</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab6938a937d0d42509dd97c46c7ec3f0e"><a name="ab6938a937d0d42509dd97c46c7ec3f0e"></a><a name="ab6938a937d0d42509dd97c46c7ec3f0e"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a3156f686d01a45a890ae6fd7b1cf3f3a"><a name="a3156f686d01a45a890ae6fd7b1cf3f3a"></a><a name="a3156f686d01a45a890ae6fd7b1cf3f3a"></a>认证HDFS的Kerberos用户名，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    <tr id="r2bf541a598f54a6abaacb9257ec67321"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a36c43bfaf9b44106a668ef172ca5c140"><a name="a36c43bfaf9b44106a668ef172ca5c140"></a><a name="a36c43bfaf9b44106a668ef172ca5c140"></a>hdfs.kerberosKeytab</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ad4030b99937c4946becab0a05ad41fb9"><a name="ad4030b99937c4946becab0a05ad41fb9"></a><a name="ad4030b99937c4946becab0a05ad41fb9"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="adae96cd9d118455584e07be0d513e3c0"><a name="adae96cd9d118455584e07be0d513e3c0"></a><a name="adae96cd9d118455584e07be0d513e3c0"></a>认证HDFS的Kerberos keytab路径，未启用Kerberos认证集群不配置</p>
    </td>
    </tr>
    <tr id="rc715718c37434f8a973ea6dec2274397"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a8f4edbee92dc45d1aa67023b2a25ba60"><a name="a8f4edbee92dc45d1aa67023b2a25ba60"></a><a name="a8f4edbee92dc45d1aa67023b2a25ba60"></a>hdfs.fileCloseByEndEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a001a4facae8740f299d5e7ca1993f8e9"><a name="a001a4facae8740f299d5e7ca1993f8e9"></a><a name="a001a4facae8740f299d5e7ca1993f8e9"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ad1be897c0b434c158fbe44a1ff78a590"><a name="ad1be897c0b434c158fbe44a1ff78a590"></a><a name="ad1be897c0b434c158fbe44a1ff78a590"></a>收到最后一个Event时是否关闭文件。</p>
    </td>
    </tr>
    <tr id="rbfb26ebc81584714b8fa2f0ecbc15749"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a530f21bfe9f144538c3712205ae8c38d"><a name="a530f21bfe9f144538c3712205ae8c38d"></a><a name="a530f21bfe9f144538c3712205ae8c38d"></a>hdfs.batchCallTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ad075b831ade249a39b6615e69aab68bb"><a name="ad075b831ade249a39b6615e69aab68bb"></a><a name="ad075b831ade249a39b6615e69aab68bb"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ac53f40e7d18349eba7240db41055d46a"><a name="ac53f40e7d18349eba7240db41055d46a"></a><a name="ac53f40e7d18349eba7240db41055d46a"></a>每次写入HDFS超时控制时间，单位：毫秒。</p>
    <p id="aeae7224c87ec46969831bc8f0c18fed1"><a name="aeae7224c87ec46969831bc8f0c18fed1"></a><a name="aeae7224c87ec46969831bc8f0c18fed1"></a>当不配置此参数时，对每个Event写入HDFS进行超时控制。当<span class="parmname" id="p28e8f45199794ea09d1fc4cae28d2474"><a name="p28e8f45199794ea09d1fc4cae28d2474"></a><a name="p28e8f45199794ea09d1fc4cae28d2474"></a>“hdfs.batchSize”</span>大于0时，配置此参数可以提升写入HDFS性能。</p>
    <div class="note" id="nd9c23ee414754ff580abc33dd73a4bf0"><a name="nd9c23ee414754ff580abc33dd73a4bf0"></a><a name="nd9c23ee414754ff580abc33dd73a4bf0"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="ac5be970c6595411393f32ecad2a3b6b6"><a name="ac5be970c6595411393f32ecad2a3b6b6"></a><a name="ac5be970c6595411393f32ecad2a3b6b6"></a><span class="parmname" id="pf0046215e4a94798b0a423ef2d716595"><a name="pf0046215e4a94798b0a423ef2d716595"></a><a name="pf0046215e4a94798b0a423ef2d716595"></a>“hdfs.batchCallTimeout”</span>设置多长时间需要考虑<span class="parmname" id="p03128f0e0bfb4353bb7fe3cea035f82f"><a name="p03128f0e0bfb4353bb7fe3cea035f82f"></a><a name="p03128f0e0bfb4353bb7fe3cea035f82f"></a>“hdfs.batchSize”</span>的大小，<span class="parmname" id="p97f23f51d7c14a86bcc4fc7ee0c9f8d8"><a name="p97f23f51d7c14a86bcc4fc7ee0c9f8d8"></a><a name="p97f23f51d7c14a86bcc4fc7ee0c9f8d8"></a>“hdfs.batchSize”</span>越大，<span class="parmname" id="pf0f8234547924b4d981ccd3b347f8039"><a name="pf0f8234547924b4d981ccd3b347f8039"></a><a name="pf0f8234547924b4d981ccd3b347f8039"></a>“hdfs.batchCallTimeout”</span>也要调整更长时间，设置过短时间容易导致数据写入HDFS失败。</p>
    </div></div>
    </td>
    </tr>
    <tr id="r1b60be2a793c4b6aa8cd56cf37038bab"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a68d545c4ef3c4f71bf3e9995a2080a9f"><a name="a68d545c4ef3c4f71bf3e9995a2080a9f"></a><a name="a68d545c4ef3c4f71bf3e9995a2080a9f"></a>serializer.appendNewline</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a9c53ede997cb4f8983d341b28673e235"><a name="a9c53ede997cb4f8983d341b28673e235"></a><a name="a9c53ede997cb4f8983d341b28673e235"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a824e416390154521b07055764a28279e"><a name="a824e416390154521b07055764a28279e"></a><a name="a824e416390154521b07055764a28279e"></a>将一个Event写入HDFS后是否追加换行符（'\n'），如果追加该换行符，该换行符所占用的数据量指标不会被HDFS Sink统计。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Avro Sink**

    Avro Sink把events转化为Avro events并发送到配置的主机的监听端口。常用配置如[下表](#tcf9863ee677d41a6882b71987541fa33)所示

    **表 11**  Avro Sink常用配置

    <a name="tcf9863ee677d41a6882b71987541fa33"></a>
    <table><thead align="left"><tr id="re19fc9b53efa43969c188df75afc7df6"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p660555417533"><a name="zh-cn_topic_0066459131_p660555417533"></a><a name="zh-cn_topic_0066459131_p660555417533"></a><strong id="a4b3ef20be65c4f7ebf1fd6714a5f6dea"><a name="a4b3ef20be65c4f7ebf1fd6714a5f6dea"></a><a name="a4b3ef20be65c4f7ebf1fd6714a5f6dea"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="acfed75dc45a742b08b9ce5abbc177936"><a name="acfed75dc45a742b08b9ce5abbc177936"></a><a name="acfed75dc45a742b08b9ce5abbc177936"></a><strong id="a13c9e1819de04f8abda5c649c4c55f67"><a name="a13c9e1819de04f8abda5c649c4c55f67"></a><a name="a13c9e1819de04f8abda5c649c4c55f67"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a60dbbde284224956a74d97d57add9430"><a name="a60dbbde284224956a74d97d57add9430"></a><a name="a60dbbde284224956a74d97d57add9430"></a><strong id="a830ef800b3a04beead4b9935f305b027"><a name="a830ef800b3a04beead4b9935f305b027"></a><a name="a830ef800b3a04beead4b9935f305b027"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r6e296b1504eb45fe827576692235a400"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a59bd61b8c29c414280fe5a6e1546d55d"><a name="a59bd61b8c29c414280fe5a6e1546d55d"></a><a name="a59bd61b8c29c414280fe5a6e1546d55d"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aeb897062962f4311905bb80da552798d"><a name="aeb897062962f4311905bb80da552798d"></a><a name="aeb897062962f4311905bb80da552798d"></a><strong id="a888ca45b6ab2472bacc8d77ad224f7a0"><a name="a888ca45b6ab2472bacc8d77ad224f7a0"></a><a name="a888ca45b6ab2472bacc8d77ad224f7a0"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ab0acbcd6fd62453a95e23b8d68c3e67c"><a name="ab0acbcd6fd62453a95e23b8d68c3e67c"></a><a name="ab0acbcd6fd62453a95e23b8d68c3e67c"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="r789d9fd3aa0f46d4ba39710ffc024aea"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a05cb3e099e57474faf4ebe8fed4255ef"><a name="a05cb3e099e57474faf4ebe8fed4255ef"></a><a name="a05cb3e099e57474faf4ebe8fed4255ef"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aa8e7c3480f394f92a6d5a7072bca25c6"><a name="aa8e7c3480f394f92a6d5a7072bca25c6"></a><a name="aa8e7c3480f394f92a6d5a7072bca25c6"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="af8a448089f394d3b9215cd3fcf8a9b2c"><a name="af8a448089f394d3b9215cd3fcf8a9b2c"></a><a name="af8a448089f394d3b9215cd3fcf8a9b2c"></a>类型，需配置为<span class="parmvalue" id="p260ea6b33ad54455840d7ded67b33782"><a name="p260ea6b33ad54455840d7ded67b33782"></a><a name="p260ea6b33ad54455840d7ded67b33782"></a>“avro”</span>。</p>
    </td>
    </tr>
    <tr id="r1fb98adb58c14054830c2a3764b53548"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae2fe815312de4ae6bcb2a528093a4729"><a name="ae2fe815312de4ae6bcb2a528093a4729"></a><a name="ae2fe815312de4ae6bcb2a528093a4729"></a>hostname</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p35597717533"><a name="zh-cn_topic_0066459131_p35597717533"></a><a name="zh-cn_topic_0066459131_p35597717533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a06c85d581bff44fbaca045f059d8edf2"><a name="a06c85d581bff44fbaca045f059d8edf2"></a><a name="a06c85d581bff44fbaca045f059d8edf2"></a>绑定关联的主机名或IP地址。</p>
    </td>
    </tr>
    <tr id="r0c1a3a0f05004faa8ecee29c84a5a77e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aeed48f0613464ed09459021a7c072dc1"><a name="aeed48f0613464ed09459021a7c072dc1"></a><a name="aeed48f0613464ed09459021a7c072dc1"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p924698617533"><a name="zh-cn_topic_0066459131_p924698617533"></a><a name="zh-cn_topic_0066459131_p924698617533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aba450cb5a8ba470eab62752c9459f69d"><a name="aba450cb5a8ba470eab62752c9459f69d"></a><a name="aba450cb5a8ba470eab62752c9459f69d"></a>监听端口。</p>
    </td>
    </tr>
    <tr id="r62e564bdeea247f58174047cb98b0ffd"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a4db78151f4f04c2489c7f47d5c895df3"><a name="a4db78151f4f04c2489c7f47d5c895df3"></a><a name="a4db78151f4f04c2489c7f47d5c895df3"></a>batch-size</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a7bc09ed79a584ecca7df52513cea12a5"><a name="a7bc09ed79a584ecca7df52513cea12a5"></a><a name="a7bc09ed79a584ecca7df52513cea12a5"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="af45550ce5d9e4f1fbba4964df3d5a69b"><a name="af45550ce5d9e4f1fbba4964df3d5a69b"></a><a name="af45550ce5d9e4f1fbba4964df3d5a69b"></a>批次发送的Event个数。</p>
    </td>
    </tr>
    <tr id="rede163131eec4250ae961c5d0b0aebce"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab0edd0f1bbdd412ea38b096ea3e77cb2"><a name="ab0edd0f1bbdd412ea38b096ea3e77cb2"></a><a name="ab0edd0f1bbdd412ea38b096ea3e77cb2"></a>ssl</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p334117217533"><a name="zh-cn_topic_0066459131_p334117217533"></a><a name="zh-cn_topic_0066459131_p334117217533"></a>false</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p219951417533"><a name="zh-cn_topic_0066459131_p219951417533"></a><a name="zh-cn_topic_0066459131_p219951417533"></a>是否使用SSL加密。</p>
    </td>
    </tr>
    <tr id="r6439ad5ed5f944aa95641e90a05fe1f0"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a641dabd3c6b44853992c63b1cc33d918"><a name="a641dabd3c6b44853992c63b1cc33d918"></a><a name="a641dabd3c6b44853992c63b1cc33d918"></a>truststore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ad409d4fde0414f5391e1f4716c559649"><a name="ad409d4fde0414f5391e1f4716c559649"></a><a name="ad409d4fde0414f5391e1f4716c559649"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="acede364f20694d38ac0810a4f422f219"><a name="acede364f20694d38ac0810a4f422f219"></a><a name="acede364f20694d38ac0810a4f422f219"></a>Java信任库类型。</p>
    </td>
    </tr>
    <tr id="r1ba554f453694aa9973e9053c824cdd7"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a3c4857121cf6423da51ead2a3c093c88"><a name="a3c4857121cf6423da51ead2a3c093c88"></a><a name="a3c4857121cf6423da51ead2a3c093c88"></a>truststore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a0a3be538d86b4833baee1ce331812c85"><a name="a0a3be538d86b4833baee1ce331812c85"></a><a name="a0a3be538d86b4833baee1ce331812c85"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p196860717533"><a name="zh-cn_topic_0066459131_p196860717533"></a><a name="zh-cn_topic_0066459131_p196860717533"></a>Java信任库文件。</p>
    </td>
    </tr>
    <tr id="r5bf8d80ddc454c5d80a4dd0c70c30a81"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="af1895eab45904dcc9787cb52a5eaceaf"><a name="af1895eab45904dcc9787cb52a5eaceaf"></a><a name="af1895eab45904dcc9787cb52a5eaceaf"></a>truststore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a38db08ecc8654854b9a040aa2ca0359f"><a name="a38db08ecc8654854b9a040aa2ca0359f"></a><a name="a38db08ecc8654854b9a040aa2ca0359f"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="adf82dda138354588b5ce521a0b244601"><a name="adf82dda138354588b5ce521a0b244601"></a><a name="adf82dda138354588b5ce521a0b244601"></a>Java信任库密码。</p>
    </td>
    </tr>
    <tr id="r1b03bc431e7f4c7e867ffa8c4a1ada50"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="accc23caf3bc543728bec1e35ee865314"><a name="accc23caf3bc543728bec1e35ee865314"></a><a name="accc23caf3bc543728bec1e35ee865314"></a>keystore-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p476166117533"><a name="zh-cn_topic_0066459131_p476166117533"></a><a name="zh-cn_topic_0066459131_p476166117533"></a>JKS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a9caa5e4f54d04b8cbb700486a839131f"><a name="a9caa5e4f54d04b8cbb700486a839131f"></a><a name="a9caa5e4f54d04b8cbb700486a839131f"></a>密钥存储类型。</p>
    </td>
    </tr>
    <tr id="r3487c784e9784e81a44a951f169c6320"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aba9d1f2a3fbc4b2298a4fe754deffa03"><a name="aba9d1f2a3fbc4b2298a4fe754deffa03"></a><a name="aba9d1f2a3fbc4b2298a4fe754deffa03"></a>keystore</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p831478117533"><a name="zh-cn_topic_0066459131_p831478117533"></a><a name="zh-cn_topic_0066459131_p831478117533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p240867317533"><a name="zh-cn_topic_0066459131_p240867317533"></a><a name="zh-cn_topic_0066459131_p240867317533"></a>密钥存储文件。</p>
    </td>
    </tr>
    <tr id="r57c2243216a548d89e171586a613e83c"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aee3b5126dddc4869a68d65a8f21e5b40"><a name="aee3b5126dddc4869a68d65a8f21e5b40"></a><a name="aee3b5126dddc4869a68d65a8f21e5b40"></a>keystore-password</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a4c21117bae7e46bba3e23c3848f779f7"><a name="a4c21117bae7e46bba3e23c3848f779f7"></a><a name="a4c21117bae7e46bba3e23c3848f779f7"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aca9b7d4fabc346a58257274b94875590"><a name="aca9b7d4fabc346a58257274b94875590"></a><a name="aca9b7d4fabc346a58257274b94875590"></a>密钥存储密码</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **HBase Sink**

    HBase Sink将数据写入到HBase中。常用配置如[下表](#tf429beac69444e93a744abfe1d0fb744)所示：

    **表 12**  HBase Sink常用配置

    <a name="tf429beac69444e93a744abfe1d0fb744"></a>
    <table><thead align="left"><tr id="ra970fcbddbeb4ec5bc23c81b686b33da"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a769b4777d8634bb0869894c50860b3d4"><a name="a769b4777d8634bb0869894c50860b3d4"></a><a name="a769b4777d8634bb0869894c50860b3d4"></a><strong id="a6d37fa300354467b83dbea427bfd65eb"><a name="a6d37fa300354467b83dbea427bfd65eb"></a><a name="a6d37fa300354467b83dbea427bfd65eb"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a84061bc2d39a4d5ab068eb59bd84f457"><a name="a84061bc2d39a4d5ab068eb59bd84f457"></a><a name="a84061bc2d39a4d5ab068eb59bd84f457"></a><strong id="a1bff2d21e37b485a9c5716f48441601f"><a name="a1bff2d21e37b485a9c5716f48441601f"></a><a name="a1bff2d21e37b485a9c5716f48441601f"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0066459131_p763900917533"><a name="zh-cn_topic_0066459131_p763900917533"></a><a name="zh-cn_topic_0066459131_p763900917533"></a><strong id="zh-cn_topic_0066459131_b84877817533"><a name="zh-cn_topic_0066459131_b84877817533"></a><a name="zh-cn_topic_0066459131_b84877817533"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="ra2df0f21842740cf80551de7e30423f0"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a1c1fda0a54de4529ba72ad4883ed02f1"><a name="a1c1fda0a54de4529ba72ad4883ed02f1"></a><a name="a1c1fda0a54de4529ba72ad4883ed02f1"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a970e1ea742344ab09ec7bcd370f6715a"><a name="a970e1ea742344ab09ec7bcd370f6715a"></a><a name="a970e1ea742344ab09ec7bcd370f6715a"></a><strong id="a4858c02556d6474c86bcad898d6d2778"><a name="a4858c02556d6474c86bcad898d6d2778"></a><a name="a4858c02556d6474c86bcad898d6d2778"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="abb556afd58584cf6b04a9186890ade9e"><a name="abb556afd58584cf6b04a9186890ade9e"></a><a name="abb556afd58584cf6b04a9186890ade9e"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="rdcf7ac3bb8484b9fa7c2e51c12a66737"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p568160617533"><a name="zh-cn_topic_0066459131_p568160617533"></a><a name="zh-cn_topic_0066459131_p568160617533"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a61fcc3ab01ea477c9cd0fd2e00ce4602"><a name="a61fcc3ab01ea477c9cd0fd2e00ce4602"></a><a name="a61fcc3ab01ea477c9cd0fd2e00ce4602"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a51dfd4d22d464108b62552aed4341f39"><a name="a51dfd4d22d464108b62552aed4341f39"></a><a name="a51dfd4d22d464108b62552aed4341f39"></a>类型，需配置为<span class="parmvalue" id="p233eebfa8ca548b8be56b4345498a1b8"><a name="p233eebfa8ca548b8be56b4345498a1b8"></a><a name="p233eebfa8ca548b8be56b4345498a1b8"></a>“hbase”</span>。</p>
    </td>
    </tr>
    <tr id="r86767b1614fa4a8187eb36e6e7bdb4c6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a86f24d691409443f9593c7b6d16ac3d3"><a name="a86f24d691409443f9593c7b6d16ac3d3"></a><a name="a86f24d691409443f9593c7b6d16ac3d3"></a>table</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a18dbe4ead6e6432089a4d42e8da37fb6"><a name="a18dbe4ead6e6432089a4d42e8da37fb6"></a><a name="a18dbe4ead6e6432089a4d42e8da37fb6"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa1476d1591734f379748110926c61e82"><a name="aa1476d1591734f379748110926c61e82"></a><a name="aa1476d1591734f379748110926c61e82"></a>HBase表名称。</p>
    </td>
    </tr>
    <tr id="rf50e908f3e0f4fa5aba6530a14d09b6b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p99517817533"><a name="zh-cn_topic_0066459131_p99517817533"></a><a name="zh-cn_topic_0066459131_p99517817533"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aa416818b6376422487336b4a22fdbdda"><a name="aa416818b6376422487336b4a22fdbdda"></a><a name="aa416818b6376422487336b4a22fdbdda"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a5e0c05f647bb454f92d4890169cdd727"><a name="a5e0c05f647bb454f92d4890169cdd727"></a><a name="a5e0c05f647bb454f92d4890169cdd727"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="r138bdb7aab1b4f67ab5da7a33cb9d0c1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p802703117533"><a name="zh-cn_topic_0066459131_p802703117533"></a><a name="zh-cn_topic_0066459131_p802703117533"></a>columnFamily</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a369296d6439c417fb6e6e26773e2285f"><a name="a369296d6439c417fb6e6e26773e2285f"></a><a name="a369296d6439c417fb6e6e26773e2285f"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a734fb6dd6a5b4f40abf70ad9b58bf5d2"><a name="a734fb6dd6a5b4f40abf70ad9b58bf5d2"></a><a name="a734fb6dd6a5b4f40abf70ad9b58bf5d2"></a>HBase列族名称。</p>
    </td>
    </tr>
    <tr id="r07ba877866b345249138be459c2308e3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="add882f1e15864683a4ef46fee43299d1"><a name="add882f1e15864683a4ef46fee43299d1"></a><a name="add882f1e15864683a4ef46fee43299d1"></a>batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="abcf4f8ae555c48659f0127b1328acf06"><a name="abcf4f8ae555c48659f0127b1328acf06"></a><a name="abcf4f8ae555c48659f0127b1328acf06"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a4ad9de126988457c9080ca51350efdfc"><a name="a4ad9de126988457c9080ca51350efdfc"></a><a name="a4ad9de126988457c9080ca51350efdfc"></a>每次写入HBase的Event个数。</p>
    </td>
    </tr>
    <tr id="r3305a24ac40f496bbc0bfa12743fe915"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p980622217533"><a name="zh-cn_topic_0066459131_p980622217533"></a><a name="zh-cn_topic_0066459131_p980622217533"></a>kerberosPrincipal</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a6fd92d2fc9ef4ee9a3bce453273a7cd2"><a name="a6fd92d2fc9ef4ee9a3bce453273a7cd2"></a><a name="a6fd92d2fc9ef4ee9a3bce453273a7cd2"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ac1945205e4384c40b327e0f33d17876b"><a name="ac1945205e4384c40b327e0f33d17876b"></a><a name="ac1945205e4384c40b327e0f33d17876b"></a>认证HBase的Kerberos用户名，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    <tr id="r32bcca9c56484448ba64170bdeddb062"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p379596517533"><a name="zh-cn_topic_0066459131_p379596517533"></a><a name="zh-cn_topic_0066459131_p379596517533"></a>kerberosKeytab</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab0f6be33ecc744ed90dd6eb4925381e4"><a name="ab0f6be33ecc744ed90dd6eb4925381e4"></a><a name="ab0f6be33ecc744ed90dd6eb4925381e4"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p794234417533"><a name="zh-cn_topic_0066459131_p794234417533"></a><a name="zh-cn_topic_0066459131_p794234417533"></a>认证HBase的Kerberos keytab路径，未启用Kerberos认证集群不配置。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **Kafka Sink**

    Kafka Sink将数据写入到Kafka中。常用配置如[下表](#tf898876f2a2f45629655554005c3f0a8)所示：

    **表 13**  Kafka Sink常用配置

    <a name="tf898876f2a2f45629655554005c3f0a8"></a>
    <table><thead align="left"><tr id="r83705dd984674f549a81a591a3ab58f3"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0066459131_p565891217533"><a name="zh-cn_topic_0066459131_p565891217533"></a><a name="zh-cn_topic_0066459131_p565891217533"></a><strong id="zh-cn_topic_0066459131_b808530817533"><a name="zh-cn_topic_0066459131_b808530817533"></a><a name="zh-cn_topic_0066459131_b808530817533"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="ad21340b406434c1889a8fc44e2f65e68"><a name="ad21340b406434c1889a8fc44e2f65e68"></a><a name="ad21340b406434c1889a8fc44e2f65e68"></a><strong id="a79d80603c4394a3b893f8b989164481f"><a name="a79d80603c4394a3b893f8b989164481f"></a><a name="a79d80603c4394a3b893f8b989164481f"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a3e797ff13cfd4e29bcef95a39df33046"><a name="a3e797ff13cfd4e29bcef95a39df33046"></a><a name="a3e797ff13cfd4e29bcef95a39df33046"></a><strong id="ae59bfb1ae60e4e048c7ee7337076f6eb"><a name="ae59bfb1ae60e4e048c7ee7337076f6eb"></a><a name="ae59bfb1ae60e4e048c7ee7337076f6eb"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="ra277720243374d178ac6c8a574cd5a2b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ae22f17dd53e44391b123e10a2da0658d"><a name="ae22f17dd53e44391b123e10a2da0658d"></a><a name="ae22f17dd53e44391b123e10a2da0658d"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a1624b267ba71494db8be70b05219f307"><a name="a1624b267ba71494db8be70b05219f307"></a><a name="a1624b267ba71494db8be70b05219f307"></a><strong id="a11ceb1dbc6c94b14b56b4a85f0c1a2f5"><a name="a11ceb1dbc6c94b14b56b4a85f0c1a2f5"></a><a name="a11ceb1dbc6c94b14b56b4a85f0c1a2f5"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="afd83d2ee21994e0880545cccec045f38"><a name="afd83d2ee21994e0880545cccec045f38"></a><a name="afd83d2ee21994e0880545cccec045f38"></a>与之相连的Channel</p>
    </td>
    </tr>
    <tr id="r1543a8f29d484108a61adb4411777f0e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aa744821c495f45c1b8a9bcb810aee740"><a name="aa744821c495f45c1b8a9bcb810aee740"></a><a name="aa744821c495f45c1b8a9bcb810aee740"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a1099972b687544b887c1ab69c3a9d0bc"><a name="a1099972b687544b887c1ab69c3a9d0bc"></a><a name="a1099972b687544b887c1ab69c3a9d0bc"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a59530aa82dda48e5b990c5e7c660d87e"><a name="a59530aa82dda48e5b990c5e7c660d87e"></a><a name="a59530aa82dda48e5b990c5e7c660d87e"></a>类型，需配置为<span class="parmvalue" id="pff8b3b82581945c297957c7d4b60f7fc"><a name="pff8b3b82581945c297957c7d4b60f7fc"></a><a name="pff8b3b82581945c297957c7d4b60f7fc"></a>“org.apache.flume.sink.kafka.KafkaSink”</span>。</p>
    </td>
    </tr>
    <tr id="rb14230c362534e7482c8fabe4ae18e94"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a23a9c697afcd4f3093c9ec9c56afba86"><a name="a23a9c697afcd4f3093c9ec9c56afba86"></a><a name="a23a9c697afcd4f3093c9ec9c56afba86"></a>kafka.bootstrap.servers</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aea3856345b5d4248bddb18c5dfa78395"><a name="aea3856345b5d4248bddb18c5dfa78395"></a><a name="aea3856345b5d4248bddb18c5dfa78395"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a12061b8ddfa34d8a92ee14bccf860a16"><a name="a12061b8ddfa34d8a92ee14bccf860a16"></a><a name="a12061b8ddfa34d8a92ee14bccf860a16"></a>Kafkabrokers列表，多个用英文逗号分隔。</p>
    </td>
    </tr>
    <tr id="r3b9be3b7d10546f6856c1de26b5d1e49"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a0dcb476a77b648a2a8e5bb8f2a9ac98a"><a name="a0dcb476a77b648a2a8e5bb8f2a9ac98a"></a><a name="a0dcb476a77b648a2a8e5bb8f2a9ac98a"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a8d0ba495bab74d3a84eeb43e0b1b8f9a"><a name="a8d0ba495bab74d3a84eeb43e0b1b8f9a"></a><a name="a8d0ba495bab74d3a84eeb43e0b1b8f9a"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ad3314d2a3182424fbef136a62ba5cd54"><a name="ad3314d2a3182424fbef136a62ba5cd54"></a><a name="ad3314d2a3182424fbef136a62ba5cd54"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="r667870d07e6a4c33adf350bb627a0447"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a9ed9d60b2fc148e7886f97cd531b3540"><a name="a9ed9d60b2fc148e7886f97cd531b3540"></a><a name="a9ed9d60b2fc148e7886f97cd531b3540"></a>kafka.topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ac6eeebae5265487f92da32511f6cd4be"><a name="ac6eeebae5265487f92da32511f6cd4be"></a><a name="ac6eeebae5265487f92da32511f6cd4be"></a>default-flume-topic</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a8a420ec747cc4b778230cbb76980c371"><a name="a8a420ec747cc4b778230cbb76980c371"></a><a name="a8a420ec747cc4b778230cbb76980c371"></a>数据写入的topic。</p>
    </td>
    </tr>
    <tr id="r7f33a19dea5c4d239ffddd452edc98cd"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a5767e97d5e564a8a96cce83791eea409"><a name="a5767e97d5e564a8a96cce83791eea409"></a><a name="a5767e97d5e564a8a96cce83791eea409"></a>flumeBatchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a7381dd3e46b14861a7c2fa20874a33b6"><a name="a7381dd3e46b14861a7c2fa20874a33b6"></a><a name="a7381dd3e46b14861a7c2fa20874a33b6"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p740582917533"><a name="zh-cn_topic_0066459131_p740582917533"></a><a name="zh-cn_topic_0066459131_p740582917533"></a>每次写入Kafka的Event个数。</p>
    </td>
    </tr>
    <tr id="ra7f11dfe7e3c4d00ac8f7008da20f790"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab3ebf881143d4ed391b85e82c6e019d1"><a name="ab3ebf881143d4ed391b85e82c6e019d1"></a><a name="ab3ebf881143d4ed391b85e82c6e019d1"></a>kafka.security.protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a0908b24fc0334751b1988352f6e04b85"><a name="a0908b24fc0334751b1988352f6e04b85"></a><a name="a0908b24fc0334751b1988352f6e04b85"></a>SASL_PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa25e39815a0943e69fe4ae734da16fae"><a name="aa25e39815a0943e69fe4ae734da16fae"></a><a name="aa25e39815a0943e69fe4ae734da16fae"></a>Kafka安全协议，未启用Kerberos认证集群下须配置为<span class="parmvalue" id="p62252d84cac248309ac8bd2a4fe00ad3"><a name="p62252d84cac248309ac8bd2a4fe00ad3"></a><a name="p62252d84cac248309ac8bd2a4fe00ad3"></a>“PLAINTEXT”</span>。</p>
    </td>
    </tr>
    <tr id="r68d48aea470f4ac2991c30f53a5436ad"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p309358951508"><a name="zh-cn_topic_0066459131_p309358951508"></a><a name="zh-cn_topic_0066459131_p309358951508"></a>kafka.kerberos.domain.name</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p227795341508"><a name="zh-cn_topic_0066459131_p227795341508"></a><a name="zh-cn_topic_0066459131_p227795341508"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p332029861508"><a name="zh-cn_topic_0066459131_p332029861508"></a><a name="zh-cn_topic_0066459131_p332029861508"></a>Kafka Domain名称。安全集群必填。</p>
    </td>
    </tr>
    <tr id="r4a507fb8c4d14ad9b8f4c5b1a6878215"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a1e0caf77f9b94372b0038a03fa6f1b89"><a name="a1e0caf77f9b94372b0038a03fa6f1b89"></a><a name="a1e0caf77f9b94372b0038a03fa6f1b89"></a>Other Kafka Producer Properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p897233717533"><a name="zh-cn_topic_0066459131_p897233717533"></a><a name="zh-cn_topic_0066459131_p897233717533"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a8bfe25d2b4024f6ab9a97861fd8fdf7a"><a name="a8bfe25d2b4024f6ab9a97861fd8fdf7a"></a><a name="a8bfe25d2b4024f6ab9a97861fd8fdf7a"></a>其他Kafka配置，可以接受任意Kafka支持的生产参数配置，配置需要加前缀<span class="parmvalue" id="p02b388c0a37c472da309e8cb3970a748"><a name="p02b388c0a37c472da309e8cb3970a748"></a><a name="p02b388c0a37c472da309e8cb3970a748"></a>“.kafka”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   **OBS Sink**

    OBS Sink将数据写入OBS。由于和HDFS使用了相同的文件系统接口，因此，配置参数也大致相同。常用配置如[下表](#t2d3f80bf5e8743beacc95c731fdc7277)所示：

    **表 14**  OBS Sink常用配置

    <a name="t2d3f80bf5e8743beacc95c731fdc7277"></a>
    <table><thead align="left"><tr id="r1a69af13573e4cbea3d207213d0504f1"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="a0837cb27bed0494ea26ffaf55c402a9a"><a name="a0837cb27bed0494ea26ffaf55c402a9a"></a><a name="a0837cb27bed0494ea26ffaf55c402a9a"></a><strong id="a4d82613917bf4c40801913c4b56811ae"><a name="a4d82613917bf4c40801913c4b56811ae"></a><a name="a4d82613917bf4c40801913c4b56811ae"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="a25c3dd32a1204a2eaf7b35ee0d918bca"><a name="a25c3dd32a1204a2eaf7b35ee0d918bca"></a><a name="a25c3dd32a1204a2eaf7b35ee0d918bca"></a><strong id="a9b692091406a4b52b290e7bc035ef27a"><a name="a9b692091406a4b52b290e7bc035ef27a"></a><a name="a9b692091406a4b52b290e7bc035ef27a"></a>默认值</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="a9336a61a7dd04741ba42bce34cddc12f"><a name="a9336a61a7dd04741ba42bce34cddc12f"></a><a name="a9336a61a7dd04741ba42bce34cddc12f"></a><strong id="af08a81516d3f40b0b161e25decb25404"><a name="af08a81516d3f40b0b161e25decb25404"></a><a name="af08a81516d3f40b0b161e25decb25404"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r659264a510be49f186ad245e58c507e6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a90a9d521b55a417c93c500e3d3a21cb3"><a name="a90a9d521b55a417c93c500e3d3a21cb3"></a><a name="a90a9d521b55a417c93c500e3d3a21cb3"></a>channel</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae33ca1cc95e44328adf02ff61e6d6bbe"><a name="ae33ca1cc95e44328adf02ff61e6d6bbe"></a><a name="ae33ca1cc95e44328adf02ff61e6d6bbe"></a><strong id="ab98181bcc7e446abbc87eae716980731"><a name="ab98181bcc7e446abbc87eae716980731"></a><a name="ab98181bcc7e446abbc87eae716980731"></a>-</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aa2deeed39c064e1c9bf44e236c0ad365"><a name="aa2deeed39c064e1c9bf44e236c0ad365"></a><a name="aa2deeed39c064e1c9bf44e236c0ad365"></a>与之相连的Channel。</p>
    </td>
    </tr>
    <tr id="r0fe4d3a9f7a344e39d696f27f487d5bf"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a2ec69f5656ab4584b1595df4a84c94d5"><a name="a2ec69f5656ab4584b1595df4a84c94d5"></a><a name="a2ec69f5656ab4584b1595df4a84c94d5"></a>type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a7d8d652a655842ad9ef4dc8afeac5d8e"><a name="a7d8d652a655842ad9ef4dc8afeac5d8e"></a><a name="a7d8d652a655842ad9ef4dc8afeac5d8e"></a>hdfs</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p93613717555"><a name="zh-cn_topic_0066459131_p93613717555"></a><a name="zh-cn_topic_0066459131_p93613717555"></a>类型，需配置为<span class="parmvalue" id="p95a90027b4d94b3bb210dbb7670db300"><a name="p95a90027b4d94b3bb210dbb7670db300"></a><a name="p95a90027b4d94b3bb210dbb7670db300"></a>“hdfs”</span>。</p>
    </td>
    </tr>
    <tr id="r30b1bdba863c41e2a473a61fdbc16a2f"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ad26477d62d3343479f024efa88d50c73"><a name="ad26477d62d3343479f024efa88d50c73"></a><a name="ad26477d62d3343479f024efa88d50c73"></a>monTime</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a48adb995f7ba4deeb7cf90db7f4bce3f"><a name="a48adb995f7ba4deeb7cf90db7f4bce3f"></a><a name="a48adb995f7ba4deeb7cf90db7f4bce3f"></a>0（不开启）</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p449731017555"><a name="zh-cn_topic_0066459131_p449731017555"></a><a name="zh-cn_topic_0066459131_p449731017555"></a>线程监控阈值，更新时间大于阈值时重新启动该Sink，单位：秒。</p>
    </td>
    </tr>
    <tr id="r1b33ca102160497aa378808d4dc76caa"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a10d2d9f9cedd498097a7b089db3dbe6b"><a name="a10d2d9f9cedd498097a7b089db3dbe6b"></a><a name="a10d2d9f9cedd498097a7b089db3dbe6b"></a>hdfs.path</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="aa3c5cb4d701c4480be83f013c0db9a21"><a name="aa3c5cb4d701c4480be83f013c0db9a21"></a><a name="aa3c5cb4d701c4480be83f013c0db9a21"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a546fe693ae5d40caa5672b30b2012a9c"><a name="a546fe693ae5d40caa5672b30b2012a9c"></a><a name="a546fe693ae5d40caa5672b30b2012a9c"></a>OBS路径。格式s3a://AK:SK@桶/路径/ 例如 s3a://AK:SK@obs-nemon-sink/obs-sink/</p>
    </td>
    </tr>
    <tr id="ra5450924c44d4ffa95a74a8bc5a390b5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a327acef3b07c40b0a20951ebfb20f0d2"><a name="a327acef3b07c40b0a20951ebfb20f0d2"></a><a name="a327acef3b07c40b0a20951ebfb20f0d2"></a>hdfs.inUseSuffix</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae0b9a844d1dc436fa198c43dc0fa2689"><a name="ae0b9a844d1dc436fa198c43dc0fa2689"></a><a name="ae0b9a844d1dc436fa198c43dc0fa2689"></a>.tmp</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a94cf8b3e901545e3a470352c86b7c150"><a name="a94cf8b3e901545e3a470352c86b7c150"></a><a name="a94cf8b3e901545e3a470352c86b7c150"></a>正在写入的OBS文件后缀。</p>
    </td>
    </tr>
    <tr id="re4508449e1b8441e8662ad55eb28fa96"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a2e936dc2004546b3a7e603595ec40c45"><a name="a2e936dc2004546b3a7e603595ec40c45"></a><a name="a2e936dc2004546b3a7e603595ec40c45"></a>hdfs.rollInterval</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ae88901db0a2d4e1eb1646c0c6b3f3b24"><a name="ae88901db0a2d4e1eb1646c0c6b3f3b24"></a><a name="ae88901db0a2d4e1eb1646c0c6b3f3b24"></a>30</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p648439817555"><a name="zh-cn_topic_0066459131_p648439817555"></a><a name="zh-cn_topic_0066459131_p648439817555"></a>按时间滚动文件，单位：秒。</p>
    </td>
    </tr>
    <tr id="r636bb28c97f24085bdb934651f6d879a"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab63b89817d884ba09963e1c79c5725d2"><a name="ab63b89817d884ba09963e1c79c5725d2"></a><a name="ab63b89817d884ba09963e1c79c5725d2"></a>hdfs.rollSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a51fe90330f3e44e08232a94141ca2f9b"><a name="a51fe90330f3e44e08232a94141ca2f9b"></a><a name="a51fe90330f3e44e08232a94141ca2f9b"></a>1024</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a378fd788eb1d44fb8e82fa8bd5218d34"><a name="a378fd788eb1d44fb8e82fa8bd5218d34"></a><a name="a378fd788eb1d44fb8e82fa8bd5218d34"></a>按大小滚动文件，单位：字节。</p>
    </td>
    </tr>
    <tr id="r95d746b5556f4d33bf7d7862e4755562"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0066459131_p811401217555"><a name="zh-cn_topic_0066459131_p811401217555"></a><a name="zh-cn_topic_0066459131_p811401217555"></a>hdfs.rollCount</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="ab7d3aeeb51984b82936f7990c7ecca69"><a name="ab7d3aeeb51984b82936f7990c7ecca69"></a><a name="ab7d3aeeb51984b82936f7990c7ecca69"></a>10</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a995f20ad9b514cdbbaff1d9bf5238f99"><a name="a995f20ad9b514cdbbaff1d9bf5238f99"></a><a name="a995f20ad9b514cdbbaff1d9bf5238f99"></a>按Event个数滚动文件。</p>
    </td>
    </tr>
    <tr id="r544a5e8f8edb406682466b564a5cb5f1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ac16c1ef586e446d69852821abdd1d4e5"><a name="ac16c1ef586e446d69852821abdd1d4e5"></a><a name="ac16c1ef586e446d69852821abdd1d4e5"></a>hdfs.idleTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a9071609d6b794080802af2be5e56ba03"><a name="a9071609d6b794080802af2be5e56ba03"></a><a name="a9071609d6b794080802af2be5e56ba03"></a>0</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ad433897222de4bf78bf31b7d511a4b4f"><a name="ad433897222de4bf78bf31b7d511a4b4f"></a><a name="ad433897222de4bf78bf31b7d511a4b4f"></a>自动关闭空闲文件超时时间，单位：秒。</p>
    </td>
    </tr>
    <tr id="r4529ce84cb794d2e8416e57a8c3c6c7b"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="aee43fd0d4af04fdd88bf0e2643a18053"><a name="aee43fd0d4af04fdd88bf0e2643a18053"></a><a name="aee43fd0d4af04fdd88bf0e2643a18053"></a>hdfs.batchSize</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="afcddd9e4f1e040b99f5934df7077a0b0"><a name="afcddd9e4f1e040b99f5934df7077a0b0"></a><a name="afcddd9e4f1e040b99f5934df7077a0b0"></a>1000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0066459131_p584776417555"><a name="zh-cn_topic_0066459131_p584776417555"></a><a name="zh-cn_topic_0066459131_p584776417555"></a>每次写入OBS的Event个数。</p>
    </td>
    </tr>
    <tr id="re58b5807f42045c88224f24415c2ab1a"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a1555db7d0a9d447b894d2ecb195fdb14"><a name="a1555db7d0a9d447b894d2ecb195fdb14"></a><a name="a1555db7d0a9d447b894d2ecb195fdb14"></a>hdfs.calltimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a49009bdfa6f149f5b22b472d3551c560"><a name="a49009bdfa6f149f5b22b472d3551c560"></a><a name="a49009bdfa6f149f5b22b472d3551c560"></a>10000</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="ae1edec4d9a824da4817ecbf9dd23ef7d"><a name="ae1edec4d9a824da4817ecbf9dd23ef7d"></a><a name="ae1edec4d9a824da4817ecbf9dd23ef7d"></a>和OBS交互的超时时间。单位毫秒。由于OBS rename等操作实际是拷贝文件，因此需要将这个超时时间调整的尽量大，比如1000000。</p>
    </td>
    </tr>
    <tr id="rfec4266d7467402189ce0898fd8787b6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab5a7c3bae9df4b8290d83a9dc39c37ba"><a name="ab5a7c3bae9df4b8290d83a9dc39c37ba"></a><a name="ab5a7c3bae9df4b8290d83a9dc39c37ba"></a>hdfs.fileCloseByEndEvent</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0066459131_p262275217555"><a name="zh-cn_topic_0066459131_p262275217555"></a><a name="zh-cn_topic_0066459131_p262275217555"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aef2c2f1f2c5243fbb4100796b22ff946"><a name="aef2c2f1f2c5243fbb4100796b22ff946"></a><a name="aef2c2f1f2c5243fbb4100796b22ff946"></a>收到最后一个Event时是否关闭文件。</p>
    </td>
    </tr>
    <tr id="rcb96a3dbc8a34fc4808953777731f75e"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="a0071026db8214da9b70b674a5c9d5027"><a name="a0071026db8214da9b70b674a5c9d5027"></a><a name="a0071026db8214da9b70b674a5c9d5027"></a>hdfs.batchCallTimeout</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="acd7b130aa7d2492db091475e094a6c01"><a name="acd7b130aa7d2492db091475e094a6c01"></a><a name="acd7b130aa7d2492db091475e094a6c01"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="aeabad2d291be4f6882abee881a61cf80"><a name="aeabad2d291be4f6882abee881a61cf80"></a><a name="aeabad2d291be4f6882abee881a61cf80"></a>每次写入OBS超时控制时间，单位：毫秒。</p>
    <p id="ac14f0805d9274a228728b7b70f795d8c"><a name="ac14f0805d9274a228728b7b70f795d8c"></a><a name="ac14f0805d9274a228728b7b70f795d8c"></a>当不配置此参数时，对每个Event写入OBS进行超时控制。当<span class="parmname" id="p26aabde3ab604acc9a1e84f68caf2722"><a name="p26aabde3ab604acc9a1e84f68caf2722"></a><a name="p26aabde3ab604acc9a1e84f68caf2722"></a>“hdfs.batchSize”</span>大于0时，配置此参数可以提升写入OBS性能。</p>
    <div class="note" id="na13809891a5244348101468b5daab8bd"><a name="na13809891a5244348101468b5daab8bd"></a><a name="na13809891a5244348101468b5daab8bd"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a32f0bc652e1e45ad821939b8628a79af"><a name="a32f0bc652e1e45ad821939b8628a79af"></a><a name="a32f0bc652e1e45ad821939b8628a79af"></a><span class="parmname" id="p38a8b8ffe157495d8a049dcf7c6d73fe"><a name="p38a8b8ffe157495d8a049dcf7c6d73fe"></a><a name="p38a8b8ffe157495d8a049dcf7c6d73fe"></a>“hdfs.batchCallTimeout”</span>设置多长时间需要考虑<span class="parmname" id="p3ced3d3a3d2b468a802243d9303f694c"><a name="p3ced3d3a3d2b468a802243d9303f694c"></a><a name="p3ced3d3a3d2b468a802243d9303f694c"></a>“hdfs.batchSize”</span>的大小，<span class="parmname" id="pe193ca2156764b1e8cf0e9998e22b19b"><a name="pe193ca2156764b1e8cf0e9998e22b19b"></a><a name="pe193ca2156764b1e8cf0e9998e22b19b"></a>“hdfs.batchSize”</span>越大，<span class="parmname" id="pe4446b5ccef74dc8a441e692d73924bd"><a name="pe4446b5ccef74dc8a441e692d73924bd"></a><a name="pe4446b5ccef74dc8a441e692d73924bd"></a>“hdfs.batchCallTimeout”</span>也要调整更长时间，设置过短时间容易导致数据写入OBS失败。</p>
    </div></div>
    </td>
    </tr>
    <tr id="r3a20b3dbed2f4df384e50414c71867fe"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="ab6f2199a9d734ae09cd08c1f852f651e"><a name="ab6f2199a9d734ae09cd08c1f852f651e"></a><a name="ab6f2199a9d734ae09cd08c1f852f651e"></a>serializer.appendNewline</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="a50dd34b953d54a7daad56af3291e8872"><a name="a50dd34b953d54a7daad56af3291e8872"></a><a name="a50dd34b953d54a7daad56af3291e8872"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="a7542cb2029f847faae0cbaa6de9620b0"><a name="a7542cb2029f847faae0cbaa6de9620b0"></a><a name="a7542cb2029f847faae0cbaa6de9620b0"></a>将一个Event写入OBS后是否追加换行符（'\n'），如果追加该换行符，该换行符所占用的数据量指标不会被OBS Sink统计。</p>
    </td>
    </tr>
    </tbody>
    </table>


