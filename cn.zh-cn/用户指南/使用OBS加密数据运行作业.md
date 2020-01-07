# 使用OBS加密数据运行作业<a name="ZH-CN_TOPIC_0196677182"></a>

MRS 2.1.0及之后版本支持使用OBS桶中加密后的数据来运行作业，同时支持将加密后的作业运行结果存储在OBS桶中。目前仅支持通过OBS协议访问数据。

OBS支持使用KMS秘钥的加解密方式对数据进行加解密，所有的加解密操作都在OBS完成，同时秘钥管理在DEW服务。

如需在MRS中使用OBS加密功能，用户需要有“KMS Administrator”权限，且需要在相应组件进行如下配置。

>![](public_sys-resources/icon-note.gif) **说明：**   
>如果集群同时开启“[OBS权限控制](配置MRS多用户访问OBS细粒度权限.md)”功能，此时会使用ECS配置的默认委托“MRS\_ECS\_DEFAULT\_AGENCY”或者用户设置的自定义委托的AK/SK访问OBS服务，同时OBS服务会使用接收到的AK/SK访问数据加密服务获取KMS秘钥状态，因此需要在使用的委托上绑定“KMS Administrator”策略，否则在处理加密数据时OBS会返回“403 Forbidden”的错误信息。目前MRS服务会在默认委托“MRS\_ECS\_DEFAULT\_AGENCY”绑定“KMS Administrator”策略，用户使用的自定义委托则需要用户自己绑定。  

## 前提条件<a name="section151741328125013"></a>

如需使用OBS加密功能，请先配置MRS访问OBS功能，具体请参考[MRS使用Huawei OBS方式对接OBS服务](obs方式访问OBS.md)。

## Hive配置<a name="section2456188164214"></a>

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Hive \> 服务配置”。
3.  “参数类别”选择“全部配置”，搜索并配置如下参数：

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
3.  “参数类别”选择“全部配置”，搜索并配置如下参数：

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
6.  执行以下命令，切换到客户端目录，例如“/opt/client”。

    **cd /opt/client**

7.  <a name="li13507895310"></a>执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./ autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件“/opt/client/HDFS/hadoop/etc/hadoop/core-site.xml”中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 3**  数据加密参数

<a name="table87769129208"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_1"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_1"><a name="zh-cn_topic_0196677182_p7925253152117_1"></a><a name="zh-cn_topic_0196677182_p7925253152117_1"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_1"><a name="zh-cn_topic_0196677182_p11925953102116_1"></a><a name="zh-cn_topic_0196677182_p11925953102116_1"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_1"><a name="zh-cn_topic_0196677182_p1292555302113_1"></a><a name="zh-cn_topic_0196677182_p1292555302113_1"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_1"><a name="zh-cn_topic_0196677182_p954024062214_1"></a><a name="zh-cn_topic_0196677182_p954024062214_1"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_1"><a name="zh-cn_topic_0196677182_p4809439192410_1"></a><a name="zh-cn_topic_0196677182_p4809439192410_1"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_1"></a><a name="zh-cn_topic_0196677182_ul13677522415_1"></a><ul id="zh-cn_topic_0196677182_ul13677522415_1"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_1"><a name="zh-cn_topic_0196677182_p125401740162210_1"></a><a name="zh-cn_topic_0196677182_p125401740162210_1"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_1"><a name="zh-cn_topic_0196677182_p1354074062215_1"></a><a name="zh-cn_topic_0196677182_p1354074062215_1"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_1"><a name="zh-cn_topic_0196677182_p8147131718257_1"></a><a name="zh-cn_topic_0196677182_p8147131718257_1"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="zh-cn_topic_0196677182_p1173437103213_1"><a name="zh-cn_topic_0196677182_p1173437103213_1"></a><a name="zh-cn_topic_0196677182_p1173437103213_1"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_1"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_1"><a name="zh-cn_topic_0196677182_p0540104019225_1"></a><a name="zh-cn_topic_0196677182_p0540104019225_1"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_1"><a name="zh-cn_topic_0196677182_p14602614183418_1"></a><a name="zh-cn_topic_0196677182_p14602614183418_1"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_1"><a name="zh-cn_topic_0196677182_p16602141612334_1"></a><a name="zh-cn_topic_0196677182_p16602141612334_1"></a>标识是否与OBS建立安全连接。</p>
<a name="zh-cn_topic_0196677182_ul118091720113317_1"></a><a name="zh-cn_topic_0196677182_ul118091720113317_1"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_1"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## HBase配置<a name="section92561514228"></a>

**方式一：通过界面配置。**

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> HBase \> 服务配置”
3.  “参数类别”选择“全部配置”，搜索并配置如下参数：

    **表 4**  数据加密参数

    <a name="zh-cn_topic_0196677182_table3922125311218_1"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_2"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_2"><a name="zh-cn_topic_0196677182_p7925253152117_2"></a><a name="zh-cn_topic_0196677182_p7925253152117_2"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_2"><a name="zh-cn_topic_0196677182_p11925953102116_2"></a><a name="zh-cn_topic_0196677182_p11925953102116_2"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_2"><a name="zh-cn_topic_0196677182_p1292555302113_2"></a><a name="zh-cn_topic_0196677182_p1292555302113_2"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_2"><a name="zh-cn_topic_0196677182_p954024062214_2"></a><a name="zh-cn_topic_0196677182_p954024062214_2"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_2"><a name="zh-cn_topic_0196677182_p4809439192410_2"></a><a name="zh-cn_topic_0196677182_p4809439192410_2"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_2"></a><a name="zh-cn_topic_0196677182_ul13677522415_2"></a><ul id="zh-cn_topic_0196677182_ul13677522415_2"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_2"><a name="zh-cn_topic_0196677182_p125401740162210_2"></a><a name="zh-cn_topic_0196677182_p125401740162210_2"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_2"><a name="zh-cn_topic_0196677182_p1354074062215_2"></a><a name="zh-cn_topic_0196677182_p1354074062215_2"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_2"><a name="zh-cn_topic_0196677182_p8147131718257_2"></a><a name="zh-cn_topic_0196677182_p8147131718257_2"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="zh-cn_topic_0196677182_p1173437103213_2"><a name="zh-cn_topic_0196677182_p1173437103213_2"></a><a name="zh-cn_topic_0196677182_p1173437103213_2"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_2"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_2"><a name="zh-cn_topic_0196677182_p0540104019225_2"></a><a name="zh-cn_topic_0196677182_p0540104019225_2"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_2"><a name="zh-cn_topic_0196677182_p14602614183418_2"></a><a name="zh-cn_topic_0196677182_p14602614183418_2"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_2"><a name="zh-cn_topic_0196677182_p16602141612334_2"></a><a name="zh-cn_topic_0196677182_p16602141612334_2"></a>标识是否与OBS建立安全连接。</p>
    <a name="zh-cn_topic_0196677182_ul118091720113317_2"></a><a name="zh-cn_topic_0196677182_ul118091720113317_2"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_2"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。
5.  <a name="li122668152214"></a>以root用户登录Master节点，密码为用户创建集群时设置的root密码（若集群存在多个Master节点，请分别登录每个Master节点进行[5](#li122668152214)\~[7](使用OBS加密数据运行作业.md#li13507895310)的操作）。
6.  执行以下命令，切换到客户端目录，例如“/opt/client”。

    **cd /opt/client**

7.  执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./ autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件“/opt/client/HBase/hbase/conf/core-site.xml”中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 5**  数据加密参数

<a name="table73074184229"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_3"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_3"><a name="zh-cn_topic_0196677182_p7925253152117_3"></a><a name="zh-cn_topic_0196677182_p7925253152117_3"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_3"><a name="zh-cn_topic_0196677182_p11925953102116_3"></a><a name="zh-cn_topic_0196677182_p11925953102116_3"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_3"><a name="zh-cn_topic_0196677182_p1292555302113_3"></a><a name="zh-cn_topic_0196677182_p1292555302113_3"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_3"><a name="zh-cn_topic_0196677182_p954024062214_3"></a><a name="zh-cn_topic_0196677182_p954024062214_3"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_3"><a name="zh-cn_topic_0196677182_p4809439192410_3"></a><a name="zh-cn_topic_0196677182_p4809439192410_3"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_3"></a><a name="zh-cn_topic_0196677182_ul13677522415_3"></a><ul id="zh-cn_topic_0196677182_ul13677522415_3"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_3"><a name="zh-cn_topic_0196677182_p125401740162210_3"></a><a name="zh-cn_topic_0196677182_p125401740162210_3"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_3"><a name="zh-cn_topic_0196677182_p1354074062215_3"></a><a name="zh-cn_topic_0196677182_p1354074062215_3"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_3"><a name="zh-cn_topic_0196677182_p8147131718257_3"></a><a name="zh-cn_topic_0196677182_p8147131718257_3"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="zh-cn_topic_0196677182_p1173437103213_3"><a name="zh-cn_topic_0196677182_p1173437103213_3"></a><a name="zh-cn_topic_0196677182_p1173437103213_3"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_3"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_3"><a name="zh-cn_topic_0196677182_p0540104019225_3"></a><a name="zh-cn_topic_0196677182_p0540104019225_3"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_3"><a name="zh-cn_topic_0196677182_p14602614183418_3"></a><a name="zh-cn_topic_0196677182_p14602614183418_3"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_3"><a name="zh-cn_topic_0196677182_p16602141612334_3"></a><a name="zh-cn_topic_0196677182_p16602141612334_3"></a>标识是否与OBS建立安全连接。</p>
<a name="zh-cn_topic_0196677182_ul118091720113317_3"></a><a name="zh-cn_topic_0196677182_ul118091720113317_3"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_3"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## Spark配置<a name="section19242125553711"></a>

**方式一：通过界面配置。**

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Spark \> 服务配置”
3.  “参数类别”选择“全部配置”，搜索并配置如下参数：

    **表 6**  数据加密参数

    <a name="zh-cn_topic_0196677182_table3922125311218_2"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_4"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_4"><a name="zh-cn_topic_0196677182_p7925253152117_4"></a><a name="zh-cn_topic_0196677182_p7925253152117_4"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_4"><a name="zh-cn_topic_0196677182_p11925953102116_4"></a><a name="zh-cn_topic_0196677182_p11925953102116_4"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_4"><a name="zh-cn_topic_0196677182_p1292555302113_4"></a><a name="zh-cn_topic_0196677182_p1292555302113_4"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_4"><a name="zh-cn_topic_0196677182_p954024062214_4"></a><a name="zh-cn_topic_0196677182_p954024062214_4"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_4"><a name="zh-cn_topic_0196677182_p4809439192410_4"></a><a name="zh-cn_topic_0196677182_p4809439192410_4"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_4"></a><a name="zh-cn_topic_0196677182_ul13677522415_4"></a><ul id="zh-cn_topic_0196677182_ul13677522415_4"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_4"><a name="zh-cn_topic_0196677182_p125401740162210_4"></a><a name="zh-cn_topic_0196677182_p125401740162210_4"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_4"><a name="zh-cn_topic_0196677182_p1354074062215_4"></a><a name="zh-cn_topic_0196677182_p1354074062215_4"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_4"><a name="zh-cn_topic_0196677182_p8147131718257_4"></a><a name="zh-cn_topic_0196677182_p8147131718257_4"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="zh-cn_topic_0196677182_p1173437103213_4"><a name="zh-cn_topic_0196677182_p1173437103213_4"></a><a name="zh-cn_topic_0196677182_p1173437103213_4"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_4"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_4"><a name="zh-cn_topic_0196677182_p0540104019225_4"></a><a name="zh-cn_topic_0196677182_p0540104019225_4"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_4"><a name="zh-cn_topic_0196677182_p14602614183418_4"></a><a name="zh-cn_topic_0196677182_p14602614183418_4"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_4"><a name="zh-cn_topic_0196677182_p16602141612334_4"></a><a name="zh-cn_topic_0196677182_p16602141612334_4"></a>标识是否与OBS建立安全连接。</p>
    <a name="zh-cn_topic_0196677182_ul118091720113317_4"></a><a name="zh-cn_topic_0196677182_ul118091720113317_4"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_4"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。
5.  <a name="li1244125516379"></a>以root用户登录Master节点，密码为用户创建集群时设置的root密码（若集群存在多个Master节点，请分别登录每个Master节点进行[5](#li1244125516379)\~[7](使用OBS加密数据运行作业.md#li13507895310)的操作）。
6.  执行以下命令，切换到客户端目录，例如“/opt/client”。

    **cd /opt/client**

7.  执行以下命令更新客户端配置，并输入用户名和密码，用户名为admin，密码为用户创建集群时设置的admin密码。

    **./ autoRefreshConfig.sh**


**方式二：通过客户端配置文件配置。**

在Master节点上的客户端配置文件“/opt/client/Spark/spark/conf/core-site.xml”中的增加如下参数配置（若集群存在多个Master节点，请分别登录每个Master节点进行该操作）。

**表 7**  数据加密参数

<a name="table024475513712"></a>
<table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_5"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_5"><a name="zh-cn_topic_0196677182_p7925253152117_5"></a><a name="zh-cn_topic_0196677182_p7925253152117_5"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_5"><a name="zh-cn_topic_0196677182_p11925953102116_5"></a><a name="zh-cn_topic_0196677182_p11925953102116_5"></a>取值</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_5"><a name="zh-cn_topic_0196677182_p1292555302113_5"></a><a name="zh-cn_topic_0196677182_p1292555302113_5"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0196677182_row69251753192118_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_5"><a name="zh-cn_topic_0196677182_p954024062214_5"></a><a name="zh-cn_topic_0196677182_p954024062214_5"></a>fs.obs.server-side-encryption-type</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_5"><a name="zh-cn_topic_0196677182_p4809439192410_5"></a><a name="zh-cn_topic_0196677182_p4809439192410_5"></a>SSE-KMS</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_5"></a><a name="zh-cn_topic_0196677182_ul13677522415_5"></a><ul id="zh-cn_topic_0196677182_ul13677522415_5"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row6925253112115_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_5"><a name="zh-cn_topic_0196677182_p125401740162210_5"></a><a name="zh-cn_topic_0196677182_p125401740162210_5"></a>fs.obs.server-side-encryption-key</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_5"><a name="zh-cn_topic_0196677182_p1354074062215_5"></a><a name="zh-cn_topic_0196677182_p1354074062215_5"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_5"><a name="zh-cn_topic_0196677182_p8147131718257_5"></a><a name="zh-cn_topic_0196677182_p8147131718257_5"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
<p id="zh-cn_topic_0196677182_p1173437103213_5"><a name="zh-cn_topic_0196677182_p1173437103213_5"></a><a name="zh-cn_topic_0196677182_p1173437103213_5"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
</td>
</tr>
<tr id="zh-cn_topic_0196677182_row792515311214_5"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_5"><a name="zh-cn_topic_0196677182_p0540104019225_5"></a><a name="zh-cn_topic_0196677182_p0540104019225_5"></a>fs.obs.connection.ssl.enabled</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_5"><a name="zh-cn_topic_0196677182_p14602614183418_5"></a><a name="zh-cn_topic_0196677182_p14602614183418_5"></a>true</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_5"><a name="zh-cn_topic_0196677182_p16602141612334_5"></a><a name="zh-cn_topic_0196677182_p16602141612334_5"></a>标识是否与OBS建立安全连接。</p>
<a name="zh-cn_topic_0196677182_ul118091720113317_5"></a><a name="zh-cn_topic_0196677182_ul118091720113317_5"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_5"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
</td>
</tr>
</tbody>
</table>

## Presto配置<a name="section32329519436"></a>

1.  登录MRS控制台，在左侧导航栏选择“集群列表  \>  现有集群“  ，单击集群名称。
2.  选择“组件管理 \> Presto \> 服务配置”
3.  “参数类别”选择“全部配置”，搜索并配置如下参数：

    **表 8**  数据加密参数

    <a name="zh-cn_topic_0196677182_table3922125311218_3"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0196677182_row792514537215_6"><th class="cellrowborder" valign="top" width="30%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0196677182_p7925253152117_6"><a name="zh-cn_topic_0196677182_p7925253152117_6"></a><a name="zh-cn_topic_0196677182_p7925253152117_6"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0196677182_p11925953102116_6"><a name="zh-cn_topic_0196677182_p11925953102116_6"></a><a name="zh-cn_topic_0196677182_p11925953102116_6"></a>取值</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0196677182_p1292555302113_6"><a name="zh-cn_topic_0196677182_p1292555302113_6"></a><a name="zh-cn_topic_0196677182_p1292555302113_6"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0196677182_row69251753192118_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p954024062214_6"><a name="zh-cn_topic_0196677182_p954024062214_6"></a><a name="zh-cn_topic_0196677182_p954024062214_6"></a>fs.obs.server-side-encryption-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p4809439192410_6"><a name="zh-cn_topic_0196677182_p4809439192410_6"></a><a name="zh-cn_topic_0196677182_p4809439192410_6"></a>SSE-KMS</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><a name="zh-cn_topic_0196677182_ul13677522415_6"></a><a name="zh-cn_topic_0196677182_ul13677522415_6"></a><ul id="zh-cn_topic_0196677182_ul13677522415_6"><li>SSE-KMS：表示使用KMS秘钥的加解密方式。</li><li>NONE：表示关闭加密功能。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row6925253112115_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p125401740162210_6"><a name="zh-cn_topic_0196677182_p125401740162210_6"></a><a name="zh-cn_topic_0196677182_p125401740162210_6"></a>fs.obs.server-side-encryption-key</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p1354074062215_6"><a name="zh-cn_topic_0196677182_p1354074062215_6"></a><a name="zh-cn_topic_0196677182_p1354074062215_6"></a>-</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p8147131718257_6"><a name="zh-cn_topic_0196677182_p8147131718257_6"></a><a name="zh-cn_topic_0196677182_p8147131718257_6"></a>表示用来加密的KMS密钥ID。该参数可不配置。</p>
    <p id="zh-cn_topic_0196677182_p1173437103213_6"><a name="zh-cn_topic_0196677182_p1173437103213_6"></a><a name="zh-cn_topic_0196677182_p1173437103213_6"></a>当参数“fs.obs.server-side-encryption-type”配置为“SSE-KMS”且该参数未配置时，OBS会使用OBS服务的默认KMS密钥完成加密。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0196677182_row792515311214_6"><td class="cellrowborder" valign="top" width="30%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0196677182_p0540104019225_6"><a name="zh-cn_topic_0196677182_p0540104019225_6"></a><a name="zh-cn_topic_0196677182_p0540104019225_6"></a>fs.obs.connection.ssl.enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0196677182_p14602614183418_6"><a name="zh-cn_topic_0196677182_p14602614183418_6"></a><a name="zh-cn_topic_0196677182_p14602614183418_6"></a>true</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0196677182_p16602141612334_6"><a name="zh-cn_topic_0196677182_p16602141612334_6"></a><a name="zh-cn_topic_0196677182_p16602141612334_6"></a>标识是否与OBS建立安全连接。</p>
    <a name="zh-cn_topic_0196677182_ul118091720113317_6"></a><a name="zh-cn_topic_0196677182_ul118091720113317_6"></a><ul id="zh-cn_topic_0196677182_ul118091720113317_6"><li>true：开启安全连接，当需要使用OBS加解密功能时该参数必须配置为“true”。</li><li>false：关闭安全连接。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“保存配置”，勾选“重新启动受影响的服务或实例。”并单击“确定”。

