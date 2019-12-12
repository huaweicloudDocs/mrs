# 管理Loader作业<a name="ZH-CN_TOPIC_0173178049"></a>

## 操作场景<a name="s172f8b7840734cb2a186560103e0664f"></a>

Loader页面支持创建、查看、编辑和删除作业。

## 前提条件<a name="sd476a7a66f3d4b549ca9050c09ba2847"></a>

已访问Loader页面，参见[Loader页面介绍](Loader使用简介.md#s12f4baccf3914471bee631d0ca198278)。

## 创建作业<a name="s1e05ed1345b8456fab83e7e58779dc25"></a>

1.  访问Loader页面，单击“新建作业“。
2.  在“基本信息“填写参数。
    1.  在“名称“填写一个作业的名称。
    2.  在“源连接“和“目的连接“选择对应的连接。

        选择某个类型的连接，表示从指定的源获取数据，并保存到目的位置。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果没有需要的连接，可单击“添加新连接“。  


3.  在“自“填写源连接的作业配置。

    具体请参见[Loader作业源连接配置说明](Loader作业源连接配置说明.md)。

4.  在“至“填写目的连接的作业配置。

    具体请参见[Loader作业目的连接配置说明](Loader作业目的连接配置说明.md)。

5.  在“目的连接“是否选择了数据库类型的连接？

    数据库类型的连接包含以下几种：

    -   generic-jdbc-connector
    -   hbase-connector
    -   hive-connector
    -   voltdb-connector

    “目的连接“选择数据库类型的连接时，还需要配置业务数据与数据库表字段的对应关系：

    -   是，请执行[6](#l56f38eb013c549b2b70d8f3a750ea8c4)。
    -   否，请执行[7](#l8e55b33fad0b4b52b4919120d3ab7597)。

6.  <a name="l56f38eb013c549b2b70d8f3a750ea8c4"></a>在“字段映射“填写字段对应关系。然后执行[7](#l8e55b33fad0b4b52b4919120d3ab7597)。

    “字段映射“的对应关系，表示用户数据中每一列与数据库的表字段的匹配关系。

    **表 1** “字段映射“属性

    <a name="t8db35033881c4787a479889ab05f7d52"></a>
    <table><thead align="left"><tr id="r7fadf37f19d1434684d5996690c18916"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a0908d93254424b949f4c2351fefe4ab3"><a name="a0908d93254424b949f4c2351fefe4ab3"></a><a name="a0908d93254424b949f4c2351fefe4ab3"></a><strong id="aa924acf71bf542e9ad63a9263b75291d"><a name="aa924acf71bf542e9ad63a9263b75291d"></a><a name="aa924acf71bf542e9ad63a9263b75291d"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="ae87ec43a3d804018ab7d8e3ad967803a"><a name="ae87ec43a3d804018ab7d8e3ad967803a"></a><a name="ae87ec43a3d804018ab7d8e3ad967803a"></a><strong id="a45fd4e220458425987ed07e7c3080878"><a name="a45fd4e220458425987ed07e7c3080878"></a><a name="a45fd4e220458425987ed07e7c3080878"></a>说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="rd9c73ea756164827a3527093bed0dc6c"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="aa2a6c847ab9646d5a6eb73dc9d502b78"><a name="aa2a6c847ab9646d5a6eb73dc9d502b78"></a><a name="aa2a6c847ab9646d5a6eb73dc9d502b78"></a>列号</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="accd775862e054e0582fd151cb638e651"><a name="accd775862e054e0582fd151cb638e651"></a><a name="accd775862e054e0582fd151cb638e651"></a>表示业务数据的字段顺序。</p>
    </td>
    </tr>
    <tr id="r8a984dc3dacc4bb5953dbb009e19f620"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ade8da1510a3340258d4f24da301e5e28"><a name="ade8da1510a3340258d4f24da301e5e28"></a><a name="ade8da1510a3340258d4f24da301e5e28"></a>样本</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a3cb12030f2a14364a68e29cf159cec08"><a name="a3cb12030f2a14364a68e29cf159cec08"></a><a name="a3cb12030f2a14364a68e29cf159cec08"></a>表示业务数据的第一行值样例。</p>
    </td>
    </tr>
    <tr id="rb0678da8360f4015a5967eb5efa3db03"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a4a72143b1cef4d6bb9622d751b45c604"><a name="a4a72143b1cef4d6bb9622d751b45c604"></a><a name="a4a72143b1cef4d6bb9622d751b45c604"></a>列族</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a5e550c50319247309ecc9295cf6f767c"><a name="a5e550c50319247309ecc9295cf6f767c"></a><a name="a5e550c50319247309ecc9295cf6f767c"></a><span class="parmname" id="p28f8c8717cb448de94f58e6a326691ab"><a name="p28f8c8717cb448de94f58e6a326691ab"></a><a name="p28f8c8717cb448de94f58e6a326691ab"></a>“目的连接”</span>为hbase-connector类型时，支持定义保存数据的具体列族。</p>
    </td>
    </tr>
    <tr id="r7d44d63e62eb4df9881491ee6fd2dbc4"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a752d5a31338f4496bf7095955325b77c"><a name="a752d5a31338f4496bf7095955325b77c"></a><a name="a752d5a31338f4496bf7095955325b77c"></a>目的字段</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a1f4cd890f024498b92d9e8fd76560e42"><a name="a1f4cd890f024498b92d9e8fd76560e42"></a><a name="a1f4cd890f024498b92d9e8fd76560e42"></a>配置保存数据的具体字段。</p>
    </td>
    </tr>
    <tr id="r3e9efdcdfd354c6b861df89a664338bf"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a7c19e90f39654d86b793ac8d2430fc0f"><a name="a7c19e90f39654d86b793ac8d2430fc0f"></a><a name="a7c19e90f39654d86b793ac8d2430fc0f"></a>类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a8e843ce3a0384fabba2672e3c730b18e"><a name="a8e843ce3a0384fabba2672e3c730b18e"></a><a name="a8e843ce3a0384fabba2672e3c730b18e"></a>显示用户选择字段的类型。</p>
    </td>
    </tr>
    <tr id="r4a97734d452944d2a446ac7300c091c5"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a4b3b148df68141cd8b1a83002d9d7571"><a name="a4b3b148df68141cd8b1a83002d9d7571"></a><a name="a4b3b148df68141cd8b1a83002d9d7571"></a>行键</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a42f04220b0774e72ae89aa4ed50a011e"><a name="a42f04220b0774e72ae89aa4ed50a011e"></a><a name="a42f04220b0774e72ae89aa4ed50a011e"></a><span class="parmname" id="p3e2b3f4369ce4f5285d98854b415bb48"><a name="p3e2b3f4369ce4f5285d98854b415bb48"></a><a name="p3e2b3f4369ce4f5285d98854b415bb48"></a>“目的连接”</span>为hbase-connector类型时，需要勾选作为行键的<span class="parmname" id="p23f4d75233124fdfae35040688ce15a8"><a name="p23f4d75233124fdfae35040688ce15a8"></a><a name="p23f4d75233124fdfae35040688ce15a8"></a>“目的字段”</span>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果From是sftp/ftp/obs/hdfs等文件类型连接器，Field Mapping 样值取自文件第一行数据，需要保证第一行数据是完整的，Loader作业不会抽取没有Mapping上的列。  

7.  <a name="l8e55b33fad0b4b52b4919120d3ab7597"></a>在“任务配置“填写作业的运行参数。

    **表 2**  Loader作业运行属性

    <a name="t0fc7f46bfc1e45c6a9ec15a2e0907c24"></a>
    <table><thead align="left"><tr id="r7c49faa79b48493a90977ee596e882bd"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.3.1.1"><p id="a9f1a428c7a9b432398732eee31f87692"><a name="a9f1a428c7a9b432398732eee31f87692"></a><a name="a9f1a428c7a9b432398732eee31f87692"></a><strong id="a069e95d20ba44521adb5e8f409ca38ff"><a name="a069e95d20ba44521adb5e8f409ca38ff"></a><a name="a069e95d20ba44521adb5e8f409ca38ff"></a>参数</strong></p>
    </th>
    <th class="cellrowborder" valign="top" width="75%" id="mcps1.2.3.1.2"><p id="a8d407e82957a4fb889207f43bfbd19f4"><a name="a8d407e82957a4fb889207f43bfbd19f4"></a><a name="a8d407e82957a4fb889207f43bfbd19f4"></a><strong id="a644917f1a9c84d6383671c0d69bc4096"><a name="a644917f1a9c84d6383671c0d69bc4096"></a><a name="a644917f1a9c84d6383671c0d69bc4096"></a>说明</strong></p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r94d0a93bc93d49deb1dfb83600f6aec3"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="ae906b888e1c94499b04715dee7bec621"><a name="ae906b888e1c94499b04715dee7bec621"></a><a name="ae906b888e1c94499b04715dee7bec621"></a>抽取并发数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a3df14bc0588d4da496d4f2123641c2e1"><a name="a3df14bc0588d4da496d4f2123641c2e1"></a><a name="a3df14bc0588d4da496d4f2123641c2e1"></a>设置map任务的个数。</p>
    </td>
    </tr>
    <tr id="r9def9f914f9f423fbf3a7606f56f7cce"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a685bd07b98584b28aaad79a89134c512"><a name="a685bd07b98584b28aaad79a89134c512"></a><a name="a685bd07b98584b28aaad79a89134c512"></a>加载(写入)并发数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a457a3a1a365e4f02bcfdc4f5d7c11752"><a name="a457a3a1a365e4f02bcfdc4f5d7c11752"></a><a name="a457a3a1a365e4f02bcfdc4f5d7c11752"></a>设置reduce任务的个数。</p>
    <p id="a4b34f7012ed147c0be7d3776aaa99bf0"><a name="a4b34f7012ed147c0be7d3776aaa99bf0"></a><a name="a4b34f7012ed147c0be7d3776aaa99bf0"></a>该参数只有在目的字段为Hbase和Hive时才会显示。</p>
    </td>
    </tr>
    <tr id="rf000788d16f84f92a7524c7e6cff5d78"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a03589028c19d4130b74d813df6eb65dc"><a name="a03589028c19d4130b74d813df6eb65dc"></a><a name="a03589028c19d4130b74d813df6eb65dc"></a>单个分片的最大错误记录数</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a618938189e934288bd632e3676737d5c"><a name="a618938189e934288bd632e3676737d5c"></a><a name="a618938189e934288bd632e3676737d5c"></a>设置一个错误阈值，如果单个map任务的错误记录超过设置阈值则任务自动结束，已经获取的数据不回退。</p>
    <div class="note" id="n07eb2914d4c046fcbcb93e4078142074"><a name="n07eb2914d4c046fcbcb93e4078142074"></a><a name="n07eb2914d4c046fcbcb93e4078142074"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="a511a2f0502ec4b63b3662653804c5bfa"><a name="a511a2f0502ec4b63b3662653804c5bfa"></a><a name="a511a2f0502ec4b63b3662653804c5bfa"></a><span class="parmname" id="p27dfc99c386b4ac585959e57f793e77c"><a name="p27dfc99c386b4ac585959e57f793e77c"></a><a name="p27dfc99c386b4ac585959e57f793e77c"></a>“generic-jdbc-connector”</span>的<span class="parmname" id="pcc9ff6a9ffd54760986c361ab53daf8b"><a name="pcc9ff6a9ffd54760986c361ab53daf8b"></a><a name="pcc9ff6a9ffd54760986c361ab53daf8b"></a>“MYSQL”</span>和<span class="parmname" id="p5092f66f9d17494aa2f109b3ba75de92"><a name="p5092f66f9d17494aa2f109b3ba75de92"></a><a name="p5092f66f9d17494aa2f109b3ba75de92"></a>“MPPDB”</span>默认批量读写数据，每一批次数据最多只记录一次错误记录。</p>
    </div></div>
    </td>
    </tr>
    <tr id="rcd5d2490f121446dbead7b732d0d3bee"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.3.1.1 "><p id="a959d13ef9b0d4b9488bdf1cbba7f6e8c"><a name="a959d13ef9b0d4b9488bdf1cbba7f6e8c"></a><a name="a959d13ef9b0d4b9488bdf1cbba7f6e8c"></a>脏数据目录</p>
    </td>
    <td class="cellrowborder" valign="top" width="75%" headers="mcps1.2.3.1.2 "><p id="a02a97de10a474db283417da620846d23"><a name="a02a97de10a474db283417da620846d23"></a><a name="a02a97de10a474db283417da620846d23"></a>设置一个脏数据目录，在出现脏数据的场景中在该目录保存脏数据。如果不设置则不保存。</p>
    </td>
    </tr>
    </tbody>
    </table>

8.  单击“保存“。

## 查看作业<a name="s4e88c9c393144afa8d8bad5fa142cf0b"></a>

1.  访问Loader页面，默认显示Loader作业管理页面。
    -   如果集群启用了Kerberos认证，则默认显示所有当前用户创建的作业，不支持显示其他用户的作业。
    -   如果集群未启用Kerberos认证，则显示集群中全部的作业。

2.  在“Sqoop作业“中输入指定作业的名称或连接类型，可以筛选该作业。
3.  单击“刷新列表“，可以获取作业的最新状态。

## 编辑作业<a name="s130d0dc7d09c4c21a253aba69cc208d4"></a>

1.  访问Loader页面，默认显示Loader作业管理页面。
2.  单击指定作业的名称，进入编辑页面。
3.  根据业务需要，修改作业配置参数。
4.  单击“保存“。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >左侧导航栏支持作业的基本操作，包含“运行“、“复制“、“删除“、“激活“、“历史记录“和“显示作业JSON定义“。  


## 删除作业<a name="s2f01c8435f564248a0f16df2eb14ca8a"></a>

1.  访问Loader页面。
2.  在指定作业所在行，单击![](figures/icon_mrs_deleteloaderjob.jpg)。

    您还可以勾选一个或多个作业，单击作业列表右上方的“删除作业“。

3.  在弹出的对话框窗口，单击“是，将其删除“。

    如果某个Loader作业正处于“运行中“的状态，则无法删除作业。


