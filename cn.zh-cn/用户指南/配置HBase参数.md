# 配置HBase参数<a name="ZH-CN_TOPIC_0173178441"></a>

当MRS服务中默认的参数配置不足以满足用户需要时，用户可以自定义修改参数配置来适应自身需求。

1.  登录集群详情页面，选择“组件管理”。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若集群详情页面没有“组件管理”页签，请先完成IAM用户同步（在集群详情页的“概览”页签，单击“IAM用户同步“右侧的![](figures/zh-cn_image_0207903631.png)进行IAM用户同步）。  
    >-   针对MRS 2.0.1及之前版本，登录MRS Manager页面，具体请参见[访问MRS Manager](访问MRS-Manager.md)，然后选择“服务管理”。  

2.  选择“HBase \> 服务配置”，设置“参数类别”为“全部配置”，进入HBase配置界面修改参数配置。

    **表 1**  HBase参数说明

    <a name="table430163185120"></a>
    <table><thead align="left"><tr id="row2030218315519"><th class="cellrowborder" valign="top" width="39.24392439243925%" id="mcps1.2.4.1.1"><p id="p13021439512"><a name="p13021439512"></a><a name="p13021439512"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="40.32403240324032%" id="mcps1.2.4.1.2"><p id="p123021739518"><a name="p123021739518"></a><a name="p123021739518"></a>参数说明</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.43204320432043%" id="mcps1.2.4.1.3"><p id="p83026314512"><a name="p83026314512"></a><a name="p83026314512"></a>参数值</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row123021438512"><td class="cellrowborder" valign="top" width="39.24392439243925%" headers="mcps1.2.4.1.1 "><p id="p83021338513"><a name="p83021338513"></a><a name="p83021338513"></a>hbase.regionserver.hfile.durable.sync</p>
    </td>
    <td class="cellrowborder" valign="top" width="40.32403240324032%" headers="mcps1.2.4.1.2 "><p id="p1094819171504"><a name="p1094819171504"></a><a name="p1094819171504"></a>设置是否启用Hfile耐久性以将数据持久化到磁盘。若将该参数设置为true，由于每个Hfile写入HBase时都会被hadoop fsync同步到磁盘上，则HBase性能将受到影响。</p>
    <p id="p9914183914017"><a name="p9914183914017"></a><a name="p9914183914017"></a>该参数仅在MRS 2.0.1之前版本存在。</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.43204320432043%" headers="mcps1.2.4.1.3 "><p id="p3878173417820"><a name="p3878173417820"></a><a name="p3878173417820"></a>取值范围：</p>
    <a name="ul178809348816"></a><a name="ul178809348816"></a><ul id="ul178809348816"><li>true</li><li>false</li></ul>
    <p id="p107989107314"><a name="p107989107314"></a><a name="p107989107314"></a>默认值为true</p>
    </td>
    </tr>
    <tr id="row113027316513"><td class="cellrowborder" valign="top" width="39.24392439243925%" headers="mcps1.2.4.1.1 "><p id="p73039355113"><a name="p73039355113"></a><a name="p73039355113"></a>hbase.regionserver.wal.durable.sync</p>
    </td>
    <td class="cellrowborder" valign="top" width="40.32403240324032%" headers="mcps1.2.4.1.2 "><p id="p73031634516"><a name="p73031634516"></a><a name="p73031634516"></a>设置是否启用WAL文件耐久性以将WAL数据持久化到磁盘。若将该参数设置为true，由于每个WAL的编辑都会被hadoop fsync同步到磁盘上，则HBase性能将受到影响。</p>
    <p id="p146725363219"><a name="p146725363219"></a><a name="p146725363219"></a>该参数仅在MRS 2.0.1之前版本存在。</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.43204320432043%" headers="mcps1.2.4.1.3 "><p id="p687715499814"><a name="p687715499814"></a><a name="p687715499814"></a>取值范围：</p>
    <a name="ul10877164913820"></a><a name="ul10877164913820"></a><ul id="ul10877164913820"><li>true</li><li>false</li></ul>
    <p id="p18878949886"><a name="p18878949886"></a><a name="p18878949886"></a>默认值为true</p>
    </td>
    </tr>
    </tbody>
    </table>


