# 使用OBS加密数据运行作业<a name="mrs_01_0640"></a>

MRS 1.9.x支持使用OBS文件系统中加密后的数据来运行作业，同时支持将加密后的作业运行结果存储在OBS文件系统中。目前仅支持通过OBS协议访问数据。

OBS支持使用KMS秘钥的加解密方式对数据进行加解密，所有的加解密操作都在OBS完成，同时秘钥管理在DEW服务。

如需在MRS中使用OBS加密功能，用户需要有“KMS Administrator”权限，且需要在相应组件进行如下配置。

>![](public_sys-resources/icon-note.gif) **说明：** 
>如果集群同时开启“[OBS权限控制](配置MRS多用户访问OBS细粒度权限.md)”功能，此时会使用ECS配置的默认委托“MRS\_ECS\_DEFAULT\_AGENCY”或者用户设置的自定义委托的AK/SK访问OBS服务，同时OBS服务会使用接收到的AK/SK访问数据加密服务获取KMS秘钥状态，因此需要在使用的委托上绑定“KMS Administrator”策略，否则在处理加密数据时OBS会返回“403 Forbidden”的错误信息。目前MRS服务会在默认委托“MRS\_ECS\_DEFAULT\_AGENCY”绑定“KMS Administrator”策略，用户使用的自定义委托则需要用户自己绑定。

## 前提条件<a name="section151741328125013"></a>

如需使用OBS加密功能，请先配置MRS访问OBS功能，具体请参考[配置存算分离集群（委托方式）](配置存算分离集群（委托方式）.md)。

## Hive配置<a name="section2456188164214"></a>

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Hive \> 服务配置”。
3.  将“基础配置”切换为“全部配置”，搜索并配置如下参数：

    ![](figures/5-20-12-Hive全部配置.png)

    **表 1**  数据加密参数

    <a name="table3922125311218"></a>
    <table><thead align="left"><tr id="row792514537215"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p7925253152117"><a name="p7925253152117"></a><a name="p7925253152117"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11925953102116"><a name="p11925953102116"></a><a name="p11925953102116"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p1292555302113"><a name="p1292555302113"></a><a name="p1292555302113"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row69251753192118"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p954024062214"><a name="p954024062214"></a><a name="p954024062214"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p4809439192410"><a name="p4809439192410"></a><a name="p4809439192410"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul13677522415"></a><a name="ul13677522415"></a><ul id="ul13677522415"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="row6925253112115"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p125401740162210"><a name="p125401740162210"></a><a name="p125401740162210"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1354074062215"><a name="p1354074062215"></a><a name="p1354074062215"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p8147131718257"><a name="p8147131718257"></a><a name="p8147131718257"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="p1173437103213"><a name="p1173437103213"></a><a name="p1173437103213"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="row792515311214"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p0540104019225"><a name="p0540104019225"></a><a name="p0540104019225"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p14602614183418"><a name="p14602614183418"></a><a name="p14602614183418"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p16602141612334"><a name="p16602141612334"></a><a name="p16602141612334"></a>标识是否与OBS建立安全连接。</p>
    <a name="ul118091720113317"></a><a name="ul118091720113317"></a><ul id="ul118091720113317"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。

## Hadoop配置<a name="section2054610122433"></a>

**方式一：通过界面配置。**

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> HDFS \> 服务配置”
3.  将“基础配置”切换为“全部配置”，搜索并配置如下参数：

    **表 2**  数据加密参数

    <a name="zh-cn_topic_0196677182_table3922125311218"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117"><a name="zh-cn_topic_0196677182_p7925253152117"></a><a name="zh-cn_topic_0196677182_p7925253152117"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116"><a name="zh-cn_topic_0196677182_p11925953102116"></a><a name="zh-cn_topic_0196677182_p11925953102116"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113"><a name="zh-cn_topic_0196677182_p1292555302113"></a><a name="zh-cn_topic_0196677182_p1292555302113"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214"><a name="zh-cn_topic_0196677182_p954024062214"></a><a name="zh-cn_topic_0196677182_p954024062214"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410"><a name="zh-cn_topic_0196677182_p4809439192410"></a><a name="zh-cn_topic_0196677182_p4809439192410"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415"></a><a name="zh-cn_topic_0196677182_ul13677522415"></a><ul id="zh-cn_topic_0196677182_ul13677522415"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210"><a name="zh-cn_topic_0196677182_p125401740162210"></a><a name="zh-cn_topic_0196677182_p125401740162210"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215"><a name="zh-cn_topic_0196677182_p1354074062215"></a><a name="zh-cn_topic_0196677182_p1354074062215"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257"><a name="zh-cn_topic_0196677182_p8147131718257"></a><a name="zh-cn_topic_0196677182_p8147131718257"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="zh-cn_topic_0196677182_p1173437103213"><a name="zh-cn_topic_0196677182_p1173437103213"></a><a name="zh-cn_topic_0196677182_p1173437103213"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225"><a name="zh-cn_topic_0196677182_p0540104019225"></a><a name="zh-cn_topic_0196677182_p0540104019225"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418"><a name="zh-cn_topic_0196677182_p14602614183418"></a><a name="zh-cn_topic_0196677182_p14602614183418"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334"><a name="zh-cn_topic_0196677182_p16602141612334"></a><a name="zh-cn_topic_0196677182_p16602141612334"></a>标识是否与OBS建立安全连接。</p>
    <a name="zh-cn_topic_0196677182_ul118091720113317"></a><a name="zh-cn_topic_0196677182_ul118091720113317"></a><ul id="zh-cn_topic_0196677182_ul118091720113317"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。
5.  <a name="li330464819479"></a>以root用户登录Master节点，密码为用户创建集群时设置的root密码（若集群存在多个Master节点，请分别登录每个Master节点进行[5](#li330464819479)\~[7](#li13507895310)的操作）。
6.  执行以下命令，切换到客户端目录，例如“/opt/Bigdata/client”。

    **cd /opt/Bigdata/client**

7.  <a name="li13507895310"></a>执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./ autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件（例如“/opt/Bigdata/client/HDFS/hadoop/etc/hadoop/core-site.xml”）中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 3**  数据加密参数

<a name="table87769129208"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_1"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p14141017154214"><a name="p14141017154214"></a><a name="p14141017154214"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p11142617174213"><a name="p11142617174213"></a><a name="p11142617174213"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p191426174423"><a name="p191426174423"></a><a name="p191426174423"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p1314281713422"><a name="p1314281713422"></a><a name="p1314281713422"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p13142917114216"><a name="p13142917114216"></a><a name="p13142917114216"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul1114313179423"></a><a name="ul1114313179423"></a><ul id="ul1114313179423"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p11144151711428"><a name="p11144151711428"></a><a name="p11144151711428"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1214411718422"><a name="p1214411718422"></a><a name="p1214411718422"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1514481784210"><a name="p1514481784210"></a><a name="p1514481784210"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="p131441175425"><a name="p131441175425"></a><a name="p131441175425"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p4145817204220"><a name="p4145817204220"></a><a name="p4145817204220"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p3145131714429"><a name="p3145131714429"></a><a name="p3145131714429"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p3145141784210"><a name="p3145141784210"></a><a name="p3145141784210"></a>标识是否与OBS建立安全连接。</p>
<a name="ul514541714218"></a><a name="ul514541714218"></a><ul id="ul514541714218"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## HBase配置<a name="section92561514228"></a>

**方式一：通过界面配置。**

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> HBase \> 服务配置”
3.  将“基础配置”切换为“全部配置”，搜索并配置如下参数：

    **表 4**  数据加密参数

    <a name="table141481617124211"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_2"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p171491917114219"><a name="p171491917114219"></a><a name="p171491917114219"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p31501117144217"><a name="p31501117144217"></a><a name="p31501117144217"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p1015031774212"><a name="p1015031774212"></a><a name="p1015031774212"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p141502017184217"><a name="p141502017184217"></a><a name="p141502017184217"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1515111720427"><a name="p1515111720427"></a><a name="p1515111720427"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul1515151754215"></a><a name="ul1515151754215"></a><ul id="ul1515151754215"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p1715241711425"><a name="p1715241711425"></a><a name="p1715241711425"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1015261718428"><a name="p1015261718428"></a><a name="p1015261718428"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p14152131774213"><a name="p14152131774213"></a><a name="p14152131774213"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="p3152717104220"><a name="p3152717104220"></a><a name="p3152717104220"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p41531017144218"><a name="p41531017144218"></a><a name="p41531017144218"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16153517174211"><a name="p16153517174211"></a><a name="p16153517174211"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p915341716428"><a name="p915341716428"></a><a name="p915341716428"></a>标识是否与OBS建立安全连接。</p>
    <a name="ul1515418174425"></a><a name="ul1515418174425"></a><ul id="ul1515418174425"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。
5.  以root用户登录Master节点，密码为用户创建集群时设置的root密码（若集群存在多个Master节点，请分别登录每个Master节点进行[5](#li330464819479)\~[7](#li13507895310)的操作）。
6.  执行以下命令，切换到客户端目录，例如“/opt/Bigdata/client”。

    **cd /opt/Bigdata/client**

7.  执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./ autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件（例如“/opt/Bigdata/client/HBase/hbase/conf/core-site.xml”）中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 5**  数据加密参数

<a name="table73074184229"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_3"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p215916179420"><a name="p215916179420"></a><a name="p215916179420"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p116061794215"><a name="p116061794215"></a><a name="p116061794215"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p416081734216"><a name="p416081734216"></a><a name="p416081734216"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p2161417134211"><a name="p2161417134211"></a><a name="p2161417134211"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p151611117164212"><a name="p151611117164212"></a><a name="p151611117164212"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul1916141724213"></a><a name="ul1916141724213"></a><ul id="ul1916141724213"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p0162917114217"><a name="p0162917114217"></a><a name="p0162917114217"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1216216172424"><a name="p1216216172424"></a><a name="p1216216172424"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p17163101714423"><a name="p17163101714423"></a><a name="p17163101714423"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="p1416371714423"><a name="p1416371714423"></a><a name="p1416371714423"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p3163151714216"><a name="p3163151714216"></a><a name="p3163151714216"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1016451744219"><a name="p1016451744219"></a><a name="p1016451744219"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p17164141724213"><a name="p17164141724213"></a><a name="p17164141724213"></a>标识是否与OBS建立安全连接。</p>
<a name="ul81641317174210"></a><a name="ul81641317174210"></a><ul id="ul81641317174210"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## Spark配置<a name="section19242125553711"></a>

**方式一：通过界面配置。**

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Spark \> 服务配置”
3.  将“基础配置”切换为“全部配置”，搜索并配置如下参数：

    **表 6**  数据加密参数

    <a name="table111671417144218"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_4"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p1816951754212"><a name="p1816951754212"></a><a name="p1816951754212"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p151691317204218"><a name="p151691317204218"></a><a name="p151691317204218"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p131701217164216"><a name="p131701217164216"></a><a name="p131701217164216"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p13170171734214"><a name="p13170171734214"></a><a name="p13170171734214"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p151701217114210"><a name="p151701217114210"></a><a name="p151701217114210"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul111710179424"></a><a name="ul111710179424"></a><ul id="ul111710179424"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p1017271714214"><a name="p1017271714214"></a><a name="p1017271714214"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p20173201734215"><a name="p20173201734215"></a><a name="p20173201734215"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p1517371717423"><a name="p1517371717423"></a><a name="p1517371717423"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="p1517421794215"><a name="p1517421794215"></a><a name="p1517421794215"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p11174151764219"><a name="p11174151764219"></a><a name="p11174151764219"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p131741417134216"><a name="p131741417134216"></a><a name="p131741417134216"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p41752017114210"><a name="p41752017114210"></a><a name="p41752017114210"></a>标识是否与OBS建立安全连接。</p>
    <a name="ul11175181716424"></a><a name="ul11175181716424"></a><ul id="ul11175181716424"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。
5.  以root用户登录Master节点，密码为用户创建集群时设置的root密码（若集群存在多个Master节点，请分别登录每个Master节点进行[5](#li330464819479)\~[7](#li13507895310)的操作）。
6.  执行以下命令，切换到客户端目录，例如“/opt/Bigdata/client”。

    **cd /opt/Bigdata/client**

7.  执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件（例如“/opt/Bigdata/client/Spark/spark/conf/core-site.xml”）中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 7**  数据加密参数

<a name="table024475513712"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_5"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p7181131717426"><a name="p7181131717426"></a><a name="p7181131717426"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1618201716422"><a name="p1618201716422"></a><a name="p1618201716422"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p1518211711422"><a name="p1518211711422"></a><a name="p1518211711422"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p13183181734218"><a name="p13183181734218"></a><a name="p13183181734218"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p151831317194217"><a name="p151831317194217"></a><a name="p151831317194217"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul16184181704214"></a><a name="ul16184181704214"></a><ul id="ul16184181704214"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p1818491734216"><a name="p1818491734216"></a><a name="p1818491734216"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1018561715420"><a name="p1018561715420"></a><a name="p1018561715420"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p16185171744219"><a name="p16185171744219"></a><a name="p16185171744219"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="p1618591734215"><a name="p1618591734215"></a><a name="p1618591734215"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p21867174421"><a name="p21867174421"></a><a name="p21867174421"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p518641713428"><a name="p518641713428"></a><a name="p518641713428"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p111861217194218"><a name="p111861217194218"></a><a name="p111861217194218"></a>标识是否与OBS建立安全连接。</p>
<a name="ul1818681704220"></a><a name="ul1818681704220"></a><ul id="ul1818681704220"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## Presto配置<a name="section32329519436"></a>

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Presto \> 服务配置”
3.  将“基础配置”切换为“全部配置”，搜索并配置如下参数：

    **表 8**  数据加密参数

    <a name="table16188191718421"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_6"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="p171911172424"><a name="p171911172424"></a><a name="p171911172424"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p1519181714217"><a name="p1519181714217"></a><a name="p1519181714217"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="p15191317184220"><a name="p15191317184220"></a><a name="p15191317184220"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p161921517184213"><a name="p161921517184213"></a><a name="p161921517184213"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p16192121714214"><a name="p16192121714214"></a><a name="p16192121714214"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="ul7193201711427"></a><a name="ul7193201711427"></a><ul id="ul7193201711427"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p1319311784219"><a name="p1319311784219"></a><a name="p1319311784219"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p1219413176429"><a name="p1219413176429"></a><a name="p1219413176429"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p61951717144215"><a name="p61951717144215"></a><a name="p61951717144215"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="p519581719427"><a name="p519581719427"></a><a name="p519581719427"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="p6195101734215"><a name="p6195101734215"></a><a name="p6195101734215"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p161981617194210"><a name="p161981617194210"></a><a name="p161981617194210"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="p919861784210"><a name="p919861784210"></a><a name="p919861784210"></a>标识是否与OBS建立安全连接。</p>
    <a name="ul8198217164217"></a><a name="ul8198217164217"></a><ul id="ul8198217164217"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。

