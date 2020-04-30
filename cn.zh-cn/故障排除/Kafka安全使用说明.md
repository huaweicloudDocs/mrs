# Kafka安全使用说明<a name="ZH-CN_TOPIC_0187791614"></a>

-   Kafka API简单说明
-   Kafka访问协议说明
-   Topic的ACL设置
-   针对不同的Topic访问场景，Kafka新旧API使用说明

## Kafka API简单说明<a name="zh-cn_topic_0167274777_section34977990102121"></a>

-   新Producer API

    指org.apache.kafka.clients.producer.KafkaProducer中定义的接口，在使用“kafka-console-producer.sh”时，默认使用此API。

-   旧Producer API

    指kafka.producer.Producer中定义的接口，在使用“kafka-console-producer.sh”时，加“--old-producer”参数会调用此API。

-   新Consumer API

    指org.apache.kafka.clients.consumer.KafkaConsumer中定义的接口，在使用“kafka-console-consumer.sh”时，加“--new-consumer”参数会调用此API。

-   旧Consumer API

    指kafka.consumer.ConsumerConnector中定义的接口，在使用“kafka-console-consumer.sh”时，默认使用此API。


>![](public_sys-resources/icon-note.gif) **说明：**   
>新Producer API和新Consumer API，在下文中统称为新API。  

## Kafka 访问协议说明<a name="zh-cn_topic_0167274777_section4763104010434"></a>

Kafka当前支持四种协议类型的访问：PLAINTEXT、SSL、SASL\_PLAINTEXT、SASL\_SSL。

Kafka服务启动时，默认会启动PLAINTEXT和SASL\_PLAINTEXT两种协议类型的访问监听。可通过设置Kafka服务配置参数“ssl.mode.enable”为“true”，来启动SSL和SASL\_SSL两种协议类型的访问监听。

下表是四中协议类型的简单说明：

<a name="zh-cn_topic_0167274777_table15932081102411"></a>
<table><thead align="left"><tr id="zh-cn_topic_0167274777_row66721597102411"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.1.5.1.1"><p id="zh-cn_topic_0167274777_p35740300102411"><a name="zh-cn_topic_0167274777_p35740300102411"></a><a name="zh-cn_topic_0167274777_p35740300102411"></a><strong id="zh-cn_topic_0167274777_b53227247102411"><a name="zh-cn_topic_0167274777_b53227247102411"></a><a name="zh-cn_topic_0167274777_b53227247102411"></a>协议类型</strong></p>
</th>
<th class="cellrowborder" valign="top" width="42.42424242424242%" id="mcps1.1.5.1.2"><p id="zh-cn_topic_0167274777_p16439788102411"><a name="zh-cn_topic_0167274777_p16439788102411"></a><a name="zh-cn_topic_0167274777_p16439788102411"></a><strong id="zh-cn_topic_0167274777_b13740367102411"><a name="zh-cn_topic_0167274777_b13740367102411"></a><a name="zh-cn_topic_0167274777_b13740367102411"></a>说明</strong></p>
</th>
<th class="cellrowborder" valign="top" width="20.202020202020204%" id="mcps1.1.5.1.3"><p id="zh-cn_topic_0167274777_p39227923102411"><a name="zh-cn_topic_0167274777_p39227923102411"></a><a name="zh-cn_topic_0167274777_p39227923102411"></a><strong id="zh-cn_topic_0167274777_b17506990102411"><a name="zh-cn_topic_0167274777_b17506990102411"></a><a name="zh-cn_topic_0167274777_b17506990102411"></a>支持的API</strong></p>
</th>
<th class="cellrowborder" valign="top" width="15.151515151515152%" id="mcps1.1.5.1.4"><p id="zh-cn_topic_0167274777_p8780100102411"><a name="zh-cn_topic_0167274777_p8780100102411"></a><a name="zh-cn_topic_0167274777_p8780100102411"></a><strong id="zh-cn_topic_0167274777_b11912041102411"><a name="zh-cn_topic_0167274777_b11912041102411"></a><a name="zh-cn_topic_0167274777_b11912041102411"></a>默认端口</strong></p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0167274777_row25351242102411"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0167274777_p40184753102411"><a name="zh-cn_topic_0167274777_p40184753102411"></a><a name="zh-cn_topic_0167274777_p40184753102411"></a>PLAINTEXT</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0167274777_p33739523102411"><a name="zh-cn_topic_0167274777_p33739523102411"></a><a name="zh-cn_topic_0167274777_p33739523102411"></a>支持无认证的明文访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0167274777_p48546858102411"><a name="zh-cn_topic_0167274777_p48546858102411"></a><a name="zh-cn_topic_0167274777_p48546858102411"></a>新API和旧API</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0167274777_p39981454102411"><a name="zh-cn_topic_0167274777_p39981454102411"></a><a name="zh-cn_topic_0167274777_p39981454102411"></a>21005</p>
</td>
</tr>
<tr id="zh-cn_topic_0167274777_row24288770102411"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0167274777_p21233355102411"><a name="zh-cn_topic_0167274777_p21233355102411"></a><a name="zh-cn_topic_0167274777_p21233355102411"></a>SASL_PLAINTEXT</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0167274777_p42180229102411"><a name="zh-cn_topic_0167274777_p42180229102411"></a><a name="zh-cn_topic_0167274777_p42180229102411"></a>支持Kerberos认证的明文访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0167274777_p61155416102411"><a name="zh-cn_topic_0167274777_p61155416102411"></a><a name="zh-cn_topic_0167274777_p61155416102411"></a>新API</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0167274777_p54641643102411"><a name="zh-cn_topic_0167274777_p54641643102411"></a><a name="zh-cn_topic_0167274777_p54641643102411"></a>21007</p>
</td>
</tr>
<tr id="zh-cn_topic_0167274777_row22012740102411"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0167274777_p38201498102411"><a name="zh-cn_topic_0167274777_p38201498102411"></a><a name="zh-cn_topic_0167274777_p38201498102411"></a>SSL</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0167274777_p7313670102411"><a name="zh-cn_topic_0167274777_p7313670102411"></a><a name="zh-cn_topic_0167274777_p7313670102411"></a>支持无认证的SSL加密访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0167274777_p55536365102411"><a name="zh-cn_topic_0167274777_p55536365102411"></a><a name="zh-cn_topic_0167274777_p55536365102411"></a>新API</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0167274777_p2151737102411"><a name="zh-cn_topic_0167274777_p2151737102411"></a><a name="zh-cn_topic_0167274777_p2151737102411"></a>21008</p>
</td>
</tr>
<tr id="zh-cn_topic_0167274777_row19365641102411"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.1.5.1.1 "><p id="zh-cn_topic_0167274777_p25113063102411"><a name="zh-cn_topic_0167274777_p25113063102411"></a><a name="zh-cn_topic_0167274777_p25113063102411"></a>SASL_SSL</p>
</td>
<td class="cellrowborder" valign="top" width="42.42424242424242%" headers="mcps1.1.5.1.2 "><p id="zh-cn_topic_0167274777_p20892189102411"><a name="zh-cn_topic_0167274777_p20892189102411"></a><a name="zh-cn_topic_0167274777_p20892189102411"></a>支持Kerberos认证的SSL加密访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.202020202020204%" headers="mcps1.1.5.1.3 "><p id="zh-cn_topic_0167274777_p14545748102411"><a name="zh-cn_topic_0167274777_p14545748102411"></a><a name="zh-cn_topic_0167274777_p14545748102411"></a>新API</p>
</td>
<td class="cellrowborder" valign="top" width="15.151515151515152%" headers="mcps1.1.5.1.4 "><p id="zh-cn_topic_0167274777_p37354931102411"><a name="zh-cn_topic_0167274777_p37354931102411"></a><a name="zh-cn_topic_0167274777_p37354931102411"></a>21009</p>
</td>
</tr>
</tbody>
</table>

## Topic的ACL设置<a name="zh-cn_topic_0167274777_section4369201210649"></a>

Kafka支持安全访问，因此可以针对Topic进行ACL设置，从而控制不同的用户可以访问不同的Topic。Topic的权限信息，需要在Linux客户端上，使用“kafka-acls.sh”脚本进行查看和设置。

-   操作场景

    该任务指导Kafka管理员根据业务需求，为其他使用Kafka的系统用户授予相关Topic的特定权限。

    Kafka默认用户组信息表所示。

    <a name="zh-cn_topic_0167274777_table36325152105322"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0167274777_row30425378105322"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0167274777_p48536539105322"><a name="zh-cn_topic_0167274777_p48536539105322"></a><a name="zh-cn_topic_0167274777_p48536539105322"></a><strong id="zh-cn_topic_0167274777_b34175671105322"><a name="zh-cn_topic_0167274777_b34175671105322"></a><a name="zh-cn_topic_0167274777_b34175671105322"></a>用户组名</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0167274777_p16765946105322"><a name="zh-cn_topic_0167274777_p16765946105322"></a><a name="zh-cn_topic_0167274777_p16765946105322"></a><strong id="zh-cn_topic_0167274777_b16675787105322"><a name="zh-cn_topic_0167274777_b16675787105322"></a><a name="zh-cn_topic_0167274777_b16675787105322"></a>描述</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0167274777_row8561489105322"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0167274777_p22392045105322"><a name="zh-cn_topic_0167274777_p22392045105322"></a><a name="zh-cn_topic_0167274777_p22392045105322"></a>kafkaadmin</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0167274777_p1816324105322"><a name="zh-cn_topic_0167274777_p1816324105322"></a><a name="zh-cn_topic_0167274777_p1816324105322"></a>Kafka管理员用户组。添加入本组的用户，拥有所有Topic的创建，删除，授权及读写权限。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row16346922105322"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0167274777_p49032328105322"><a name="zh-cn_topic_0167274777_p49032328105322"></a><a name="zh-cn_topic_0167274777_p49032328105322"></a>kafkasuperuser</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0167274777_p12195606105322"><a name="zh-cn_topic_0167274777_p12195606105322"></a><a name="zh-cn_topic_0167274777_p12195606105322"></a>Kafka超级用户组。添加入本组的用户，拥有所有Topic的读写权限。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row42651590105322"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0167274777_p32226784105322"><a name="zh-cn_topic_0167274777_p32226784105322"></a><a name="zh-cn_topic_0167274777_p32226784105322"></a>kafka</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0167274777_p60232702105322"><a name="zh-cn_topic_0167274777_p60232702105322"></a><a name="zh-cn_topic_0167274777_p60232702105322"></a>Kafka普通用户组。添加入本组的用户，需要被kafkaadmin组用户授予特定Topic的读写权限，才能访问对应Topic。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   前提条件
    1.  系统管理员已明确业务需求，并准备一个Kafka管理员用户（属于kafkaadmin组）。
    2.  已安装Kafka客户端。

-   操作步骤
    1.  使用PuTTY工具，以客户端安装用户，登录安装Kafka客户端的节点。
    2.  切换到Kafka客户端安装目录，例如“/opt/kafkaclient”。

        **cd /opt/kafkaclient**

    3.  执行以下命令，配置环境变量。

        **source bigdata\_env**

    4.  执行以下命令，进行用户认证。（普通集群跳过此步骤）

        **kinit** _组件业务用户_

    5.  执行以下命令，切换到Kafka客户端安装目录。

        **cd Kafka/kafka/bin**

    6.  使用“kafka-acl.sh”进行用户授权常用命令如下：
        -   查看某Topic权限控制列表：

            **./kafka-acls.sh --authorizer-properties zookeeper.connect=<ZooKeeper集群业务IP:2181/kafka \> --list --topic <Topic名称\>**

        -   添加给某用户Producer权限：

            **./kafka-acls.sh --authorizer-properties zookeeper.connect=<ZooKeeper集群业务IP:2181/kafka \> --add --allow-principal User:<用户名\> --producer --topic <Topic名称\>**

        -   删除某用户Producer权限：

            **./kafka-acls.sh --authorizer-properties zookeeper.connect=<ZooKeeper集群业务IP:2181/kafka \> --remove --allow-principal User:<用户名\> --producer --topic <Topic名称\>**

        -   添加给某用户Consumer权限：

            **./kafka-acls.sh --authorizer-properties zookeeper.connect=<ZooKeeper集群业务IP:2181/kafka \> --add --allow-principal User:<用户名\> --consumer --topic <Topic名称\> --group <消费者组名称\>**

        -   删除某用户Consumer权限：

            **./kafka-acls.sh --authorizer-properties zookeeper.connect=<ZooKeeper集群业务IP:2181/kafka \> --remove --allow-principal User:<用户名\> --consumer --topic <Topic名称\> --group <消费者组名称\>**

            >![](public_sys-resources/icon-note.gif) **说明：**   
            >MRS 1.6.3及之前版本，无论集群是否开启Kerberos认证ZooKeeper默认端口号均为24002。MRS 1.6.3及之后版本，无论集群是否开启Kerberos认证ZooKeeper默认端口号均为2181。  




## 针对不同的Topic访问场景 ，Kafka新旧API使用说明<a name="zh-cn_topic_0167274777_section741709110652"></a>

-   场景一：访问设置了ACL的Topic

    <a name="zh-cn_topic_0167274777_table1808920512500"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0167274777_row6623531612500"><th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.1"><p id="zh-cn_topic_0167274777_p6346036912500"><a name="zh-cn_topic_0167274777_p6346036912500"></a><a name="zh-cn_topic_0167274777_p6346036912500"></a><strong id="zh-cn_topic_0167274777_b3427241112500"><a name="zh-cn_topic_0167274777_b3427241112500"></a><a name="zh-cn_topic_0167274777_b3427241112500"></a>使用的API</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.2"><p id="zh-cn_topic_0167274777_p2460190012500"><a name="zh-cn_topic_0167274777_p2460190012500"></a><a name="zh-cn_topic_0167274777_p2460190012500"></a><strong id="zh-cn_topic_0167274777_b2009050812500"><a name="zh-cn_topic_0167274777_b2009050812500"></a><a name="zh-cn_topic_0167274777_b2009050812500"></a>用户属组</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.3"><p id="zh-cn_topic_0167274777_p1671845812500"><a name="zh-cn_topic_0167274777_p1671845812500"></a><a name="zh-cn_topic_0167274777_p1671845812500"></a><strong id="zh-cn_topic_0167274777_b1624840212500"><a name="zh-cn_topic_0167274777_b1624840212500"></a><a name="zh-cn_topic_0167274777_b1624840212500"></a>客户端参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.4"><p id="zh-cn_topic_0167274777_p4105221712500"><a name="zh-cn_topic_0167274777_p4105221712500"></a><a name="zh-cn_topic_0167274777_p4105221712500"></a><strong id="zh-cn_topic_0167274777_b3392563312500"><a name="zh-cn_topic_0167274777_b3392563312500"></a><a name="zh-cn_topic_0167274777_b3392563312500"></a>服务端参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.5"><p id="zh-cn_topic_0167274777_p6362173712500"><a name="zh-cn_topic_0167274777_p6362173712500"></a><a name="zh-cn_topic_0167274777_p6362173712500"></a><strong id="zh-cn_topic_0167274777_b3572472212500"><a name="zh-cn_topic_0167274777_b3572472212500"></a><a name="zh-cn_topic_0167274777_b3572472212500"></a>访问的端口</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0167274777_row802139812500"><td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p4575350212500"><a name="zh-cn_topic_0167274777_p4575350212500"></a><a name="zh-cn_topic_0167274777_p4575350212500"></a>新API</p>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" width="20%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p1504619512500"><a name="zh-cn_topic_0167274777_p1504619512500"></a><a name="zh-cn_topic_0167274777_p1504619512500"></a>用户需满足以下条件之一即可：</p>
    <a name="zh-cn_topic_0167274777_ul41485484125112"></a><a name="zh-cn_topic_0167274777_ul41485484125112"></a><ul id="zh-cn_topic_0167274777_ul41485484125112"><li>属于系统管理员组</li><li>属于kafkaadmin组</li><li>属于kafkasuperuser组</li><li>被授权的kafka组的用户</li></ul>
    <p id="zh-cn_topic_0167274777_p4795262912500"><a name="zh-cn_topic_0167274777_p4795262912500"></a><a name="zh-cn_topic_0167274777_p4795262912500"></a></p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p5895776112500"><a name="zh-cn_topic_0167274777_p5895776112500"></a><a name="zh-cn_topic_0167274777_p5895776112500"></a>security.protocol=SASL_PLAINTEXT sasl.kerberos.service.name = kafka</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p1084937012500"><a name="zh-cn_topic_0167274777_p1084937012500"></a><a name="zh-cn_topic_0167274777_p1084937012500"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0167274777_p638378312500"><a name="zh-cn_topic_0167274777_p638378312500"></a><a name="zh-cn_topic_0167274777_p638378312500"></a>sasl.port（默认21007）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row5745405312500"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p2326671612500"><a name="zh-cn_topic_0167274777_p2326671612500"></a><a name="zh-cn_topic_0167274777_p2326671612500"></a>security.protocol=SASL_SSL sasl.kerberos.service.name = kafka</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p555583512500"><a name="zh-cn_topic_0167274777_p555583512500"></a><a name="zh-cn_topic_0167274777_p555583512500"></a>ssl.mode.enable配置为true</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p4736951512500"><a name="zh-cn_topic_0167274777_p4736951512500"></a><a name="zh-cn_topic_0167274777_p4736951512500"></a>sasl-ssl.port（默认21009）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row2367245712500"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p3842085312500"><a name="zh-cn_topic_0167274777_p3842085312500"></a><a name="zh-cn_topic_0167274777_p3842085312500"></a>旧API</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p2508134912500"><a name="zh-cn_topic_0167274777_p2508134912500"></a><a name="zh-cn_topic_0167274777_p2508134912500"></a>不支持访问</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p1832336112500"><a name="zh-cn_topic_0167274777_p1832336112500"></a><a name="zh-cn_topic_0167274777_p1832336112500"></a>不涉及</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p779729812500"><a name="zh-cn_topic_0167274777_p779729812500"></a><a name="zh-cn_topic_0167274777_p779729812500"></a>不涉及</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0167274777_p2760144012500"><a name="zh-cn_topic_0167274777_p2760144012500"></a><a name="zh-cn_topic_0167274777_p2760144012500"></a>不涉及</p>
    </td>
    </tr>
    </tbody>
    </table>

-   场景二：访问未设置ACL的Topic

    <a name="zh-cn_topic_0167274777_table6389886112511"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0167274777_row3796580912511"><th class="cellrowborder" valign="top" width="20.307969203079693%" id="mcps1.1.6.1.1"><p id="zh-cn_topic_0167274777_p5533168912511"><a name="zh-cn_topic_0167274777_p5533168912511"></a><a name="zh-cn_topic_0167274777_p5533168912511"></a><strong id="zh-cn_topic_0167274777_b2822315812511"><a name="zh-cn_topic_0167274777_b2822315812511"></a><a name="zh-cn_topic_0167274777_b2822315812511"></a>使用的API</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="19.96800319968003%" id="mcps1.1.6.1.2"><p id="zh-cn_topic_0167274777_p437449612511"><a name="zh-cn_topic_0167274777_p437449612511"></a><a name="zh-cn_topic_0167274777_p437449612511"></a><strong id="zh-cn_topic_0167274777_b3937047112511"><a name="zh-cn_topic_0167274777_b3937047112511"></a><a name="zh-cn_topic_0167274777_b3937047112511"></a>用户属组</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="18.90810918908109%" id="mcps1.1.6.1.3"><p id="zh-cn_topic_0167274777_p3489158112511"><a name="zh-cn_topic_0167274777_p3489158112511"></a><a name="zh-cn_topic_0167274777_p3489158112511"></a><strong id="zh-cn_topic_0167274777_b4558877412511"><a name="zh-cn_topic_0167274777_b4558877412511"></a><a name="zh-cn_topic_0167274777_b4558877412511"></a>客户端参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="22.447755224477554%" id="mcps1.1.6.1.4"><p id="zh-cn_topic_0167274777_p170318512511"><a name="zh-cn_topic_0167274777_p170318512511"></a><a name="zh-cn_topic_0167274777_p170318512511"></a><strong id="zh-cn_topic_0167274777_b1532866912511"><a name="zh-cn_topic_0167274777_b1532866912511"></a><a name="zh-cn_topic_0167274777_b1532866912511"></a>服务端参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="18.36816318368163%" id="mcps1.1.6.1.5"><p id="zh-cn_topic_0167274777_p3366271312511"><a name="zh-cn_topic_0167274777_p3366271312511"></a><a name="zh-cn_topic_0167274777_p3366271312511"></a><strong id="zh-cn_topic_0167274777_b3452896112511"><a name="zh-cn_topic_0167274777_b3452896112511"></a><a name="zh-cn_topic_0167274777_b3452896112511"></a>访问的端口</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0167274777_row4538248612511"><td class="cellrowborder" rowspan="6" valign="top" width="20.307969203079693%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p5210277212511"><a name="zh-cn_topic_0167274777_p5210277212511"></a><a name="zh-cn_topic_0167274777_p5210277212511"></a>新API</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.96800319968003%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p5957497812511"><a name="zh-cn_topic_0167274777_p5957497812511"></a><a name="zh-cn_topic_0167274777_p5957497812511"></a>用户需满足以下条件之一：</p>
    <a name="zh-cn_topic_0167274777_ul6641275412511"></a><a name="zh-cn_topic_0167274777_ul6641275412511"></a><ul id="zh-cn_topic_0167274777_ul6641275412511"><li>属于系统管理员组</li><li>属于kafkaadmisumn组</li><li>属于kafkasuperuser组</li></ul>
    <p id="zh-cn_topic_0167274777_p2669528412511"><a name="zh-cn_topic_0167274777_p2669528412511"></a><a name="zh-cn_topic_0167274777_p2669528412511"></a></p>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" width="18.90810918908109%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p25743348103948"><a name="zh-cn_topic_0167274777_p25743348103948"></a><a name="zh-cn_topic_0167274777_p25743348103948"></a>security.protocol=SASL_PLAINTEXT</p>
    <p id="zh-cn_topic_0167274777_p1483438412511"><a name="zh-cn_topic_0167274777_p1483438412511"></a><a name="zh-cn_topic_0167274777_p1483438412511"></a>sasl.kerberos.service.name = kafka</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p6073441612511"><a name="zh-cn_topic_0167274777_p6073441612511"></a><a name="zh-cn_topic_0167274777_p6073441612511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0167274777_p2054063612511"><a name="zh-cn_topic_0167274777_p2054063612511"></a><a name="zh-cn_topic_0167274777_p2054063612511"></a>sasl.port（默认21007）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row5064800312511"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p884756512511"><a name="zh-cn_topic_0167274777_p884756512511"></a><a name="zh-cn_topic_0167274777_p884756512511"></a>用户属于kafka组</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p4556418412511"><a name="zh-cn_topic_0167274777_p4556418412511"></a><a name="zh-cn_topic_0167274777_p4556418412511"></a>allow.everyone.if.no.acl.found配置为true</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p6682030012511"><a name="zh-cn_topic_0167274777_p6682030012511"></a><a name="zh-cn_topic_0167274777_p6682030012511"></a>sasl.port（默认21007）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row6451178812511"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p5807233512511"><a name="zh-cn_topic_0167274777_p5807233512511"></a><a name="zh-cn_topic_0167274777_p5807233512511"></a>用户需满足以下条件之一：</p>
    <a name="zh-cn_topic_0167274777_ul5288897212511"></a><a name="zh-cn_topic_0167274777_ul5288897212511"></a><ul id="zh-cn_topic_0167274777_ul5288897212511"><li>属于系统管理员组</li></ul>
    <a name="zh-cn_topic_0167274777_ul3557291512511"></a><a name="zh-cn_topic_0167274777_ul3557291512511"></a><ul id="zh-cn_topic_0167274777_ul3557291512511"><li>属于kafkaadmin组</li></ul>
    <a name="zh-cn_topic_0167274777_ul2863382812511"></a><a name="zh-cn_topic_0167274777_ul2863382812511"></a><ul id="zh-cn_topic_0167274777_ul2863382812511"><li>kafkasuperuser组用户</li></ul>
    </td>
    <td class="cellrowborder" rowspan="2" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p2883897712511"><a name="zh-cn_topic_0167274777_p2883897712511"></a><a name="zh-cn_topic_0167274777_p2883897712511"></a>security.protocol=SASL_SSLsasl.kerberos.service.name = kafka</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p5425583312511"><a name="zh-cn_topic_0167274777_p5425583312511"></a><a name="zh-cn_topic_0167274777_p5425583312511"></a>ssl-enable配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p3264633712511"><a name="zh-cn_topic_0167274777_p3264633712511"></a><a name="zh-cn_topic_0167274777_p3264633712511"></a>sasl-ssl.port（默认21009）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row2538157812511"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p4264196612511"><a name="zh-cn_topic_0167274777_p4264196612511"></a><a name="zh-cn_topic_0167274777_p4264196612511"></a>用户属于kafka组</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p10244813125217"><a name="zh-cn_topic_0167274777_p10244813125217"></a><a name="zh-cn_topic_0167274777_p10244813125217"></a>allow.everyone.if.no.acl.found配置为“true”</p>
    <p id="zh-cn_topic_0167274777_p50545911125221"><a name="zh-cn_topic_0167274777_p50545911125221"></a><a name="zh-cn_topic_0167274777_p50545911125221"></a>ssl-enable配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p2172818612511"><a name="zh-cn_topic_0167274777_p2172818612511"></a><a name="zh-cn_topic_0167274777_p2172818612511"></a>sasl-ssl.port（默认21009）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row6133594712511"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p215578212511"><a name="zh-cn_topic_0167274777_p215578212511"></a><a name="zh-cn_topic_0167274777_p215578212511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p4040065812511"><a name="zh-cn_topic_0167274777_p4040065812511"></a><a name="zh-cn_topic_0167274777_p4040065812511"></a>security.protocol=PLAINTEXT</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p5122786212511"><a name="zh-cn_topic_0167274777_p5122786212511"></a><a name="zh-cn_topic_0167274777_p5122786212511"></a>allow.everyone.if.no.acl.found配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p5581618712511"><a name="zh-cn_topic_0167274777_p5581618712511"></a><a name="zh-cn_topic_0167274777_p5581618712511"></a>port（默认21005）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row3258364112511"><td class="cellrowborder" valign="top" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p2202929812511"><a name="zh-cn_topic_0167274777_p2202929812511"></a><a name="zh-cn_topic_0167274777_p2202929812511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p3954271912511"><a name="zh-cn_topic_0167274777_p3954271912511"></a><a name="zh-cn_topic_0167274777_p3954271912511"></a>security.protocol=SSL</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p62454500125158"><a name="zh-cn_topic_0167274777_p62454500125158"></a><a name="zh-cn_topic_0167274777_p62454500125158"></a>allow.everyone.if.no.acl.found配置为“true”</p>
    <p id="zh-cn_topic_0167274777_p1493132912520"><a name="zh-cn_topic_0167274777_p1493132912520"></a><a name="zh-cn_topic_0167274777_p1493132912520"></a>ssl-enable配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p1828266812511"><a name="zh-cn_topic_0167274777_p1828266812511"></a><a name="zh-cn_topic_0167274777_p1828266812511"></a>ssl.port（默认21008）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row3032628512511"><td class="cellrowborder" valign="top" width="20.307969203079693%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p4050998112511"><a name="zh-cn_topic_0167274777_p4050998112511"></a><a name="zh-cn_topic_0167274777_p4050998112511"></a>旧Producer</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.96800319968003%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p6008300112511"><a name="zh-cn_topic_0167274777_p6008300112511"></a><a name="zh-cn_topic_0167274777_p6008300112511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.90810918908109%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p3488493812511"><a name="zh-cn_topic_0167274777_p3488493812511"></a><a name="zh-cn_topic_0167274777_p3488493812511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p710776812511"><a name="zh-cn_topic_0167274777_p710776812511"></a><a name="zh-cn_topic_0167274777_p710776812511"></a>allow.everyone.if.no.acl.found配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0167274777_p3885834612511"><a name="zh-cn_topic_0167274777_p3885834612511"></a><a name="zh-cn_topic_0167274777_p3885834612511"></a>port（默认21005）</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0167274777_row1418080112511"><td class="cellrowborder" valign="top" width="20.307969203079693%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0167274777_p779419612511"><a name="zh-cn_topic_0167274777_p779419612511"></a><a name="zh-cn_topic_0167274777_p779419612511"></a>旧Consumer</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.96800319968003%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0167274777_p2735017712511"><a name="zh-cn_topic_0167274777_p2735017712511"></a><a name="zh-cn_topic_0167274777_p2735017712511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.90810918908109%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0167274777_p77185412511"><a name="zh-cn_topic_0167274777_p77185412511"></a><a name="zh-cn_topic_0167274777_p77185412511"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="22.447755224477554%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0167274777_p6252019512511"><a name="zh-cn_topic_0167274777_p6252019512511"></a><a name="zh-cn_topic_0167274777_p6252019512511"></a>allow.everyone.if.no.acl.found配置为“true”</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.36816318368163%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0167274777_p3097104912511"><a name="zh-cn_topic_0167274777_p3097104912511"></a><a name="zh-cn_topic_0167274777_p3097104912511"></a>ZooKeeper服务端口：clientPort（默认24002）</p>
    </td>
    </tr>
    </tbody>
    </table>


